# マイコン [microcomputer]

マイコンに関してまとめたマイノートです。今後も随時追加予定です！

This is my notebook that summarizes about "microcomputer". I will add contents as needed.

Twitterモーメント：https://twitter.com/i/moments/781979032006963200

![twitter_ _](https://user-images.githubusercontent.com/25688193/29314524-4b65016c-81f9-11e7-8b6a-b7409839db79.png)

## 目次 [Contents]

1. [マイコン全般](#マイコン全般)
    1. ポート
    1. クロック
    1. タイマ
    1. 割り込み
    1. ウォッチドックタイマ（WDT）
    1. ADコンバータ
    1. スタンバイ機能
    1. UART通信
    1. EEPROMの制御
1. [RENESAS製マイコン](#RENESAS製マイコン)
1. [NEC製マイコン](#NEC製マイコン)
1. [低レイヤーの組み込み設計 Memo](#低レイヤーの組み込み設計Memo)


<a id="マイコン全般"></a>

## ■ マイコン全般

### ◎ ポート
![twitter_ _ 1-1_161022](https://user-images.githubusercontent.com/25688193/29314528-4f568fa2-81f9-11e7-91d7-7de8a7190ffd.png)<br>

### ◎ クロック
![twitter_ _ 1-1_161022](https://user-images.githubusercontent.com/25688193/29314536-55233872-81f9-11e7-9f9f-cfed72b9863f.png)<br>

### ◎ タイマ
![twitter_ _ 1-1_161022](https://user-images.githubusercontent.com/25688193/29314540-5965fdb6-81f9-11e7-8f31-36048d3cafbc.png)<br>


### ◎ AD コンバータ
![image](https://user-images.githubusercontent.com/25688193/47918039-b41a3800-deee-11e8-8faf-6ad4799bea81.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47918069-cac08f00-deee-11e8-8767-58fbd3d7be28.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47918174-1a9f5600-deef-11e8-9443-aa8e29e7dbd1.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47918213-34409d80-deef-11e8-9101-b54f9188a499.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47918236-46bad700-deef-11e8-8274-dc1a54df33e2.png)<br>


### ◎ UART通信
![twitter_ _uart _161106](https://user-images.githubusercontent.com/25688193/29314545-5cac243c-81f9-11e7-8790-e0d7be97b2d0.png)<br>


### ◎ EEPROM の制御
![image](https://user-images.githubusercontent.com/25688193/47918268-6f42d100-deef-11e8-8a6f-fb9d8344138d.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47918319-9ac5bb80-deef-11e8-8be9-a386eaecea06.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47918358-b3ce6c80-deef-11e8-93fd-3f1ca57dc4b8.png)<br>


<a id="RENESAS製マイコン"></a>

## ■ RENESAS製マイコン

![twitter_ _78k0_8bit 2-1_161022](https://user-images.githubusercontent.com/25688193/29314553-631325fa-81f9-11e7-85fe-a0c4d5e01320.png)<br>
![twitter_ _78k0_8bit 2-2_161022](https://user-images.githubusercontent.com/25688193/29314554-6336d9e6-81f9-11e7-891f-a27433211217.png)<br>
![twitter_ _78k0_16bit 2-1_161015](https://user-images.githubusercontent.com/25688193/29314557-6356d854-81f9-11e7-9a41-a93fa3bcaa12.png)<br>
![twitter_ _78k0_16bit 2-2_161015](https://user-images.githubusercontent.com/25688193/29314555-63418346-81f9-11e7-835a-26226c6bada8.png)<br>
![twitter_ _78k0_16bit 2-3_161015](https://user-images.githubusercontent.com/25688193/29314556-634f2a78-81f9-11e7-8313-3c33f2fe22df.png)<br>


<a id="NEC製マイコン"></a>

## ■ NEC製マイコン

![twitter_ _r8c_ 1-1_161015](https://user-images.githubusercontent.com/25688193/29314561-6b1dbc06-81f9-11e7-9c08-b39a7a25f07b.png)<br>
![twitter_ _r8c_ 1-2_161015](https://user-images.githubusercontent.com/25688193/29314562-6b406a26-81f9-11e7-9af1-bd1a1da5eb38.png)<br>


<a id="低レイヤーの組み込み設計Memo"></a>

## ■ 低レイヤーの組み込み設計 Memo

- （アセンブラで直接叩く場合の）マスカブル割り込みの割り込み受付処理
    - 割り込み要求受付後、CPUは各種フラグレジスタ（キャリーフラグ、ゼロフラグ等）、PC（プログラムカウンタ）をスタックにPushする。割り込みハンドラ復帰後（REIT命令後）、CPUはスタックにPushしていたフラグレジスタとPCをスタックからPopする。
    - 割り込みハンドラで使用するレジスタは、割り込みハンドラの先頭でユーザーによってスタックへPushする必要がある。この場合、割り込みハンドラ復帰前（REIT命令前）、ユーザーによってスタックへPushしていたレジスタをスタックからPopする必要がある。
    - あるいは割り込みハンドラの先頭でレジスタバンクの切り替えを行い、割り込みハンドラ復帰前にレジスタバンクの再切り替えを必要がある。


- 多重割り込み
    - ある割り込み処理中に、それよりも高い割り込み優先レベル（＝同時に発生した割り込み要因の優先度）の割り込みが発生した場合、割り込み処理中であっても、高優先割り込み処理を行う必要がある。<br>
    ※割り込み処理中に、それよりも低い優先レベルの割り込みが発生した場合、今の割り込み処理が終わった後、受け付けられる。

- リセットスタート直後の割り込み禁止処理
    - リセットスタート直後の割り込み禁止処理を行なうことなしに、スタックポインタや特殊レジスタの設定、RAMの初期化などを行ってしまうと、これら設定前に割り込みが発生してしまった場合に、メモリ破壊やCPUの暴走などを招いてしまう可能性がある。
    - 従って、リセットスタート直後に、割り込み禁止命令 DI で割り込み禁止とする必要がある。

- 割り込み処理中の汎用レジスタのスタックへの退避、復帰
    - 割り込み処理の先頭で、汎用レジスタのスタックへの PUSH を行わずに汎用レジスタを操作してしまうと、割り込み処理が完了して、メイン側の処理に戻った際にも、レジスタの値が変更されたままになっおり、想定外の誤動作が発生してしまう。
    - 従って、割り込み処理の先頭で汎用レジスタをPUSH、割り込み処理の最後で汎用レジスタのスタックからのPOPを行う必要がある。（※レジスタバンクの切り替えでメモリを退避、復帰している場合には不要）

- 周期的に発生する割り込みの割り込み完了タイミング
    - 周期的に発生する割り込みの割り込み処理は、次の周期での割り込み発生までに処理が完了していないと、CPUを独占してしまい、他の処理が行われなくなってしまう。
    - 従って、（処理ルート、割り込み負荷、動作温度などによらず）次の周期の割り込み発生までに処理が完了している必要がある。

- 使用しない割り込みの割り込み禁止処理
    - 使用しない割り込みに対しては、割り込み禁止処理を行っていないと、その割り込みが発生した場合に、余計な過負荷が生じてしまう。
    - 又、使用していない割り込みに対する割り込みベクターテーブルに無処理のルーチンのアドレスを登録していないと、CPU動作が保証されない懸念が生じてしまう。

- クロック信号の発信安定化待ち時間
    - 一般的に、RESET直後、プログラムはマイコン内蔵の低速オンチップオシレータで動作しているが、CPUクロックを即座に外部発振子に切り替えると、外部発振回路の発振が安定しておらず、プログラムが停止する可能性があるので、外部発振回路の発振が安定するのを待って、CPUクロックを外部発振子に切り替える必要がある。<br>
    ※ 一般的に外部発振回路の発振安定化時間は数msec～10msec程度

- クロック信号の発信安定化待ち時間
    - 一般的に、RESET直後、プログラムはマイコン内蔵の低速オンチップオシレータで動作しているが、CPUクロックを即座に外部発振子に切り替えると、外部発振回路の発振が安定しておらず、プログラムが停止する可能性があるので、外部発振回路の発振が安定するのを待って、CPUクロックを外部発振子に切り替える必要がある。<br>
    ※ 一般的に外部発振回路の発振安定化時間は数msec～10msec程度

- CPUポートの入力信号安定化待ち時間
    - 一般的に、入力信号（SW入力、センサ入力等）の供給電源投入直後は入力信号が不安定であり、安定するのには時間がかかる。入力信号を制御に使用する際は、入力回路のハードウェア特性から安定化時間を割り出し、入力信号が安定するのを待って取得する必要がある。

- リセット時のCPUポート初期設定
    - RESET後のポート初期設定時、一般的にポート方向は入力ポートに設定されているが、ポート方向を出力ポートで使用する場合に、「①ポート方向を出力ポートに設定→②ポート出力の設定」の順で設定すると、①出力ポート設定～②ポート出力の設定の間、RESET後のマイコン固有のポート初期値が誤って出力されてしまう。
    - 「①ポート出力の設定→②ポート方向を出力ポートに設定」の順で設定し、RESET後のマイコン固有のポート初期値が出力されないようにする必要がある。

