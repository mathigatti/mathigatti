---
title: Coding Psychological Experiments
date: 2019-06-09 18:39:02
tags:
cover_image: images/psychological.jpg
---

Psychopy library is a useful framework to develop psychological experiments using Python. In this example I will show how to develop a basic experiment that registers how much time it takes for someone to press a key, then I will save the data as a csv file. The full code can be found [here](https://gist.github.com/mathigatti/3635a6414118e34fa90786fb67b6b7ea).

<img src="https://ucarecdn.com/747786fb-53a6-470f-9d21-1c0285d2d320/" width="100%" border="5" />

## The code

### Libraries
First I import the libraries
```python
from psychopy import visual, core, event
import datetime # Used to register the date of the experiment
import pandas as pd # Used to save the data as csv easily
```

### Setting constants and global variables
```python
# Colours
gray = '#969696'
black = '#000000'
white = '#FFFFFF'

# Window parameters
resolution = [300, 300]
```

### Defining main functions

#### Window

In psychopy you define the window where all the screens are going to be displayed like this

```python
def window(resolution):
    fullScreen = False
    win = visual.Window(resolution,units="pix",  color=gray,
     colorSpace='hex', fullscr=fullScreen, monitor = "testMonitor")
    win.setMouseVisible(False)
    return win
```

#### Screens

We are going to define the screens now. Here we will specify the text messages, its style, the background colour and all that kind of things. Our program has only two screens, the starter screen that ask you to start, and the stop screen that records how long you took to press the button.

<img src="https://ucarecdn.com/75931ec1-0f82-45f1-be76-22004d39dc4f/" width="100%" border="5" />

```python
def loadInstructionsAndFlip(win):
    background = visual.Rect(win, width=resolution[0]+10,
     height=resolution[1]+10, fillColor=black, fillColorSpace='hex')
    msg1 = visual.TextStim(win, text="press [ q ] to exit",
     pos=(0.0,(-resolution[1]*0.10)), color=white, colorSpace='hex')
    msg2 = visual.TextStim(win, text="press [ n ] to continue",
     color=white, colorSpace='hex',alignHoriz='center', alignVert='center')
    background.draw()
    msg1.draw()
    msg2.draw()

    # Elements are only displayed after the flip command is executed
    win.flip()

def loadStartScreenAndFlip(win):
    background = visual.Rect(win, width=resolution[0]+10,
     height=resolution[1]+10, fillColor=gray, fillColorSpace='hex')
    msg1 = visual.TextStim(win, text="press any key to start",
     color=white, colorSpace='hex')
    background.draw()
    msg1.draw()

    # Elements are only displayed after the flip command is executed
    win.flip()
```

#### Main logic
Here we implement the main logic of the program. We create the clock that measures the time. We reset it on every iteration and show each screen every time.
```python
def startScreensAndRecordData(win):
    clock = core.Clock()
    win.clearBuffer()

    data = []
    loadStartScreenAndFlip(win)
    event.waitKeys()

    while True:
        loadInstructionsAndFlip(win)
        clock.reset()
        keys = event.waitKeys(keyList=["n","q"])
        for key in keys:
            time = clock.getTime()
            print("You pressed the {} key on {} seconds"
                .format(key,round(time,3)))
            data.append([key,time])
            if key == "q":
                return data
            else:
                loadStartScreenAndFlip(win)
                event.waitKeys()
```

#### Puting all together and saving it
Finally we put everything together and save the file as a CSV using pandas :)


```python
def main():
    win = window(resolution)
    data = startScreensAndRecordData(win)

    pd.DataFrame(data,columns=["Key","Time"])
    .to_csv('experiment_' + str(datetime.date.today()) + '.csv')


```

![](https://ucarecdn.com/e0615065-b962-4851-998e-1d4da0ce1d75/)
