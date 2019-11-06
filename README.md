# Telegram
该脚本，可以获取群成员、群聊天记录、用户所加的群的信息
可以实现单/多用户，轮回加群。

【依赖安装：】
  https://docs.telethon.dev/en/latest/basic/installation.html

【主要配置文件：】
client_config ---> 用户信息配置文件
config_final ---> 获取聊天信息、加群信息、用户信息等
tg_add_group_final ---> 用户加群脚本

【获取信息运行顺序：】
1、client_config
  需要手动添加用户api_id api_hash phone
  (api_id 获取地址：https://my.telegram.org/auth)
2、更改 config_final 中的需要更改区域（已用#号标注）
3、运行 config_final 文件即可

【用户加群运行顺序：】
1、需要提供一个待加群的文件，文件内为需要添加的群的链接 。仅限于：
      t.me/joinchat/AAAAAFgE0vF0JpV4_vky1A
      t.me/STunionn
   此两种类型链接
2、client_config配置
3、tg_add_group_final
  将第一步的文件地址，添加到该文件中的路径上。已用#标注出来
4、运行tg_add_group_final 文件即可
