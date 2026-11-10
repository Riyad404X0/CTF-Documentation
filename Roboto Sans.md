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
let's pick first one robots.txt 
<img width="1599" height="824" alt="2" src="https://github.com/user-attachments/assets/69c43ab9-30df-49fc-9090-65adf87800aa" />
as we see There is something hidden from us by some sort of encode and is preply base64 or rot13
and after decode we get this
<img width="1597" height="44" alt="4" src="https://github.com/user-attachments/assets/58795f5a-fae5-4167-be6b-904841c7b652" />
as we see js/myfile.txt is the url path for the flag 
<img width="1596" height="825" alt="5" src="https://github.com/user-attachments/assets/cdd87760-198c-4c2a-8a45-04ddfff2459d" />
get flag!

