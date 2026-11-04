# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Apriti sesamo
# Description 
I found a web app that claims to be impossible to hack!
# Discover
we can see is login page 
<img width="1599" height="778" alt="1" src="https://github.com/user-attachments/assets/bcaf2469-4e67-4661-82cd-422bc4d5ed4f" />

# Step 1: Finding the Backup File

When you open the login page, you won't find any obvious vulnerabilities in the normal interface

Using hints, we find a clue indicating that the developer used the Emacs text editor.

In Emacs, backup files are created and end with a tilde (~) after the filename (e.g., login.php~ or access page like /impossibleLogin.php~)

By accessing the backup file link, you can read the source code of the login page and understand how the data verification works
<img width="1464" height="828" alt="2" src="https://github.com/user-attachments/assets/2a3b3598-2c99-4e65-8bc1-a8b2e62fc412" />
<img width="1599" height="779" alt="3" src="https://github.com/user-attachments/assets/ca1a500e-c164-4f03-a5ff-5ab92dd70970" />
after we do dcode we get this 

    <?php
    if (isset($_POST['username']) && isset($_POST['pwd'])) {
      $yuf85e0677 = $_POST['username'];
      $rs35c246d5 = $_POST['pwd'];

    if ($yuf85e0677 == $rs35c246d5) {
        echo "<br/>Failed! No flag for you";
    } else {
        if (sha1($yuf85e0677) === sha1($rs35c246d5)) {
            echo file_get_contents("../flag.txt");
        } else {
             echo "<br/>Failed! No flag for you";
          }
        }
      }
    ?>

# step 2: Exploiting a PHP (Type Juggling/SHA-1) Vulnerability

In the source code, the script checks if the sha1() function matches the username and password (e.g., sha1($username) === sha1($pwd))

Vulnerability: In PHP, if you pass an array instead of plain text to the sha1() function, the function cannot process the array and will return null with a warning.

When the username and password are passed as arrays (e.g., username[]=123&pwd[]=456 using a tool like Burp Suite or by modifying the request):

The equation becomes: null === null

The result is true, bypassing the password verification

After bypassing the screen, the desired flag is displayed directly (e.g., reading the contents of a flag.txt file)
<img width="1599" height="865" alt="4" src="https://github.com/user-attachments/assets/874ef9e6-3254-4547-8079-dbbc217bfbe5" />
<img width="1554" height="775" alt="5" src="https://github.com/user-attachments/assets/04d67fe5-ea3a-4e93-af37-ad861414964a" />





