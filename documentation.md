# Inspector Documentation

Inspector is a tool for shortcut developers to inspect and modify runtime objects such as dictionaries, lists, text, numbers, and boolean values. It’s a powerful tool that goes far beyond Show Result and Quick Look.

![Go Beyond Show Result and Quick Look with Inspector](https://atow.files.wordpress.com/2019/01/ebb3a11d-43d7-4fe1-a3c0-fe4403c0a6a8.png?w=1280)

Inspector is great for viewing and changing JSON API responses and other complex list and dictionary objects. 

![Inspecting a web API request](https://atow.files.wordpress.com/2019/01/35d3c4e8-bff9-45c6-b5ef-8e699146b078.png?w=1280)

## Table of Contents
- [Downloading and Installing](#installation)
- [Using Inspector](#usage)
- [Exploring the Inspector Interface](#explore)
- [Modifying Objects](#modify)
- [Handling Lists](#lists)
- [Changing Settings](#settings)
- [Updating Inspector](#update)
- [License](#license)

<span id="installation" class="section-header"></span>
## Downloading and Installing 
The latest version of Inspector can be found at RoutineHub.co:

<a href="https://routinehub.co/shortcut/1106” class=“button button-primary">Download Inspector from RoutineHub.co</a>

<span id="usage" class="section-header"></span> 
## Using Inspector
Place a Run Shortcut Action with "_inspector" as the designated shortcut immediately after the object you wish to view. 

![Inspecting objects with Inspector](https://atow.files.wordpress.com/2019/01/6b54e455-1dde-4fa4-84da-abc24788aedb.png?w=1280)

When your shortcut runs and reaches the Run Shortcut call, Inspector will launch and expand the object for viewing and editing. You can drill down into lists and dictionaries and view/modify singular objects. Objects that can’t be edited natively are displayed using Quick Look.

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

![Continue, Back to Top, and Back](https://atow.files.wordpress.com/2019/01/f700ff4c-d00a-49d6-a141-61c5e7039a8d.png?w=1280)

### Object
This section displays the portion of the object currently being inspected. Tapping on a singular object (Text, Number, or Boolean) will display the object. Tapping on a dictionary or list will cause Inspector to drill down and inspect the selected object. 

### Actions

- **Quick Look**: Performs a Quick Look Action on the current object. 
- **Copy to Clipboard**: Copies the modified object to your iOS device’s clipboard. Depending on the [Copy Locally setting](#settings), this object may be on just your local clipboard or available to all your supported iCloud devices via Handoff. 
- **Share**: Displays the Share Sheet for the current object. 
- **Revert Object to Original**: The current object will be replaced by the original object.  Any changes you may have made will be lost. This operation can be undone. 
- **About Inspector**: Displays the Inspector About screen, where you can find the current version and build number for Inspector.
- **Help**: Opens the documentation you are reading now. 
- **Settings**: Displays the [Inspector Settings menu](#settings).

<span id="modify" class="section-header"></span> 
## Modifying Objects 
Tapping on a singular object like Text, Numbers, or Booleans will open an editor window allowing you to modify the object.

![Modifying objects with Inspector](https://atow.files.wordpress.com/2019/01/902ccfe6-1d32-48a9-9335-7d076ee9cbc0.png?w=1280)

Changes you make will be applied to the singular object. Inspector will then re-display the parent object (list or dictionary), where you’ll be able to see that your changes were made.

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

When using the Quick Look, Copy to Clipboard, and Share Actions alongside a set value for List Pagination, the entire list will be used with the action instead of the page slice you are viewing. 

<span id="returning" class="section-header"></span> 
## Returning Object
Tap **Continue** to return the modified object back to the calling shortcut. Lists that had been converted to a dictionaries will be transformed back to a list prior to being returned. 

<span id="revert" class="section-header"></span> 
## Reverting Object
You can revert back to the original object by tapping **Revert to Original Object**. Any changes you have made to the passed-in object will be removed. This operation cannot be undone.

![Reverting Back to the Original Object](https://atow.files.wordpress.com/2019/01/3c77c6b0-d26e-4a50-b232-1a792c3c13c8.png?w=1280)

<span id="settings" class="section-header"></span> 
## Changing Settings
You can adjust the following settings in Inspector:

- **Adjust List Pagination**: Set the number of list items to be displayed on each page in Inspector. 
- **Change Language**: Inspector is currently localized in English, but it’s ready for localization. If you would like to help with localizing Inspector, please <a href=“mailto:inspector+localization@tow.com”>contact me</a>.
- **Copy to Local Clipboard**: Choose whether you want objects to be copied to the global clipboard (used with Handoff) or just the local clipboard of your iOS device.

![Inspector Settings](https://atow.files.wordpress.com/2019/01/6892a1d1-c260-40c8-9782-61876ecf74c0.png?w=1280)

<span id="update" class="section-header"></span> 
## Updating Inspector
Run Inspector without any parameters from the Shortcuts app to display the welcome menu with an option to Check for Updates.

Updates are handled by UpdateKit. 

>Note: Due to the large size of Inspector, a regular call to UpdateKit will result in a blank OK screen when trying to download the update. As a result, tapping Check for Updates… will display a temporary Safari page (the window closes after 30 seconds) with a link and auto-redirect to UpdateKit. You’ll have to tap the link to Open UpdateKit in Shortcuts to proceed.

<span id="license" class="section-header"></span> 
# License
>Copyright © 2018-2019 Adam Tow • tow.com • @atow
>
>Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
>
>The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
>
>THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

