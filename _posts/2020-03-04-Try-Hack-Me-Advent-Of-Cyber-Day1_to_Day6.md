
So this is a website where you can get man challenges and box that you can root to improve your knowledge.
Today I am going to solve the Advent_Of_Cyber  the 25 days challenge for complete beginners
The link is given below
<https://tryhackme.com/dashboard>
## Day 1(Task 6)
So we are given with a login website and we have to register on it using any credentials you want

![](img/thm_advent/1.png)


After loggin in we have the following screen inspecting the cookies on the website we have the following results

![](img/thm_advent/2.png)

we have an cookie **authid** and it seems to be urlencoded and base64 encoded 

![](img/thm_advent/3.png)

On decoding it we have authid=**ghi##########** 
here the hidden part show the constant part of cookie 

so now we change the user to mcinventory and forge the cookie and inject it into the browser 
authid=*mcinventory##########*

![](img/thm_advent/4.png)

so now we have the answers for Task 6

## Day2(Task 7)

Now we are give a url and we have to find the hidden directries at the given url 
using gobuster for the job 

```bash
gobuster -u http://<ur-machine-ip>:3000 -w /usr/share/dirb/common.txt
```

![](img/thm_advent/5.png)

now on to the directory we get a admin login page 
looking at the source we have 

![](img/thm_advent/6.png)

searching for the repository on github

![](img/thm_advent/7.png)

now entering the default creds


And We have successfully completed the task :)

## Day3(Task 8)
This is a forensics challenge we have to basically just answer the questions on the site by looking at the pcap file
### For ques 1

![](img/thm_advent/8.png)

###for ques 2

![](img/thm_advent/9.png)

###for ques 3
we have to save the hash found in the output above and crack the hash with hashcat using rockyou.txt as given in the hint 

![](img/thm_advent/10.png)


One more Day complete :)

## Day4(Task 9)

This task is about basic understanding of linux and moving around in linux

### ques 1
to see number of visible files  **serioulsy :(**

![](img/thm_advent/11.png)

### ques 2
use cat to see the contest *EzPz*

![](img/thm_advent/12.png)

### ques 3
```bash 
grep -r password
```
using the command about the grep *recursively*
this help us save time rather that perform grep on each file

![](img/thm_advent/13.png)

### ques 4
```bash
grep -r '[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}'
```
here using a regex string we can easily carve out the IP address

![](img/thm_advent/14.png)

### ques 5
```bash
cat /etc/passwd |grep /bin/bash
```
using this we can see how many users have shell access to the machine

![](img/thm_advent/15.png)

### ques 6
```bash
sha1sum file8
```
using the **sha1sum** command to get the hash

![](img/thm_advent/16.png)


### ques 7
Since we don't have permissions to read /etc/shadow file 
so we find other files having string shadow in it and to which we have permission to read 
```bash
find / -name "*shadow*" 2>/dev/null
```

![](img/thm_advent/17.png)

we get an interesting shadow.bak file which we can so reading it we find the mcsysadmin's password hash


![](img/thm_advent/18.png)