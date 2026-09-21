# AIRUNS问数 口播成片 v2

竖屏口播约 45 秒。聊天附件会下成 0KB，请用下面方式下载。

> **状态（2026-09-21 23:28 CST）**：base64 分片上传进行中。完整分片就绪后，用下面命令合成。

## Mac 一键合成（40KB 分片方案）

分片路径：`chunks/p000` … `chunks/p106`（共 107 个，每片 ≤40000 字符 base64）

```bash
cd ~/Downloads
mkdir -p airuns-promo && cd airuns-promo
for i in $(seq -f '%03g' 0 106); do
  curl -fsSL -o p$i "https://raw.githubusercontent.com/tllrhry/airuns-wenshu-promo-v2/main/chunks/p$i"
done
cat p000 p001 p002 p003 p004 p005 p006 p007 p008 p009 \
    p010 p011 p012 p013 p014 p015 p016 p017 p018 p019 \
    p020 p021 p022 p023 p024 p025 p026 p027 p028 p029 \
    p030 p031 p032 p033 p034 p035 p036 p037 p038 p039 \
    p040 p041 p042 p043 p044 p045 p046 p047 p048 p049 \
    p050 p051 p052 p053 p054 p055 p056 p057 p058 p059 \
    p060 p061 p062 p063 p064 p065 p066 p067 p068 p069 \
    p070 p071 p072 p073 p074 p075 p076 p077 p078 p079 \
    p080 p081 p082 p083 p084 p085 p086 p087 p088 p089 \
    p090 p091 p092 p093 p094 p095 p096 p097 p098 p099 \
    p100 p101 p102 p103 p104 p105 p106 > all.b64
base64 -D -i all.b64 -o AIRUNS-wenshu-promo-v2.mp4
ls -lh AIRUNS-wenshu-promo-v2.mp4
# expect: size 3189824, md5 b2b4a579f9c4183f3c1e10fd65f997d4
md5 AIRUNS-wenshu-promo-v2.mp4
open AIRUNS-wenshu-promo-v2.mp4
```

期望：**3189824** 字节，md5 **`b2b4a579f9c4183f3c1e10fd65f997d4`**。

清单：https://raw.githubusercontent.com/tllrhry/airuns-wenshu-promo-v2/main/chunks/MANIFEST.txt

仓库：https://github.com/tllrhry/airuns-wenshu-promo-v2

## Download & assemble (Mac)

Pieces: `chunks/p000` … `chunks/p106` (107 files). Ignore any `*.w` leftovers.

```bash
cd ~/Downloads && mkdir -p airuns-promo && cd airuns-promo
for i in $(seq -f '%03g' 0 106); do
  curl -fsSL -o "p$i" "https://raw.githubusercontent.com/tllrhry/airuns-wenshu-promo-v2/main/chunks/p$i"
done
cat $(seq -f 'p%03g' 0 106) > all.b64
base64 -D -i all.b64 -o AIRUNS-wenshu-promo-v2.mp4
ls -lh AIRUNS-wenshu-promo-v2.mp4
md5 -q AIRUNS-wenshu-promo-v2.mp4   # expect b2b4a579f9c4183f3c1e10fd65f997d4
open AIRUNS-wenshu-promo-v2.mp4
```

Expected size: **3189824** bytes.

Local copy (preferred if Grok Bot is connected):  
`~/projects/nanjingyinhang/skilltohtml/exports/AIRUNS-wenshu-promo-v2.mp4`
