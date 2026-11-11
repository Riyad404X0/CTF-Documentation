# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Forbidden Paths
# Description 
Most web application developers use third party components without testing their security. Some of the past affected companies are:

Equifax (a US credit bureau organization) - breach due to unpatched Apache Struts web framework CVE-2017-5638
Mossack Fonesca (Panama Papers law firm) breach - unpatched version of Drupal CMS used
VerticalScope (internet media company) - outdated version of vBulletin forum software used
Can you identify the components and exploit the vulnerable one?
# discover
<img width="1599" height="778" alt="1" src="https://github.com/user-attachments/assets/341bbca2-eee9-4b64-93dd-4fa008bb111a" />
we can see is login page and thay give us demo account for test and we need to be admin for this website
<img width="1599" height="781" alt="2" src="https://github.com/user-attachments/assets/27b804c3-8c32-41cc-95af-510d1ec8d03b" />
and after login we can see is there nothing to see but we have cookies 
<img width="1599" height="784" alt="3" src="https://github.com/user-attachments/assets/685a510e-12ef-4183-85c7-56843a3f5c66" />
and it's json web token as we see it's start by eyJ0 and to make sure ,just do decode 
<img width="1598" height="262" alt="4" src="https://github.com/user-attachments/assets/a3cb2daf-1d47-4b68-a68e-d81c75e58a69" />
and is 


$\color{#00ffff}\textsf{jwt vulnerability}$

# exploit
we need tuen role from user to admin by Modifier for JWT 

open developer tools
open this website 

https://www.jwt.io/
after we go to this website will going to copy cookies value and paste it in jwt website and will going to change alg hash algorithms and role to admin to get this work and output is our payload 
<img width="1599" height="769" alt="5" src="https://github.com/user-attachments/assets/c98eb70a-dced-4555-a44d-d7afbbce1ecc" />
<img width="1599" height="647" alt="6" src="https://github.com/user-attachments/assets/adfe450e-b7b9-4679-ba69-a759001b46e6" />
and after this copy payload and paste it in 




