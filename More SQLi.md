# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : More SQLi
# Description 
Can you find the flag on this website.
# Discover
we can see it's login page and hint said SQLiLite
<img width="1599" height="785" alt="1n" src="https://github.com/user-attachments/assets/17602621-e595-48fc-aed2-f8805f4e414d" />

# exploit 
we use admin as username
and password you use this payload

    'OR 1==1 --
<img width="1555" height="780" alt="2" src="https://github.com/user-attachments/assets/ff229f36-719f-4b03-8abd-e4fd0fa3e470" />

and when we see response burp suite ,POSt methed
we can see is showing flag
<img width="1598" height="866" alt="3" src="https://github.com/user-attachments/assets/e6eded23-9dc8-4602-81ba-56d36bd82f38" />
