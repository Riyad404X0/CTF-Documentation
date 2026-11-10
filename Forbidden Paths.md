# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Forbidden Paths
# Description 
Can you get the flag?

We know that the website files live in /var/www/html/ and the flag is at /flag.txt but the website is filtering absolute file paths. Can you get past the filter to read the flag?
# discover
<img width="1599" height="781" alt="1" src="https://github.com/user-attachments/assets/de05d167-fbf1-4fa3-82c2-566f18085a59" />
we have this website and input box and when we enter name one of them story we get story and you can read story
# exploit
the ctf description says files live in /var/www/html/ and the flag is at /flag.txt and that is likely vulnerability Local File Disclosure (LFD) 
# Local File Disclosure (LFD) 
A Local File Disclosure (LFD) or Local File Inclusion (LFI) vulnerability occurs when a web application takes user-supplied input to load or read a file (such as via a parameter like page, file, or sample) without proper sanitization. This allows an attacker to use directory traversal sequences (such as ../) to escape the web root and read sensitive local files on the server (like /etc/passwd, source code, .env files, or CTF 
