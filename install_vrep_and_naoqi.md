# **Experience of Vrep, NAO and Python(1)**
&nbsp;&nbsp;This semester I have a course called **_Human Computer Interaction_** and there is a task for us to try to use v-rep and program a robot model in v-rep called **_NAO_** with python. Our teacher will tell seldom to us about this so I have to learn it by myself. However, I find that I can't find an article complete enough, which can tell me how to build the environment on my PC. Fortunately, I built it succesfully after solving many conufsing problems. And now I'd like to write down my experience. _(As I'm using Windows OS, this article will be based on Windows OS.)_

&nbsp;&nbsp;In this condition, what we need are 4 things:  
<center>python2.7 32bit
spyder  
PyQt4 32 bit  
naoqi sdk</center>

&nbsp;&nbsp;Now let me introduce these parts first so that you can know why we need them. Of course to write python scripts we need python. And I recommend python2.7 in 32 bit because we need to come with the naoqi sdk. This sdk developed by SoftBank seems to only come with python2.7 in 32 bits. As for Spyder, it's a python extension pack for scientific computing. And if you have installed PyQt, you can have a user interface of spyder. It has blocks for scripts and console lines. After all, spyder can be a good tool for robot programming with python. And about naoqi, as I mentioned before, it's an sdk pack for NAO. Your NAO programming can be easier with this and I see that it's also recommened by [official NAO website](https://www.ald.softbankrobotics.com/en/robots/nao). 

&nbsp;&nbsp;For real, when I didn't use the pack and want to make NAO in vrep walk, I tried again and again and find it so hard to make the robot put down it's foot. As a beginner, I think this can be so hard, I tried many remote API functions such as simxGetJointMatrix and simxSetJointTargetVelocity but to my confusion they didn't work at all, on NAO. So I decided to use naoqi for it seems so easy to make the robot walk with this sdk pack. I just installed it successfully last night and haven't tried it. I will write down some experience about using this sdk pack in next article. 

&nbsp;&nbsp;`Python 2.7` is really easy to get and install. The only thing to remind is that remember to add it into system path or you cannot use it later. And if you don't add it into path, it won't appear in install directory and then there will be some problem while you're installing naoqi. You can test if it's installed by entering 'python' into the comment prompts. If it go to python console line, python27 is already installed.

&nbsp;&nbsp;As we install python2.7 in 32 bits, the version of `spyder` we install should also be in 32 bits. There are several ways to install spyder. In simple way, you can download python(x,y) and install it. Then you will find spyder and PyQt are both installed and other scientific computering tools for python. However I don't think it's the best method because I failed to install python(x,y). Actually, I installed it but I can't open the interface of python(x,y). I don't know why and the whole instalation pack of python(x,y) can be over 800 MB. I think it's too big (: . So I installed spyder in a little bit more complex methods. I used the pip instruction which can help you install python parts with `comment prompts`.

&nbsp;&nbsp;Open the command prompt of your OS and input
```
pip install spyder
```
and then tap Enter, the system will collect the required pack from the Internet and install them itself. Be careful that the download speed can be slow. 

&nbsp;&nbsp;And for `PyQt4`, I installed it by downloading a .whl file myself. you can get the .whl file [here](https://www.lfd.uci.edu/~gohlke/pythonlibs/). And to make PyQt come with the installed spyder and python2.7, we should download PyQt for python2.7 and in 32 bits. The .whl file is just the file which the pip instruction use to install PyQt. So I open the command prompt again and the change the directory to the folder where I save the  .whl file and then input
```
pip install PyQt4-4.11.4-cp27-cp27m-win32
``` 
_('PyQt4-4.11.4-cp27-cp27m-win32' is the name of the .whl file I downloaded)_ . Wait for a while, and PyQt4 is already installed. Now we can test if spyder and PyQt4 is really installed. Enter 'spyder' to the comment prompts. If there is graphical interface, spyder and PyQt4 are installed successfully.


&nbsp;&nbsp;You can get v-rep at their [official website](http://www.v-rep.eu/index.html). And the EDU version of v-rep is free. However, be careful that don't download a 64 bit version. Or you will get an error when you try to import the programming pack into python.

&nbsp;&nbsp;At last, let's talk about naoqi. I think it's really difficult to install because even if I installed it, there will be an error when I tried to import it. Maybe it's just because I was using 64-bit python2.7, but who knows:) . After all, I can import it successfully now. You can get naoqi on [the SoftBank website](https://community.ald.softbankrobotics.com/en/resources/software/language/en-gb). Pay attention that the site may require you to sign in before download. And then we will get a .exe file. We run the file and select the version of python we want to install naoqi with. And when naoqi is installed, we need to check if it can be imported. We can open spyder and enter 'import naoqi' into console lines and if there is no error, we have installed naoqi succefully. If python can't find the module, we should set python path with spyder. Add the folder path where we installed naoqi, and try again. 