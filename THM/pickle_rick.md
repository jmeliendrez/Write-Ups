<p align="center">
<img src="https://i.imgur.com/nlQEM3O.png" alt="Pickle Rick"/>
</p>

# Pickle Rick

At the end of the **Web Hacking Fundamentals** module in TryHackMe you are tasked with a challenge to put together all that you've learnt in the module. I was a little apprehensive as it had taken me a few months to go through the content with my busy schedule. I want to say that I really enjoyed this challenge as was a bit of fun, not too complex but just enough to take me about an hour and a half to complete. 

## Walkthrough

### Enumeration

The first phase in any web testing is recon and enumeration. We want to know what is present on the IP provided. We assume that we'll get atleast a port 80 for HTTP on the IP in a port scan using **nmap**. We'll then need to do some recon on the web site.


### Exploitation

### Further Research
After I completed the room I went on YouTube and watched [**John Hammond’s** solution to the challenge](https://youtu.be/oCAtfcr3iUw). I really enjoyed watching him work through it differently. I was impressed by the fact that he made a reverse shell in the command dialogue box. I tried it out myself and was kicking myself to how easy it was moving around the file system like that. 

So, back to when I first logged in to `login.php` we go need to execute a command using python3 (as python 2 does not run on the server). We also need to set up a listener on our local machine.

We use `nc -lnvp 1234` to set up our listener in the terminal.

Then we use [PentestMonkey's](https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet#:~:text=shell%20here.-,Python,-This%20was%20tested) reverse shell script. We'll need to modify it to have our IP address and port number. We also need to make sure that we run it using python3 and not just python. Copy and paste it into the dialogue box on the webpage. Click 'Execute' and the page should just hang.

Checking our listener we see that we are connected.

