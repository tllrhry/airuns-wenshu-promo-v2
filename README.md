# AIRUNS问数 口播成片 v2

竖屏口播约 45 秒。聊天附件会下成 0KB，请用下面方式下载。

## Mac 一键合成

```bash
cd ~/Downloads
mkdir -p airuns-promo && cd airuns-promo
for i in $(seq -w 0 23); do
  curl -fsSL -o c$i "https://raw.githubusercontent.com/tllrhry/airuns-wenshu-promo-v2/main/chunks/c$i"
done
cat c0* > all.b64
base64 -D -i all.b64 -o AIRUNS-wenshu-promo-v2.mp4
ls -lh AIRUNS-wenshu-promo-v2.mp4
open AIRUNS-wenshu-promo-v2.mp4
```

期望约 **3.1MB**。

仓库：https://github.com/tllrhry/airuns-wenshu-promo-v2
