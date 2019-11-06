# Telegram
该脚本，可以获取群成员、群聊天记录、用户所加的群的信息
可以实现单/多用户，轮回加群。

依赖安装：
  https://docs.telethon.dev/en/latest/basic/installation.html
          '''
  Installation
        Telethon is a Python library, which means you need to download and install Python from https://www.python.org/downloads/ if you haven’t already. Once you have Python installed, run:

        pip3 install -U telethon --user
        To install or upgrade the library to the latest version.

        Installing Development Versions
        If you want the latest unreleased changes, you can run the following command instead:

        pip3 install -U https://github.com/LonamiWebs/Telethon/archive/master.zip --user
        Note

        The development version may have bugs and is not recommended for production use. However, when you are reporting a library bug, you should try if the bug still occurs in this version.

        Verification
        To verify that the library is installed correctly, run the following command:

        python3 -c "import telethon; print(telethon.__version__)"
        The version number of the library should show in the output.

        Optional Dependencies
        If cryptg is installed, the library will work a lot faster, since encryption and decryption will be made in C instead of Python. If your code deals with a lot of updates or you are downloading/uploading a lot of files, you will notice a considerable speed-up (from a hundred kilobytes per second to several megabytes per second, if your connection allows it). If it’s not installed, pyaes will be used (which is pure Python, so it’s much slower).

        If pillow is installed, large images will be automatically resized when sending photos to prevent Telegram from failing with “invalid image”. Official clients also do this.

        If aiohttp is installed, the library will be able to download WebDocument media files (otherwise you will get an error).

        If hachoir is installed, it will be used to extract metadata from files when sending documents. Telegram uses this information to show the song’s performer, artist, title, duration, and for videos too (including size). Otherwise, they will default to empty values, and you can set the attributes manually.

        Note

        Some of the modules may require additional dependencies before being installed through pip. If you have an apt-based system, consider installing the most commonly missing dependencies:

        apt update
        apt install clang lib{jpeg-turbo,webp}-dev python{,-dev} zlib-dev
        pip install -U --user setuptools
        pip install -U --user telethon cryptg pillow
        Thanks to @bb010g for writing down this nice list.
        '''

主要配置文件：
client_config ---> 用户信息配置文件
config_final ---> 获取聊天信息、加群信息、用户信息等
tg_add_group_final ---> 用户加群脚本

获取信息运行顺序：
1、client_config
  需要手动添加用户api_id api_hash phone
  (api_id 获取地址：https://my.telegram.org/auth)
2、更改 config_final 中的需要更改区域（已用#号标注）
3、运行 config_final 文件即可

用户加群运行顺序：
1、需要提供一个待加群的文件，文件内为需要添加的群的链接 。仅限于：
      t.me/joinchat/AAAAAFgE0vF0JpV4_vky1A
      t.me/STunionn
   此两种类型链接
2、client_config配置
3、tg_add_group_final
  将第一步的文件地址，添加到该文件中的路径上。已用#标注出来
4、运行tg_add_group_final 文件即可
