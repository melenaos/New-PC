# New-PC
Installation sequence when I buy a new PC


## Applications to install
- [Visual studio](https://visualstudio.microsoft.com/downloads/). Both VSCode and Visual Studio 2022
- [Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer)
- [Azure Storage Emulator](https://learn.microsoft.com/en-us/azure/storage/common/storage-use-emulator). Must migrate to Azurite!
- [KeePass](https://keepass.info/download.html)
  - [All plugins](https://keepass.info/plugins.html). Download the plugin `.plgx` and save it in the `C:\Program Files\KeePass Password Safe 2\Plugins` folder.
  - [OneDrive synch](https://github.com/KoenZomers/KeePassOneDriveSync/releases)
- [Obsidian](https://obsidian.md/download)
- [Discord](https://discord.com/)
- [Github Desktop](https://desktop.github.com/)
- [Git cli](https://git-scm.com/download/win). It is needed for VSCode git integration
- [Sql Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads), download the `Developer` version.
- [Sql Server Management Studio](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16)
  - [SSMS Direct link](https://aka.ms/ssmsfullsetup)  
- [node](https://nodejs.org/en/download). Add Additional building tools (including Chocolate)
- [nvm-windows](https://github.com/coreybutler/nvm-windows/releases)
  - `nvm install 16.17` 



## Office
To find the installation media for Office 2019/2016 visit https://account.microsoft.com/services

Visit [setup.office.com](https://setup.office.com/) to activate a new license.

## MyShortcut
By default all downloaded from internet scripts (or every script) doens't run without permittion. Unblock this restriction.

`Set-ExecutionPolicy Unrestricted -scope CurrentUser`

And then for every script, including MyShortcut run

`Unblock-File ...`

## PowerShell
[Full article](https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal)

Install the [New powershell](https://www.microsoft.com/en-us/p/powershell/9mz1snwt0n5d?SilentAuth=1&wa=wsignin1.0&WT.mc_id=-blog-scottha#activetab=pivot:overviewtab) from the marketplace.

Change the default shell to the 'PowerShell' and maybe edit the settings.json to clear up some unneeded shells

Download [CascadiaCode font](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/CascadiaCode.zip?WT.mc_id=-blog-scottha), unzip and install them.

Change the Terminal settings to use `CascadiaCode NF` font.

### Add an alias to edit the `profile`
Type `Notepad $Profile` to edit the profile

Add the following at the profile file and save
```
function Edit-ProfileFile{
   Notepad $profile
}
Set-Alias ep Edit-ProfileFile
```
Next time you load the PowerShell you will be able to edit the profile file with the command `ep`

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

and add the following at the $profile (`notepad $profile` or just `ep`)

`Import-Module -Name Terminal-Icons`

### PSReadLine
https://github.com/PowerShell/PSReadLine

#### installation
```
Install-Module -Name PowerShellGet -Force
Exit
```
and then `Install-Module PSReadLine -AllowPrerelease -Force`

The profile file should look like: 
https://github.com/melenaos/New-PC/blob/main/Microsoft.PowerShell_profile.ps1

