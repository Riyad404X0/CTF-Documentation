# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : byp4ss3d
# Description 
A university's online registration portal asks students to upload their ID cards for verification. The developer put some filters in place to ensure only image files are uploaded but are they enough? Take a look at how the upload is implemented. Maybe there's a way to slip past the checks and interact with the server in ways you shouldn't.
# First step : Discover the web page
<img width="1599" height="778" alt="1" src="https://github.com/user-attachments/assets/07e5a3c2-79ff-4a89-b6a6-608dd3e7762b" />
we can see we can just upload to webpage just 3 file type (JPG, PNG, or GIF)

# What we should do:
we need flag.txt or somthing like that inside we can get our flag 
so we have to write php file and hide it like png file 
and use this file to get webshell on website
you can use this exploit
<img width="753" height="317" alt="php" src="https://github.com/user-attachments/assets/c8bc7736-c088-465b-8763-55e41e5f6017" />

# in terminal /linux
you do
nano exploit.php
and will Write the PHP shell code as shown in the image
and save it by ctrl + x 
and to upload php file we need add File Extension  (JPG, PNG, or GIF)
<img width="156" height="147" alt="2" src="https://github.com/user-attachments/assets/89449e69-20ba-488b-90e2-f485a41fe17a" />
# 
after you upload file you can see is Successfully uploaded
<img width="1599" height="777" alt="3" src="https://github.com/user-attachments/assets/21541b2c-9e2d-4b84-b055-5a3cce6b0839" />

now you can not execute file php as php file is PNG file ,we need execute php PNG file as php file by useing .htaccess
The .htaccess file is short for hypertext access. It's used to control web server settings and is important for protecting your website from attacks that could completely destroy it, among other critical functions
next is Create a file name it .htaccess and add this to file by
using nano .htaccess and put this code
  
#AddType application/x-httpd-php .png























