# VAutoHotkey

Automation program similar to AutoHotkey, except with a C# core, and a JavaScript (NodeJS) scripting engine.

Example script:
```
AddGlobalHotkey("Control+Shift+N", {capture: true, onDown: function(data) {
	// if explorer isn't running yet, start it
	if (!GetProcess("explorer"))
        Run("C:/Windows/explorer.exe");
	// else, find its first window, then show and activate it
    else {
        var window = GetWindow({process: "explorer", class: "CabinetWClass"});
        if (window) {
            window.Show();
            window.Activate();
        }
    }
}});
```

# Installation

1) Download and install NodeJS: http://nodejs.org  
2) Download this project's folder contents. (simple way: click "Clone or download" near the page's top-right, "Download ZIP", then extract/copy-out its inner folder somewhere)  
3) Open the "VAutoHotkey" root folder, and run the "Install.bat" file.  
4) [optional] If you want to have your script run at startup/user-logon, run the "EnableRunAtStartup.bat" file.

# Usage

1) Open the UserScript.js file, and add your own hotkeys/commands. (see below for options)  
2) Open the "VAutoHotkey" root folder, and run the "Start.bat" or "StartAsAdmin.bat" file. (some commands require admin rights)  

# Scripting

TODO