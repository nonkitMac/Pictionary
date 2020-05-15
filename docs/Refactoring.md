[Documents](Documents) > Refactoring

This page illustrates what kind of refactoring will be done for this project.

## Update Version
Update version information according to Semantic Versioning below.

## Use Init() Subroutine
Use `Init()` subroutine such as following code.
```
Sub Init
  GraphicsWindow.Title = "Pictionary"
  gw = 598
  gh = 428
  GraphicsWindow.Width = gw
  GraphicsWindow.Height = gh
  GraphicsWindow.BackgroundColor = "LightGray"
EndSub
```

## Use Array.GetItemCount()
Use `Array.GetItemCount(shape)` instead of hard coded number.

## Replace Shape_ to Sprite_ Subroutines
Replace `Shape_Add()` and `Group_Add()` to `Stripe_Add()`. 

## Use Caption Maker
[maker/CaptionMaker.sb](https://github.com/nonkitMac/Pictionary/blob/master/src/maker/CaptionMaker.sb) will create such as following code.
```
Sub Shapes_Init_Caption
  ' Shapes | Initialize shapes data
  ' return shX, shY - current position of shapes
  ' return shape - array of shapes
  shX = 426 ' x offset
  shY = 358 ' y offset
  shape = ""
  shape[1] = "func=text;x=0;y=0;text=Ellipse;fn=Trebuchet MS;fs=50;fb=True;pw=0;bc=Black;"
EndSub
```
Use this code to show the caption.

## Add New Line Between Subroutines
Add a new line between subroutines.

## Remove Not Used Subroutine
[maker/FindSubNotUsed.sb](https://github.com/nonkitMac/Pictionary/blob/master/src/maker/FindSubNotUsed.sb) will find subroutines not used.  Following list is a sample output.
```
C:\Users\nonki\Documents\GitHub\Pictionary\Ellipse.sb Math_CartesianToPolar Shapes_CalcRotatePos Shapes_Move Shapes_Remove Shapes_Rotate
```
This means that subroutines Math_CartesianToPolar, Shapes_CalcRotatePos, Shapes_Move, Shapes_Remove and Shapes_Rotate should be removed from Ellipse.sb

# See Also
- [Semantic Versioning 2.0.0](https://semver.org/)
- [Small Basic Coding Pattern](https://github.com/nonkit/SmallWikiPad/wiki/Small-Basic-Coding-Pattern)

____

Copyright © 2017-2020 Nonki Takahashi.

[![Creative Commons License](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).