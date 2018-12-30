# Note day2

* ORG
  * ORG 0x7c00
  * この機械言が実行時にPCのメモリのどこに読み込まれることになるか？
* JMP
  * goto
* entry:
  * ラベル
* MOV
  * MOV AX,0
    * AXに0を代入する
    * AXはレジスタ。レジスタはCPUの変数
* レジスタ
  * AX: アキュムレーター, CX: カウンタとか
  * 各種の演算にAXを使うと、機械語が簡潔にかけたりする

```
ADD CX,0x1234 => 81 c1 34 12
ADD AX,0x1234 => 05 34 12
```

* ラベル
  * ラベルはただの数字。なので代入できる
* []がつく場合
  * MOV命令では、レジスタだけでなく、メモリの番地を指定することができる
  *メモリの番地を指定する場合は、データサイズも指定する
  * `MOV WORD [678],123`
    * 678番地に16bitの数値として123を書き込む
* CMP
  * compare
  * `CMP AL,0`
* JE
  * jump if equal
* INT命令
  * ソフトウェア割り込み命令
  * とりあえずこれで、BIOSの関数を呼ぶことができる
  * [BIOSサービス割り込み一覧](http://softwaretechnique.jp/OS_Development/Tips/bios_services.html)
  * UEFIだと、アセンブラレベルで呼び出し変えているのか....?
* ORGの番地について
  * 0x7c00はブートセクタが読み込まれるアドレス

  ## Ref
  * http://oswiki.osask.jp/?%28AT%29BIOS
  * https://qiita.com/pollenjp/items/d15fce401bccd37e8059