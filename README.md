# oh-my-posh windows
### Guide to setup oh-my-posh with powerline in windows

01. Install the windows terminal from [store](https://aka.ms/terminal)
02. Download the powershell by running below command in Windows Terminal (Make sure Terminal is using Windows Powershell)
` winget install JanDeDobbeleer.OhMyPosh -s winget `
03. [Download the DaddyTimeMono NF font](https://drive.google.com/file/d/1DqRKAuQAvFVr39A8w1CeJYuiXf3kiuDd/) or any other [Nerd font](https://www.nerdfonts.com/)
04. Make the downloaded font in settings of terminal. Pressing `Ctrl+Shift+,` will open the settings.json file.

```
...
"profiles": {
    "defaults": {
      "font": {
        "face": "DaddyTimeMono NF"
      }
    },
    "list": [
      {
        "commandline": "%SystemRoot%\\System32\\WindowsPowerShell\\v1.0\\powershell.exe",
        ....
```
05. Restart terminal with Admin privilege
06. Edit the profile settings with notepad by running `notepad $PROFILE`
07. If above command returns error, that means profile setting file is not present. To make one, run - `New-Item -Path $PROFILE -Type File -Force`
08. Run `oh-my-posh init pwsh | Invoke-Expression` .If this returns error saying running script is dsiabled in this system, run `Set-ExecutionPolicy RemoteSigned`
09. Load the new profile with command `. $PROFILE`
10. Restart the terminal and enjoy !
