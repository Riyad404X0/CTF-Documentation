# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : Apriti sesamo
# Description
How about trying to match a regular expression 
hint : Access the webpage and try to match the regular expression associated with the text field
# Discover
we can see we have Input fild 
<img width="1596" height="775" alt="1" src="https://github.com/user-attachments/assets/c1c313e5-06e9-49cc-b8e1-054601424087" />
# exploit
when we see source code for webpage in function send_request
<img width="1599" height="777" alt="2" src="https://github.com/user-attachments/assets/b13f43ff-3d37-4f0c-b8fb-61531146313d" />

// ^a.....y!?
we get this and thay said we need to match this Regex ,like academy,already etc
academy is the is large percentage the way to get flag

<img width="1599" height="783" alt="3" src="https://github.com/user-attachments/assets/ab143210-4c71-4800-976d-e8e945b21e0e" />
<img width="1597" height="785" alt="4" src="https://github.com/user-attachments/assets/1d912c28-0858-4857-92ff-eb51e20d125c" />
get flag




