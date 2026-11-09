# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Apriti sesamo
# Description 
The developer of this website mistakenly left an important artifact in the website source, can you find it?
# Discover
we see the page is How to We Do Yogas 
<img width="1586" height="782" alt="1" src="https://github.com/user-attachments/assets/9b6a4e46-1063-46c1-b702-8362c82d685c" />

and the Description said we need to see source code for the page 
# find the flag:
and the best way for get source code is by useing source code editor like vscode and is going split files css,js,html and make it esay for us to find the flag
first we need to get files in our local machine by this wget commend

     wget --mirror --convert-links --adjust-extension --page-requisites --no-parent http://xebec.cylabacademy.net:16992/
after that we get the website files and go to file button and open folder 
and as we see showing all files 
<img width="1599" height="825" alt="2" src="https://github.com/user-attachments/assets/600e2b78-ca2b-439e-aae0-14d159543122" />
the flag is it is likely  Comments it is like doing note in code page but it is not going to function like code instead it's To organize the code
and every languge has oun Comments methed to do like in python is # and java script // 


