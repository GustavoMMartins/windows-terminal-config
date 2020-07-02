# New Windows terminal settings :star:

Repository for the new [Windows terminal](https://github.com/microsoft/terminal) settings.

- Configure Git Bash on the [Windows terminal](https://github.com/microsoft/terminal).
- Themes 
- Adding the windows terminal shortcut with the right mouse button.

## Configuring Git Bash

![](https://github.com/GustavoMMartins/windows-terminal-config/blob/master/images/git_bash.jpg)

Just put the code in Json below :point_down:

```
{
    "guid" : "{00000000-0000-0000-0000-000000012345}",
    "closeOnExit" : true,
    "colorScheme" : "Campbell",
    "commandline" : "\"%PROGRAMFILES%\\git\\bin\\bash.exe\" --login -i -l",
    "cursorColor" : "#FFFFFF",
    "cursorShape" : "bar",
    "fontFace" : "Consolas",  
    "historySize" : 9001,
    "icon" : "%PROGRAMFILES%\\git\\mingw64\\share\\git\\git-for-windows.ico",
    "name" : "Git Bash",
    "snapOnInput" : true
},
```

Some of these settings are to stay with the default configuration and coloring of Git Bash inside the [Windows terminal](https://github.com/microsoft/terminal).

* Note: If you want to modify your main terminal just place the git bash guid in "defaultProfile" :exclamation:

## Themes

![](https://github.com/GustavoMMartins/windows-terminal-config/blob/master/images/retro_color.jpg)

The theme used by default will always be that of the power shell. These settings use the terminal's retro theme.

```
"schemes": [
    {
        "name": "Retro",
        "background": "#000000",
        "black": "#00ff00",
        "blue": "#00ff00",
        "brightBlack": "#00ff00",
        "brightBlue": "#00ff00",
        "brightCyan": "#00ff00",
        "brightGreen": "#00ff00",
        "brightPurple": "#00ff00",
        "brightRed": "#00ff00",
        "brightWhite": "#00ff00",
        "brightYellow": "#00ff00",
        "cyan": "#00ff00",
        "foreground": "#00ff00",
        "green": "#00ff00",
        "purple": "#00ff00",
        "red": "#00ff00",
        "white": "#00ff00",
        "yellow": "#00ff00"
    }
],
```

## Adding the [Windows terminal](https://github.com/microsoft/terminal) shortcut with the right mouse button.

1. The step by step to add the [Windows terminal](https://github.com/microsoft/terminal) with the right mouse button starts by placing the following code below: point_down: inside the configs profiles :point_down:

```
"startingDirectory": "."
```

2. Now just create a file with the name "wt.reg" edit it and add the following code: point_down:

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\wt]
 @="Open Windows Terminal here"

[HKEY_CLASSES_ROOT\Directory\Background\shell\wt\command]
 @="C:\\Users\\<User>\\AppData\\Local\\Microsoft\\WindowsApps\\wt.exe"
```

Note: Change the User variable to your Windows user name.


3. Just save the edit and then merge the file.


### :collision: Optional

1. Get the [Windows terminal](https://github.com/microsoft/terminal) icon.

2. Create a folder inside your "AppData / Local" folder with the name WTerminal (just type %USERPROFILE%/AppData/Local/ within Win + R) and place the icon inside it.

3. Inside the windows registry editor go to "HKEY_CLASSES_ROOT\Directory\Background\shell\wt" create a new String with the value name of "Icon" and the value data of "%USERPROFILE%/AppData/Local/WTerminal/terminal.ico" and save the record.
