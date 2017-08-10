---
layout: post
title: Analysing Whatsapp Chat Backups with Python
subtitle: Or what I do when i'm bored
---

Whatsapp has an interesting feature where it allows you to send your chat history with as an email. That got me thinking, what if I ran a lingustic analyser on that chat history. Believe it or not it ended up providing some fairly interesting insights.  
  

We'll be using two tools for our analysis:
-- https://github.com/ravikiranj/whatsapp-chat-analysis
-- https://github.com/wheatear/wordsworth

## Analysing with Wordsworth

	
##### Clone the repository
~~~
$ git clone https://github.com/wheatear/wordsworth
~~~

##### Install Dependencies 

Step 1a: Install pip (if you don't have it already)

~~~
$ sudo apt-get install python-pip
~~~

Step 1b: Install python NLTK

~~~
$ sudo pip install nltk
~~~

Step 2: Launch the python interpreter

~~~ 
$ python 
~~~

Step 3: Download the ```Brown``` and ```Punkt``` dataset


```
>>> import nltk
>>> nltk.download('brown')
>>> nltk.download('punkt')
```

Step 4: Get blessings 
  Before you get started you need to install the python blessings library to colorize the terminal output. 
	

```
$ sudo pip install blessings
```

Step 5: Run wordsworth
  Okay we can finally run the analyser we've set up.
  Print the top 50-ngrams in textfile.txt

~~~
python wordsworth.py --filename textfile.txt --top 50-ngrams
~~~

#### Example Output 
![1](https://github.com/wheatear/wordsworth/raw/master/screenshots/screenshot3.png?raw=true)

![2](https://github.com/wheatear/wordsworth/raw/master/screenshots/screenshot6.png?raw=true)
  
![3](https://github.com/wheatear/wordsworth/raw/master/screenshots/screenshot7.png?raw=true)
