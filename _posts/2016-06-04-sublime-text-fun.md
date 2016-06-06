---
layout: post
title: Setting Up Sublime Text For Maximum Fun
---

I'm going to be blunt, I absolutely adore sublime text. I've tried others like Atom, Notepad++, Vim and though Atom's functionality comes closest to sublime text, it simply is not as performance optimized as Sublime Text.
  
Vim on the other hand is essential to learn for anyone who's going to be working with remote server's via SSH, because nano simply doesn't cut it at times. Though I only use Vim when I absolute _have_ to!
  
This post is going to talk about a few tips and tricks for sublime text that make it almost addicting to use.

### Multiple Cursors

If you haven't been utilizing multiple cursors in sublime till now... please allow me to usher you into the new age. You can never unsee!

Select a word and use Ctrl+D to make multiple cursors for the same word. 

![mutlicursor](http://i.imgur.com/ufEyUmx.gif)

I don't know about you but that right there is sexy.
  
**ProTip:** You can easily unselect the last cursor by hitting Ctrl+U

## Extending Sublime with Packages

Sublime text has this thing called Package Control which allows us to easily search for and install packages natively from Sublime Text itself.

### Installing Package Control

Go to https://packagecontrol.io/installation and copy the code for your version. 
  
Open the console in Sublime text by typing Ctrl+` and paste the code into the console and hit enter. Give it a minute or so and restart sublime so the changes have taken affect.
  
You can now open the package control by typing Ctrl+Shift+P 

### Install Materialize Theme

Open up your package control by typing Ctrl+Shift+P and type 'Install' and press enter on 'Package Control: Install Package'
  
Search for Materialize and install the package. Now go to preferences > settings-user and define the theme as:

```json
{
  theme: Material Monokai
}
```

You can change the color scheme to match the theme by going to preferences > color scheme > materialize
  
There are more Material Themes on saadq's [github](https://github.com/saadq/Materialize) 

### Install Enhanced Side Bar

Search for EnhancedSideBar in the sublime package control and install it. This greatly extends the sidebar 