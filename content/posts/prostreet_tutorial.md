---
title: 'How to play Need for Speed ProStreet on Linux'
date: 2025-04-04
draft: false
tags:
- Linux
- Tutorial
---

Hi! Over the last summer, I've gotten the Need for Speed itch. Thus, I've decided to play a title I have never fully played: ProStreet. Getting it to work on Linux was a bit of a challenge, however, so I decided to document how I was able to install the game and play it.

## Necessary files and programs

The first thing you need is the game. The game isn't available for purchase anymore, unless you buy it second hand. As such, [here's a link to an archive of the game](https://drive.google.com/file/d/13ZxE-Fznpklvf4NCpbskO8KM7uJDnyfG/view?usp=sharing). It will have the game with the latest official patch, which is still a bit broken.

Next, you will need a special .exe file for the game. This special .exe, to my knowledge, removes the need for the game's DVD to be inserted, alongside having some sort of fixes in-built too. [Here's a link for that special .exe file](https://drive.google.com/file/d/19gBVE_-6Ebnl3wZFriqxCx02l8pLSX2l/view?usp=sharing).

Next, you will need Wine and Winetricks installed. This is different based on the distribution you're running and I believe that putting the install process for these two programs here is unnecessary, so please find another tutorial on installing Wine and Winetricks for your distribution of choice.

Finally, I do recommend you install [ThirteenAG's ProStreet Generic Fix](https://thirteenag.github.io/wfp#nfsps). This fixes some more problems with the game, including the broken 16:9 aspect ratio.

## Install steps

1. Extract the game files from the first archive provided and place the .exe file from the second archive provided in the game files, replacing the original.
2. Generate the prefix/bottle for the game:

`WINEPREFIX=/path/to/your/prefix WINEARCH=win32 winecfg`

3. Install the necessary libraries required for the game:

`WINEPREFIX=/path/to/your/prefix WINEARCH=win32 winetricks d3dx9_34 dxvk`

4. After you follow the install instructions for the community fixes from [ThirteenAG's website](https://thirteenag.github.io/wfp#nfsps), open up `winecfg` inside the prefix (the command from step 2 will do just that). Click on the tab named *Libraries* and click inside the text box/dropdown menu under the label *New override for library*, type `dinput8` and then click *Add* and, lastly, click *Apply*.

## Closing words

That's it! You can now launch the game by going in the game folder, pointing to your prefix and launching the game exe with Wine. Enjoy!
