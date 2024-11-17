# WORK IN PROGRESS

# How to run ED MDFCougar on kubuntu (24.04.1 LTS)

## Preamble
If you want to run ED on a single monitor on kubuntu, just install Steam, install ED, select Proton v8.0-5 as compatibility option and run it. Works like a charm. I was even able to use my bindings from my windows installation to use my X-56 H.O.T.A.S. No Lutris, no Xinerama, just Steam and ED.

For me, the by far greatest obstacle has been to get Elite Dangerous running on kubuntu, spanning three of my six monitors like in Windows' NVidia Surround, that is. As there are many different ways around the www to achieve this I'll go very briefly over this topic.

1. Install Steam via "Discover"
2. Select Elite Dangerous and set *Compatibility* to *Proton 8.5-0*
3. Install ED
4. In a terminal run ```WINEPREFIX=~/.local/share/Steam/steamapps/compatdata/{STEAM ID GOES HERE}/pfx winecfg``` (path may vary)
5. Set "Virtual Desktop" to your desired resoulution (in my case 7680x1440)
6. Run the script ```ultrawide``` (you can download my script [here](https://github.com/Kepas-Beleglorn/EDMDFCugar_kubuntu/blob/main/ultrawide))</br><sub>I have to do this step after every login.</sub>
8. Start ED from Steam. On first start compiling the Vulkan shaders takes some... lots of time. About 10 Minutes in my case.
9. Set resolution in game options.
10. Hide the window title of the wine window.
11. Have fun!

I had to force the use of my RTX 3080 by manipulating EDs configuration file, otherwise it was locked to the RTX 3060. Another issue I still have to solve is, that the virtual display gets lost whenever the display manager is being restartet, e.g. because I rearranged my displays.

Helpful sources:
* [Configure WINE](https://www.reddit.com/r/SteamPlay/comments/aikukh/howto_doubletriple_monitor_setup_in_games_that/?rdt=36459)
* [Setup virtual display](https://unix.stackexchange.com/questions/585069/unable-to-add-a-virtual-display-to-xorg/585078#585078)

## What is ED:MDF Cougar?
ED MDF Cougar is an optional additional tool that 

>Extends Elite's cockpit instrumentation onto additional monitors. Connect Thrustmaster Cougars / touchscreen monitors for extra immersion. This app has so many features some of which include: Fleet Carrier support, Mission route optimiser, Mining gameplay extras, Piracy gameplay extras, Bounty hunting extras. Beautifully animates the screens for extra levels of realism.

You can find more information on that here [edcodex.info](https://edcodex.info/?m=tools&entry=488) and here [cougardisplay.site](http://cougardisplay.site/)

## How to install and use ED:MDF Cougar
I won't do a deep-dive into the theory and background of wine, as there are many guides that explain a lot of things much better than I could.

So let's just go for the installation process.
1. Install `PlayOnLinux` via "Discover" or `sudo apt install playonlinux`
2. Download the [most recent release of ED:MDFCougar](http://cougardisplay.site/downloadfiles.html) and extract it's content somewhere you'll find it easily when you need it.
3. Run `PlayOnLinux` and select "Install"</br>![image](https://github.com/user-attachments/assets/6358cc4d-72e6-496d-a54b-59cde1a2df3f)
4. Select "Install a non-listed program"</br>![image](https://github.com/user-attachments/assets/0f4889a4-44ba-428a-8bf5-03f22469bc2b)
5. Go through the process via the "Next" button until you're prompted for some input.
6. The first choice is `install a program in a new virtual drive`. This is essential at this point!</br>![image](https://github.com/user-attachments/assets/21f7409a-d6f1-4742-bef2-e7417756388c)
7. Give it a proper name. As I'm going to add more tools, like EDMC, to this wine-prefix, I call it `ED Tools`</br>![image](https://github.com/user-attachments/assets/938871e9-3096-4493-89a9-a248d082df5b)
8. Now set the name of the directory without spaces.</br>![image](https://github.com/user-attachments/assets/65b932fc-cb89-411c-9653-eecc00bc49c3)
10. As we need the `AccessDatabaseEngine_X64.exe` check `Install some libraries`.</br>![image](https://github.com/user-attachments/assets/9ba92515-caf3-4c25-a366-b512d9e18f9e)
11. Select the 64bit variant.</br>![image](https://github.com/user-attachments/assets/9b921d78-4e48-4cb3-a958-3b398c5681d4)
12. **Now** we're going to install the above mentioned libraries. This step is used to trick `PlayOnLinux` into performing an installation for an actual application.</br>![image](https://github.com/user-attachments/assets/16e700eb-d27e-49cc-b56b-4d4bd88c3d35)
13. Select the `AccessDatabaseEngine_X64.exe` and after that click `Next`</br>![image](https://github.com/user-attachments/assets/e058b6f6-aa3e-451a-9cd0-4998d481bf8d)
14. The regular setup processs like in Windows will be started.</br>![image](https://github.com/user-attachments/assets/47cd2c67-dc20-4310-9404-f9e26f5d2754)
15. Just click `Next` until finished.</br>![image](https://github.com/user-attachments/assets/eb43b5e0-a12b-4055-8ae0-fe7d6dd7567a)
16. And yes, you leave the windows path as it is!</br>![image](https://github.com/user-attachments/assets/272aa812-4f0c-4494-a5b7-835ebd340209)
17. Now you copy the `MDFCougar`directory and it's contents to the newly created wine environment. In my case that's `~/.PlayOnLinux/wineprefix/ed_tools/drive_c/Program Files`</br>![image](https://github.com/user-attachments/assets/d83a5a27-f6ce-4e7e-b09b-a1efc643a1ae)
18. Back in `PlayOnLinux` you select `Browse`</br>![image](https://github.com/user-attachments/assets/3cbef620-20e4-4ac3-a866-cc7fa895540b)
19. Look for the `MDFCougar.exe` and select it.</br>![image](https://github.com/user-attachments/assets/a47b653a-fdef-41dc-876f-a94693dab029)
20. You can change the name for the shortcut if you want to.</br>![image](https://github.com/user-attachments/assets/5fa32e1f-1b0d-42da-a7d1-009483c318f8)
21. After this step select `I don't wat to make another shortcut`. For now, that is.</br>![image](https://github.com/user-attachments/assets/37f5a1d0-a0c6-4787-9e8a-2444127ed6a4)
22. Now you have a shortcut for your `MDFCougar`</br>![image](https://github.com/user-attachments/assets/7cdb0781-399f-43c0-aa90-1e42cda757ee)
23. Now select the new shortcut and click `Run`. MDFCougar should start after a few seconds. On ~~first~~ start you'll get a message about missing Explorer database. We'll cope with that ~~in a moment~~ hopefully.</br>![image](https://github.com/user-attachments/assets/8df8b836-3c16-4809-85c3-e4801826b56e)
24. As Elite Dangerous is running within a different wine-prefix we have to adjust the paths where to get the data from the game. I'll do it via `symlinks`. Always cd into the target directory of your MDFCougar installation first!</br>
    - `~/.PlayOnLinux/wineprefix/ed_tools/drive_c/users/{user}/AppData/Local$ ln -s ~/.steam/debian-installation/steamapps/compatdata/359320/pfx/drive_c/users/steamuser/AppData/Local/Frontier\ Developments`
    - `~/.PlayOnLinux/wineprefix/ed_tools/drive_c/users/{user}/Saved Games$ ln -s ~/.steam/debian-installation/steamapps/compatdata/359320/pfx/drive_c/users/steamuser/Saved\ Games/Frontier\ Developments`
    - `~/.PlayOnLinux/wineprefix/ed_tools/drive_c/users/{user}/Pictures$ ln -s ~/.steam/debian-installation/steamapps/compatdata/359320/pfx/drive_c/users/steamuser/Pictures/Frontier\ Developments`
25. Run ED and start MDF Cougar.   




## my system
* CPU:    11th Gen Intel(R) Core(TM) i9-11900KF @ 3.50GH
* GPU1:   Geforce RTX 3080
* GPU2:   Geforce RTX 3060
* RAM:    64GB DDR4 (4x 16GB)</sub>
