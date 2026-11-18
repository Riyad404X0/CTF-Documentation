# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Client-side-again
# Description
Can you break into this super secure portal ?
# Discover
we see this website
<img width="1555" height="776" alt="1" src="https://github.com/user-attachments/assets/6323ad0e-cb0c-4d26-95a9-35167d254eaf" />
and thay say Enter valid credentials to proceed and when we try enter something like admin we get this 
<img width="1556" height="784" alt="2" src="https://github.com/user-attachments/assets/2341f2a9-98ab-408a-a2e0-e6a13625f1a7" />
we goes to source page and when we look close we get javasecript code and the code is disorganized and when we read we see this variable _0x5a46 over her and we need to print out this variable by console.log function
# exploit
open devloper tool by F12 and go to console and add the javasecript code and add function console.log to read variable
<img width="1561" height="780" alt="4" src="https://github.com/user-attachments/assets/6d7bfc2b-052a-42c0-b0a5-511a72209b1a" />
<img width="1557" height="783" alt="5" src="https://github.com/user-attachments/assets/b1fe5b3b-25a9-4412-93ca-e64f1d6e8e89" />
get flag! academy{not_this_again_3226eb}
