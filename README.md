# Convert RPG Maker VX(Ace) game to MV(MZ)

## Before the game convert
### Requirements
- An `RPG Maker game` you want to convert
#### Core script file
- Script file required for conversion
Download from [here](https://forums.rpgmakerweb.com/index.php?threads/vx-ace-to-mv-converter.45296) or directly from [here](https://pastebin.com/dl/MBxUzQwP)
#### Tools
- `RPG Maker VX(Ace) and RPG Maker MV(MZ) program`
- `Text editor` (Recommended VSCode or notepad++)
- `Waifu2X` (used for upscaling images for conversion)
- `Sound editor software` (GoldWave, Audacity, etc...)
#### Core files in the source game folder
- `DATA folder`
- `Game.rvproj` (RPGVX Project) or `Game.rvproj2` (RPGVXAce Project)
![화면 캡처 2022-12-04 122023](https://user-images.githubusercontent.com/65770938/205474301-9c0bc625-6027-450a-9c44-fd8157bd2708.png)

If there's no Data folder and no Project file, please move to the next step.

## RPG Maker VX(Ace) decrypter ([Skip](https://github.com/Udtshi/RPG-Maker-converter/blob/main/README.md#Convert-the-game) this step if you are satisfied with the [requirements](https://github.com/Udtshi/RPG-Maker-converter#requirements).)
- Download this tool on the [website](http://rpgcrisis.net/forums/files/file/65-rgssad-rgss2a-rgss3a-decrypter/) or you can download directly from [here](https://github.com/Udtshi/RPG-Maker-converter/releases)
- Search Game.rgss3a (encrypted game data) file.
![화면 캡처 2022-12-04 161211-1](https://user-images.githubusercontent.com/65770938/205479010-b450547e-9d66-4083-85c4-62bab643f1b5.png)

Open [RGSSAD - RGSS2A - RGSS3A Decrypter] program

![화면 캡처 2022-12-04 161416-1](https://user-images.githubusercontent.com/65770938/205479113-514c876d-dbf4-4ebf-8c5b-b835eccba899.png) |![화면 캡처 2022-12-04 161729](https://user-images.githubusercontent.com/65770938/205479114-587b2428-b213-4b71-b6a4-11903e979caf.png)
---| ---|
`Extract all files` and `Generate Game project files` to match your game version. | `Graphics`(picture data) and `Data`(remaining data) folders are created under the Extract folder. Game.rvproj(2) file has been created.

Copy these folder and project files to your source game folder, and delete Game.rgss3a (encrypted game data) file.

## Convert the game
### 1. Open RPG Maker VX(Ace) program
  Open `decryped project file`(Game.rvproj(2)). Go to Tools - Script Editor, copy the downloaded script and paste it `ABOVE` the `MAIN bench`
![화면 캡처 2022-12-04 121911-1](https://user-images.githubusercontent.com/65770938/205475688-4c51743a-8528-41c1-a4a3-c846f7b3aa6b.png)


### 2. Convert game file
  When the game starts with playtest(F12 key), the convert script will be launched with a black screen. Please be patient to wait.
  After the title appears, close the game window and check the game folder. mv-data folder will be created.
![화면 캡처 2022-12-04 122101-1](https://user-images.githubusercontent.com/65770938/205475945-0da81c94-5842-4cd4-a929-87223633efb9.png)

RPG Maker VX(Ace) game data converted with JSON file. It will be used in the next step.


### 3. Open RPG Maker MV(MZ) program
  Go to File and create new project.
![화면 캡처 2022-12-04 122846](https://user-images.githubusercontent.com/65770938/205476114-e0b31a5b-e419-4be5-9aa1-7f5e8c3bc4bf.png)
  Go to `Documents\RMMZ\"Your project"` and overwrite converted JSON files into the data folder.

![화면 캡처 2022-12-04 122917](https://user-images.githubusercontent.com/65770938/205476123-69f7fdf2-b801-485b-80eb-995a1015db05.png)

Close the project `WITHOUT SAVING` the project and open it again.

![화면 캡처 2022-12-04 124036](https://user-images.githubusercontent.com/65770938/205476265-e0896d59-5985-42c2-a6e1-b9c412cfcec5.png)
  VX(Ace) game data have been loaded successfully.
  But as you can see, map data looks messy. It means you have to convert not only map data but also pictures too.


### 4. Upscale pictures 
  RPG Maker VX(Ace) used a `544 x 416` for game resolution, and `32 x 32` for a block of tiles. but updated to MV(MZ), it changed to `816 x 624`, and `48 x 48` each, a 1.5x increased.
  So, we have to upscale images with a 1.5x increase on Waifu2X.
![화면 캡처 2022-12-04 122635-1](https://user-images.githubusercontent.com/65770938/205476946-5657b133-e486-4297-a732-3403a0b68bb6.png)
  Open Waifu2X, and set the size. Drag or click the Browse button to select the `Graphics` folder in your VX(Ace) game folder.
  When the processing has been done, Graphics(your selected option) folder is created. Enter the folder, select all the folders, overwrite to MV(MZ) project folder `Documents\RMMZ\"your project"\img`.
  
![화면 캡처 2022-12-04 123925](https://user-images.githubusercontent.com/65770938/205477127-e2eee6bb-38de-44ec-a8ae-ef3109724a6b.png)
Once you close the project and reopen it, the messy map data has been gone!


### 5. Sound convert
  Unfortunately, RPG Maker MV(MZ) supports M4A and OGG audio files. I recommend converting to OGG because it can be used on PC and Android platforms.

![화면 캡처 2022-12-04 152029](https://user-images.githubusercontent.com/65770938/205477443-52d3d534-4b66-4eb5-a3e9-81049fc8ce0b.png) |![화면 캡처 2022-12-04 152043](https://user-images.githubusercontent.com/65770938/205477441-2eb51689-7710-4916-8091-b37517c2d97a.png)
-- | -- |
Add folder with `MP3`, `WAV`, `etc.` files | Select `OGG`, `44100Hz`, `192kpbs` (depended on the source file), `stereo`

![화면 캡처 2022-12-04 122506-1](https://user-images.githubusercontent.com/65770938/205477329-9a73c069-25d0-437a-986e-44c0d0421ec8.png) |![화면 캡처 2022-12-04 154019-1](https://user-images.githubusercontent.com/65770938/205478139-365acaf8-0a8b-4744-8629-f72fac1b3eff.png)
-- | -- |
Source audio file | Converted audio file

I used Batch Processing features in GoldWave. After the Processing, rename the folder name to lowercase. ex) BGM->bgm

### 6. Copy Font
![화면 캡처 2022-12-04 183409](https://user-images.githubusercontent.com/65770938/205483694-daf72cb0-0f38-48e3-9287-f6e005d3564e.png)

Head to the source `game folder\Fonts`, and copy to the converted 'game folder\Fonts'.

## Done
Go back to RPG Maker MV(MZ) program, click playtest.
![화면 캡처 2022-12-04 131043](https://user-images.githubusercontent.com/65770938/205479689-aeccfd44-0f77-475e-85fd-86a2617409fe.png) |![화면 캡처 2022-12-04 130749](https://user-images.githubusercontent.com/65770938/205479692-b3f6df90-dc60-4e49-a6bd-7fc15423eccb.png)
--- | --- |
RPG Maker VX Ace game `544 x 416` (source) | RPG Maker MZ game `816 x 624` (converted)

## Errors
RPG Maker MV(MZ) is basically operated as a javascript language.
Please click [here](https://github.com/Udtshi/RPG-Maker-converter/wiki/Home) to check more information about it.
