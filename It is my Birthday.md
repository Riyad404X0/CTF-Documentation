# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : It is my Birthday.
# Description 
I sent out 2 invitations to all of my friends for my birthday! I'll know if they get stolen because the two invites look similar, and they even have the same md5 hash, but they are slightly different! You wouldn't believe how long it took me to find a collision. Anyway, see if you're invited by submitting 2 PDFs to my website
# Discover
<img width="1599" height="780" alt="1" src="https://github.com/user-attachments/assets/7c270c37-89d4-4599-96ad-c03ae73726a2" />
we see this website and thay tell us to upload two pdf file to get throw and after we make pdf file and name it a.pdf and b.pdf
,after we upload this two pdf files we get MD5 hashes do not match!
<img width="1598" height="779" alt="2g" src="https://github.com/user-attachments/assets/02a6bccd-7f2c-48fb-8bd0-382109354008" />
so to pass this filter we need to have different file name and same md5 hash value ,we can get two file with same hash from this website 
https://www.mscs.dal.ca/~selinger/md5collision/
to do md5collision
and this hash value is explain 
<img width="1599" height="821" alt="3" src="https://github.com/user-attachments/assets/21b6b003-d6ad-4e83-a191-f8da642a2761" />
upload files 
<img width="1599" height="780" alt="4" src="https://github.com/user-attachments/assets/912af276-120c-4546-8245-cf6b6e0bdbc2" />
<img width="1599" height="780" alt="5" src="https://github.com/user-attachments/assets/f3873786-8aaf-4b96-8ced-ce8bc04397f6" />
get flag!



