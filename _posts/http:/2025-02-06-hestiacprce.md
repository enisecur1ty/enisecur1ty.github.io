---
date: 2025-02-06
layout: page
title: "Third Exploit Of The Month - Hestia Control Panel RCE"
tags: [vulnerability research, exploit development]
categories: [CVE, Exploit Development, Vulnerability Research]
image: https://i.pinimg.com/originals/3c/df/aa/3cdfaa826b40efdc80c00b5d914399f9.gif
---
![img-description](https://i.pinimg.com/originals/3c/df/aa/3cdfaa826b40efdc80c00b5d914399f9.gif)

Here's the exploit code
[PacketStorm Hestia Control Panel RCE](https://packetstorm.news/files/id/189606/)
<br><br>
And Here's The Github Link
[Github](https://github.com/enisecur1ty/Hestia-Control-Panel-Remote-Code-Execution-Exploit)

<h2>Hestia Control Panel 1.9.3 Remote Code Execution (RCE)</h2>

Ah, Hestia Control Panel... a nice little tool to manage your servers, right? Well, not anymore. While it’s an excellent platform for admins, it’s also got a nasty Remote Code Execution (RCE) bug that just screams “Exploit Me!”. So, buckle up, because we’re diving into how we can take full control of a server running version 1.9.3. Let's get into some real hacking.

<h2>What’s Going Down?</h2>

Hestia is a slick web management tool that many admins love because it's open-source and powerful. But like all good things, it has its flaws. In version 1.9.3, there’s an RCE vulnerability that allows us to run arbitrary commands on the target system. That means with just a malicious payload and a little finesse, we can gain remote access and do whatever we want on the server. Sweet, right?

<h2>How to Exploit It? The Basics</h2>

Alright, let’s break down the steps for exploiting this vulnerability. Here’s the deal:

#--> <b>Login to the Panel</b>: First, we need to get ourselves logged into the target Hestia Control Panel. We're going to need the username and password (duh). But hold on, we also need to bypass some pesky CSRF tokens, because we don't like to play fair.

#--> <b>Cronjob Injection</b>: Once we’re in, it’s time for the magic. The bug lets us create a new cron job with our own code that gets executed on the server. Imagine it as planting a time bomb that goes off whenever we want. The cron job is pretty much a hidden backdoor to execute whatever we like on the system.

#--> <b>Triggering the Payload</b>: Now that we’ve created our cron job with the reverse shell payload, we just need to set up our listener to catch the shell. As soon as the cron job runs, we’re in.

<h2>What Happens Next?</h2>
Once the cron job is created and your listener is up, boom, the server executes the reverse shell payload, and you’re in like Flynn. From here, it’s game over. You now have control of the system, and it all started with a simple cron job injection.

<h2>Wrap Up</h2>
This is a pretty straightforward RCE vulnerability, but the impact is significant. Any server running Hestia Control Panel 1.9.3 is vulnerable, and if you’re quick enough, you can gain control :D. Remember, always test responsibly and within authorized environments—this is just for educational purposes. Stay safe, stay stealthy, and always patch those systems!
