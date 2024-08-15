# oh-my-posh windows

### Guide to setup oh-my-posh with powerline in windows

1.  Install the windows terminal from [store](https://aka.ms/terminal)
2.  Download the OhMyPosh by running below command in Windows Terminal (Make sure Terminal is using Windows Powershell)
    `winget install JanDeDobbeleer.OhMyPosh -s winget`
    if failed to initiate, go to windows store and install app installer. Below picture for reference-

![Image of app installer](https://i.ibb.co/xz6hqgh/app-installer.png)

3.  [Download the DaddyTimeMono NF font](https://drive.google.com/file/d/1DqRKAuQAvFVr39A8w1CeJYuiXf3kiuDd/) or any other [Nerd font](https://www.nerdfonts.com/)
4.  Make the downloaded font in settings of terminal. Pressing `Ctrl+Shift+,` will open the settings.json file.
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

5.  Restart terminal with Admin privilege
6.  Edit the profile settings with notepad by running `notepad $PROFILE`
7.  If above command returns below error, that means profile setting file is not present. To make one, run - `New-Item -Path $PROFILE -Type File -Force`

![image](https://github.com/abirtasrif/omp-windows/assets/1532446/9dccf911-f500-4273-81e1-bc6412de9d58)

8.  Now edit the profile by `notepad $PROFILE` and save the file after putting `oh-my-posh init pwsh | Invoke-Expression` in the profile.
9.  Run `oh-my-posh init pwsh | Invoke-Expression` , the shell should be start working immediately.
10. If this returns error saying running script is disabled in this system, run `Set-ExecutionPolicy RemoteSigned`
11. Load the new profile with command `. $PROFILE`
12. Restart the terminal and enjoy !

### Extras

- To add `Open in Terminal` option in windows context menu, create a file anywhere in your computer with a .reg extension (you may create a txt.file and rename the extension to reg).

- Edit the file with notepad or any other text editor and paste and save below code, save and close.

```
Windows Registry Editor Version 5.00 [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Shell Extensions\Blocked]
"{9F156763-7844-4DC4-B2B1-901F640F5155}"=-
```

- Now right click on that file and `Run as administrator`
