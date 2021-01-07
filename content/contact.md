+++
title = "Challenges present on Threads and there Solutions"
date = "2020-12-16"
sidemenu = "true"
description = "Developed by Enciphers"
+++

As we know there are many vulnerabilities present in the Threads web application so to find out and exploit each of  these vulnerabilities are the challenges on Threads application.
#### Note: (hints are provided under the heading of each challenges in a small paragraph, so read them at your own risks).   
Here is the list of all the challenges which a user can solve:

## Challenge-1:(Self-XSS)
 
Hint:  Insert a payload under the name of the account (could be done when registering an account or changing the existing account name for the profile section.


## Challenge-2:(Directory brute-forcing)

Hint: There is a directory (/management) where we can login as admin with the hardcoded mail which is `abhinav@enciphers.com` . To Brute Force all the directories you can take help of tool Dirsearch.


## Challenge-3:(MongoDB Injection)

Hint : It is present in the search feature of the application where it works like this if the name (exact) matches with the application then it will show that user's id and its information. Also if you pass {$gt: ''}  in the search field, it would show all the users as the query which was executing.


## Challenge-4:(JWT Authentication)

Note:  For JWT challenge, hardcoded email is ‘abhinav@enciphers.com’ and the password for it is ‘123’. So first make sure that an account exists with the above email id and then try to forge the token.

Hint:  The application uses cookie-based authentication but has the support of JWT as well.There is a /management page which has an authentication system which works via JWT API. When logging in to the /management page by providing your credentials, you would see that you are not authorized to log in. Now to become authorized user one has to forge the token of the admin account since its using HMAC so the current secret key is thr3@ds@000t so forge a token with ‘abhinav@enciphers.com’.You can replace the token via burp request and response or just change the token under local storage and refresh the page you should have admin access where you can delete other users.


## Challenge-5:(Insecure Direct Object Reference)

Hint:  Deleting Comment/Post of any user using BurpSuite (having the UUID).


## Challenge-6:(Server-side Request Forgery)

Hint: So it is in  the profile section where you can upload your profile picture via URL, its very simple basics SSRF. You can fetch internal files(which exists) on the server like /etc/passwd .Then inspect the profile page and download the updated image you would see the /etc/passwd content .


## Challenge-7:(Attribute-XSS)

Hint:  Under the profile section, you can change your website link, it would execute only when visited in an unauthenticated state.


## Challenge-8:(Cross-site Request Forgery)

Hint: The Threads application is CSRF vulnerable because it does not create anti csrf tokens. So basically as an attacker you can change victims password, name,other information on profile section. You have to send the malicious link to the victim  which should be clicked by  the victim to perform action in it. The malicious file to change victim's password is  attached to the link he sent.  


These are all the challenges present on Threads application which you can solve.
Happy learning,Happy hacking!
 

