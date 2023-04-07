# New-PC
Installation sequence when I buy a new PC



## KeePass
https://keepass.info/download.html

### Plugins
https://keepass.info/plugins.html

Download the plugin `.plgx` and save it in the `C:\Program Files\KeePass Password Safe 2\Plugins` folder.

https://github.com/KoenZomers/KeePassOneDriveSync/releases


## Git
https://desktop.github.com/

https://git-scm.com/download/win

## Visual studio
Download Visual studio 2022 and VS Code from here
https://visualstudio.microsoft.com/downloads/

## Office
To find the installation media for Office 2019/2016 visit https://account.microsoft.com/services

Visit [setup.office.com](https://setup.office.com/) to activate a new license.

## PowerShell
[Full article](https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal)
Install the [New powershell](https://www.microsoft.com/en-us/p/powershell/9mz1snwt0n5d?SilentAuth=1&wa=wsignin1.0&WT.mc_id=-blog-scottha#activetab=pivot:overviewtab) from the marketplace.

Change the default shell to the 'PowerShell' and maybe edit the settings.json to clear up some unneeded shells

Download [CascadiaCode font](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/CascadiaCode.zip?WT.mc_id=-blog-scottha), unzip and install them.

Change the Terminal settings to use `CascadiaCode NF` font.

### Oh My Posh

Installation
```
winget install JanDeDobbeleer.OhMyPosh
# restart shell to reload PATH
```

Edit $Profile
`Test-Path $profile` : Test if the file exists
`New-Item -path $profile -type file –force` : Create if not exists

The profile script will now be created. It will be in the location following the “Directory:” output. When we browse to that location, the profile script will be there waiting for us to modify. Open the file named “Microsoft.Powershell_profile.ps1”

Edit the file and add this `oh-my-posh --init --shell pwsh --config ~/Documents/PowerShell/ohmyposhv3-v2.json | Invoke-Expression`
Download [Oh my posh json](https://gist.githubusercontent.com/shanselman/1f69b28bfcc4f7716e49eb5bb34d7b2c/raw/8e9c9a8736ff4e9e5a863c20833d614549ccbc32/ohmyposhv3-v2.json) and save it at the Documents/Powershell folder

Reload Profile `. $PROFILE`

### Colors and Icons in directories
`Install-Module -Name Terminal-Icons -Repository PSGallery`

and add the following at the $profile (`code $profile`)

`Import-Module -Name Terminal-Icons`

### PSReadLine
https://github.com/PowerShell/PSReadLine
