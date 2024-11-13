# How to run ED MDFCougar on kubuntu (24.04.1 LTS)

## Preamble
If you want to run ED on a single monitor on kubuntu, just install Steam, install ED, select Proton v8.0-5 as compatibility option and run it. Works like a charm. I was even able to use my bindings from my windows installation to use my X-56 H.O.T.A.S. No Lutris, no Xinerama, just Steam and ED.

For me, the by far greatest obstacle has been to get Elite Dangerous running on kubuntu, spanning three of my six monitors like in Windows' NVidia Surround, that is. As there are many different ways around the www to achieve this I'll go very briefly over this topic.

1. Install Steam via "Discover"
2. Select Elite Dangerous and set *Compatibility* to *Proton 8.5-0*
3. Install ED
4. In a terminal run ```WINEPREFIX=~/.local/share/Steam/steamapps/compatdata/{STEAM ID GOES HERE}/pfx winecfg``` (path may vary)
5. Set "Virtual Desktop" to your desired resoulution (in my case 7680x1440)
6. Run the script ```ultrawide``` (you can download my script [here](https://github.com/Kepas-Beleglorn/EDMDFCugar_kubuntu/blob/main/ultrawide))   <sub>I have to do this step after every login.</sub>
8. Start ED from Steam. On first start compiling the Vulkan shaders takes some... lots of time. About 10 Minutes in my case.
9. Set resolution in game options.
10. Hide the window title of the wine window.
11. Have fun!

I had to force the use of my RTX 3080 by manipulating EDs configuration file, otherwise it was locked to the RTX 3060. Another issue I still have to solve is, that the virtual display gets lost whenever the display manager is being restartet, e.g. because I rearranged my displays. At the moment i ha
Helpful sources:
* [Configure WINE](https://www.reddit.com/r/SteamPlay/comments/aikukh/howto_doubletriple_monitor_setup_in_games_that/?rdt=36459)
* [Setup virtual display](https://unix.stackexchange.com/questions/585069/unable-to-add-a-virtual-display-to-xorg/585078#585078)

## What is ED:MDF Cougar?
ED MDF Cougar is an optional additional tool that 

>Extends Elite's cockpit instrumentation onto additional monitors. Connect Thrustmaster Cougars / touchscreen monitors for extra immersion. This app has so many features some of which include: Fleet Carrier support, Mission route optimiser, Mining gameplay extras, Piracy gameplay extras, Bounty hunting extras. Beautifully animates the screens for extra levels of realism.

You can find more information on that here [edcodex.info](https://edcodex.info/?m=tools&entry=488) and here [cougardisplay.site](http://cougardisplay.site/)

## How to install and use ED:MDF Cougar
First you should download the most recent release and extract it's content somewhere you'll find it easily when you need it.

## my system
* CPU:    11th Gen Intel(R) Core(TM) i9-11900KF @ 3.50GH
* GPU1:   Geforce RTX 3080
* GPU2:   Geforce RTX 3060
* RAM:    64GB DDR4 (4x 16GB)</sub>
