# blue
![image](https://user-images.githubusercontent.com/15976103/196897891-a9474adc-9e60-4340-9406-736829639092.png)


https://user-images.githubusercontent.com/15976103/203185034-fe1e0b6e-f373-45fe-884e-2eec649355f3.mp4


新的 PR(Issue) 来了来了来了!

## 树莓派 + [蓝牙热敏打印机](https://mobile.yangkeduo.com/goods2.html?goods_id=215919711645) + 内网穿透 + GitHub Actions


## 如何在树莓派中设置蓝牙设备并找到地址

1. bluetoothctl (以下步骤都在 ctl 中执行)
2. agent on
3. discoverable on
4. scan on --> 这步找到蓝牙热敏打印机的地址
5. trust ${地址}
6. pair ${地址}

---
利用 rfcomm 连接
```shell
sudo rfcomm connect 1 ${地址} &
```

## how to?

- raspberry(3b+) 以上有蓝牙的版本 set up bluetooth
- 内网穿透
- 更改 raspberry_printer 中的 secret （为了安全）
- 找到蓝牙设备地址
- 利用 rfcomm 连接蓝牙设备 
- 启动 server 
- 设置 GitHub Actions
- Enjoy it

## raspberry server

- pip install -r requirements.txt
- nohup python3 app.py &
- or use Gunicorn or uWSGI or others

## GitHub Actions

- change ./github/workflows/new_pr_bluetooth.yml to your own
- add secret `BLUE` in your repo (Actions secrets)
- Done or left some issues

## 小米音箱

- pip3 install git+https://github.com/yihong0618/MiService.git
- 参考 [MiService](https://github.com/yihong0618/MiService) README 增加 env -> .bashrc
- 测试 `micli 5-3 '哈哈哈哈哈您有新的PULLREQUEST请注意查收'` 看看是否成功 
- 重新部署

## 参考资料

- [DingdangD1-PoC](https://github.com/LynMoe/DingdangD1-PoC)
- [GGLyn swift version](https://github.com/Lakr233/GGLyn)
- [Cloudflare Argo Tunnel 小试：我终于可以用树莓派做网站啦](https://dmesg.app/argo-tunnel.html)
- [最像素字体](https://github.com/SolidZORO/zpix-pixel-font)

## 赞赏

- 谢谢就够了
- Just enjoy it.
