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


