---
title : "[python code] keyboard and mouse control"
date : "2021-10-25"
tags : [CodeDictionary,MouseControl,KeyboardControl,Python]
topics : [CodeDictionary]
---

## how to install
pip install pyautogui

## Finding Coordinate
It will display current mouse coordinate every second.
```python

import pyautogui
import time

while True:
 print("Current Mouse Position : ", pyautogui.position())
 time.sleep(1)
```

## mouse control

```python

import pyautogui

pyautogui.moveTo(300, 300) # move (x=300, y=300)
pyautogui.moveRel(x, y, t) # move (from current pos, move x and y with time. If t is 2, it will take 2 second to move)
pyautogui.click() # click
pyautogui.doubleClick() # double click
pyautogui.click(button='right') # right click

```

## keyboard control

```python

import pyautogui

pyautogui.write('hello world!') # type 'hello world!'

pyautogui.press('shift') # press shift
pyautogui.press('ctrl') # press ctrl 

pyautogui.keyDown('ctrl') # hold ctrl
pyautogui.keyUp('ctrl') # unhold ctrl

pyautogui.hotkey('ctrl', 'c') # ctrl + c 

pyautogui.press(['left', 'left', 'left']) # press left arrow 3 times
pyautogui.press('left', presses=3) # press left arrow 3 times
pyautogui.press('enter', presses=3, interval=3) # press enter 3 times after 3 second pressed
```
#### possible keywords for keyboard control
['\t', '\n', '\r', ' ', '!', '"', '#', '$', '%', '&', "'", '(',')', '\*', '+', ',', '-', '.', '/', '0', '1', '2', '3', '4', '5', '6', '7','8', '9', ':', ';', '<', '=', '>', '?', '@', '[', '\\', ']', '^', '\_', '`','a', 'b', 'c', 'd', 'e','f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o','p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', '{', '|', '}', '~','accept', 'add', 'alt', 'altleft', 'altright', 'apps', 'backspace', 'browserback', 'browserfavorites', 'browserforward', 'browserhome', 'browserrefresh', 'browsersearch', 'browserstop', 'capslock', 'clear', 'convert', 'ctrl', 'ctrlleft', 'ctrlright', 'decimal', 'del', 'delete', 'divide', 'down', 'end', 'enter', 'esc', 'escape', 'execute', 'f1', 'f10', 'f11', 'f12', 'f13', 'f14', 'f15', 'f16', 'f17', 'f18', 'f19', 'f2', 'f20', 'f21', 'f22', 'f23', 'f24', 'f3', 'f4', 'f5', 'f6', 'f7', 'f8', 'f9', 'final', 'fn', 'hanguel', 'hangul', 'hanja', 'help', 'home', 'insert', 'junja', 'kana', 'kanji', 'launchapp1', 'launchapp2', 'launchmail', 'launchmediaselect', 'left', 'modechange', 'multiply', 'nexttrack', 'nonconvert', 'num0', 'num1', 'num2', 'num3', 'num4', 'num5', 'num6', 'num7', 'num8', 'num9', 'numlock', 'pagedown', 'pageup', 'pause', 'pgdn', 'pgup', 'playpause', 'prevtrack', 'print', 'printscreen', 'prntscrn', 'prtsc', 'prtscr', 'return', 'right', 'scrolllock', 'select', 'separator', 'shift', 'shiftleft', 'shiftright', 'sleep', 'space', 'stop', 'subtract', 'tab', 'up', 'volumedown', 'volumemute', 'volumeup', 'win', 'winleft', 'winright', 'yen', 'command', 'option', 'optionleft', 'optionright']

