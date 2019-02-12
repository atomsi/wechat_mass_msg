# wechat_mass_msg
wechat mass msg delivery tool,  it can send out same message to all of your friend, even more than 200
## 1. 生产登录二维码, 需扫描登录
    import itchat
    import pandas as pd
    # 登录，执行本函数，itchat自动把二维码下载到本地并打开，手机微信扫描即可。
    itchat.auto_login()
## 2. 获取微信朋友清单
    friendList = itchat.get_friends(update=True)[1:]
    len(friendList)
## 3. 发送信息到文件传输助手
    import time SINCERE_WISH = u'*与家人给您拜年！辞旧迎新，感谢过去各位的帮助与支持，新年到，祝大家身体健康，万事如意！'

    itchat.send( SINCERE_WISH, 'filehelper')
## 4. 循环发送
    count = 0
    for friend in friendList:
        itchat.send( SINCERE_WISH, friend['UserName'])
        time.sleep(5)
        count += 1
    print("----end----")
