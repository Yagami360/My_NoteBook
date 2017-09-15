# 電子回路 [Electronic circuit]

電子回路に関してまとめたオンラインマイノートです。今後も随時追加予定です。

This is my notebook that summarizes about "Electronic circuit". I will add contents as needed.

>Twitterモーメント：https://twitter.com/i/moments/781974719750742016
![twitter_ _](https://user-images.githubusercontent.com/25688193/29314651-dd4b7282-81f9-11e7-99b5-7d2cef223481.jpg)

## 項目 [Contents]
1. [基本回路、素子](#ID_1)
    1. [入出力インピーダンス [input impedance]](#ID_1-1)
    1. [抵抗 [resistor]](#ID_1-2)
        1. [プルアップ抵抗 [pull-up resistor]・プルダウン抵抗 [pull-down resistor]](#ID_1-2-1)
    1. [コンデンサー [capacitor]](#ID_1-3)
    1. [トランジスター [transistor]](#ID_1-4)
    1. [FET [Field effect transistor]（電界効果トランジスタ）](#ID_1-5)
        1. [MOS-FET [metal-oxide-semiconductor field-effect transistor]](#ID_1-5-1)
        1. [CMOS-FET [Complementary MOS]](#ID_1-5-2)    
    1. [ダイオード](#ID_1-6)
        1. [ツェナーダイオード](#ID_1-6)
    1. [オペアンプ](#ID_1-7)
        1. [ボルテージフォロワ（バッファ回路）](#ID_1-7-1)
        1. [非反転増幅回路](#ID_1-7-2)
        1. [反転増幅回路](#ID_1-7-3)
        1. [コレパレーター [comparator]](#ID_1-7-4)    
    1. [LED](#ID_1-9)    
    1. [センサー [sensor]](#ID_1-10)
        1. [温度センサー（サーミスタ）[thermistor]](#ID_1-10-1)
1. [IC [Integrated Circuit]（集積回路）](#ID_2)
    1. [モータードライバー IC [motor diver IC]](#ID_2-1)
    2. [CAN トランシーバー、CAN コントローラー](#ID_2-2)
1. [応用回路](#ID_4)
    1. [CR フィルタ回路 [HPF : High-pass filter], [LPF : Low-pass filter]](#ID_4-1)
    1. [DC-DC コンバータ [DC-DC Converter]](#ID_4-2)
    1. [発振回路 [electronic oscillator]](#ID_4-3)
    1. [タイマー回路](#ID_x-x)
    1. [回転センサー回路](#ID_x-x)
    1. [タイムラグユニット回路](#ID_x-x)
1. [その他](#ID_5)
    1. [基板（プリントプレート）](#ID_5-1)
    1. [漏れ電流（リーク電流）[leakage current]](#ID_5-2)
    1. [サージ電圧 [surge voltage]](#ID_5-3)
    1. [アクチュエータ [actuator]](#ID_5-4)
        1. [正逆タイプ](#ID_5-4-1)
        1. [1wayタイプ](#ID_5-4-2)    
    1. [ブロアレジスター](#ID_5-5)
    1. [ブラシモーター（ブロアモーター等）](#ID_5-6)
        1. [ブラシモーターとブラシノイズ](#ID_5-6)
    1. [](#ID_5-x)

<a id="ID_1"></a>

## 基本回路、素子

<a id="ID_1-1"></a>

### 入出力インピーダンス
![default](https://user-images.githubusercontent.com/25688193/29314783-92dc9d06-81fa-11e7-8e2a-4be1c4b8bb23.jpg)

<a id="ID_1-2"></a>

### 抵抗 [resistor]
![image](https://user-images.githubusercontent.com/25688193/30503856-d11713d4-9aa6-11e7-81a2-616fd736991b.png)

<a id="ID_1-2-1"></a>

#### プルアップ抵抗 [pull-up resistor]・プルダウン抵抗 [pull-down resistor]
![twitter_ _ 1-1_161015](https://user-images.githubusercontent.com/25688193/29314661-e820ec78-81f9-11e7-8f99-ee603353e5f8.png)
![twitter_ _ 1-2_161015](https://user-images.githubusercontent.com/25688193/29314660-e80d915a-81f9-11e7-9fd1-d101dac95cb2.png)

<a id="ID_1-3"></a>

### コンデンサー [capacitor]
![twitter_ _ 1-1_161015](https://user-images.githubusercontent.com/25688193/29314686-08d4d1c8-81fa-11e7-9c08-fbcf56da236d.png)

<a id="ID_1-4"></a>

### トランジスター [transistor]
![twitter_ _ 1-1_161015](https://user-images.githubusercontent.com/25688193/29314671-f3b951ec-81f9-11e7-84a0-49adf1ff1409.png)

<a id="ID_1-5"></a>

### FET [Field effect transistor]（電界効果トランジスタ）

<a id="ID_1-5-1"></a>

#### MOS-FET [metal-oxide-semiconductor field-effect transistor]
![twitter_ _mos-fet1-1_161015](https://user-images.githubusercontent.com/25688193/29314678-fc348120-81f9-11e7-927b-f16edaf60933.png)

<a id="ID_1-5-2"></a>

#### CMOS-FET [Complementary MOS]
![twitter_ _cmos-fet1-1_161015](https://user-images.githubusercontent.com/25688193/29314679-fc365f68-81f9-11e7-968a-326a59cc1580.png)
![twitter_ _cmos-fet1-2_161015](https://user-images.githubusercontent.com/25688193/29314676-fc31f252-81f9-11e7-8747-0c9d9ebd8b0e.png)

<a id="ID_1-6"></a>

### ダイオード [diode]

<a id="ID_1-6-1"></a>

#### ツェナーダイオード [Zener diode]
![twitter_ _ _161015](https://user-images.githubusercontent.com/25688193/29314731-5314441c-81fa-11e7-8e8f-82f8107f1ecc.png)

<a id="ID_1-7"></a>

### オペアンプ [operational amplifier]
![image](https://user-images.githubusercontent.com/25688193/30503335-c6a80482-9aa4-11e7-9058-dd47159de3d3.png)

<a id="ID_1-7-1"></a>

#### ボルテージフォロワ（バッファ回路）[Buffer]
![image](https://user-images.githubusercontent.com/25688193/30504578-a07fe274-9aaa-11e7-939c-716083c212e1.png)
![image](https://user-images.githubusercontent.com/25688193/30504625-dd347748-9aaa-11e7-8f60-a85bf46e2aa2.png)

<a id="ID_1-7-2"></a>

#### 非反転増幅回路

<a id="ID_1-7-3"></a>

#### 反転増幅回路

<a id="ID_1-7-4"></a>

### コレパレーター [comparator]

<a id="ID_1-9"></a>

## LED

<a id="ID_1-10"></a>

### センサー [sensor]

<a id="ID_1-10-1"></a>

#### 温度センサー（サーミスタ）[thermistor]
![twitter_ _ 1-1_161022](https://user-images.githubusercontent.com/25688193/29314758-6785d744-81fa-11e7-8d69-8a3ebf43301f.png)


<a id="ID_3"></a>

## IC

<a id="ID_3-1"></a>

### モータードライバー IC [moter driver IC]
![image](https://user-images.githubusercontent.com/25688193/30502994-7b808250-9aa3-11e7-886e-bd68c4880274.png)
![image](https://user-images.githubusercontent.com/25688193/30503246-86e85cb6-9aa4-11e7-84e0-9c6e731ca5c0.png)
![image](https://user-images.githubusercontent.com/25688193/30503302-ae6eba82-9aa4-11e7-800d-6a4518587236.png)

<a id="ID_3-2"></a>

### CAN トランシーバー
![image](https://user-images.githubusercontent.com/25688193/30503809-9ea88f0e-9aa6-11e7-9ba5-8b31ec9d0bf9.png)
![image](https://user-images.githubusercontent.com/25688193/30503842-b6cbd74e-9aa6-11e7-92d3-e2164bcef9dc.png)

<a id="ID_4"></a>

## 応用回路

<a id="ID_4-1"></a>

### CR フィルタ [HPF : High-pass filter], [LPF : Low-pass filter]
![image](https://user-images.githubusercontent.com/25688193/30502803-bf044558-9aa2-11e7-9f60-6e2e791bd8ab.png)
![image](https://user-images.githubusercontent.com/25688193/30502843-eb36466c-9aa2-11e7-96c1-da5908820ad6.png)


<a id="ID_4-2"></a>

### DC-DC コンバーター [DC-DC Converter]
![image](https://user-images.githubusercontent.com/25688193/30502934-3c24eb1e-9aa3-11e7-94e2-2e2fcc0c6b7c.png)
![image](https://user-images.githubusercontent.com/25688193/30502958-5323dece-9aa3-11e7-9945-938e02ca4a60.png)

<a id="ID_4-3"></a>

### 発振回路 [electronic oscillator]
![twitter_ _ 1-1_161015](https://user-images.githubusercontent.com/25688193/29314664-ec947626-81f9-11e7-9c4e-e889689595e4.png)
![twitter_ _ 1-2_161015](https://user-images.githubusercontent.com/25688193/29314665-ec94bb36-81f9-11e7-8059-c50b282dd818.png)




<a id="ID_5"></a>

## その他

<a id="ID_5-1"></a>

### 基板（プリントプレート）
![default](https://user-images.githubusercontent.com/25688193/29314781-9180516e-81fa-11e7-87d2-0a6f74b26c8f.jpg)

<a id="ID_5-2"></a>

### 漏れ電流（リーク電流）[leakage current]
![twitter_ _ 1-1_161015](https://user-images.githubusercontent.com/25688193/29314669-f0e66b4e-81f9-11e7-8b46-e015a20c08c1.png)

<a id="ID_5-3"></a>

### サージ電圧 [surge voltage]
![twitter_ _ 1-1_161022](https://user-images.githubusercontent.com/25688193/29314699-243154dc-81fa-11e7-9c2a-6dd07158b2d9.png)

<a id="ID_5-4"></a>

### アクチュエータ [actuator]

<a id="ID_5-4-1"></a>

#### 正逆タイプ
アクチュエータのダンパが双方向に駆動するアクチュエータ。

<a id="ID_5-4-2"></a>

#### 1wayタイプ
アクチュエータのダンパが単方向に駆動するアクチュエータ。</br>
回転開始のSWを押下すると、外部端子１・外部端子２のどちらか一方をGNDに落とすとその位置（外部端子１ or 外部端子２位置）にコントロ－ルされる。</br>
目標位置に到達すると、ACT内部で外部端子（外部端子１or外部端子２）が駆動電圧となり、モーター間電圧が0V状態となり、（外部端子１ or 外部端子２の目標位置で）停止する。</br>
この後、再度、回転開始SWを押下すると同方向に回転を再開する。
![image](https://user-images.githubusercontent.com/25688193/30503768-6d7910d4-9aa6-11e7-897a-577e429dba41.png)

<a id="ID_5-5"></a>

### ブロアレジスター
![image](https://user-images.githubusercontent.com/25688193/30503507-7d519fa4-9aa5-11e7-8219-e4693d9026ea.png)
![image](https://user-images.githubusercontent.com/25688193/30503536-95115db4-9aa5-11e7-955c-88e758ec4f6a.png)

<a id="ID_5-6"></a>

### ブラシモーター（ブロアモーター等）
![image](https://user-images.githubusercontent.com/25688193/30503430-25614b78-9aa5-11e7-960d-146554abd1f8.png)

<a id="ID_5-6-1"></a>

#### ブラシモーターとブラシノイズ
![image](https://user-images.githubusercontent.com/25688193/30503459-3ffd9f7c-9aa5-11e7-8d90-e4d7ce0bbd6d.png)
