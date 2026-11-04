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



