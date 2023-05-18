# oh-my-posh windows
### Guide to setup oh-my-posh with powerline in windows

01. Install the windows terminal from [store](https://aka.ms/terminal)
02. Download the powershell by running below command in Windows Terminal (Make sure Terminal is using Windows Powershell)
` winget install JanDeDobbeleer.OhMyPosh -s winget `
if failed to initiate, go to windows store and install app installer. Below picture for reference-

![Image of app installer](https://i.ibb.co/xz6hqgh/app-installer.png)

03. [Download the DaddyTimeMono NF font](https://drive.google.com/file/d/1DqRKAuQAvFVr39A8w1CeJYuiXf3kiuDd/) or any other [Nerd font](https://www.nerdfonts.com/)
04. Make the downloaded font in settings of terminal. Pressing `Ctrl+Shift+,` will open the settings.json file.
add below lines into `"defaults":{}` array
```
"font": {
        "face": "DaddyTimeMono NF"
      }

```

it should be look like this-

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
07. If above command returns below error, that means profile setting file is not present. To make one, run - `New-Item -Path $PROFILE -Type File -Force`


 ![image](https://github.com/abirtasrif/omp-windows/assets/1532446/9dccf911-f500-4273-81e1-bc6412de9d58)

08. Now edit the profile by `notepad $PROFILE` and save the file after putting `oh-my-posh init pwsh | Invoke-Expression` in the profile.
09. Run `oh-my-posh init pwsh | Invoke-Expression` , the shell should be start working immediately.
10. If this returns error saying running script is disabled in this system, run `Set-ExecutionPolicy RemoteSigned`
11. Load the new profile with command `. $PROFILE`
12. Restart the terminal and enjoy !
