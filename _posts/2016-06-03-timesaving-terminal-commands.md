---
title: Time Saving Terminal Commands
layout: post
---

I love learning about new things that can help reduce annoying or frustrating things I do frequently while working. There are some of my favorite terminal commands to make my life just a tiny bit less miserable. 

### Run The Last Command As Sudo

~~~bash
sudo !!
~~~

![sudo](http://i.imgur.com/lWvyhsN.gif)

It always feels like i'm screaming 'SUDO!!!' at my terminal :3

### Bring Up The Last Command As An Argument

This will bring up the last command as an argument, its useful for when you entered a long file path in a previous command and need it again in another

~~~bash
Alt + .
~~~

### Reverse String Search In Terminal

This has to be one of my favorites. Ever find yourself pressing the up arrow key frantically trying to reload that obscure command you typed 30 minutes ago that you really need again? Just press ctrl+r on your terminal and type a partial of the command to bring it up. Keep pressing it to cycle through all of the ones that match it.

![reverse-string](http://i.imgur.com/hEMPUvl.gif)

### Display Your Current External IP Address

~~~bash
curl ifconfig.me
~~~

This will display your current external IP address which your machine uses to communicate to the web.

### Quick ASCII Table

You've probably needed to look at an ASCII table at one point or another, and then you've probably had to google for it. Guess what, linux's man pages provides an in built one!

~~~bash
man ascii
~~~

### Terminal Star Wars

Okay this one has less to do with work and more to do with appreciating the sheer amount of hours put into making this happen. Watch an ASCII based star wars right in your terminal!

~~~bash
telnet towel.blinkenlights.nl
~~~
