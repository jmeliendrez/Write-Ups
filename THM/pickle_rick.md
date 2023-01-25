<p align="center">
<img src="https://i.imgur.com/nlQEM3O.png" alt="Pickle Rick"/>
</p>

# Pickle Rick

At the end of the **Web Hacking Fundamentals** module in TryHackMe you are tasked with a challenge to put together all that you've learnt in the module. I was a little apprehensive as it had taken me a few months to go through the content with my busy schedule. I want to say that I really enjoyed this challenge as was a bit of fun, not too complex but just enough to take me about an hour and a half to complete. 

## Walkthrough

### Enumeration

The first phase in any web testing is recon and enumeration. We want to know what is present on the IP provided. We assume that we'll get atleast a port 80 for HTTP on the IP in a port scan using **nmap**. We'll then need to do some recon on the web site.

So, I do an `nmap` scan.

<p>
<img src="https://i.imgur.com/jVV97UN.png" height="80%" width="80%" alt=""/>
</p>

Our results show that we have both port 22 and 80 open. Port 22 is for SSH and there isn't much we can do there. I attempted an anonymous login but was refused. We also do not have enough information at this stage. As you can see, running `-sV -sC` (service scan and default scripts) gives us a little more information. We can see that a web server is running (Apache 2.4.18), our target is a Linux system (Ubuntu) and that the http-title returns, "Rick is sup4r cool". 

Next I navigate to the page and find a static webpage with not much to go off. I then inspect the web page and this reveals some leaked data. We observe that a comment has been left in the HTML saying, "Note to self, remember username! Username: R1ckRul3s". Definetely something to take note of later. 

<p>
<img src="https://i.imgur.com/EQq0372.png" height="80%" width="80%" alt=""/>
</p>

This information indicates that there must be a login page somewhere. At this point I try using this username to login to SSH but this fails. I then think of running gobuster but this only leads me to the `/assets` directory which doesn't hold much.

<p>
<img src="https://i.imgur.com/koTx6Sa.png" height="80%" width="80%" alt=""/>
</p>

I then remember that nmap has a script that does http enumeration. I run this and find a couple of pages. It is at this point that I remember that gobuster has the `-x` flag to denote file types that it can search for. HTTP-enum script gives us both 'login.php' and 'robots.txt'.

<p>
<img src="https://i.imgur.com/QJhi16R.png" height="80%" width="80%" alt=""/>
</p>

I then navigate to the 'robots.txt' file and find the following.

<p>
<img src="https://i.imgur.com/lIAGa75.png" height="80%" width="80%" alt=""/>
</p>

Hmmm... no idea what that's about. If you've seen the show you know that that is what Rick says but there's indication of its significance. 

I then go to the 'login.php' page. And it redirects me to 'portal.php'. As implied, we are at a login page. I put in the username and then spend some time thinking about the password. Then I think to [myself](what a wonderful world), maybe I can use the text in 'robots.txt' as a password?

<p>
<img src="https://i.imgur.com/7i5aPGR.png" height="80%" width="80%" alt=""/>
</p>

And BOOM! we're in!!! We are presented with a page that has a 'Command Panel', a dialogue box and an 'Execute' button.

<p>
<img src="https://i.imgur.com/I4UhiDj.png" height="80%" width="80%" alt=""/>
</p>

### Exploitation

### Further Research
After I completed the room I went on YouTube and watched [**John Hammond’s** solution to the challenge](https://youtu.be/oCAtfcr3iUw). I really enjoyed watching him work through it differently. I was impressed by the fact that he made a reverse shell in the command dialogue box. I tried it out myself and was kicking myself to how easy it was moving around the file system like that. 

So, back to when I first logged in to `login.php` we go need to execute a command using python3 (as python 2 does not run on the server). We also need to set up a listener on our local machine.

We use `nc -lnvp 1234` to set up our listener in the terminal.

Then we use [PentestMonkey's](https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet#:~:text=shell%20here.-,Python,-This%20was%20tested) reverse shell script. We'll need to modify it to have our IP address and port number. We also need to make sure that we run it using python3 and not just python. Copy and paste it into the dialogue box on the webpage. Click 'Execute' and the page should just hang.

Checking our listener we see that we are connected.

