this is the writup for the [room](https://tryhackme.com/room/ohsint) on try hackme

lets start !!
we are given with an image 

![](img/thm_oshint/WindowsXP.jpg)

lets see what exiftool gives us 

![](img/thm_oshint/1.png)

So we got a username - **OWoodflint**

lets search for it using sherlock.py and we got that there is a twitter account with this username

lets search google with this username

![](img/thm_oshint/2.png)

so there is a Wordpress blog as well lets checkout the twitter account first

![](img/thm_oshint/3.png)

we get the answer to first question

there is also a bssid mention by him in a tweet lets geolocate it
I found that [this](wigle.net) is useful

![](img/thm_oshint/4.png)

So we find that our target lives in London

On infitely zooming in I find the ssid
its **UnileverWifi**

![](img/thm_oshint/5.png)


after a lot of digging I could not find the email so I though of checking github as there might be some repo with the username and yes I got the email

![](img/thm_oshint/6.png)


for the 6th question its straight forward we can get it by looking at his blog

![](img/thm_oshint/7.png)


for the last question we had to find the password of the person so I searched his twitter account but got nothing so I looked deep into his blog and got the password in the source code

![](img/thm_oshint/8.png)

and yup another room solved I found this quiet easy as it was basic recon but practice is always good :)



