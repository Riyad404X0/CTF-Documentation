# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : 3v@l
# find the flag 
<img width="1599" height="781" alt="1" src="https://github.com/user-attachments/assets/83ad357c-e52a-4de1-b0d9-36c5dbfe4d81" />
as we see the website tell us to submit the flag but we don't have flag and waht we need is the take look at source page
and we get js file 
<img width="1599" height="779" alt="2" src="https://github.com/user-attachments/assets/a3e74e7d-fbdb-4f4c-914f-42ced71449ad" />
and when we take very close look we see is end point 
<img width="1599" height="777" alt="3" src="https://github.com/user-attachments/assets/b9f6a35f-67f5-4a1f-916f-2980918c8d25" />
and after we add this endpoint to our url ,will going to download file JIFxzHyW8W and to read the file bay cat command

    cat JIFxzHyW8W 
<img width="1599" height="820" alt="4" src="https://github.com/user-attachments/assets/7fdd0db3-3473-499e-bcd5-4d4aaa722539" />
and after we scroll down
<img width="1599" height="815" alt="5" src="https://github.com/user-attachments/assets/943d85b2-286b-4e36-b393-bfe49034114b" />
get flag!


