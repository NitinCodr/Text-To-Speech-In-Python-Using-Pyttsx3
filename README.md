# Text-To-Speech-In-Python-Using-Pyttsx3
Voice Assistant is amazing, isn’t it? Guess what, we can create our own voice assistant to support us in our everyday lives. It would not be high-end voice assistance but a combination of basic text-to-speech and speech recognition in Python.
In this blog, we will take look at Text-To-Speech Engine, Pyttsx3, that will give voice to our computer or machine.

# Installing Pyttsx3 Using Pip
```
pip install pyttsx3
```
This will install the pyttsx3 library in your machine or the virtual environment if you are using it.

# Text-To-Speech Using Pyttsx3 In Python
We have installed the necessary package needed for Text-To-Speech Conversion, so now let’s code it.
```
import pyttsx3

engine = pyttsx3.init()
engine.say("This is Text-To-Speech Engine Pyttsx3")
engine.runAndWait()
engine.stop()
```
Let’s understand this code line by line.

First of all, we’re going to import the pyttsx3 package that we’ve installed using the pip. The name pyttsx3 is really big and we might make an error when coding a big program.

We can give a short name using the Python import alias syntax.

Example:
```
pip install pyttsx3 as tts

```
You can use a different name as you like. I’m going for the original name because it specifically describes the name of the package. If a shorter syntax for this package is created later, you can use it.
```
engine = pyttsx3.init()
```
The above code initializes the pyttsx3 package. The Instance of the initialized pyttsx3 package is stored in the engine variable. We are calling the variable engine as it works as the engine and converts Text-To-Speech whenever execute the functions from the package.
```
engine.say("This is Text-To-Speech Engine Pyttsx3")
```
There is a built-in say() function in the pyttsx3 package that takes a string value and speaks it out.
```
engine.runAndWait()

```
This function keeps track when the engine starts converting text to speech and waits for that much time, and does not allow the engine to close. If we don’t write this code, it may happen that the engine might not work properly as the processes will not be synchronized.

After all the processes are over, we shut down the engine by calling stop() function.

# Change Text-To-Speech Voice In Pyttsx3 Python
We can also change the voice of the engine, the default is the voice of a male named David.

To change the voice of the pyttsx3 engine, first, we will have to get the list of objects of voices.
```
voices = engine.getProperty('voices')
```
The getProperty() function of the pyttsx3 package takes a string as a parameter and returns an object matching the string.
```
print(voices)
```
When we print the voices, we get a list that contains two objects.
```
[<pyttsx3.voice.Voice object at 0x000001AF1634D820>, 
<pyttsx3.voice.Voice object at 0x000001AF1634DB80>]
```
Let’s Print Each Voices.
```
print(voices[0])
print(voices[1])
```
voices[0] – This Voice’s name is Microsoft David Desktop (Male Voice Default).

voices[1] – This is the Female Voice named Microsoft Zira Desktop.
```
# Voices[0]

<Voice id=HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech\Voices\Tokens\TTS_MS_EN-US_DAVID_11.0
name=Microsoft David Desktop - English (United States)
languages=[]
gender=None
age=None>

# voices[1]

<Voice id=HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech\Voices\Tokens\TTS_MS_EN-US_ZIRA_11.0
name=Microsoft Zira Desktop - English (United States)
languages=[]
gender=None
age=None>
```
Now when we have understood the voice property. Also, stored the voices list from the engine.getProperty('voices') function. Let’s change the Voice of the engine to Female Voice Named Zira.

The naming convention of the pyttsx3 functions is very convenient. getProperty() function is used to get the property related to that string. So, the setProperty() function is used to set property based on a string.
```
engine.setProperty('voice', voices[1].id)
```
The above code changes the voice to Zira, the setProperty() function takes the property name and the changing property id.
# Changing Speed Rate In Pyttsx3
We can also change the Speed of the Speech Engine.

First, Let’s see what is the default rate that the voice ships with.
```
rate = engine.getProperty('rate')
print (rate)
```
Get the Speed Rate of the engine using the getProperty() function and print it.

The Default Speed Rate of the Speech Engine is 200.

If we set the Speed below 200 the voice will speak slowly and above 200 will increase the speed rate of the engine.
```
engine.setProperty('rate', 100) # Decrease the Speed Rate x2
engine.setProperty('rate', 250) # Increase the Speed Rate x1.25
```
# Change Volume In Pyttsx3
In the previous section, we learned how to change the speed rate of the engine. In this section we will see how we can increase the volume of the engine.
```
volume = engine.getProperty('volume')
print(volume)                            # current volume level
engine.setProperty('volume', 2.0)
```
The Code is almost similar for getting and setting every property in pyttsx3.

# Saving The Audio In Pyttsx3
You can also save the Text-to-Speech Conversion as an audio file.
```
engine.save_to_file('Text-To-Speech you want to save as a audio file', 'audio.mp3')
```
The save_to_file() function takes two parameters, first the text you want to convert to speech and save it, next the name of the file along with the extension of the audio file.

Today we got to know the basics of the pyttsx3 and how to work with it. The next blog will focus on the Speech Recognition part and then we’ll combine both to make a Voice Assistant with some features.
