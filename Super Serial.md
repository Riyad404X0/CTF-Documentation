# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Super Serial
# Description 
Try to recover the flag stored on this website

# 1 Source Code Discovery

Check robots.txt: Navigating to /robots.txt reveals a disallowed entry for /admin.phps. The .phps extension indicates the server is configured to display raw PHP source code.

Inspect Application Source: Append s to the known .php files to read their source code:

/index.phps shows it includes cookie.php and authentication.php.

/cookie.phps reveals that the server reads the login cookie, URL-decodes and Base64-decodes it, and passes it directly into PHP's unserialize() function. If an 

error occurs during validation, it echoes the deserialized object inside an error message.

/authentication.phps defines an access_log class with a public $log_file property and a __toString() magic method that calls read_log(), which executes 

file_get_contents($this->log_file)

