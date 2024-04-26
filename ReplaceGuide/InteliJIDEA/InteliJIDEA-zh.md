# 替换 IDEA 启动图片

****

## 2024 版本

- `C:\Users\userName\AppData\Local\Programs\IntelliJ IDEA Ultimate\lib\product.jar` 备份该文件
- 创建一个文件夹 `test` 用来修改，将 `product.jar` 放到该文件夹下
- 在 `test` 文件夹下打开 `windows powershell` 终端，执行 `jar -xvf .\product.jar` 解压
- 将其中的  `idea_logo@2x.png` 和 `idea_logo.png` 用 `windows` 自带的画图软件打开，`ctrl + a` 全选删除图片
- 将需要替换的图片用画图打开，然后 `ctrl + a` 选中全部并设置图片像素大小分别和上面两个照应，然后复制这个要替换的图片到上面两个文件中，一定要保证像素大小是一致的，替换之后保存一下
- 之后把 `test` 文件夹删完，将原来备份过的 `product.jar` 拖进来，把替换过图片的 `idea_logo@2x.png` 和 `idea_logo.png` 也拖进来
- 在终端执行命令 ` jar -uvf product.jar idea_logo.png` 和 ` jar -uvf product.jar idea_logo@2x.png` 完成替换，然后把 `product.jar` 丢回原来的位置，替换掉
- 然后到 `C:\Users\userName\AppData\Local\JetBrains\IntelliJIdea2024.1\splash\` 把 `splash` 里面缓存的文件全部删掉即可

****

## 2023 版本

- `C:\Users\userName\AppData\Local\Programs\IntelliJ IDEA Ultimate\lib\app.jar` 备份该文件
- 创建一个文件夹 `test` 用来修改，将 `app.jar` 放到该文件夹下
- 在 `test` 文件夹下打开 `windows powershell` 终端，执行 `jar -xvf .\app.jar` 解压
- 将其中的  `idea_logo@2x.png` 和 `idea_logo.png` 用 `windows` 自带的画图软件打开，`ctrl + a` 全选删除图片
- 将需要替换的图片用画图打开，然后 `ctrl + a` 选中全部并设置图片像素大小分别和上面两个照应，然后复制这个要替换的图片到上面两个文件中，一定要保证像素大小是一致的，替换之后保存一下
- 之后把 `test` 文件夹删完，将原来备份过的 `app.jar` 拖进来，把替换过图片的 `idea_logo@2x.png` 和 `idea_logo.png` 也拖进来
- 在终端执行命令 ` jar -uvf app.jar idea_logo.png` 和 ` jar -uvf app.jar idea_logo@2x.png` 完成替换，然后把 `app.jar` 丢回原来的位置，替换掉
- 然后到 `C:\Users\userName\AppData\Local\JetBrains\IntelliJIdea2023.1\splash\` 把 `splash` 里面缓存的文件全部删掉即可