# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : 3v@l
# Description 
ABC Bank's website has a loan calculator to help its clients calculate the amount they pay if they take a loan from the bank. Unfortunately, they are using an eval function to calculate the loan. Bypassing this will give you Remote Code Execution (RCE). Can you exploit the bank's calculator and read the flag?
# Discover 
we can see formula and thay want us to Enter input for it
<img width="1599" height="779" alt="1g" src="https://github.com/user-attachments/assets/a39a8dc0-a6e8-4f71-87ae-570d4e850abd" />
and when will go to source page we can see the server is python and  thay block us from input same keywords 
<img width="1599" height="779" alt="2" src="https://github.com/user-attachments/assets/61ebcb18-d96c-4011-bb2f-bc874f2a5892" />
We conclude that Python code must be written to display the contents of the flag.txt file but thay block us from input same keywords
<img width="1597" height="779" alt="3" src="https://github.com/user-attachments/assets/4cab396c-940d-4f5d-83a3-0fd088e5080f" />
<img width="1599" height="780" alt="4" src="https://github.com/user-attachments/assets/53287c48-9e00-4982-a273-ca7d571dfe6a" />
as we can see thay stop us from get the flag
# exploit
to get the flag we need to encode the input for bypass eval function , use encode like base64 or Character Encoding
will be using Character Encoding ASCII
go to https://www.ascii-code.com/ , and Replacing keywords thay stop us from useing it with their own encoder in table
open(/flag.txt).read()

will be like this 
        
    open(chr(47)+"f"+"l"+"a"+"g"+chr(46)+"t"+"x"+"t").read()
<img width="1598" height="778" alt="fanly" src="https://github.com/user-attachments/assets/2f13169d-3ef1-4f69-ad77-75ae0dc4e89f" />
get our flag



   


