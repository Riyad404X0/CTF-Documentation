# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Some Assembly Required 2
# find the flag 
as we see the website thay need from us to submit flag but we don't have flag 
<img width="1599" height="780" alt="1" src="https://github.com/user-attachments/assets/0d48fbca-7373-43f8-99ee-17e3b4c637b8" />
let's take some look at the source page is javasecript file 
<img width="1599" height="783" alt="2" src="https://github.com/user-attachments/assets/f5817b13-e9e2-486b-bf7a-10e0120fd92a" />
and when we look close is show us endpoint 
<img width="1599" height="773" alt="3" src="https://github.com/user-attachments/assets/6422590f-1c57-498c-8961-d85957b9bbe7" />
and after add this endpoint to our url ,is download file aD8SvhyVkb ,to read this file we need to use cat command

    cat aD8SvhyVkb

after scroll down we get this text but is likely encoder 
<img width="1599" height="819" alt="4" src="https://github.com/user-attachments/assets/ca5c1eb9-8e7a-4507-868a-9b8ce809940c" />
but we need to decode this ,will goes to 
https://gchq.github.io/CyberChef/



