# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : findme
# Description 
Help us test the form by submiting the username as test and password as test!
# Discover
we get this login page and we had already username and password and do login 
<img width="1599" height="779" alt="1g" src="https://github.com/user-attachments/assets/d9173c80-d091-444d-94cc-72e87c96a936" />
after we login we see this -> I was redirected here by a friend of mine but i couldnt find anything. Help me search for flags :-)
and from title findme 
<img width="1599" height="780" alt="2" src="https://github.com/user-attachments/assets/f67650f5-3dd3-4e9b-80a2-6f480a29e66b" />
and we need to open burp suite to see server response Before you enter password and username
and POST methed when we enter username and password the server response by flag in new URL path that server is giving id in end of path of the url /next-page/id=YWNhZGVteXtwcm94aWVzX2Fs is base64 encode and inspector is do dcode and we get first part flag 
     
                            YWNhZGVteXtwcm94aWVzX2Fs --> academy{proxies_al
<img width="1598" height="862" alt="3" src="https://github.com/user-attachments/assets/8479cd15-a729-41ec-ad92-7821a4da1fb9" />



