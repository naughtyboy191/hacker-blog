## Observe Closely(Forensics),50 pts

Running strings on the binary shows us a hidden_binary at the end of the png file 
lets run binwalk 
![](img/utctf20/1.png)

we can confirm that there is indeed a binary hidden inside the file lets extract and run it 
![](img/utctf20/2.png)

we got the flag!!

## 1 Frame per Minute(Forensics),50 pts

As the SSTV was mentioned in the challenge description 
It was similar to the *moonwalk* challenges in the picoCTF

I used this mobile [app](https://play.google.com/store/apps/details?id=xdsopl.robot36&hl=en_IN) in auto-detect mode and let the audio play and I got the flag

![](img/utctf20/3.png)

## [basics]Forensics,50 pts

we just check the file type of the file give and it just turns out to be text so we grep for our flag and get the flag

![](img/utctf20/4.png)

## spectre(Forensics),50 pts

As the name gave the hint ,this must the challenge in which the flag is hidden in the spectrogram of the audio file

firing up Sonic-Visualiser and plotting spectrogram gives us the flag
![](img/utctf20/5.png)


## epic admin pwn(Web), 50 pts

we are provided with the following login website vulnerable to SQLi

![](img/utctf20/6.png)

lets intercept the request with burp and use it with burp 

![](img/utctf20/7.png)

now using sqlmap gets us the pass

![](img/utctf20/8.png)

## The Legend of Hackerman Pt. 1(Forensics),50 pts

so the png file is corrupted so lets compare the corrupted png with another png file
we see that there is error in magic bytes so lets correct it

![](img/utctf20/9.png)

![](img/utctf20/10.png)

now we can easily view the image

![](img/utctf20/11.png)

