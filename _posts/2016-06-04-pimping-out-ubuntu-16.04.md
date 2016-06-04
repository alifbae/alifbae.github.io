---
layout: post
title: Pimping out Ubuntu 16.04 LTS
---

I find myself rebuilding my system a lot, either because I want to experiment with new Desktop Environments or because I keep corrupting my system files because I break something. 
  
Whatever the case may be I have a standard setup to make my Ubuntu installation stand out by adding some sprinkles on top, and to generally imporve workability and productivity.

### Update and Upgrade

This is a no brainer but it is still worth mentioning, run this to update your system packages so you're up to date with the latest security and software updates. 

~~~
$ sudo apt-get update && sudo apt-get upgdate 
~~~

### Install Unity Tweek Tool

~~~	
$ sudo apt-get install unity-tweak-tool
~~~

to run the tweak tool:

~~~
$ unity-tweak-tool
~~~

One thing I love about 16.04 is that they _finally_ added the ability to move the launcher to the bottom of the screen. It just feels more ergonomic to me and saves that precious horizontal screen space. 
  
Go ahead and play around with the settings and get something going that you like yourself. 

### Install Numix themes and Icons

Numix is a stunning flat theme for Ubuntu and just makes it that much prettier imo. Yes I care about aesthetics because if i'm spending the rest of my life looking at a screen i'd prefer it's something nice to look at. Maybe i'll talk about a [ricing](https://wiki.installgentoo.com/index.php/GNU/Linux_ricing) tutorial in the future. 

~~~ 
$ sudo add-apt-repository ppa:numix/ppa
$ sudo apt-get update
$ sudo apt-get install numix-gtk-theme numix-icon-theme-circle
~~~

Now after you're done installing the themes and icons, open unity-tweak-tool, under appearance > Theme, click 'Numix' or 'Numix Daily'.
  
After that you can set your icons by clicking on the 'Icons tab' and choosing either of the three new Numix icon packs, whichever one you like the most. I personally prefer 'Numix-circle'


### System Load Indicator

I personally love seeing data about my system in the overhead bar in Ubuntu.

~~~
$ sudo apt-get install indicator-multiload
~~~

Launch the indicator from the dash and you'll see a system resource monitor in your top bar. 

![indicator](http://i.imgur.com/KxpKDRd.png)

### Install Google Chrome

Chrome is my default browser and installing it is easy. Download the .deb package file from https://www.google.com/chrome/browser/desktop/index.html
  
open your terminal and go to the directory where the .deb file downloaded and run the following:

~~~
$ sudo dpkg --install <filename>
~~~

### Make User Scripts Executable From Anywhere

Ever have a script you use frequently in a folder somewhere on your filesystem that you have to keep cd-ing and ls-ing to get to? 
  
Wouldn't it be easy it you could simply type the name of the script anywhere from your terminal and it would execute? Linux can do that too!

Make sure your script has a shebang at the top, for example for a bash script you'd have:

~~~
#!/bin/bash
~~~

Now add the directory you want all your scripts to be path executable to your .bashrc file. Fire up your text editor and open ~/.bashrc

Simply add the path of the directory at the end of your .bashrc as follows, I like to keep mine in ~/Code/bin/

~~~
# make ~/Code/bin executable from everywhere
export PATH=$PATH:"~/Code/bin"
~~~


### Setup Terminal Colors

I'm very picky with colors with it comes to my work enviroment, be it my code editor or my terminal. Thankfully since you're smart enough to be using linux you can easily change your terminal colors. I like to keep mine simple like so:

![bash](http://i.imgur.com/wORw2j7.png)

To change your colors to mine simply copy my .bashrc into your ~/.bashrc as is. 

{% gist alif-bae/327e46b9b33b2e4f2b5ba1c5327f63cb %}
