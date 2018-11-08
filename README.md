## This is Github page for Documentation for *OPENSTUDIO PROJECT* RISD DM19

- OPEN STUDIO ON CIT 4th FLOOR!
We (Young&Win DM19) will build a twitter bot -- which collects data from audience by voice recognition.
We will update all the steps we go through for document& for me& for review back in the future!

>[editor on GitHub](https://github.com/digitalmonkey-risd/twitter/edit/master/README.md)


### 1.Basic Materials We Use for the Project ٩(๑•̀o•́๑)و 

~*-.RaspberryPI (FAILED..)*~

- Set up WIFI with username/pass in RaspberryPT in our case (RISD-WIFI) :
NOOBS > etcher > flash!
At the beginning, setup > network > select the wifi and type ID/PASS
Don’t need to select or configure. It will automatically setup

- TWITTER BOTS
Twitter Apps > apply for developer account
https://projects.raspberrypi.org/en/projects/getting-started-with-the-twitter-api/
https://apps.twitter.com/

### 2. Install these to your Computer!

- PIP
install PIP to your computer using Terminal (MAC)
```markdown
$ sudo pip install 
```
also you might need to install below to install twisted

```markdown
$ pip install twisted
```

Also, if you need upgrade below is the code
```markdown
$ sudo pip --upgrade pip
```

- SpeedRecognition
after that you need to install speech recognition by the code below
```markdown
$ sudo pip install SpeechRecognition
```


Also if your computer is preinstalled with python2, you might want to install Anaconda to use python3.
Anaconda is allowing you to go back and forth between python2 and python3.
- https://www.anaconda.com/download/#macos

- pyaudio or portaudio.
  this is like speech-to-test plug-in. This will activate and allow to access your mic from python. 
  do one of below
```markdown
$ brew install portaudio
```
```markdown
$ pip install pyaudio
```

###3. Open Sublime 
```markdown
# as is to refer
import speech_recognition as sr
import time



from twython import Twython

from auth import (
    consumer_key,
    consumer_secret,
    access_token,
    access_token_secret
)
twitter = Twython(
    consumer_key,
    consumer_secret,
    access_token,
    access_token_secret
)


# Recognizer() command to let make it listen
r = sr.Recognizer()


while True:
	with sr.Microphone() as source:
		print("say something")
		audio = r.listen(source)
		print("time over, thanks")

# recognize_sphinx part can be changed to recognize_google. but only 50/day
	try:
		message = (r.recognize_sphinx(audio))
		twitter.update_status(status=message+" #DM_OpenStudio")
		print("Tweeted: %s" % message)
		sleep(10)
	except:
		pass;
```



Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

```


### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/digitalmonkey-risd/twitter/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

### Some Defaults

You can use the [editor on GitHub](https://github.com/digitalmonkey-risd/twitter/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

