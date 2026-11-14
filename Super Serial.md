# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Super Serial
# Description 
Try to recover the flag stored on this website

# 1 Source Code Discovery

Check robots.txt: Navigating to /robots.txt reveals a disallowed entry for /admin.phps. The .phps extension indicates the server is configured to display raw PHP source code
<img width="1599" height="824" alt="11" src="https://github.com/user-attachments/assets/2b157b0a-b278-426f-ab51-8e6d98c1e2bd" />

Inspect Application Source: Append s to the known .php files to read their source code

/index.phps shows it includes cookie.php and authentication.php
<img width="1599" height="773" alt="2" src="https://github.com/user-attachments/assets/358a877c-4c1c-4006-b170-1cce8d4dbb82" />

/cookie.phps reveals that the server reads the login cookie, URL-decodes and Base64-decodes it, and passes it directly into PHP's unserialize() function. If an 
<img width="1599" height="777" alt="3" src="https://github.com/user-attachments/assets/c4022ae9-131b-4623-9898-7489601e94cd" />

error occurs during validation, it echoes the deserialized object inside an error message

/authentication.phps defines an access_log class with a public $log_file property and a __toString() magic method that calls read_log(), which executes 

file_get_contents($this->log_file)

# 2 Payload
Serialized Object: Create a serialized PHP string for the access_log class setting $log_file to ../flag (the location noted in the challenge hint)

    O:10:"access_log":1:{s:8:"log_file";s:7:"../flag";}

Encode the Payload: Base64-encode the serialized string
<img width="1599" height="869" alt="4" src="https://github.com/user-attachments/assets/1ee86a9c-da87-40b4-aefa-3efb9a96f444" />

    TzoxMDoiYWNjZXNzX2xvZyI6MTp7czo4OiJsb2dfZmlsZSI7czo3OiIuLi9mbGFnIjt9

# 3 Exploitation
Navigate to /authentication.php and change cookie name to login and value to Payload 
<img width="1556" height="816" alt="5" src="https://github.com/user-attachments/assets/39e69a70-b27d-4282-8177-8dc126801cb0" />
get flag!

    


    

