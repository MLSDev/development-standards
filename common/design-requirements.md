# Design Requirements

This document describes main requirements for graphic assets that need to be provided to developers for implementation into the application.

1. [General Requiements](#general-requirements)
1. [iOS](#ios)
1. [Android](#android)
 

## General Requirements

All the general artworks need to be provided in __\*.ai__, __\*.eps__ or __\*.psd__ files. 

All the layers should be grouped in accordance with screens.

All the titles should be written in English and express their meaning. For instance, main screen should be named _"main screen"_, not _"11111"_.

 
## iOS

In case the application supports both landscape and portrait orientations, images need to be provided in all orientations. Design for landscape mode on iPhone can differ drastically from portrait, so it should be provided separately.

UI controls (buttons, text fields, charts, ext.) need to be provided _without_ text drawn. At the same time font type and size need to be indicated in a project _Design Guidelines_ so that developer could be able to implement that font into UI.

Any text that will be shown in the app needs to be described separately. The following should be stated:
* Font type (deliver this particular font in digital form, preferably in __\*.ttf__ format). _Keep in mind that not all the fonts are localized into different languages_
* Color value in RGB, font size, font style (bold, italic, underlined etc)


### Icons

Sizes of icons can be found here: 

https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/IconMatrix.html

Height and width of any image should be multiple of screen resolution:
* 2x for Retina devices;
* 3x for Retina HD devices (e.g. iPhone 6 Plus).


### UI Controls

UI controls should be provided in either:
*  @1x.pdf (__vector format is mandatory__, e.g. Adobe Illustrator);

or 

* @2x.png, @3x.png (Adobe Photoshop) with alpha channel (without background), __without margins__.


### Background Images

For background images we support these resolutions: 
* 640x960 - iPhone 4s
* 640x1136 - iPhone 5, 5s
* 750x1134 - iPhone 6
* 1242x2208 - iPhone 6 Plus
* 1536x2048 - iPad


## Android

Design needs to be provided in these sizes _(1dp = 1px for mdpi (160 dpi))_:
* ldpi (0.75x)
* mdpi (1.0x)
* hdpi (1.5x)
* xhdpi (2x)
* xxhdpi (3x)

For example, if you use an image of 100x100 resolution for 320x480 (_mdpi_) display, then to make sure this image is displayed properly on the _ldpi_, image’s resolution should be changed to 75x75 (0.75 x 100). The same resizing needs to be done for _hdpi_, _xhdpi_ and _xxhdpi_ screens.
 
For __gradients__ that should be used in design elements, RGB codes of colors used for gradients need to be provided. This allows generating simple backgrounds in software instead of using heavy graphic files.  


### UI Controls

UI controls need to be provided in [9-patch](http://developer.android.com/tools/help/draw9patch.html) __png__ format with alpha channel, __without margins__.

For every button there should be graphics for all its states (pressed, normal, disabled, selected etc).


### Icons
 
App icons that shown in menu should be delivered in these sizes: 
* 36х36px
* 48х48px
* 72х72px
* 96х96px 

App icon that will be shown in Google Play should be of 512х512 size.
