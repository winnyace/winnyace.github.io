---
title: "OUTDATED AND POTENTIALLY WRONG! Fixing a new bug that causes TF2 to crash on startup on Linux."
date: 2023-09-05
draft: false
tags:
- Tutorial
- Linux
- One-off
- TF2
- Outdated
---

## DISCLAIMER

Hi! It's winny from the future. This article is:

1. Very old;
2. Potentially incorrect in the Debian section entirely!

I decided to leave this article up for the sake of historical purposes, but this issue has been fixed, I believe, [since the introduction of the 64-bit client for Team Fortress 2, almost a year ago.](https://www.teamfortress.com/post.php?id=220436) As such, please don't use this article. If you have issues with something regarding Team Fortress 2 and Linux, check [TF2's ProtonDB page.](https://www.protondb.com/app/440) Thank you!

<details>
<summary><b>The old article</b></summary>

Hi! I like playing TF2. It's a fun game, even if Valve doesn't really give a shit about it. Problem is that I haven't played in quite some time and I wanted to play it recently. Sadly, I couldn't due to a new update that introduced a bug, I think. I would tell you more if I knew more. All I know is the fix for this issue, that I found on [ProtonDB's page for TF2.](https://www.protondb.com/app/440#F5eUgPqkSk)

## Fixing on Arch Linux/Anything Arch Linux based

The solution involves installing an AUR package called `lib32-gperftools`. It's some Google modified memory allocation functions that improve performance for C and C++, from the looks of it.

Whatever AUR helper you have, use it to install it. I use [paru](https://github.com/Morganamilo/paru), so for me, it's a simple `paru -S lib32-gperftools`. Other AUR helpers should have a similar syntax.

Afterwards, in the TF2 launch options add `LD_PRELOAD=/usr/lib32/libtcmalloc.so %command%`. Put them at the beginning of your already existing launch options. The game should open up now without any issues.

## Fixing on Debian/Ubuntu/Anything Debian/Ubuntu based

**Since I'm not on Debian, I will guess here. I'm not responsible for breaking your system.**

The solution is to install a package called `libgoogle-perftools4`. It's some Google modified memory allocation functions that improve performance for C and C++, from the looks of it.  Install it with `sudo apt install libgoogle-perftools4`.

Afterwards, in the TF2 launch options add `LD_PRELOAD=/usr/lib32/libtcmalloc.so %command%`. Put them at the beginning of your already existing launch options. The game should open up now without any issues.

## Conclusion

Hope this helped ya! May Gaben give you no bots/cheaters in your casual games and plently of random crits. See ya!
</details>
