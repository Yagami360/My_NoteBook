# 情報理論[Information theory] / 情報数理

情報理論、情報数理に関してまとめたマイノートです。随時追加予定です。

This is my notebook that summarizes about "Information theory". I will add contents as needed.

> Twitterモーメント：https://twitter.com/i/moments/796112497388335105
![default](https://user-images.githubusercontent.com/25688193/30401928-f17583b8-9916-11e7-9148-6c766bff5b65.png)

## 項目 [Contents]

1. [概要、全体 MAP [Overview]](#ID_1)
1. [情報理論の基礎](#ID_2)
    1. [情報と確率](#ID2-1)
    1. [情報と確率空間 [probability space]、確率変数](#ID_2-2)
    1. [情報源 [information source]](#ID_2-3)
        1. [無記憶情報源（記憶のない情報源）[ i.i.d : independent and identically distributed ]](#ID_2-3-1)
        1. [記憶のある情報源（マルコフ情報源）](#ID_2-3-2)
    1. [通信路（情報を伝達する媒体）[channel]](#ID_2-4)
        1. [記憶のない通信路（無記憶通信路）](#ID_2-4-1)
        1. [記憶のある通信路（Gilblertモデル等）](#ID_2-4-2)
    1. [情報の符号化 [encode]（情報を数量化する）](#ID_2-5)
        1. [符号木](#ID_2-5-1)
        1. [情報源と符号語の集合](#ID_2-5-1)
    1. [情報量（情報の価値を定量化する）](#ID_2-6)
        1. [クラフトの不等式 [Kraft's inequality]](#ID_2-6-1)
        1. [KL 情報量 [Kullback–Leibler divergence]](#ID_2-6-2)
1. [情報の符号化 [encode]](#ID_3)
    1. [情報量符号化](#ID_3-1)
        1. [エントロピー [entropy]（情報量の平均値）](#ID_3-1-1)
            1. [同時エントロピー [joint entropy]](#ID_3-1-1-1)
        1. [クロス・エントロピー [cross-entropy] と KL-情報量（情報源符号化の観点からみたKL-情報量）](#ID_3-1-2)
        1. [情報量符号化定理（シャノンの第１定理）](#ID_3-1-3)
        1. [Fano符号とシャノン符号](#ID_3-1-4)
        1. [エントロピーと漸近等分割性 [AEP : Asymptotic Equipartition Property]](#ID_3-1-5)
    1. [通信路符号化](ID_3-2)
       1. [条件付きエントロピー [conditional entropy] と相互情報量 [Mutual information]](ID_3-2-1)
        1. [通信路符号化定理（シャノンの第２定理）](#ID_3-2-2)
1. [連続情報の離散化 [discretization]](#ID_4)
    1. [連続情報のエントロピー（微分エントロピー）](#ID_4-1)
    1. [標本化 [sapling] と量子化 [quantization]](#ID_4-2)
        1. [ベクトル量子化 [QV : quantization vector]](#ID_4-2-1)
            1. [k-means 法](#ID_4-2-1-1)
            1. [学習ベクトル量子化 [LQV : leaning quantization vector]](#ID_4-2-1-2)
1. [情報幾何学 [Information Geometry]](#ID_5)
    1. [確率分布空間とモデル多様体](#ID_5-1)
    1. [KL-情報量 [Kullback–Leibler divergence]](#ID_5-2)
        1. [m-表現（混合表現）とe-表現（指数表限）](#ID_5-2-1)
    1. [曲がった空間内での”まっすぐな”線と”平らな”面（m-測地線、e-測地線 ）](#ID_5-3)
    1. [直交葉層化 [foliation] と射影 [projection]](#ID_5-4)
1. [【補足】情報幾何学から見た機械学習](#ID_6)
    1. [モデル選択](#ID_6-1)
    1. [推定量のバラツキ](#ID_6-2)
    1. [AIC（赤池の情報量基準）[Akaike's Information Criterion]](#ID_6-3)
    1. [混合モデル [mixed model]とアンサンブル学習（集団学習） [ensemble learning]](#ID_6-4)
        1. [混合モデルによるモデル多様体の拡大（混合モデルの幾何学的解釈）](#ID_6-4-1)
            1. [混合正規分布モデル [GMM : Gaussian Mixture Model]](#ID_6-4-1-1)
            1. [混合正規分布モデルの幾何学的観点](#ID_6-4-1-2)
        1. [EM アルゴリズム [expectation–maximization algorithm]](#ID_6-4-2)
            1. [EM アルゴリズムの適用例](#ID_6-4-2-1)
            1. [EM アルゴリズムの幾何学解釈](#ID_6-4-2-2)
        1. [ブースティング [Boosting]、アダブースト [AdaBoost]](#ID_6-4-3)
            1. [アダブースト [AdaBoost]](#ID_6-4-3-1)
                1. [AdaBoost の学習アルゴリズムの導出](#ID_6-4-3-1-1)
                1. [AdaBoost の幾何学的解釈](#ID_6-4-3-1-2)
        1. [バギング [Bagging]](#ID_6-4-4)
            1. [バギングの幾何学解釈](#ID_6-4-4-1)
        1. [【補足】最尤度推定](#ID_6-4-5)
        1. [【補足】ブーストトラップ法](#ID_6-4-6)
1. [【補足】グラフ理論 [graph theory]（外部リンク）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%B0%E3%83%A9%E3%83%95%E7%90%86%E8%AB%96_Note.md)
1. [【補足】最適化問題 [optimization problem]（数理計画問題 [mathematical programming]（外部リンク）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E6%9C%80%E9%81%A9%E5%8C%96%E5%95%8F%E9%A1%8C_Note.md)
1. [【補足】統計学 / 統計解析 [statistics]（外部リンク）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E7%B5%B1%E8%A8%88%E8%A7%A3%E6%9E%90_Note.md)
1. [【補足】多変量解析（外部リンク）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90_Note.md)
1. [【補足】機械学習 [Machine Learning]（外部リンク）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92_Note.md)
    1. [【補足】ニューラルネットワーク [Neural Network]（外部リンク）]()
1. [参考文献](#参考文献)

- 追記予定項目
    - 情報幾何学
        - ...

<a id="ID_1"></a>

## 概要、全体 MAP [Overview]
> 記載中...

<a id="ID_2"></a>

## 情報理論の基礎

<a id="ID_2-1"></a>

### 情報と確率
![image](https://user-images.githubusercontent.com/25688193/30414177-373b5f9e-995d-11e7-809f-3239e540c3ff.png)

<a id="ID_2-2"></a>

### 情報と確率空間、確率変数
![image](https://user-images.githubusercontent.com/25688193/30414211-61112aba-995d-11e7-855b-f2e2d407d0f6.png)
![twitter_ _ _1-2_170610](https://user-images.githubusercontent.com/25688193/29311445-1082c78e-81ed-11e7-8224-2d8e93d282f4.png)

<a id="ID_2-3"></a>

### 情報源 [information source]
![image](https://user-images.githubusercontent.com/25688193/30414253-93f09790-995d-11e7-9a63-6a3e860c7603.png)
![image](https://user-images.githubusercontent.com/25688193/30414280-af8068a0-995d-11e7-8332-f9fb99222201.png)

<a id="ID_2-3-1"></a>

#### 無記憶情報源（記憶のない情報源）[ i.i.d : independent and identically distributed ]
![twitter_ _ _2-2_170611](https://user-images.githubusercontent.com/25688193/29311443-1081ab7e-81ed-11e7-89a7-a47df233d881.png)

<a id="ID_2-3-2"></a>

#### 記憶のある情報源（マルコフ情報源）
![twitter_ _ _2-3_170611](https://user-images.githubusercontent.com/25688193/29311447-10871b40-81ed-11e7-8e5e-2d6680a15292.png)

<a id="ID_2-4"></a>

### 通信路（情報を伝達する媒体）[channel]
![twitter_ _ _3-1_170611](https://user-images.githubusercontent.com/25688193/29311446-1085a6f2-81ed-11e7-9f50-9db8f8c5c2c3.png)

<a id="ID_2-4-1"></a>

#### 記憶のない通信路（無記憶通信路）
![twitter_ _ _3-2_170611](https://user-images.githubusercontent.com/25688193/29311449-10a4bd26-81ed-11e7-931d-4e5cd46d1905.png)

<a id="ID_2-4-2"></a>

#### 記憶のある通信路（Gilblertモデル等）
![twitter_ _ _3-3_170611](https://user-images.githubusercontent.com/25688193/29311450-10a5fec0-81ed-11e7-9b26-ef322d3c0f07.png)

<a id="ID_2-5"></a>

### 情報の符号化 [encode]（情報を数量化する）
![twitter_ _ _4-1_170611](https://user-images.githubusercontent.com/25688193/29311451-10a78fc4-81ed-11e7-83c8-f397a8134c6c.png)

<a id="ID_2-5-1"></a>

#### 符号木
![twitter_ _ _4-2_170612](https://user-images.githubusercontent.com/25688193/29311452-10ab4704-81ed-11e7-85f2-bebdd340afad.png)

<a id="ID_2-5-2"></a>

#### 情報源と符号語の集合
![twitter_ _ _4-3_170612](https://user-images.githubusercontent.com/25688193/29311454-10c20c46-81ed-11e7-98ed-6a354585ebe8.png)

<a id="ID_2-6"></a>

### 情報量（情報の価値を定量化する）
![image](https://user-images.githubusercontent.com/25688193/30414311-db885a34-995d-11e7-9280-7d8c486b4d3a.png)

<a id="ID_2-6-1"></a>

#### クラフトの不等式 [Kraft's inequality]
![image](https://user-images.githubusercontent.com/25688193/30414339-04912b54-995e-11e7-937d-d8d436b691ba.png)
![image](https://user-images.githubusercontent.com/25688193/30414358-2002d28e-995e-11e7-92f7-becfa7d0fb09.png)
![twitter_ _ _5-2_170613](https://user-images.githubusercontent.com/25688193/29311455-10c8aa9c-81ed-11e7-9e62-077d4ce89274.png)

<a id="ID_2-6-2"></a>

#### KL 情報量 [Kullback–Leibler divergence]
![twitter_ _ _5-3_170613](https://user-images.githubusercontent.com/25688193/29311456-10ca58c4-81ed-11e7-94e5-46d9731e7dcc.png)
![twitter_ _ _5-4_170613](https://user-images.githubusercontent.com/25688193/29311457-10d04a22-81ed-11e7-9fa1-35ade00b2f30.png)
![twitter_ _ _5-5_170613](https://user-images.githubusercontent.com/25688193/29311458-10e52a50-81ed-11e7-92d1-39b388bb38ac.png)
![twitter_ _ _5-6_170613](https://user-images.githubusercontent.com/25688193/29311460-10ec8534-81ed-11e7-9e8a-87f325fc4db2.png)



<a id="ID_3"></a>

## 情報の符号化 [encode]

<a id="ID_3-1"></a>

### 情報量符号化
![image](https://user-images.githubusercontent.com/25688193/30414389-546dcb64-995e-11e7-98b8-79c9ee038795.png)

<a id="ID_3-1-1"></a>

#### エントロピー [entropy]（情報量の平均値）
![image](https://user-images.githubusercontent.com/25688193/30414423-892464c6-995e-11e7-8890-ffc5f6e6ee22.png)
![image](https://user-images.githubusercontent.com/25688193/30414485-d3998c8e-995e-11e7-9c2b-996ece75fd95.png)

<a id="ID_3-1-1-1"></a>

##### 同時エントロピー [joint entropy]
![image](https://user-images.githubusercontent.com/25688193/30414514-f078fa10-995e-11e7-9233-8af7bd4ce881.png)

<a id="ID_3-1-2"></a>

#### クロス・エントロピー [cross-entropy] と KL-情報量（情報源符号化の観点からみたKL-情報量）
![twitter_ _ _7-3_170617](https://user-images.githubusercontent.com/25688193/29311470-113157cc-81ed-11e7-99cb-47d999a49ace.png)
![image](https://user-images.githubusercontent.com/25688193/30414623-77e4aa8a-995f-11e7-9b27-7bb09f8198eb.png)
![image](https://user-images.githubusercontent.com/25688193/30414639-8cacf3f0-995f-11e7-936b-4a80688c9723.png)

<a id="ID_3-1-3"></a>

#### 情報量符号化定理（シャノンの第１定理）
![twitter_ _ _7-5_170617](https://user-images.githubusercontent.com/25688193/29311472-113c75f8-81ed-11e7-87e6-4bb7ed26a043.png)

<a id="ID_3-1-4"></a>

#### Fano符号とシャノン符号
> 記載中...

<a id="ID_3-1-5"></a>

#### エントロピーと漸近等分割性 [AEP : Asymptotic Equipartition Property]
![twitter_ _ _7-10_1_170620](https://user-images.githubusercontent.com/25688193/29311473-113e20ba-81ed-11e7-95ad-9cc89b277a4f.png)
![twitter_ _ _7-10_2_170620](https://user-images.githubusercontent.com/25688193/29311474-113e4bd0-81ed-11e7-93a5-d7f8707a9896.png)


<a id="ID_3-2"></a>

### 通信路符号化
![image](https://user-images.githubusercontent.com/25688193/30414697-c8b2e094-995f-11e7-98ac-bbb1b4bcb057.png)

<a id="ID_3-2-1"></a>

#### 条件付きエントロピー [conditional entropy] と相互情報量 [Mutual information]
![image](https://user-images.githubusercontent.com/25688193/30414724-e85f8014-995f-11e7-9761-fe5a97c7068e.png)
![twitter_ _ _8-2_170620](https://user-images.githubusercontent.com/25688193/29311476-11552c60-81ed-11e7-8526-4052735328f0.png)
![twitter_ _ _8-3_170620](https://user-images.githubusercontent.com/25688193/29311477-115a4240-81ed-11e7-8f00-f8b8570a1136.png)

<a id="ID_3-2-2"></a>

#### 通信路符号化定理（シャノンの第２定理）
![twitter_ _ _8-4_170623](https://user-images.githubusercontent.com/25688193/29311480-11636dc0-81ed-11e7-8a72-106073d5eb31.png)
![twitter_ _ _8-5_170623](https://user-images.githubusercontent.com/25688193/29311478-1161b282-81ed-11e7-85b6-f303874b7e17.png)

<a id="ID_4"></a>

## 連続情報の離散化 [discretization]
![image](https://user-images.githubusercontent.com/25688193/30414755-0598660a-9960-11e7-855d-a73433ebdd51.png)

<a id="ID_4-1"></a>

### 連続情報のエントロピー（微分エントロピー）
![image](https://user-images.githubusercontent.com/25688193/30414782-20ee0248-9960-11e7-9bd4-2bb65c8e8d67.png)
![twitter_ _ _9-2_170623](https://user-images.githubusercontent.com/25688193/29311481-11646dba-81ed-11e7-8057-91071ed26ed2.png)


<a id="ID_4-2"></a>

### 標本化 [sapling] と量子化 [quantization]
![image](https://user-images.githubusercontent.com/25688193/30414801-3b212852-9960-11e7-964f-8ab4ef0f8846.png)

<a id="ID_4-2-1"></a>

#### ベクトル量子化 [QV : quantization vector]
![image](https://user-images.githubusercontent.com/25688193/30414832-642e9298-9960-11e7-97c3-6fb0703ea9f7.png)

<a id="ID_4-2-1-1"></a>

##### k-means 法
![twitter_ _ _9-4_170623](https://user-images.githubusercontent.com/25688193/29311483-117f7628-81ed-11e7-927d-d69409eb61f3.png)

<a id="ID_4-2-1-2"></a>

##### 学習ベクトル量子化 [LQV : leaning quantization vector]
![twitter_ _ _9-5_170623](https://user-images.githubusercontent.com/25688193/29311485-118904ae-81ed-11e7-82b5-7cd3c5ca863d.png)



<a id="ID_5"></a>

## 情報幾何学 [Information Geometry]
![image](https://user-images.githubusercontent.com/25688193/30414855-84a75fdc-9960-11e7-9a58-a93f3bab86d4.png)

<a id="ID_5-1"></a>

### 確率分布空間とモデル多様体
![image](https://user-images.githubusercontent.com/25688193/30414920-a5c596ca-9960-11e7-8aae-18d9039c6679.png)
![twitter_ _ _6-2_170613](https://user-images.githubusercontent.com/25688193/29311462-10efe86e-81ed-11e7-9c3e-230a1142b215.png)

<a id="ID_5-2"></a>

### KL-情報量 [Kullback–Leibler divergence]
![twitter_ _ _6-3_170613](https://user-images.githubusercontent.com/25688193/29311461-10ef620e-81ed-11e7-8b1a-cafa74328805.png)
![image](https://user-images.githubusercontent.com/25688193/30414957-df4fb902-9960-11e7-8273-c2f77817ff90.png)

<a id="ID_5-2-1"></a>

#### m-表現（混合表現）、e-表現（指数表限）
![image](https://user-images.githubusercontent.com/25688193/30414994-fcec3670-9960-11e7-90a0-acd1e7f1e015.png)


<a id="ID_5-3"></a>

### 曲がった空間内での”まっすぐな”線と”平らな”面（m-測地線、e-測地線 ）
![twitter_ _ _6-5_170615](https://user-images.githubusercontent.com/25688193/29311464-110c04f4-81ed-11e7-8aaa-c17643bbb360.png)
![twitter_ _ _6-6_170615](https://user-images.githubusercontent.com/25688193/29311465-110d28e8-81ed-11e7-9960-6f7aa284d561.png)

<a id="ID_5-4"></a>

### 直交葉層化 [foliation] と射影 [projection]
![twitter_ _ _6-7_170616](https://user-images.githubusercontent.com/25688193/29311466-11151b84-81ed-11e7-8696-d9e8d4fc25ab.png)
![twitter_ _ _6-8_170616](https://user-images.githubusercontent.com/25688193/29311468-111797f6-81ed-11e7-8856-1d32ae05ccc8.png)


<a id="ID_6"></a>

## 【補足】情報幾何学から見た機械学習

<a id="ID_6-1"></a>

### モデル選択
![twitter_ _ _10-1_170625](https://user-images.githubusercontent.com/25688193/29311484-1188abc6-81ed-11e7-8241-d0475f23a9f3.png)
![twitter_ _ _10-2_170625](https://user-images.githubusercontent.com/25688193/29311486-118c1df6-81ed-11e7-9252-c9f6a1f61113.png)

<a id="ID_6-2"></a>

### 推定量のバラツキ
> 記載中...


<a id="ID_6-3"></a>

### AIC（赤池の情報量基準）[Akaike's Information Criterion]
![twitter_ _ _10-3 _170627](https://user-images.githubusercontent.com/25688193/29311488-119f0d08-81ed-11e7-9536-464b5f983148.png)
![twitter_ _ _10-4 _170627](https://user-images.githubusercontent.com/25688193/29311492-11c00f1c-81ed-11e7-9c5d-e695a0e6f977.png)
![twitter_ _ _10-5 _170627](https://user-images.githubusercontent.com/25688193/29311491-11b3784c-81ed-11e7-9ee3-e43044f32a2b.png)
![twitter_ _ _10-6 _170627](https://user-images.githubusercontent.com/25688193/29311493-11c4c962-81ed-11e7-990c-ee73bf8ea245.png)
![twitter_ _ _10-7_170626](https://user-images.githubusercontent.com/25688193/29311494-11cc77de-81ed-11e7-93e3-ddcbf692cd58.png)


<a id="ID_6-4"></a>

### 混合モデル [mixed model]とアンサンブル学習（集団学習） [ensemble learning]
![twitter_ _ _11-1_170626](https://user-images.githubusercontent.com/25688193/30400845-382106c4-9913-11e7-8253-f11084f92847.png)

<a id="ID_6-4-1"></a>

#### 混合モデルによるモデル多様体の拡大（混合モデルの幾何学的解釈）
![image](https://user-images.githubusercontent.com/25688193/30415043-2ede325a-9961-11e7-865b-a209f11be7ec.png)

<a id="ID_6-4-1-1"></a>

##### 混合正規分布モデル [GMM : Gaussian Mixture Model] 
![image](https://user-images.githubusercontent.com/25688193/30415111-846fb662-9961-11e7-80e4-abb1b1b9865f.png)

<a id="ID_6-4-1-2"></a>

##### 混合正規分布モデルの幾何学的観点
![image](https://user-images.githubusercontent.com/25688193/30415203-fcf52266-9961-11e7-979a-39f8fdf9d966.png)
![image](https://user-images.githubusercontent.com/25688193/30415230-1bee4c6a-9962-11e7-8f3c-a3357373c575.png)
![image](https://user-images.githubusercontent.com/25688193/30415375-c0b9178e-9962-11e7-8aa3-f88e7bd97a78.png)
![image](https://user-images.githubusercontent.com/25688193/30415398-d9c87a9e-9962-11e7-8244-0b5de3bcce16.png)
![twitter_ _ _11-5_170630](https://user-images.githubusercontent.com/25688193/30400846-38223ae4-9913-11e7-8ac3-d8851bc4d7ac.png)


<a id="ID_6-4-2"></a>

#### EM アルゴリズム [expectation–maximization algorithm]
![twitter_ _ _11-6_170701](https://user-images.githubusercontent.com/25688193/30400850-3837c4fe-9913-11e7-95a6-70fec69c6a10.png)

<a id="ID_6-4-2-1"></a>

##### EM アルゴリズムの適用例
![image](https://user-images.githubusercontent.com/25688193/30416196-3f828700-9966-11e7-9e66-e02b69ec18ef.png)
![image](https://user-images.githubusercontent.com/25688193/30416221-5781ae8a-9966-11e7-90ba-373b4a2a3476.png)
![image](https://user-images.githubusercontent.com/25688193/30416156-102b22fa-9966-11e7-8d12-eb481dba881f.png)
![image](https://user-images.githubusercontent.com/25688193/30416174-25ed04b4-9966-11e7-9768-881625d9d656.png)

<a id="ID_6-4-2-2"></a>

##### EM アルゴリズムの幾何学的解釈
![image](https://user-images.githubusercontent.com/25688193/30415457-1a321702-9963-11e7-8922-1d9a10f55478.png)
![image](https://user-images.githubusercontent.com/25688193/30415473-311b90ce-9963-11e7-95a4-5eec3cc5fee0.png)
![image](https://user-images.githubusercontent.com/25688193/30415510-4f899a9c-9963-11e7-8e62-f1be5a2fb6ad.png)
![image](https://user-images.githubusercontent.com/25688193/30415534-696ec5ea-9963-11e7-8f78-00b9a2c8e9e0.png)

<a id="ID_6-4-3"></a>

### ブースティング [Boosting]、アダブースト [AdaBoost]
![image](https://user-images.githubusercontent.com/25688193/30401309-c15335d8-9914-11e7-990f-011187f57e63.png)

<a id="ID_6-4-3-1"></a>

#### アダブースト [AdaBoost]
![image](https://user-images.githubusercontent.com/25688193/30415636-d4ee38dc-9963-11e7-9090-28ffc5325dae.png)
![image](https://user-images.githubusercontent.com/25688193/30415665-0441c360-9964-11e7-8783-85cb1b27fd09.png)

<a id="ID_6-4-3-1-1"></a>

##### アダブーストの学習アルゴリズムの導出
![image](https://user-images.githubusercontent.com/25688193/30416003-7bf65b90-9965-11e7-9808-11de51cdb027.png)
![image](https://user-images.githubusercontent.com/25688193/30416046-962e982e-9965-11e7-88a4-d81bc4058bee.png)
![twitter_ _ _11-13_170703](https://user-images.githubusercontent.com/25688193/30400857-38676c4a-9913-11e7-9409-b5c9081c38a6.png)

<a id="ID_6-4-3-1-2"></a>

##### アダブーストの幾何学的解釈
![twitter_ _ _11-14_170704](https://user-images.githubusercontent.com/25688193/30400858-38686fe6-9913-11e7-85c1-e7ce2374513b.png)
![image](https://user-images.githubusercontent.com/25688193/30415807-ab48b664-9964-11e7-86de-2c300c3107ee.png)
![image](https://user-images.githubusercontent.com/25688193/30415837-d0222376-9964-11e7-8098-d53d03e3c62c.png)
![twitter_ _ _11-16_170705](https://user-images.githubusercontent.com/25688193/30400861-387c20ae-9913-11e7-8e09-ca1bd7b100fd.png)
![image](https://user-images.githubusercontent.com/25688193/30415878-fe5da328-9964-11e7-87ce-b3c66542e3d4.png)

<a id="ID_6-4-4"></a>

#### バギング [Bagging]
![image](https://user-images.githubusercontent.com/25688193/30415910-2310251a-9965-11e7-8cb6-55434f78d045.png)
![image](https://user-images.githubusercontent.com/25688193/30415937-371b910c-9965-11e7-9171-0671ea3cfb96.png)

<a id="ID_6-4-4-1"></a>

#### バギングの幾何学的解釈
![twitter_ _ _11-19_170707](https://user-images.githubusercontent.com/25688193/30400863-388d60a8-9913-11e7-81b5-d2f6ddb2ab8f.png)

<a id="ID_6-4-5"></a>

#### 【補足】最尤度推定
![twitter_ _ _11-7 _170701](https://user-images.githubusercontent.com/25688193/30400853-3845b30c-9913-11e7-8a6b-2a392801c6b6.png)

<a id="ID_6-4-6"></a>

#### 【補足】ブートストラップ法
![image](https://user-images.githubusercontent.com/25688193/30401567-bfd0cb02-9915-11e7-9192-e0e87588e6a3.png)
![image](https://user-images.githubusercontent.com/25688193/30401467-5bfae2b6-9915-11e7-92dc-1c68981ae1c2.png)





<a name="参考文献"></a>

## 参考文献
> 情報数理の基礎と応用 (ライブラリ情報学コア・テキスト) </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%83%85%E5%A0%B1%E6%95%B0%E7%90%86%E3%81%AE%E5%9F%BA%E7%A4%8E%E3%81%A8%E5%BF%9C%E7%94%A8-%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA%E6%83%85%E5%A0%B1%E5%AD%A6%E3%82%B3%E3%82%A2%E3%83%BB%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88-%E5%B0%BE%E7%95%91-%E4%BC%B8%E6%98%8E/dp/4781912109?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4781912109)</br>

> 情報理論の基礎―情報と学習の直観的理解のために (SGC Books) </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%83%85%E5%A0%B1%E7%90%86%E8%AB%96%E3%81%AE%E5%9F%BA%E7%A4%8E%E2%80%95%E6%83%85%E5%A0%B1%E3%81%A8%E5%AD%A6%E7%BF%92%E3%81%AE%E7%9B%B4%E8%A6%B3%E7%9A%84%E7%90%86%E8%A7%A3%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AB-SGC-Books-%E6%9D%91%E7%94%B0-%E6%98%87/dp/4781912125?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4781912125)</br>

> はじめてのパターン認識 </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)</br>

> パターン認識と機械学習 上（ベイズ理論による統計的予測）</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98%E3%81%A8%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92-%E4%B8%8A-C-M-%E3%83%93%E3%82%B7%E3%83%A7%E3%83%83%E3%83%97/dp/4621061224)</br>
> パターン認識と機械学習 下（ベイズ理論による統計的予測）</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98%E3%81%A8%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92-%E4%B8%8B-%E3%83%99%E3%82%A4%E3%82%BA%E7%90%86%E8%AB%96%E3%81%AB%E3%82%88%E3%82%8B%E7%B5%B1%E8%A8%88%E7%9A%84%E4%BA%88%E6%B8%AC-C-M-%E3%83%93%E3%82%B7%E3%83%A7%E3%83%83%E3%83%97/dp/4621061240/ref=pd_lpo_sbs_14_t_2?_encoding=UTF8&psc=1&refRID=4NVPYNHD2TGV0PZ1KQS0)</br>