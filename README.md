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
burp suite tool or Another way by curl but today we'r use burp
# 2 : Discover a web page
<img width="1597" height="775" alt="frist_lock" src="https://github.com/user-attachments/assets/fd53e289-2fb2-434f-8d1f-78ddf6862674" />
you can see login page 
