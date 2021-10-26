---
title : "[python code]get Coordinate by image"
date : "2021-10-26"
tags : [CodeDictionary,CoordinateByImg,Python]
topics : [CodeDictionary]
---

## get Coordinate by image
pyautogui started left-top side of monster. If there are multiple images on screen, only return the coordinate of most left-top side image. If there is no same image, return FileNotFoundError

```python

import pyautogui

def getCoordinateByImg(imgAddress):
    imgLocatedCoordinate = pyautogui.locateOnScreen(imgAddress)  # get image from the address

    if (imgLocatedCoordinate):
        return pyautogui.center(imgLocatedCoordinate)  # return the center coordinate.
    else:
        print("image never found")
        raise FileNotFoundError
```

#### 에러
- pyscreeze.PyScreezeException: The Pillow package is required to use this function: type "pip install Pillow --upgrade" in terminal