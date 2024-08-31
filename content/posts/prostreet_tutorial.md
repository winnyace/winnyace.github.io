---
title: 'How to play Need for Speed ProStreet on Linux'
date: 2024-08-31T10:52:46+03:00
draft: false
tags:
- Linux
- Tutorials
---

Hi! Over the summer, I've gotten the Need for Speed itch. Thus, I've decided to play a title I have never finished: ProStreet. Getting to work on Linux was a bit of a challenge, however. I hope this post will help you run the game. It worked for me under openSUSE Tumbleweed, with Wine version 9.16 .

The first thing you need is the game. The game isn't available for purchase anymore, unless you buy second hand, so pirating is possible. I personally recommend just pirating the game. Here's [a link](https://pixeldrain.com/u/maXwYgoi) to an archive of the game. It will have the game with the latest official patch, which is still a bit broken.

Next, we will need a special .exe file for the game. Here's [a link](https://g06.mobiletarget.net/?y=4f95b43f&x=%2FuICh%2FSHYIusoj2por6XBj85TS0CEeI%2Br0nLW8JXALPAAwCSBFxoN5N11CHniB7sAg%2BZ%2FLqcjP3zS6bv9%2BfLyJvfzN9WO8iTSWOqHxvWEe5ozbsjKUChiXKvTSKBOXdS) for that special .exe file as well. Just replace the .exe from the game folder with the one from the provided archive.

Afterwards, it is time to set up our prefix. You would need `winetricks` installed for this step and obviously Wine. I won't be going over this step, since there are already plenty of tutorials for doing that. To generate the prefix, type in a terminal `WINEPREFIX=/path/to/your/prefix WINEARCH=win32 winecfg`. It will open up the config program for Wine. Now it is time to install the required stuff for the game to work. Type in a terminal `WINEPREFIX=/path/to/your/prefix WINEARCH=win32 winetricks d3dx9_34 dxvk`. This will be enough to play the game, without community fixes.

I recommend you do install community fixes, however. The one I used was [ThirteenAG's ProStreet Generic Fix](https://github.com/ThirteenAG/WidescreenFixesPack/releases/tag/nfsps). Just download it and replace the files from the game folder with the ones from the archive. After that, open `winecfg` in your prefix, go to the Libraries, and in dropdown box, type `dinput8` and click Add. 

That's it! You can now launch the game by going in the game folder, pointing to your prefix and launching the game exe. Enjoy!

Recommendation for complete newbies:
* For the prefix path, I recommend `/home/<your_username>/.local/share/wineprefixes/nfsps`. The folder wineprefixes doesn't exist by default. You can create it with the terminal by typing `mkdir $HOME/.local/share/wineprefixes`.