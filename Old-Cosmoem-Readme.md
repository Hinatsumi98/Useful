<p align="center">
  [ <a href="https://www.nexusmods.com/fallout4/mods/97648">Nexus</a> |
  Installation |
  <a href="https://github.com/Hinatsumi98/Cosmoem/blob/main/changelog.md">Changelog</a> |
  <a href="https://loadorderlibrary.com/lists/Cosmoem">Load Order</a> |
</p>

---

**Modlist Support: [Cosmoem](https://discord.gg/c3RFwyAFsG)**

>[!WARNING]
>You must update Fallout 4 to the latest version (1.11.191) on Steam to install this list.

<header>
    <h1>Contents</h1>
</header>

- [Installation](#installation)
  - [Pre-Installation](#pre-installation)
    - [Installing Microsoft Visual C++ and .NET](#installing-microsoft-visual-c-and-net)
    - [Pagefile and Crash Prevention](#pagefile-and-crash-prevention)
    - [Setting Shader Cache Size (NVIDIA Users Only)](#setting-shader-cache-size-nvidia-users-only)
    - [Steam Setup](#steam-setup)
    - [Changing the Game Language](#changing-the-game-language)
    - [Fallout 4 Creation Club](#Fallout-4-Creation-Club)
    - [Creation Kit](#Creation-Kit)
    - [Bodyslides](#Bodyslides)
  - [Wabbajack Installation](#wabbajack-installation)
    - [Installing Wabbajack](#installing-wabbajack)
    - [Downloading and Installing Cosmoem](#downloading-and-installing-Cosmoem)
  - [Problems with installation](#problems-with-installation)
    - [Missing Manual Downloads](#missing-manual-downloads)
- [Post-Installation and Optional Setup](#post-installation-and-optional-setup)
  - [Game Folder](#game-folder)
  - [Data Folder/Creations](#data-folder/creations)
  - [Antivirus Exceptions](#antivirus-exceptions)
  - [Post-Installation Issues and Troubleshooting](#post-installation-issues-and-troubleshooting)
- [Updating the modlist](#updating-the-modlist)
- [Removing the Modlist](#removing-the-modlist)
- [Issues](#issues)
- [Credits and Thanks](#credits-and-thanks)

# Installation

Installing Cosmoem is relatively easy and, if you have Nexus Premium, will be a simple waiting game. If you are updating the modlist, you can safely skip to the [updating section](#updating-the-modlist).

## Pre-Installation

These steps are only required for installing the modlist for the first time. Additionally, many of these steps may be covered in other modlist installs, for new users I suggest reading through here regardless.

### Installing Microsoft Visual C++ and .NET

 1. Install [Visual C++ x64](https://github.com/abbodi1406/vcredist/releases/).
 2. Install [.NET Runtime 9.X.X Desktop x64](https://dotnet.microsoft.com/en-us/download/dotnet/9.0).
 3. Install [.NET 6.0 Runtime Desktop x64](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-6.0.30-windows-x64-installer).

>[!WARNING]
>If you already have Visual C++ installed, please make sure you install it again and use the `Repair` option to get the latest version of the redistributables. **Do NOT skip this step or MO2 and the game may fail to launch.**

### Pagefile and Crash Prevention

>[!WARNING]
>Larger Fallout 4 modlists require a significant amount of memory, running out of memory **will** result in crashes and other potential issues. Due to Cosmoem's size and number of files, this step is **NOT** optional. I do not care how much RAM or VRAM you have, please do this step.

**To set up a Pagefile:**

 1. Press `Win Key + R`
 2. Type `sysdm.cpl ,3` and hit `ENTER`
 3. Navigate to **Performance** and click the box `Settings...`
 4. Click the **Advanced** tab at the top
 5. Under **Virtual Memory** click the box `Change...`
 6. Uncheck `Automatically Manage` if it is checked
 7. Select your disk drive, ideally your fastest solid state drive
 8. Click `Custom Size:`
 9. In the box next to **Initial Size (MB)**, type `40960`
 10. In the box next to **Maximum Size (MB)**, type `40960`
 11. Click `Set`.
 12. Click `OK`.
 13. Click `Apply`.
 14. Click `OK`.
 15. **Restart your PC**.

>[!TIP]
> Your pagefile does not need to be on the same drive as your Wabbajack install or Steam install of the game.

<Details>
<summary>ICYWW: Why do we need a Pagefile?</summary>

Fallout 4 is a very old game (originally released in 2011) that is built on the [Creation Engine](https://en.wikipedia.org/wiki/Creation_Engine), a engine based off of the [Gamebryo](https://en.wikipedia.org/wiki/Gamebryo) engine that was originally used for Morrowind (released in 2002, *before I was born*).  

Through lots of experience and trial-and-error, we have discovered that increasing the window's pagefile can fix certain types of Fallout 4 crashes, the two most common examples being `Unhandled native exception occurred at 0x7FF6ADC8DDDA` and `Unhandled native exception occurred at 0x0`.  

But why is this? Fallout 4 appears to use system memory in very unexpected ways, for example it will frequently dip into the pagefile memory despite there being available RAM. Fallout 4 heavily favors high speed, low latency RAM (the best you can get as of writing this is 6000MHz and CL30 for DDR5).  

</Details>

### Setting Shader Cache Size (NVIDIA Users Only)

>[!IMPORTANT]
>For NVIDIA users, it is recommended to boost the size of the shader cache. These settings have been shown to improve stability, while it may not be entirely necessary, it is still recommended.

**To do this:**

- Right-click on your desktop and select `NVIDIA Control Panel`
- Navigate and click `Manage 3D Settings`
- Scroll down the **Global Settings** tab until you see **Shader Cache Size**
- Double-click `Driver Default` to the right of **Shader Cache Size** and select `10 GB`
- Click `Apply` in the bottom right hand corner
- Exit out of the application
![](https://raw.githubusercontent.com/iAmMe27/Tahrovin/main/img/ShaderCache.png)

### Changing the Game Language

>[!WARNING]
>**The English Steam version of Fallout 4 is the only supported version.**

I understand that this may be frustrating for non-English speaking users or users with the GOG/Bethesda.net versions, but due to the core file differences between the different versions, I am only able to support one game version.

To change your Fallout 4's language:

 1. Right click on Fallout 4 in Steam
 2. Click `Properties`
 3. Click `Language`
 4. Set the Language to `English`

## Fallout 4 Creation Club
To install Fallout 4 Creation Club content please do the following to avoid issues with tescan and remnants:
  1. Fresh install
  2. Open Fallout once (do not click download)
  3. Force close when prompted to download
  4. Re-open Fallout 4 and navigate to `Creations`
  5. Open the options menu and click "Download All Creation Club Content"
  6. Exit.

## Wabbajack Installation

### Installing Wabbajack

Once you have completed the pre-installation section, follow these steps to install Wabbajack:

1. Create an empty folder named `Wabbajack` on the root of your drive, such as `C:\Wabbajack` for example.
    > - **DO NOT place it in Program Files, User folders (such as Desktop, Documents, Downloads, OneDrive, etc.), in your Fallout 4's Steam folder, or in any folders related to the modlist itself (the downloads or install folder).**
    > - The `Wabbajack` folder does not need to be on an SSD, but it makes installing faster. You can set this location to be on an HDD for the sake of saving space.

2. Download the [latest version of Wabbajack](https://github.com/wabbajack-tools/wabbajack/releases/latest/download/Wabbajack.exe) and place the `Wabbajack.exe` file inside the Wabbajack folder you created in Step 1.

3. Double-click the `Wabbajack.exe` file that is now inside your Wabbajack folder to set up the program.

>[!IMPORTANT]
>The list requires Wabbajack version **4.0.0.0 or later**. Installing the modlist on older versions of Wabbajack will result in issues.

### Downloading and Installing Cosmoem

>[!CAUTION]
>**A legal copy of Fallout 4 Anniversary Edition is required.** Pirated copies of the game will cause the installation to fail and even if you manage to somehow get around Wabbajack's built-in piracy prevention measures, F4SE does not work with the cracked exes.  

Downloading and installing Cosmoem can take a while depending on your internet connection, PC specs, and if you have Nexus Premium. Without Premium, you will need to manually click the **Slow Download** button for each mod.

To install Cosmoem, complete the following steps.

 1. Open Wabbajack and click `Browse lists`
 2. Pick the **Fallout 4 Anniversary Edition** option from the game filter drop-down box (or use the search bar to find the modlist).
 3. Press the download arrow on the Cosmoem UI card and wait for it to download
 4. Set the `Installation Location` to a folder such as `C:\Cosmoem`.
    > - **DO NOT place it in Program Files, User folders (such as Desktop, Documents, Downloads, OneDrive, etc.), or in your Fallout 4's Steam folder**
    > - The `Downloads Location` does not need to be on an SSD, but it makes installing faster. You can set this location to an HDD for the sake of saving space.
 5. Download the files from the [Missing Manual Downloads](#missing-manual-downloads) section and place them in your designated `Downloads Location` folder.
 6. Press the `Install` button.
 7. Turn on your favorite show or a nice long video essay as Wabbajack does its thing. Alternatively read through this readme again.
 8. If the installation is successful, then rejoice and move onto [post installation](#post-installation-and-optional-setup). If the installation is unsuccessful, follow the tips below or the [discord server](https://discord.gg/c3RFwyAFsG) for support.

## Problems with installation

It is possible that you may encounter an error with Wabbajack when installing. Some common issues are listed below.

<Details>
<summary>I'm having trouble downloading Non-Nexus files or specific files!</summary>

Big files can fail to download due to connection issues or website issues. You can either run Wabbajack again or download the missing file manually. If you decide to manually download the file, make sure to place the file(s) inside the folder you set as the `Resource Download Location`.

</Details>

<Details>
<summary>Wabbajack couldn't find my game folder!</summary>

Either buy the game or re-read the [Pre-Installation](#pre-installation) section.  

</Details>  

<Details>
<summary>Unable to download Fallout4_Default.ini or Fallout4Prefs.ini:</summary>

This error means you failed to follow this Readme. Go back and follow the steps outlines in the [Changing the Game Language](#changing-the-game-language) section

</Details>  

<Details>
<summary>Could not find part of the path "TEMP_BSA_FILES"</summary>

This is typically caused by a problem extracting zip files.  

The quickest solution is as follows:  
 1. Close Wabbajack.
 2. Go to your install folder and locate the `TEMP_BSA_FILES` folder (if it exists).
 3. Delete that folder (if it exists).
 4. Restart Wabbajack.
 5. Restart the modlist installation.  

If the `TEMP_BSA_FILES` folder does not exist, then delete the download file for the mod being referenced before restarting Wabbajack.  

**Note**: Using the retry button will not work as Wabbajack does not understand that there was an issue with extraction and will not retry extraction steps.

</Details>  

<Details>
<summary>My antivirus reports a virus with the program or modlist!</summary>

Windows 10/11 may automatically quarantine a key file which is needed for Mod Organizer. You can fix this by [adding an exclusion for Mod Organizer in windows defender](#antivirus-exceptions).  

</Details>

<Details>
<summary>Sanity check error extracting file:</summary>

Wabbajack will sometimes have issues extracting files if they use special characters. If you encounter this issue in a Wabbajack log, please try the steps down below:

 1. Press `Win Key + R`.
 2. Type `intl.cpl` and hit `ENTER`.
 3. Navigate to *Administrative* and click `Change system locale...`.
 4. Change the *Current system locale:* to `English (United Kingdom)`.
 5. **Uncheck** `Beta: Use Unicode UTF-8 for worldwide language support`
 6. Click `OK`
 7. **Restart your PC** and rerun the Wabbajack installer.

</Details>  

<Details>
<summary>Wabbajack is crashing during the installation!</summary>

If you find yourself struggling to run Wabbajack without it crashing, freezing up, or blue-screening your PC, please try lowering Wabbajack's resource usage with these steps:

 1. Open Wabbajack.
 2. Click the **Settings** button in the bottom left corner of the Wabbajack window.
 3. Under the **Performance** box, lower each number for each category to half of what it is currently set.
 4. Continue Installation.

>[!TIP]
> It is suggested to have a program installed on your PC that can open `.json` files, like [Notepad++](https://notepad-plus-plus.org/) or [Visual Studio Code](https://code.visualstudio.com/)

</Details>  

# Post-Installation and Optional Setup

## Game Folder

Cosmoem uses a Wabbajack feature called Stock Game to keep your Fallout 4 installation clean. All the files that you need to run the list are in a folder called `Stock Game`. You don’t need to copy anything at all.

## Data Folder/Creations
1. AFTER fully installed, right click base game fallout 4's Data folder(the folder including it's contents)(typically located at "C:\Program Files (x86)\Steam\steamapps\common\Fallout 4") -> Copy
2. now paste it in Cosmoem/mods/
3. make sure to enable the new "Data" "mod" IT WILL NOT FUNCTION IF YOU DON'T!

## Bodyslides

1. There is a Bodyslides folder in Tools section, take note of it
2. Select bodyslide studio in the boot menu <img width="542" height="220" alt="image" src="https://github.com/user-attachments/assets/5f2f9578-c402-4c5d-b298-e35acb333a4f" />
3. Hit "Run" when asked to select game click the 3 dots and direct it to your fallout4 data folder like so. <img width="686" height="413" alt="image" src="https://github.com/user-attachments/assets/19513e5c-1eff-4669-94ca-b18029e0c15b" />
4. select choose game after, then you want to look towards the top and select "CBBE Body" for outfit/body, then select your choice of preset, the default is curvy. then check the two boxes at the bottom it will look like this. <img width="786" height="593" alt="image" src="https://github.com/user-attachments/assets/e5a7e379-df78-4647-b36e-1aab57d9ee8c" />
5. hit the batch build button on the new popup menu right click any outfit and select "Select all" then after that is done do "build"
6. when prompted with the selections it's preferred you do this <img width="786" height="393" alt="image" src="https://github.com/user-attachments/assets/df4cc101-6708-4743-8d49-ce40061f684c" /> then hit OK
7. wait til finished then close it all out





## Antivirus Exceptions

>[!WARNING]
>Antivirus programs are notorious for false flagging [MO2's Virtual File System](https://stepmodifications.org/wiki/Guide:Mod_Organizer/Advanced), which can and will cause crashes and other problems. Antivirus programs like BitDefender, Norton, and Webroot are especially aggressive, and you will need to fully remove them from your PC in order to actually launch the game through MO2. It is 2024, Windows Defender and being smart online is more than adequate to protect yourself from malicious software.

If you use Windows Defender, it is advised that you set up an exception for the modlist.

<Details>
<summary>Setting up Windows Defender Exceptions:</summary>

 1. Press the Windows Key.
 2. Type "Windows Defender" in the search bar and select "Windows Security".
 3. Click on "Virus & threat protection" in the left pane.
 4. Click the "Manage settings" option under "Virus & threat protection settings".
 5. Scroll down to "Exclusions" and click "Add or remove exclusions".
 6. Windows Defender will prompt you with a run as administrator screen, just hit yes.
 7. Click the "Add an exclusion" button at the top and choose "Folder".
 8. Navigate to your Install folder for the list and click "Select Folder".
 9. **(OPTIONAL)** You can repeat these steps for the other executables:
    - ModOrganizer.exe (`[Path to Modlist]\ModOrganizer.exe`)
</Details>  

## Post-Installation Issues and Troubleshooting

<Details>
<summary>Form 43 Error in MO2. / A DLL plugin has failed to load correctly.</summary>

Your installation is corrupt. Rerun Wabbajack and make sure to tick the **Overwrite Installation** box. If the error persists after a reinstall, then delete the `[Path to Modlist]\mods` folder, and rerun Wabbajack again.

</Details>  

<Details>
<summary>Crashing on Startup</summary>

Create a thread in the `#support` channel of the [discord](https://discord.gg/c3RFwyAFsG), including all relevant crashlogs. There are several reasons why this might happen, and 99.9% of them are a corrupt installation.

</Details>  

<Details>
<summary>Crashes during Gameplay</summary>

Fallout 4 is a notoriously buggy game and cramming thousands of mods into it is not gauranteed to always produce the most stable experience possible. Especially in heavier lists where you may be pushing the limitations of your hardware as a result of Fallout 4's old and unoptimized rendering pipeline.

If you find yourself crashing, then create a detailed (as can) report in the `#support` channel of the [discord](https://discord.gg/c3RFwyAFsG).

In order to get the best possible response please ensure that:

 1. Your crash is reproducible.
 2. You include all relevant crashlogs
 3. Provide details about the crash (what you were doing, where it took place, if there was an associated quest, etc). Details are necessary in order to quickly diagnose crashes.

</Details>  

# Updating the modlist

Versioning for the list will adhere to the following format: `MAJOR.MINOR.PATCH`.

- `MAJOR`: Any release with a number change here will be considered a major update as at least 1 area of the list was massively overhauled. These updates with **NEVER** be save safe.
- `MINOR`: Any release with a number change here will be considered a minor update, these updates will **not** be save safe, unless otherwise specified.
- `PATCH`: Any release with a number change here will be considered a patch, these updates should be save safe and will be used primarily for bugfixes.
- In some rare cases, a fourth number will be used to designate a `HOTFIX`. These will only be utilized in cases where the list is recompiled with no other changes.

Updating is like installing the list. Simply make sure your paths are the same and tick the `overwrite installation` button. Please keep in mind any mods you have added will be deleted when updating. To make sure that Wabbajack does not delete your added mods upon updating, prefix your mods with `[NoDelete]`.

>[!IMPORTANT]
>Saves can be continued across **Save-Safe** updates. Updates will be indicated whether or not they are **Save-Safe** on the [Changelog](https://github.com/Hinatsumi98/Cosmoem/blob/main/changelog.md). It is suggested that you backup your saves before updating if you plan on continuing them.

# Removing the Modlist

Simply delete the Cosmoem folder. Congratulations, you have uninstalled Cosmoem.

# Issues

>[!TIP]
>If you encounter any bugs or issues while playing the list, the [Cosmoem](https://discord.gg/c3RFwyAFsG) support server is preferred and will have the fastest turn around time for support.
# Credits and Thanks

- *YOU* for reading this.
- [Apostasy](https://github.com/Oghma-Infinium/Apostasy/blob/main/README.md) for the readme base
