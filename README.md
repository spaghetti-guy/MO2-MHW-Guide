# MO2-MHW-Guide
This is just a mirror of my Mod Organizer 2 guide for Monster Hunter: World (https://www.nexusmods.com/monsterhunterworld/mods/5347), posted here as a backup. I literally pasted this into a BBCode-to-Markdown converter, replaced all \[spoiler] tags with \<details> in Notepad++, then pasted it into this readme, so apologies if it's weirdly formatted here. I'll add the files to a folder on this respository as well.

# Paste starts below here
**IMPORTANT NOTE: I ended up rambling and over explaining literally everything in this guide, my apologies. As a result, this has sort of become a giant wall of text. I've put as many things into spoiler tags as possible in order to make it easier to navigate. One benefit of my word vomit is that you should be able to get up and running with Mod Organizer 2 for MHW even if you've never modded ANY game before. Using MO2 does NOT require hours of research when using it for MHW. Lots of this guide is just "click this, then click that" and "basically, it means..." If you read it all, you'll also learn a few  things about modding aspects that show up in almost every other game on the Nexus, so that's cool.**


## **Introduction**
## **What is this guide?**
This is a tutorial on how to setup Mod Organizer 2 (MO2) and use it to manage mods in Monster Hunter: World. ~~ I will not be going into great depth on many of the awesome features of MO2 as that is outside the scope of this guide~~ (Oops), but I will ~~ briefly~~ explain the ones that are most useful to managing mods in MHW. For more detailed information on Mod Organizer 2, please check the [official post on the Skyrim SE page.](https://www.nexusmods.com/skyrimspecialedition/mods/6194) **DISCLAIMER: I am not a part of the MO2 development team, nor am I affiliated with them. This is a tutorial written by a regular user like you.**

## **Why should I use MO2 when I already know how to manually manage mods?**
Better mod visibility
<details>Mod Organizer 2 provides a convenient interface to manage your mods and allows you to enable or disable them freely without renaming or deleting files. Manually installing mods requires you to remember which files belong to which mods. This gets trickier and trickier the more mods you install. Was that file from an armor swap? Or a face retexture? MO2 clearly shows you exactly which files belong to which mod and shows you every mod you have installed.</details>
Better conflict management
<details>MO2 provides an intuitive way to manage file conflicts in a "non-destructive" way. When installing a mod manually to your nativePC folder, if a different mod added the same file, you must immediately choose to keep either the old or the new file. This is a "destructive" way to manage conflicts because one file is permanently destroyed. Mod Organizer 2 is "non-destructive" because conflicts are resolved by your load order. This means that if you want to overwrite a skin overhaul mod with a mod that changes your face, you place the face mod below the body mod in your load order. No files are destroyed in this process.</details>
The base game directory is untouched
<details>One of the key features of MO2 is something called ["uvfs" or "User Space Virtual File System"](https://github.com/ModOrganizer2/usvfs). I won't go into technical detail on how this works (and I am not qualified to), but the TL;DR of it is that when you install mods with MO2, nothing is actually placed in your real nativePC folder. They are stored in a folder completely outside of MHW's folder. When you launch Monster Hunter through Mod Organizer 2, a virtual nativePC folder is created that MHW uses to read your mods. This virtual folder is created when you launch the game through MO2 and destroyed (intentionally) when you close it. One benefit of this is that at any time, you can open Steam and launch MHW without MO2 and you will have a perfectly untouched, unmodded game. This also means that you can easily enable or disable installed mods by just ticking a checkbox. When you launch the game through MO2, only mods that are enabled are put into this virtual nativePC folder.</details>
## **Why should I use MO2 when I already use Vortex?**
<details>Honestly, I haven't used Vortex since late 2018. It may work fine for MHW. I prefer MO2 because of the uvfs feature I described above and because you can run it in a portable instance. This means MO2 won't touch your other games or place "folder managed by Vortex" files everywhere. Mod Organizer 2 does exactly what you tell it to and nothing more. In addition to this, MO2 allows you to inject the ReShade binaries into the game when it launches, fixing the issue with DirectX 12 that is present at the time of writing this guide. **TL;DR: you do you.**</details>


## **The Guide**
## **Requirements**

* The latest official version of Monster Hunter: World. Pirated or older versions probably won't work. **I will not provide support for pirates.**
* A fresh, unmodified installation of MHW. You should not have mods installed before performing these steps or you may run into issues. If your game is already modded, I recommend removing your nativePC folder and re-installing your mods with MO2. Otherwise, you will almost certainly run into problems.
* The [latest Visual C++ packages. ](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads)﻿﻿Download and install the x86 and x86 versions:
![https://i.imgur.com/ybWqgij.png](https://i.imgur.com/ybWqgij.png)
## **Installing Mod Organizer 2**
Please do not start these steps until all requirements above are true. We will be installing MO2 in portable mode for this guide because it's the way I'm most comfortable with and will allow us to be sure no other games or mod lists are touched. 


1. Create a new folder called "MHW" at the root of the same drive Monster Hunter: World is installed on. For example, if Monster Hunter: World is installed in "C:\Program Files (x86)\Seaam\steamapps\common\...", you should create a folder at "C:\MHW\". The exact path isn't super important, we just want to make sure this new folder is on the same drive as the game and that it's not in a folder like Desktop, Downloads. or Program Files. 
1. Head to [the MO2 page on the Skyrim SE Nexus site](https://www.nexusmods.com/skyrimspecialedition/mods/6194?tab=files)﻿ and click "Manual Download" under the main Mod Organizer 2 download to get the latest installer. Don't worry, the version here works with all games.
1. Run the downloaded Mod Organizer 2 installer and accept the license agreement. 
1. At the next screen, click "Browse" and navigate to the folder you created in step 1, then click "Next" to go to the next screen.
1. Leave the rest of the settings as default and click "Next" a few times, then "Install" to install.
1. Click "Finish". Mod Organizer 2 should start automatically. A window will appear explaining what an "instance" is. 
1. Click "Next" once, then choose "Create a portable instance". 
1. Monster Hunter: World should appear in the list of games to manage, click it. If it does not appear, launch the game once through Steam, then exit at the main menu. This allows for necessary registry keys to be created.
1. The next screen asks where the data should be stored. Leave the pre-filled location selected (should be the folder you created in step 1)  and click "Next".
1. You should be presented with a screen that looks similar the screenshot below. Note that your "Instance location" and "Game location" will be slightly different as the paths depend on your specific locations.
![https://i.imgur.com/oqqKvMh.png](https://i.imgur.com/oqqKvMh.png)﻿
1. Click "Finish" to create the instance. The main MO2 interface will automatically launch its main interface.


## **Launching Monster Hunter: World**
If you close MO2 and need to get back into it, navigate to the folder you created in step 1 above, then launch "ModOrganizer.exe". Note that from now on, you should always run MHW through MO2. Before proceeding, give the game a test run to make sure everything is working. Make sure Steam is running, then click the "Run" button in the top right corner of MO2. 
![https://i.imgur.com/PJtK4Dl.png](https://i.imgur.com/PJtK4Dl.png)

You can create a shortcut for this by clicking the "Shortcut" button directly below the "Run" button and choosing where you want the shortcut to go. If something isn't working during your test run, stop here to troubleshoot before proceeding further into the guide.


## **Some Configuration Changes**
These are some initial tweaks and fixes to finalize our MO2 installation.


1. Click "Tools" then "Settings" in the top menu bar. Or press CTRL+S.
1. Click the tab labeled "Nexus".
1. If you do not see your Nexus Mods profile information under "Nexus Account", click "Connect to Nexus" and sign in.
1. Click "Associate with "Download with manager" links".
1. Click the tab labeled "General".
1. Check the boxes next to "Show meta information" and "Compact list".
1. Click "OK" to close the settings menu.

## **Enable Dark Mode (optional)**
<details>This one isn't technically required, but I personally do it immediately after a new installation of MO2.

1. Click "Tools" then "Settings" in the top menu bar. Or press CTRL+S.
1. Click the tab labeled "Theme" then click "None" and choose a new theme. I personally recommend "1809 Dark Mode" and will be using it for the rest of my screenshots in this guide.
1. Click "OK".
</details>
## **Create a New Profile (strongly recommended)**
<details>You can think of a profile like different mod lists. I recommend creating a new one and leaving the "Default" profile untouched. This means if you ever want to play the game without mods (like if you want to play online with friends), you can switch to the default profile. When playing alone, you can use your modded profile. This is not required, but it's super easy and strongly recommended.


1. Click the profile selector box, highlighted green below, and choose "Manage..." (You can also press CTRL+P or click "Tools" in the top men, then "Profiles"
![https://i.imgur.com/n85g0jD.png](https://i.imgur.com/n85g0jD.png)
1. In the window that appears, first uncheck "Use profile-specific Game INI files" and choose "Yes" when prompted to delete.
1. Click the button labeled "Create" in the upper right.
1. Give your profile a name to indicate it will be the modded version. I recommend something like "MHW-Modded".
1. Then click "OK".
1. Click your new profile once, then click "Select" in the bottom right.

When you install mods, they will be added to your selected profile. With the setup above, "Default" will be the unmodded game and "MHW-Modded" would be your profile with all your mods.</details>
## **Creating Separators (very helpful if you plan on adding many mods)**
<details>Separators are just a way for us to group our mods into categories. For instance, we can put all of our clothing mods under one category and UI changes under another. While not strictly necessary, separators become more helpful the more mods you install because they can help give you an idea of where you should place a mod in your load order.

1. To create a new separator, click the small wrench and screwdriver icon directly to the right of your profile name.
![https://i.imgur.com/wx9HWux.png](https://i.imgur.com/wx9HWux.png)
1. Then click "Create separator".
1. Enter the name of the separator you'd like to use. For reasons explained further on in the guide, let's name the first one "ESSENTIAL MODS" and click "OK".
1. You'll see the separator appear in your list of mods on the left side. Right-click it and choose "Select Color".
1. Pick any color you'd like, then click "OK". From now on, all new separators will default to the same color.

</details>

## **Managing Mods**
The hard part is now done, all that's left is to mod the game! Thankfully, installing and managing mods in MO2 is pretty simple and intuitive. But first, a VERY quick rundown on the "Load Order" as it's important to understanding how mods are loaded into the game. 

## **Load Order (very important, I'll keep it short, I promise)**
<details>**TL;DR: if SomeModA requires you to have SomeModB installed first, make sure SomeModA has a lower priority (larger number in the "Priority" column) compared to SomeModB. This way, SomeModA will load after SomeModB.
**
* Mods in MHW are loaded into the game based on the number in the "Priority" column. 
* The mod with priority 0 is the highest priority and is loaded first, then 1, then 2, etc. Separators are ignored. 
* When 2 mods add the same file to the game this creates a "conflict" and is indicated by a lightning bolt in the "Conflicts" column.
* The mod with the lower priority (larger number in the priority column) will "win" the conflict and will overwrite the conflicting files of the one with the lower number.
* You can adjust the priority of mods simply by dragging them above or below other mods in the main mod window.
* More information on conflict management will be listed towards the bottom of the page in the **Troubleshooting and FAQ** section.
</details>
## **Installing Mods**
The high-level flow for downloading a mod is: download mod from the Nexus -> double click the mod in the "Downloads" tab of MO2 to install -> enable it -> move it to a good place in your load order. You will still need Stacker's Loader for the vast majority of mods, so let's walk through that together as a an example of how to install mods:


1. First, make sure the game is closed, then head over to [the mod page for Stacker's Loader](https://www.nexusmods.com/monsterhunterworld/mods/1982)﻿ and click the "Files" tab.
1. Under "Main Files", you should see Stacker's latest release of their loader. Click the orange "Mod Manager Download" button. If you install a different mod that does not have a "Mod Manager Download" button, check out the **Troubleshooting and FAQ** section down below for special instructions.
1. A popup will appear making sure you have all the requirements for the mod. Click the orange "Download" button. Even though it says the "Performance Booster" is required to use the loader, we still need to install the loader first.
1. Back in Mod Organizer 2, click the "Downloads" tab on the right side. This tab is where your downloaded (but not installed) files will appear. You should see "Stacker's Loader" listed there.
![https://i.imgur.com/46TGcg9.png](https://i.imgur.com/46TGcg9.png)
1. Once the download is finished, double-click the mod to begin to install it. A window will appear showing you the contents of the mod. 
1.  The first time you install a mod, you'll see a prompt with some information on what this window means. Read through the prompts in the gray box, then click the green arrow and repeat. Keep in mind the wording in the prompts is specific to Bethesda games, but the idea is the same for MHW, we just use "nativePC" instead of "Data" for mods. Stacker's Loader is configured correctly so it should work with MO2 without any modifications. But some mods are not packaged correctly and we will need to rename folders within the mod to make sure everything works. Detailed instructions for that will be provided below in the **Troubleshooting and FAQ** section. 
1. For now, click "OK" to install Stacker's Loader. You should see "Stacker's Loader" appear in the mod list directly under the "ESSENTIAL MODS" separator we created earlier in the guide. And this is most likely where we want to keep it because almost all other mods depend on it.
1. Even though it's installed, it is not actually enabled yet. **Only enabled mods will be loaded when we launch the game.** To enable the mod, click the checkbox next to it's name. 
![https://i.imgur.com/6idXr5Z.png](https://i.imgur.com/6idXr5Z.png)
1. Stacker's Loader will now be loaded the next time you run MHW through MO2.


## **FAQ, More Info, and Troubleshooting**
In this section of the guide, I'll walk you through a few specific scenarios you will probably encounter and show you to to deal with them. If you aren't having any issues and are already sick of reading my walls of text, you can skip this section and close the page here, you've suffered enough!

## **Conflict Management**
The first thing to note about conflicts is that they aren't necessarily bad to have. Sometimes you will create your own conflicts intentionally. Conflicts are only bad when they are ignored and you do not make a decision on them. Before explaining conflict management more, familiarize yourself with the information in the "Load Order" section above. I've also attached some test files to this page that will conflict. You can use these 3 files to play around and see which files win in certain scenarios.
<details>**What causes a conflict**
As mentioned above, a conflict arises when 2 mods try to add a file by the same name. Like 2 weapon mods both trying to modify the appearance of long swords. When you are manually installing mods, you are notified of these conflicts when Windows lets you know a file already exists and you must resolve this conflict immediately by choosing which one to keep. If only it told you which mod created the existing file, right? 

In MO2, you are first informed of conflicts by these little lightning bolt icons, shown below. A green "+" icon means that file wins the conflict, a red "-" icon means that file loses the conflict, and a gray lightning bolt means the mod is obsolete (all its files are overwritten by other mods.
![https://i.imgur.com/ugMUCzv.png](https://i.imgur.com/ugMUCzv.png)
You can get more information by double-clicking one of the conflicting mods and then clicking the "Conflicts" tab. You should see information on exactly which specific files are conflicting and which mod is "winning" the conflict. The mod that wins the conflict is the one that will be loaded into the game. 

**Actually managing a conflict**
The easiest way to manage a conflict in MO2 is to simply make sure the mod you want to win has a lower priority (larger number in the "Priority" column) than the one you want to lose. Let's say the screenshot above is in your mod list. You installed [Dropped Items EFX (Unique Version 2) by Crimson,](https://www.nexusmods.com/monsterhunterworld/mods/2325?tab=description) but you want to swap the icons with Vuze's icons in [Bold Icon Pack for Dropped Items efx (Unique ver.).](https://www.nexusmods.com/monsterhunterworld/mods/2351?tab=description) What does that mean for our conflict? Do we have a problem? 

The answer is no. In the screenshot above, Dropped Items efx has a priority of 3 and Vuze's icon pack has a priority of 4. This means MO2 will load all files in Dropped Items efx, then the files from Vuze's icon pack will overwrite them. This is exactly what we want in this example..The conflict is "resolved" because you decided this is what you want to happen.

**Individual file hiding**
In the same example above, what if you only wanted Vuze's ammo icon to appear in game? You can't just load Dropped Items efx after Vuze's icons or else they will all be overwritten. We need only some of the files from Vuze's pack to win and the others to lose the conflict. To address this, you can hide individual files per mod. We can do this in the "Conflicts" tab of Vuze's mod
![https://i.imgur.com/l9FYW5t.png](https://i.imgur.com/l9FYW5t.png)
We can see the 3 conflicting files, and the ammo texture is the one ending in "amm.tex". Since we don't want the other 2 textures in our game, we can right-click "zny.tex" and "mat.tex" and choose "Hide". You'll see them appear in the third section, showing they are no longer conflicting, meaning the icons in Dropped Items efx will win. To unhide them, we can simply right-click the hidden texture and choose "Unhide".

**Testing some mod conflicts**
If you want to do testing with mod conflicts, head to the "Files" tab of this guide and download all 3 of the optional files, ConflictTestA, B, and C. Make sure to click "Mod Manager Download". Once they're downloaded, follow the steps in the Installing Mods section to install and enable them. The contents of the mods are as follows:
ConflictTestA

* TestFile1.txt
* TestFile2.txt

ConflictTestB

* TestFile1.txt

ConflictTestC

* TestFile2.txt
* TestFile3.txt

Go ahead and move these mods around in your load order. Watch what happens to the lightning bolt after each move. If you want to see the effects of your load order changes, click "Monster Hunter: World" to in the upper right corner and then click "Explore Virtual Folder" and "Run"
![https://i.imgur.com/UNTeo2L.png](https://i.imgur.com/UNTeo2L.png)
This will let you see the virtual folders MO2 creates when it launches the game. In the window that opens, double click the "nativePC" folder, you should see the 3 test files here. Right-click each of them one at a time and choose "Edit" (you can't choose "Open"). The file should open in Notepad and show you which mod won the conflict. Close the Explorer++ window that opened , re-arrange the conflict test mods, and click "run again". You can clearly see which files will make it into the game when it's launched through MO2.

To remove the test mods, right-click them in the mod list and choose "Remove Mod".
</details>
## **Mods Uploaded Incorrectly to the Nexus**
Sometimes, mod authors upload their mods to the Nexus with improper folder structure. This can be annoying, but it's easier to just fix it yourself rather than contact the author to do so. We'll go through 2 common examples in the spoiler tag here.
<details>99% of the time, we want all files from a mod to go into the nativePC folder. Though there are very small set of exceptions such as Stacker's Loader which needs to put files outside of nativePC. When you install a mod for MHW, you are presented with a window that will show you the contents of the mod. 
![https://i.imgur.com/gMoGOt0.png](https://i.imgur.com/gMoGOt0.png)
You can click the arrows to expand the folders to see the contents. "<monster hunter world>" means the folder MHW is installed in. Directly under that , you'll see "nativePC" is checked. This mod is setup perfectly and the files will be installed to the (virtual) nativePC folder, which is what we want.

**Mods with an extra folder**
Sometimes, mod authors add an extra folder their nativePC folder is in. Thankfully, this is super easy to fix. Take a look at the test file I have in the "Miscellaneous" section titled "BadFolderTestExtraFolder.zip". When you install it with MO2, click the arrow next to "BadFolderTestExtraFolder" to expand it to see our "nativePC" folder hiding inside it. 
![https://i.imgur.com/1qcQ8t3.png](https://i.imgur.com/1qcQ8t3.png)
This is a problem because if you click "OK" now, the mod will be installed to "<monster hunter world>\BadFolderTestExtraFolder\nativePC", which means it won't be in the "nativePC" folder that Stacker's Loader reads from and thus will not make it into the game. To fix this, we just need to tell MO2 to ignore that extra folder by right-clicking the "BadFolderTestExtraFolder" in the content section and selecting "Set as <monster hunter world> directory". You'll see the content window update to only show the "nativePC" folder as well as its contents. Problem solved! 

**Mods with no nativePC folder**
Another semi-common occurrence on the Nexus are files uploaded with no "nativePC" folder. The mod author may instruct you to manually install it by saying "place this in your nativePC folder". We can fix this when installing with MO2 as well by just creating the "nativePC" folder during installation. Download the other test file in the "Miscellaneous" section of this guide, the one titled  "BadFolderTestNonativePC". When you install it, you'll see the following
![https://i.imgur.com/o45SOI7.png](https://i.imgur.com/o45SOI7.png)
No nativePC folder in sight. To fix, simply right-click "<monster hunter world>" and choose "Create directory". Enter "nativePC" for the name and click "OK" to create the new folder. Then, drag the mod content (the text file in this case) into the "nativePC" folder. Now we're in business!
</details>
## **Mods with no "Mod Manager Download" Button (Manually Installing Mods)**
When a mod author uploads a mod, they can choose to disable the "Mod Manager Download" button, leaving "Manual Download" as the only option. They do this ~~ to be difficult~~ because their mod probably has special installation instructions or is an external tool (not a mod). But oftentimes the mod will still work fine when installed manually through MO2. Here's how to manually install a mod in MO2.
<details>**IMPORTANT NOTE: external tools such as [Vuze's WorldChunk tool](https://www.nexusmods.com/monsterhunterworld/mods/6) really cannot be installed through MO2. This also goes for all the damage meters and save editing tools. An easy to remember rule of thumb is that files that come with the extension of ".exe" cannot be installed through Mod Organizer 2.**

To install a mod in MO2 manually, 

1. Click the "Manual Download" button on the "Files" tab of the mod's Nexus page. A .zip or .7z file which contains the mod will be downloaded.
1. Simply drag this new archive into the "Downloads" tab of MO2. This will copy it to a folder managed by MO2. The .zip or .7z file that's sitting in your downloads folder can be deleted.
1. (Optional) You'll notice there's a red warning signal next to the mod name. This is because MO2 does not know where this file was downloaded from. Right-click the mod in your "Downloads" tab and choose "Query info". This will tell make MO2 grab the correct info from the Nexus.
1. Install the mod as normal. 

</details>
## **Installing ReShade / ReShade not working**
Because I know this will come up, I'll create an entry here. At the time of writing this guide, there is currently a bug with the DirectX 12 version of MHW and ReShade, namely that it does not work. You can fix this by manually loading the ReShade libraries as [described in my other guide here.](https://www.nexusmods.com/monsterhunterworld/mods/5345) You can set this up once and never worry about it again because you will launch MHW through MO2 as normal. Note: the ReShade preset you want to use should be installed directly to Monster Hunter: World's REAL folder. So something like "C:\Program Files (x86)\Steam\steamapps\common\Monster Hunter World".


## **Conclusion**
Sorry again about how long  this got. As I wrote, it slowly transformed from "a brief guide to using Mod Organizer 2 with MHW" into "a general MO2 guide". In any case, thank you for reading, it means a lot! I've disabled the mod rewards program for the test files because I feel it would be ridiculous to profit from sharing this information. I also won't post any other donation links for the same reason. That said, if you found any of this helpful, it would honestly make my day to hear about it in the posts. I love helping people and would LOVE to hear that the 4300 words I just typed weren't wasted LOL.

**If there's anything you'd like me to explain more, please let me know and I will add it to the guide if I can. **

**If you get stuck on any part, let me know and I can rewrite it to make it clearer.**
