## This is Github page for Documentation for *OPENSTUDIO PROJECT* RISD DM19

- OPEN STUDIO ON CIT 4th FLOOR!
We (Young&Win DM19) will build a twitter bot -- which collects data from audience by voice recognition.
We will update all the steps we go through for document& for me& for review back in the future!

>[editor on GitHub](https://github.com/digitalmonkey-risd/twitter/edit/master/README.md)


## 1.Basic Materials We Use for the Project ٩(๑•̀o•́๑)و 


- TWITTER BOTS
Twitter Apps > apply for developer account
https://projects.raspberrypi.org/en/projects/getting-started-with-the-twitter-api/
https://apps.twitter.com/

- TTS API
[Thinking Sphinx](https://freelancing-gods.com/thinking-sphinx/v4/installing_sphinx/mac.html) or
[Google Web Speech API](https://www.google.com/intl/en/chrome/demos/speech.html)

- [Anaconda](https://conda.io/docs/user-guide/tasks/manage-python.html)


## 2. Install these to your Computer!

### PIP
install PIP to your computer using Terminal (MAC)
```markdown
$ sudo pip install 
```
also you might need to install below to install things

```markdown
$ pip install twisted
```

Also, if you need upgrade below is the code
```markdown
$ sudo pip --upgrade pip
```

### SpeedRecognition
after that you need to install speech recognition by the code below
```markdown
$ sudo pip install SpeechRecognition
```

### Anaconda
Also if your computer is preinstalled with python2, you might want to install [Anaconda](https://www.anaconda.com/download/#macos) to use python3.
Anaconda is allowing you to go back and forth between python2 and python3.
Download from website link and install. After that, go steps below to launch environment to perform different ver of python
```markdown
$ conda
```
```markdown
$ conda search python
```
type the version of python you want to install in the area where "py36" is typed. you can have some instructions from there:
[Install Python with Anaconda](https://conda.io/docs/user-guide/tasks/manage-python.html)
```markdown
$ conda create -n py36 python=3.6 anaconda
```
```markdown
$ source activate py36
```
If it worked well your terminal might display like this
```markdown
(py36) youngin@youngsa-mbp ~ (master)
```
and check the version. If it matches with the version you installed it worked!
```markdown
$ python -V
Python 3.6.6 :: Anaconda, Inc.
```
### pyaudio or portaudio.
  this is like speech-to-test plug-in. This will activate and allow to access your mic from python. 
  do one of below
```markdown
$ brew install portaudio
```
```markdown
$ pip install pyaudio
```

## 3. Open Sublime Text and make two .py files as below
one is for recognition > twitt and the other is for reading API

### tts.py
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
### auth.py
this name can be changed, or directly typed in your tts file
```markdown
consumer_key        = 'your Key'
consumer_secret     = 'your Key'
access_token        = 'your Key'
access_token_secret = 'your Key'
```

## 4.Run Anaconda -- In case you have different version of python installed. As far I tested it works well in python 3.6
```markdown
$ source activate py36
```

## 5. Rud your code!
```markdown
$ cd /yourPathWhere tts.py is in 
```
```markdown
$ python tts.py
```

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
