# AssetPicker - iOS (Objective-C)

`AssetPicker` is a `UIViewController` subclass that provides an alternative solution to standard UIImagePickerController. Highlights are :-
* Have both modes within single screen (Use Library or Use Camera).
* Select Multiple Assets (Photos / Videos).
* Browse all the albums within one screen.
* Filters :- Photos(Default), Videos, All
* Supports Portrait & Landscape Modes. (No autorotation supported)
* Uses Blocks for completion & cancel (Maintains integrity of code)
* Provides original ALAsset in returned response. (Better use it's properties)
* Provides ContentsURL for both Photos & Videos. (No UIImage directly, memory issues with multiple selection)

## Requirements

* iOS 6.0 or later, ARC is must.
* QuartzCore.Framework
* AssetsLibrary.Framework

## How To Use

Configuring AssetPicker is just like this :

	[AssetPicker showAssetPickerIn:self.navigationController
                 completionHandler:^(AssetPicker* picker, NSArray* assets)
     {
         NSLog(@"Assets --> %@", assets);
         
         // Do your stuff here
         
         // All done with the resources, let's reclaim disk memory
         [AssetPicker clearLocalCopiesForAssets];
     }
                     cancelHandler:^(AssetPicker* picker)
     {
         NSLog(@"Cancelled.");
     }];

and your work is done. AssetPicker does it all for you.
* It uses AssetsLibrary to fetch Albums Info, populates it into a nice UI.
* Provides all the albums browsing within one screen.
* Provides Camera option for new photo / video capture.

## iPad Portrait
![iPadPortrait] (https://raw.githubusercontent.com/taruntyagi697/AssetPicker/master/Screenshots/iPadPortrait.png)
## iPad Landscape
![iPadLandscape] (https://raw.githubusercontent.com/taruntyagi697/AssetPicker/master/Screenshots/iPadLandscape.png)

## iPhone Portrait
![iPhonePortrait] (https://raw.githubusercontent.com/taruntyagi697/AssetPicker/master/Screenshots/iPhonePortrait.png)
## iPhone Landscape
![iPhoneLandscape] (https://raw.githubusercontent.com/taruntyagi697/AssetPicker/master/Screenshots/iPhoneLandscape.png)
    
## Demo App
    Demo app includes just the above 'How To Use' code for reference.