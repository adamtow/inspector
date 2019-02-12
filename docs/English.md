# Inspector

Inspector is a utility for shortcut developers to inspect and modify runtime objects such as dictionaries, lists, text, numbers, and boolean values. It is a powerful tool that goes far beyond the Show Result and Quick Look actions. Inspector is great for viewing and changing JSON API responses and other complex list and dictionary objects. 

![Go Beyond Show Result and Quick Look with Inspector](https://atow.files.wordpress.com/2019/01/ebb3a11d-43d7-4fe1-a3c0-fe4403c0a6a8.png?w=1280)

![Inspecting a web API request](https://atow.files.wordpress.com/2019/01/35d3c4e8-bff9-45c6-b5ef-8e699146b078.png?w=1280)

## Table of Contents
- [Downloading and Installing](#installation)
- [Using Inspector](#usage)
- [Exploring the Inspector Interface](#explore)
- [Modifying Objects](#modify)
- [Handling Lists](#lists)
- [Returning Objects](#return)
- [Reverting Objects](#revert)
- [Changing Settings](#settings)
- [Updating Inspector](#update)
- [Localization](#localization)
- [License](#license)

***

<span id="installation" class="section-header"></span>
## Downloading and Installing 
The latest version of Inspector can be found at RoutineHub.co:

<a href="https://routinehub.co/shortcut/1106” class=“button button-primary">Download Inspector from RoutineHub.co</a>

***

<span id="usage" class="section-header"></span> 
## Using Inspector
Place a Run Shortcut Action with "_inspector" as the shortcut immediately after the object you wish to view. 

![Inspecting objects with Inspector](https://atow.files.wordpress.com/2019/01/90bc44ca-343a-4d33-b842-f3dd035edf16.png?w=1280)

When your shortcut runs and reaches the Run Shortcut call, Inspector will launch and expand the object for viewing and editing. You can drill down into lists and dictionaries and view/modify singular objects. Objects that can’t be edited natively are displayed using Quick Look.

***

<span id="explore" class="section-header"></span>
## Exploring the Inspector Interface
The Inspector interface has three sections:

1. Navigation
2. Object
3. Actions

### Navigation

- **Path**: The text atop the menu will display the path to the current object being inspected.
- **Continue**: This returns the modified object back to the shortcut that called Inspector.
- **Back to Top**: This menu item appears when you are at least two levels away from the root of the inspected object. Back to Top returns you to the root. All changes you have made to the object will be preserved. 
- **Back**: This menu item appears when you are at least one level away from the root of the inspected object. Tapping Back takes you one level up the object depth chain. All changes you have made at the current depth will be preserved. 

![Continue, Back to Top, and Back](https://atow.files.wordpress.com/2019/01/84655503-fea8-43cb-9fbd-6bddb4486c09.png?w=1280)

### Object
This section displays the portion of the object currently being inspected. Tapping on a singular object (Text, Number, or Boolean) will display the object. Tapping on a dictionary or list will cause Inspector to drill down and inspect the selected object. 

### Actions

- **Quick Look**: Performs a Quick Look Action on the current object. 
- **Copy to Clipboard**: Copies the modified object to your iOS device’s clipboard. Depending on the [Copy Locally setting](#settings), this object may be placed on your local clipboard or made available to all your supported iCloud devices via Handoff.
- **Share**: Opens the iOS Share sheet for the current object. 
- **Revert to Original Object**: The current object will be replaced by the original object.  Any changes you may have made will be lost. This operation can be undone. 
- **About Inspector**: Displays the Inspector About screen, where you can find the current version and build number for Inspector.
- **Help**: Opens the documentation you are reading now. 
- **Settings**: Displays the [Inspector Settings menu](#settings).

***

<span id="modify" class="section-header"></span> 
## Modifying Objects 
Tapping on a singular object like Text, Numbers, or Booleans will open an editor window allowing you to modify the object.

![Modifying objects with Inspector](https://atow.files.wordpress.com/2019/01/7161a3bd-4174-43c9-ab76-e8968fb56575.png?w=1280)

Changes you make will be applied to the singular object. Inspector will then re-display the parent object (list or dictionary), where you will be able to see that your changes were made.

***

<span id="lists" class="section-header"></span> 
## Handling Lists
Lists are first converted to dictionaries prior to being displayed in Inspector. Indices are changed to zero-prefixed numbered keys for sorting purposes:

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

to

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

Tapping **Back**, **Back to Top**, or **Continue** will cause the converted list dictionary to be transformed back into a list.

![List Pagination in Inspector](https://atow.files.wordpress.com/2019/01/ebc96a8a-edf6-4552-8a7e-e73654c3d02c.png)

When a List Pagination value in [Settings](#settings) has been set, the list will be broken up into pages. Additional menu items for navigating through the list will appear:

- **Previous Page**: Goes back to the previous page of items in the list.
- **Jump to Page**: Jumps to a numbered list page.
- **Next Page**: Goes to the next page of items in the list.

>Note: Converting a list to a dictionary may take some time for large lists.

The entire list will be used with the Quick Look, Copy to Clipboard, Share, and Revert to Original Object actions.

***

<span id="return" class="section-header"></span> 
## Returning Objects
Tap **Continue** to return the modified object back to the calling shortcut. Lists that had been converted to a dictionaries will be transformed back to a list prior to being returned. 

***

<span id="revert" class="section-header"></span> 
## Reverting Objects
You can revert back to the original object at any depth level by tapping **Revert to Original Object**. Any changes you have made to the current object will be removed. This operation cannot be undone.

![Reverting Back to the Original Object](https://atow.files.wordpress.com/2019/01/8be50ec2-8bcb-41a7-b892-bd8e057c2708.png?w=1280)

>Tip: If you want to revert back to the object as it was originally passed into Inspector, return to the root level by tapping either **Back to Top** or **Back** multiple times until only the **Continue** navigation menu item remains. Then, tap **Revert to Original Object**.

***

<span id="settings" class="section-header"></span> 
## Changing Settings
You can adjust the following settings in Inspector:

![Inspector Settings](https://atow.files.wordpress.com/2019/01/04c217b4-d484-4ddf-8782-0ae80ebc942a.png?w=1280)

- **Adjust List Pagination**: Set the number of list items to be displayed on each page in Inspector. 
- **Change Language**: Inspector is currently localized in English, but it’s ready for localization. If you would like to help with localizing Inspector, please <a href=“mailto:inspector+localization@tow.com”>contact me</a>.
- **Copy to Local Clipboard**: Choose whether you want objects to be copied to the global clipboard (used with Handoff) or just the local clipboard of your iOS device.
- **Show Debug Menu**: When enabled, additional menu items will appear in the Inspector main window for viewing the Object Key Stack, Current Object, and the Current Object Stack.

![Inspector Debug Menu](https://atow.files.wordpress.com/2019/01/2735a491-483b-430d-99dd-514dc829319f.png?w=1280)

***

<span id="update" class="section-header"></span> 
## Updating Inspector
Run Inspector without any parameters from the Shortcuts app to display the welcome menu with an option to Check for Updates.

Updates are handled by [UpdateKit](http://mikebeas.com/updatekit/). 

>Note: Due to the large size of Inspector, a regular call to UpdateKit will result in a blank OK screen when trying to download the update. As a result, tapping **Check for Updates**… will display a temporary Safari page (the window closes after 30 seconds) with a link to run the UpdateKit shortcut. You’ll have to tap **Open this page in “Shortcuts”?** or **Check for Inspector Updates** to proceed.

![Checking for Updates](https://atow.files.wordpress.com/2019/01/6848e2d9-8e38-4e89-9454-90ea3fa75a54.png?w-1280)

<span id="localization"></span>
## Localization
Inspector is available in English, but the application is fully ready to be localized. I have developed an application, Localization Helper, that will assist you in localizing Inspector into your language.

> [**Download Localization Helper from RoutineHub &raquo;**](https://routinehub.co/shortcut/1931)

When the localization file is complete, either submit a pull request on [my GitHub page](https://github.com/adamtow/) or [contact me](mailto:inspector+localization@tow.com).


***

<span id="license" class="section-header"></span> 
# License
>Copyright © 2018-2019 Adam Tow • tow.com • @atow
>
>Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
>
>The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
>
>THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.