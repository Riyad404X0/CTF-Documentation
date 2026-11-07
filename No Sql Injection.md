# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : No Sql Injection
# Description 
Can you try to get access to this website to get the flag?
hint1:Not only SQL injection exist but also NonSQL injection exists
hint2:Make sure you look at everything the server is sending back
# Discover
we can see is login page  
<img width="1599" height="780" alt="1g" src="https://github.com/user-attachments/assets/d7bac71a-c03d-48b5-ad05-525026ebdd05" />
#
and when we download source code for the website 
as we see is mongodb database , is save data as json file
<img width="1599" height="860" alt="2" src="https://github.com/user-attachments/assets/934c5170-5656-4179-9b4b-7370ada1aef0" />

