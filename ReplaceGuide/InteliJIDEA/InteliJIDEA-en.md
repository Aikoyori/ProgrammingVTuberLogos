# Replace the IDEA boot image

****

## 2024 version

- Back up the file `C:\Users\userName\AppData\Local\Programs\IntelliJ IDEA Ultimate\lib\product.jar`
- Create a folder named `test` for modification, and put `product.jar` into this folder
- Open `Windows Powershell` terminal in the `test` folder, execute `jar -xvf .\product.jar` to decompress
- Open `idea_logo@2x.png` and `idea_logo.png` with the built-in paint software of Windows, press `ctrl + a` to select all and delete the image
- Open the replacement image with the built-in paint software of Windows, then press `ctrl + a` to select all and set the pixel size to correspond to the two files above. Then copy this replacement image to the two files above, make sure the pixel sizes are the same, save it after replacement
- Delete all files in the `test` folder, then drag the backed up `product.jar` into it, and also drag the replaced `idea_logo@2x.png` and `idea_logo.png`
- Execute the command ` jar -uvf product.jar idea_logo.png` and ` jar -uvf product.jar idea_logo@2x.png` in the terminal to complete the replacement, then put `product.jar` back to its original position to replace
- Then go to `C:\Users\userName\AppData\Local\JetBrains\IntelliJIdea2024.1\splash\`, delete all the cached files in the `splash` folder.

****

## 2023 and lower version

- Back up the file `C:\Users\userName\AppData\Local\Programs\IntelliJ IDEA Ultimate\lib\app.jar`
- Create a folder named `test` for modification, and put `app.jar` into this folder
- Open `Windows Powershell` terminal in the `test` folder, execute `jar -xvf .\app.jar` to decompress
- Open `idea_logo@2x.png` and `idea_logo.png` with the built-in paint software of Windows, press `ctrl + a` to select all and delete the image
- Open the replacement image with the built-in paint software of Windows, then press `ctrl + a` to select all and set the pixel size to correspond to the two files above. Then copy this replacement image to the two files above, make sure the pixel sizes are the same, save it after replacement
- Delete all files in the `test` folder, then drag the backed up `app.jar` into it, and also drag the replaced `idea_logo@2x.png` and `idea_logo.png`
- Execute the command ` jar -uvf app.jar idea_logo.png` and ` jar -uvf app.jar idea_logo@2x.png` in the terminal to complete the replacement, then put `app.jar` back to its original position to replace
- Then go to `C:\Users\userName\AppData\Local\JetBrains\IntelliJIdea2023.3\splash\`, delete all the cached files in the `splash` folder.
