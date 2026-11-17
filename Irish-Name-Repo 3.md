# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Irish-Name-Repo 1
# Description
Try to see if you can login as admin!
# Discover
when we took look for first time we see List 'o the Irish and Pictures of the actors Irish, I think
but when we goes to left 3 lines and when we click on it we get admin login button
<img width="1599" height="779" alt="1" src="https://github.com/user-attachments/assets/f91ad27f-ad0e-41f6-aa50-300e890f8c39" />
# exploit
when we use our payload we get nothing 
<img width="1599" height="783" alt="1" src="https://github.com/user-attachments/assets/71fc69e9-3979-456d-b6aa-83c8c8076075" />
and when we see on request dubug is set to 0 that means taht value is 0 false and we need to turn it into 1 true 
and server is response

password: &#039;OR 1=1 --

SQL query: SELECT * FROM admin where password = &#039;&#039;BE 1=1 --&#039;
and when we see hint:Seems like the password is encrypted
so the server is encode to our input like base64 or ROT13
let's try ROT13 
<img width="1599" height="776" alt="4" src="https://github.com/user-attachments/assets/76668127-6cc5-4c72-b51b-2808f449dabd" />
and OR switch into be 

<img width="1599" height="865" alt="5" src="https://github.com/user-attachments/assets/dfaabd65-4740-4fcb-b917-a7bc91a21da0" />
get flag!


