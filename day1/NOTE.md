# 付属CD-ROM
https://book.mynavi.jp/supportsite/detail/4839919844.html

ダウンロードしたISOイメージの中身をマウントする

```
mount -o loop -t iso9660 HariboteOS.iso /media
```

# 各種ツールのインストール

```
sudo apt install qemu
sudo apt install ghex # バイナリエディタ
sudo apt install nasm
```

# Ref
* http://www.geocities.co.jp/SiliconValley/9979/asm/asmhead.html
* http://hrb.osask.jp/wiki/?tools/nask

# Note

* helloos.imgを表示してみる。バイナリエディタの編集は諦め。
* qemu-system-i386 helloos.img
  * 無事表示された
  * i386でも,x86-64でも表示はされた。命令セットに互換性があるのか...？
* .nasをコピーして、helloos1.asmとして保存
  * tabをスペースに変換したり、先頭の空白除去したりしても問題はない様子
* nask vs nasm
  * http://hrb.osask.jp/wiki/?tools/nask に違いが書いてある
  * RESB 18
    * TIMES 18 DB 0
* アセンブラ
  * DB
    * Data Byte
    * 1byte書き込む
    * 0xeb, 0x4e
  * DW
    * Data Word. 16bit = 2byte
  * DD
    * Data Double Word. 32bit = 4byte
  * RESB
    * Reserve Byte。予約バイト
    * RESBでwarningが出る
      * ↑参照
  * $
    * この行が先頭から、何バイト目かどうか
    * nasmだとちょっと定義が違う...?
  * $$
    * ORGの番地