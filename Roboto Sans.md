# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Roboto_Sans
# Description 
The flag is somewhere on this web application not necessarily on the website. Find it.
# Discover
we can see is website for How to We Do Yogas
<img width="1597" height="780" alt="1" src="https://github.com/user-attachments/assets/be62d306-ddf7-4c1f-86cb-4117ea6cddf9" />
# find the flag
open gobuster is tool for url endpoint enumeration is need for url and wordlist 
[Uploading wordlist.txt…]()
and use this commend

    gobuster dir -u http://xebec.cylabacademy.net:12800/ -w '/home/fox/FOX/wordlist.txt'
we get this 
<img width="1600" height="457" alt="1h" src="https://github.com/user-attachments/assets/e85f30c7-0e2a-4618-8bf6-470e0a01eb99" />
