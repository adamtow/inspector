# Inspector Documentation

Inspector goes beyond Quick Look and Show Results, allowing shortcut developers to view and modify the contents of dictionaries, lists, text, numbers, and booleans at runtime.

Inspector is great for inspecting and changing web API responses and other complex list and dictionary objects. 

## Table of Contents
- Download and Installation 
- Usage
- Exploring the Inspector Interface
- Viewing Objects
- Modifying Objects 
- Handling Lists
- Actions
- Returning Objects
- License

<span id="" class="section-header"></span>
## Download and Installation 
The latest version of Inspector can be found at RoutineHub.co:




<span id="" class="section-header"></span> 
## Usage
Using Inspector is very easy. Simply place a Run Shortcut Action (with "_inspector" as the designated shortcut) immediately after the object you wish to inspect. 

When your shortcut runs and reaches the call to Inspector, it will launch and expand your object for viewing. 

<span id="" class="section-header"></span>
## Exploring the Inspector Interface
The Inspector interface has three sections:

1. Navigation
2. Object
3. Actions

### Navigation

- **Continue**: This returns you back to the shortcut that called Inspector. All changes you have made to the object will be preserved and returned. 
- **Back to Top**: This menu item appears when you have gone at least two levels deeper into the inspected object. Back to Top returns you to the root of the inspected object. All changes you have made to the object will be preserved. 
- **Back**: This menu item appears when you have gone one level deeper into the inspected object. Tapping Back takes you one level up the object depth chain. All changes you have made to the object will be preserved. 

### Object
This section displays the portion of the object currently being inspected. Tapping on a singular object (Text, Number, or Boolean) will display the object. Tapping on a dictionary or list will cause Inspector to drill down and inspect that object. 

### Actions

- **Revert Object to Original**: The original object will replace any changes you may have made. This operation can be undone. 
- **Copy Object to Clipboard**: copies the modified object to your iOS device’s clipboard. 
- **Share Object**: Displays a quick look on the modified object. 
- **About Inspector**: Displays the Inspector about screen, with the current version and build number. 
- **Help**: Opens the documentation you are reading now. 
- **Settings**: Displays the Inspector settings menu. See the [Settings section](#settings) for more details. 

<span id="" class="section-header"></span> 
## Viewing Objects



<span id="" class="section-header"></span> 
## Modifying Objects 
Tapping on a singular object like Text, Numbers, or Booleans will Open an editor modal allowing you to edit the contents of the object.

Were you to tap on Continue, the modified value will be sent to the calling shortcut. 

<span id="" class="section-header"></span> 
## Handling Lists
Lists are converted to dictionaries prior to being displayed in Inspector. Indices are changed to numbered keys:

```
1
2
3
…
15
16
17
…
100
101
```

To

```
001
002
003
…
015
016
017
…
100
101
```

Keys are prefixed with 0s so they can be displayed in the proper sort order. 

Tapping Back, Back to Top, or Continue will cause the  dictionary to be converted back into a list. 

<span id="" class="section-header"></span> 
## Actions

<span id="" class="section-header"></span> 
## Returning Objects

<span id="" class="section-header"></span> 
## License

<span id="" class="section-header"></span> 
## Settings

<span id="" class="section-header"></span> 