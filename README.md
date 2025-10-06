## MAGICIAN LORD - AGAIN CHANGES FROM HELL ROMHACK

Magician Lord is a fantastic game, featuring outstanding graphics and music for its time. Unfortunately, it suffers from an extremely high difficulty level, the result of last-minute changes made to increase profitability for arcade operators.

The goal of this patch is to rebalance the difficulty to bring it closer to the average difficulty of 16-bit era games, so that everyone can enjoy this excellent title without having to spend dozens of hours on it — time being the most precious resource for retro gamers. It’s also a good warm-up for those who wish to later take on the brutality of the original :)

The patch applies to the ROM from set 2 (the version released on Neo-Geo AES), as it offers a more console-like experience: there’s an introduction to the story, and each death sends you back to the last checkpoint.

### List of Changes

#### Gameplay
- 8 HP max (6 in the original version)
- 5 lives per credit (2 in the original version)
- Invincibility time doubled after being hit
- Global level timer removed (normally hidden), which used to spawn an invincible monster after a few minutes
- Disabled automatic monster spawns when staying in the same area for several seconds
- You now need to get hit twice to lose one power level. This is visually represented by the power cell cracking after the first hit before disappearing
- You can drop off ladders by pressing the jump button
- When transformed, pressing `C` allows you to return to Elta’s base form while keeping the extra HP
- In his base form, Elta can now fire 4 magic missiles simultaneously on screen (2 in the original)
- Reduced HP for certain enemies that required too many hits to defeat
- Removed the time limit for Gal Agiese’s dialogue before each boss, allowing you to enjoy the full music. Press any button to skip directly to the boss

#### Visuals
- The power gauge design has been completely redone to match the HP bar’s style
- Realignment of the orbs at the top of the screen
- Improved character shadows for better contrast and consistency
- Removed the score and hi-score display. Let’s be honest: NO ONE plays Magician Lord for the score — especially not a modded version! The remaining lives counter has been moved to the top-left corner to maximize space for those gorgeous graphics

#### Translation
- Complete retranslation of the English version, known for its infamous lines (“Again changes to hell”), to better match the Japanese script
- Fear not, fans of the Engrish original translation: at the title screen, you can switch between the two translations by pressing `D`

#### Cheats
- For those playing without a memory card who wish to resume from the last reached level, you can press `UP+C+D` at any time to automatically skip to the next stage

### Instructions

> **Note:** I won’t go into details on how to use an IPS patch, gzip a file, or anything technical — Google and AI are your friends ;)

#### Requirements
Make sure you have the ROMs `maglord.zip` and `maglordh.zip`, then extract the files `maglord_p1.ips` and `maglord_s1.ips` from the patch archive (choose the folder according to the desired language).

1. Create a folder named `maglord_acfh`
2. Unzip `maglord.zip`, patch `005-s1.s1` with `maglord_s1.ips`, and place the resulting file in `maglord_acfh`
3. Unzip `maglordh.zip`, patch `005-p1.p1` with `maglord_p1_fr.ips`, then copy the resulting file into `maglord_acfh`

Your `maglord_acfh` folder should contain:
- `005-s1.s1`
- `005-p1.p1`

> **Note:** If you want to verify that everything is correct, here are the SHA-256 checksums for each file:  
> 005-s1.s1 original: `a7124fdb61bc9603884507cc1e92cf58de35f67c7226ff46125f511ab3393f5f`  
> 005-p1.p1 original: `a315c99a9bca39fd0b37e2313717013697d2534b6f7f524cf398cc27e4278915`  
> 005-s1.s1 patched: `a1b94cdf1eda89f294666a2dcd3547314eb856b6e91a6db6fb29a9b97acd0ff1`  
> 005-p1.p1 patched French/English: `a376a41f7e415a05edee410629ce738310e955f243a4524f92221f3fa020abf1`  
> 005-p1.p1 patched English/Engrish: `2158117de70847a70eed789ce5289c623a60abe78feab3f0c06b5466646aafd8`

#### Playing on MAME / Final Burn
1. In the `maglord_acfh` folder, create a zip archive containing `005-s1.s1` and `005-p1.p1` and name it `maglordh.zip`
2. Place it in MAME’s `roms` folder alongside the original `maglord.zip` (no need to modify the latter)
3. Launch the game via command line: `mame maglordh`. The graphical UI cannot be used because it blocks modified ROMs from launching.

#### Playing on Modded Switch (LayeredFS)
1. Requirement: you must have the ACA version of Magician Lord installed
2. In the `maglord_acfh` folder, gzip the files `005-s1.s1` and `005-p1.p1` and rename them to `p1.bin.gz` and `s1.bin.gz` respectively
3. On your Switch SD card, create the folder `/atmosphere/contents/01007920038F6000/romfs`
4. Copy both `p1.bin.gz` and `s1.bin.gz` there
5. Launch the game (ignore the startup error message)

#### Playing on Darksoft
1. In the `maglord_acfh` folder, rename `005-s1.s1` to `srom` and `005-p1.p1` to `prom`
2. Retrieve the Darksoft ROM, which is a folder named `maglordh` containing: `crom0`, `fpga`, `m1rom`, `prom`, `srom`, and `vroma0`. Replace `prom` and `srom` with the files from step 1.
3. Copy this folder to your Darksoft SD card

#### Playing on Analogue Pocket
1. Requirement: you must have the Neo-Geo core installed on openFPGA
2. Follow the "Playing on Darksoft" instructions above to create the ROM (a folder named `maglordh`)
3. Rename the folder `maglordh` to `maglord_acfh`
4. On your Analogue Pocket SD card, copy this folder to `/Assets/ng/common/`
5. Then go to your chosen core (e.g. `/Assets/ng/Mazamars312.NeoGeo`), where you’ll find many JSON files (one per game)
6. Duplicate `Magician Lord (AES).json` and rename it to `Magician Lord (Again changes from Hell).json`
7. Edit the file `Magician Lord (Again changes from Hell).json` and replace `"data_path": "maglordh"` with `"data_path": "maglord_acfh"`
8. In the game list, launch `Magician Lord (Again changes from Hell)`

#### Generating a .neo file to play on MisterFPGA, NeoSD, or the Geolith emulator
1. Requirement: have the tool [neosdconv](https://github.com/city41/neosdconv) installed
2. Retrieve the MAME ROM `maglord.zip` and extract it. Get the files `005-c1.c1`, `005-c2.c2`, `005-c3.c3`, `005-c4.c4`, `005-c5.c5`, `005-c6.c6`, `005-m1.m1`, `005-v11.v11`, `005-v21.v21`, and `005-v22.v22`, and copy them into the `maglord_acfh` folder (be careful not to overwrite the two existing files)
3. From the parent directory of `maglord_acfh`, run the following command:  
