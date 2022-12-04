# Convert RPG Maker VX(Ace) game to MV(MZ)

## Before the converting
![화면 캡처 2022-12-04 122023](https://user-images.githubusercontent.com/65770938/205474301-9c0bc625-6027-450a-9c44-fd8157bd2708.png)

Please check the DATA folder and the Game.rvproj(2)(RPGVX(Ace)Project) file exists in your game folder.

## Requirements
- An RPG Maker game you want to convert
- RPG Maker VX(Ace) and MV(MZ) program
- Text Editor (Recommended VSCode)
- Waifu2X (used for upscaling images for conversion)
### Important
- Script file to conversion
Download from [here](https://forums.rpgmakerweb.com/index.php?threads/vx-ace-to-mv-converter.45296) or directly from [here](https://pastebin.com/dl/MBxUzQwP)
## RPG Maker VX(Ace) decrypter (Skip this step if you are satisfied with the requirements.)
- Use this [Tool](http://rpgcrisis.net/forums/files/file/65-rgssad-rgss2a-rgss3a-decrypter/) or you can download directly [here](https://github.com/Udtshi/RPG-Maker-converter/releases)

## Convert
### 1. Open RPG Maker VX(Ace) program
  Open decryped project file
  Go to Tools - Script Editor
  Copy the downloaded script and paste it `ABOVE` the `MAIN bench`
![화면 캡처 2022-12-04 121911-1](https://user-images.githubusercontent.com/65770938/205475688-4c51743a-8528-41c1-a4a3-c846f7b3aa6b.png)

### 2. Convert game file
  When the game starts with playtest(F12 key), the convert script will be launched with a black screen. Please be patient to wait.
  After the title appears, close the game window and check the game folder. mv-data folder will be created.
![화면 캡처 2022-12-04 122101-1](https://user-images.githubusercontent.com/65770938/205475945-0da81c94-5842-4cd4-a929-87223633efb9.png)

All we need to do is copy the converted JSON file.

### 3. Open RPG Maker MV(MZ) program
  Go to File and create new project.
![화면 캡처 2022-12-04 122846](https://user-images.githubusercontent.com/65770938/205476114-e0b31a5b-e419-4be5-9aa1-7f5e8c3bc4bf.png)
  Go to `Documents\RMMZ\"Your project"` and overwrite converted JSON files into the data folder.

![화면 캡처 2022-12-04 122917](https://user-images.githubusercontent.com/65770938/205476123-69f7fdf2-b801-485b-80eb-995a1015db05.png)
Close the project WITHOUT SAVING the project and open it again.

![화면 캡처 2022-12-04 124036](https://user-images.githubusercontent.com/65770938/205476265-e0896d59-5985-42c2-a6e1-b9c412cfcec5.png)
  VX(Ace) game data have been loaded successfully.
  But as you can see, map data looks messy. It means you have to convert not only map data but also pictures too.

### 4. Upscale pictures 
  RPG Maker VX(Ace) used a 544 x 416 for game resolution, and 32 x 32 for a block of tiles. but updated to MV(MZ), it changed to 816 x 624, and 48 x 48 each, a 1.5x increased.
  So, we have to upscale images with a 1.5x increase on Waifu2X.
![화면 캡처 2022-12-04 122635-1](https://user-images.githubusercontent.com/65770938/205476946-5657b133-e486-4297-a732-3403a0b68bb6.png)
  Open Waifu2X, and set the size. Drag or click the Browse button to select the `Graphics` folder in your VX(Ace) game folder.
  When the processing has been done, Graphics(your selected option) folder is created. Enter the folder, select all the folders, overwrite to MV(MZ) project folder `Documents\RMMZ\"your project"\img`.
  
![화면 캡처 2022-12-04 123925](https://user-images.githubusercontent.com/65770938/205477127-e2eee6bb-38de-44ec-a8ae-ef3109724a6b.png)
The messy map data has been gone!
