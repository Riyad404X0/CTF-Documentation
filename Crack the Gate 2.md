# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Crack the Gate 2
# Description 
The login system has been upgraded with a basic rate-limiting mechanism that locks out repeated failed attempts from the same source. We’ve received a tip that the system might still trust user-controlled headers. Your objective is to bypass the rate-limiting restriction and log in using the known email address: ctf-player@cylabacademy.org and uncover the hidden secret. The website is running here
. Can you try to log in?.

Download the passwords list 

# First step : Preparing the environment
first Download requirements
password list 
burp suite tool or Another way by FuFF but today we'r use burp
# 2 : Discover a web page
<img width="1597" height="775" alt="frist_lock" src="https://github.com/user-attachments/assets/fd53e289-2fb2-434f-8d1f-78ddf6862674" />
you can see login page 
so we have email address: ctf-player@cylabacademy.org
and when we try random password we find this message here
<img width="1596" height="779" alt="2_lock" src="https://github.com/user-attachments/assets/0dd6297d-43ba-4413-b2c1-ffea6bde973f" />
There is an IP rate limit is a defense method and you can tell by hint 2 :
Read more about X-forwarded-For
The X-Forwarded-For (XFF) HTTP header field is a common method for identifying the originating IP address of a client connecting to a web server through an HTTP proxy or load balancer.
and We can change our IP address to baypass IP rate limit
# 3 : exploit
open burp suite
and open our request
<img width="1599" height="858" alt="3lock" src="https://github.com/user-attachments/assets/41846a17-db72-4fe3-957e-6aa804b3d7aa" />
you can see request POST method , and we see our Credential in request
{"email":"ctf-player@cylabacademy.org","password":"test"}
so click Right and click on send to repeater to do Request modification
and add  X-forwarded-For HTTP request header
X-forwarded-For:10.10.10.0 any ip you went and After each attempt, change the last octet like 0 to 1 
and will try all password in passwordlist.txt and after you do that you get our flag
<img width="1599" height="854" alt="5" src="https://github.com/user-attachments/assets/f2ca81d2-c09c-4586-82c3-b171bf7fb24b" />






