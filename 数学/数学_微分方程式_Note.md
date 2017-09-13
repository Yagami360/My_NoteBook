# 微分方程式 [differential equation]

微分方程式のツイートに関しのマイノートです。今後も随時追加予定です。</br>
（基本PC or タブレット端末からの閲覧用の画像サイズになってます）

This is my notebook that summarizes about "differential equation". </br>
I will add contents as needed!

> Twitterモーメント ： https://twitter.com/i/moments/838576386277138432
![twitter_ 2_](https://user-images.githubusercontent.com/25688193/30379666-3ea91eaa-98d2-11e7-97f2-c3c82ac8f1c2.jpg)

## 項目 [Contents]

1. [概要 [Overview]](#ID_1)
1. [常微分方程式 [O.D.E : ordinary differential equation]](#ID_2)
    1. [１階微分方程式 [First-order differential equation]](#ID_2-1)
        1. [変数分離型 [separation of variables]](#ID_2-1-1)
        1. [同次形 [Homogeneous Equations]](#ID_2-1)
    1. [１階線型微分方程式 [First-order linear differential equation]](#ID_2-2)
    1. [完全微分方程式 [exact differential equation]](#ID_2-3)
    1. [完全形における解の存在と一意性 </br>＜ピカールの逐次近似法 [method of successive approximations] ＞](#ID_2-4)
        1. [ピカールの近似列](#ID_2-4-1)
            1. [(a) ピカールの近似列の算出](#ID_2-4-1-1)
            1. [(b) ピカールの近似列の収束性](#ID_2-4-1-2)
        1. [逐次近似法を使用した方程式の解の導出](#ID_2-4-2)
    1. [ニュートン・ラプソン法（数値解析） [Newton-Raphson method]](#ID_2-5)
    1. [２階定係数斉次線形微分方程式 [homogeneous linear differential equation]](#ID_2-6)
        1. [(i) b^2 -4ac > 0 のとき](#ID_2-6-1)
        1. [(i) b^2 -4ac < 0 のとき](#ID_2-6-2)
        1. [(i) b^2 -4ac = 0 のとき](#ID_2-6-3)
    1. [２階変係数斉次線形微分方程式 [Inhomogeneous linear differential equation]](#ID_2-7)
        1. [定数変化法 [variation of constants]](#ID_2-7-1)
        1. [代入法](#ID_2-7-2)
            1. [① 右辺が多項式の形をしている場合](#ID_2-7-2-1)
            1. [② 右辺が（多項式×指数関数）の形をしている場合](#ID_2-7-2-2)
            1. [③ 右辺が（多項式×三角関数）になっている場合](#ID_2-7-2-3)
    1. [級数解 [Series solution]](#ID_2-8)
        1. [べき級数 [series] とその性質](#ID_2-9)
            1. [収束半径と収束、発散、及びCauchyの判定法による収束半径の決定](#ID_2-9-1)
            1. [Tayler 展開](#ID_2-9-2)
        1. [特異点 [singularity] 、オイラーの方程式](#ID_2-10)
            1. [（特異点が t0=0 の場合で） t > 0 のとき](#ID_2-10-1)
            1. [（特異点が t0=0 の場合で） t < 0 のとき](#ID_2-10-2)
        1. [確定特異点 [fixed singular point]、フロベニウスの方法 [Frobenius method]](#ID_2-11)
            1. [確定特異点 [fixed singular point]](#ID_2-11-1)
            1. [フロベニウスの方法 [Frobenius method]](#ID_2-11-2)
                1. [１つの例の場合](#ID_2-11-2-1)
                1. [一般的な場合](#ID_2-11-2-2)
                    1. [決定方程式](#ID_2-11-2-2-1)
                    1. [決定方程式における r1, r2 の差が整数になる場合の、１次独立な２つの解と一般解](#ID_2-11-2-2-2)
                    1. [決定方程式が重解になる場合の、１次独立な２つ目の解](#ID_2-11-2-2-3)
1. [関数解析 [functional analysis] と常微分方程式](#ID_3)
    1. [ラプラス変換 [Laplace transform]](#ID_3-1)
        1. [ラプラス変換を使用した微分方程式の解法](#ID_3-1-1)
    1. [フーリエ解析 [Fourier analysis]](#ID_3-2)
        1. [フーリエ級数 [Fourier series]、フーリエ級数展開](#ID_3-2-1)
        1. [複素フーリエ級数](#ID_3-2-2)
        1. [フーリエ変換 [Fourier transform]](#ID_3-2-3)
        1. [フーリエ解析を使用した微分方程式の解法](#ID_3-2-4)
            1. [熱伝導方程式 [Heat Conduction Equation]](#ID_3-2-4-1)
1. [連立常微分方程式 [simultaneous ordinary differential equations]](#ID_4)
    1. [線形系の解の代数的性質](#ID_4-1)
    1. [線形代数の微分方程式への応用](#ID_4-2)
    1. [１階の線形斉次連立微分方程式の解を見つける方法](#ID_4-3)
        1. [固有値 λ が複素数解のとき](#ID_4-3-1)
        1. [固有値 λ が重解のとき](#ID_4-3-2)
    1. [基本解行列 [fundamental matrix solution]](#ID_4-4)
    1. [非斉次線形連立方程式（定数変化法）](#ID_4-5)
1. [微分方程式の定性的性質 [qualitative properties of differential equation] と力学系 [dynamical system]](#ID_5)
    1. [自律系微分方程式 [autonomous system of differential equation] と線形システムにおける安定性](#ID_5-1)
    1. [平衡解の安定性](#ID_5-2)
        1. [自律系微分方程式の平衡解の安定性](#ID_5-2-1)
    1. [相平面 [phase plane]](#ID_5-3)
    1. [](#ID_5-x)
1. [参考文献](#参考文献)

- 追記予定項目
    - 微分方程式の全体 MAP 図
    - 偏微分方程式 [partial differential equation]
    - 関数解析 [functional analysis] 視点での、
        - フーリエ解析 [Fourier analysis]、フーリエ変換
        - ラプラス変換 [Laplace transform]
        - グリーン関数 [Green's function]
        - 超関数 [generalized function]
        - デルタ関数、インパルス関数 [delta function]
    - 力学系 [dynamical system]
        - 軌道の定性的性質
        - 線形システムの相図
        - 解の長期的振る舞い
    - 数値解析による解法 [Numerical Analysis]
    - 確率微分方程式 [stochastic differential equation]
        - ブラック–ショールズの方程式[Black–Scholes equation]


</br>

<a id="ID_1"></a>

## 概要 [Overview]、全体 MAP

> 記載中...

</br>
<a id="ID_2"></a>

## 常微分方程式 [O.D.E : ordinary differential equation]

<a id="ID_2-1"></a>

### １階微分方程式 [First-order differential equation]

<a id="ID_2-1-1"></a>

#### 変数分離型 [separation of variables]
![twitter_ _1-1_170306](https://user-images.githubusercontent.com/25688193/29313856-b49c63f8-81f6-11e7-95f8-0d1d34273914.png)

<a id="ID_2-1-2"></a>

#### 同次形 [Homogeneous Equations] 
![twitter_ _1-2_170306](https://user-images.githubusercontent.com/25688193/29313855-b49c3b26-81f6-11e7-9a26-5eca635633c5.png)

</br>
<a id="ID_2-2"></a>

### １階線型微分方程式 [First-order linear differential equation]
![twitter_ _1-3_170306](https://user-images.githubusercontent.com/25688193/29313857-b4a1e9f4-81f6-11e7-807f-878ca3c8c9a4.png)
![twitter_ _1-4_170306](https://user-images.githubusercontent.com/25688193/29313860-b4a3cc4c-81f6-11e7-9127-d1a4581b3279.png)

</br>
<a id="ID_2-3"></a>

### 完全微分方程式 [exact differential equation]
![twitter_ _1-5_170307](https://user-images.githubusercontent.com/25688193/29313858-b4a2a2e0-81f6-11e7-895b-0510ab988458.png)
![twitter_ _1-6_170307](https://user-images.githubusercontent.com/25688193/29313859-b4a2e99e-81f6-11e7-9c96-b95bbeba9edb.png)

</br>
<a id="ID_2-4"></a>

### 完全形における解の存在と一意性　＜ピカールの逐次近似法 [method of successive approximations] ＞

<a id="ID_2-4-1"></a>

#### ピカールの近似列
![twitter_ _1-7_170309](https://user-images.githubusercontent.com/25688193/29313862-b4c4d6e4-81f6-11e7-931c-8bbb3a9fb691.png)

<a id="ID_2-4-1-1"></a>

#### (a) ピカールの近似列の算出
![twitter_ _1-8_170309](https://user-images.githubusercontent.com/25688193/29313861-b4c37830-81f6-11e7-833b-bebbc82bdfe4.png)
![twitter_ _1-9_170309](https://user-images.githubusercontent.com/25688193/29313865-b4c8c3e4-81f6-11e7-82c9-69568d95fde2.png)

<a id="ID_2-4-1-2"></a>

#### (b) ピカールの近似列の収束性
![twitter_ _1-10_170311](https://user-images.githubusercontent.com/25688193/29313866-b4c90656-81f6-11e7-9186-62a3e60ee8ab.png)

![twitter_ _1-11_170311](https://user-images.githubusercontent.com/25688193/29313863-b4c77aa2-81f6-11e7-9e8f-634278e00738.png)

<a id="ID_2-4-2"></a>

#### 逐次近似法を使用した方程式の解の導出

![twitter_ _1-12_170312](https://user-images.githubusercontent.com/25688193/29313864-b4c841bc-81f6-11e7-9caa-ef7eff7fc30a.png)
![twitter_ _1-13_170312](https://user-images.githubusercontent.com/25688193/29313868-b4e8bd20-81f6-11e7-853d-873fa3241157.png)

<a id="ID_2-5"></a>

#### ニュートン・ラプソン法（数値解析）[Newton-Raphson method]
![twitter_ _1-14_170313](https://user-images.githubusercontent.com/25688193/29313867-b4e831a2-81f6-11e7-9c4b-83aa2065c80d.png)
![twitter_ _1-15_170313](https://user-images.githubusercontent.com/25688193/29313871-b4f31d74-81f6-11e7-8a04-0a0550bb50d6.png)

<a id="ID_2-6"></a>

### ２階定係数斉次線形微分方程式 [homogeneous linear differential equation]
![twitter_ _2-1_170314](https://user-images.githubusercontent.com/25688193/29313869-b4edbb7c-81f6-11e7-8b03-9ebfc519ddb7.png)

<a id="ID_2-6-1"></a>

#### (i) b^2 -4ac > 0 のとき
![twitter_ _2-2_170314](https://user-images.githubusercontent.com/25688193/29313870-b4ef7bba-81f6-11e7-877d-5c7a8e5a917c.png)

<a id="ID_2-6-2"></a>

#### (ii) b^2 -4ac < 0 のとき
![twitter_ _2-3_170315](https://user-images.githubusercontent.com/25688193/29313872-b503c688-81f6-11e7-8192-e23255578e38.png)
![twitter_ _2-4_170315](https://user-images.githubusercontent.com/25688193/29313873-b5123916-81f6-11e7-9d95-e2c4d5f3b6f8.png)
![twitter_ _2-5_170315](https://user-images.githubusercontent.com/25688193/29313874-b512bc06-81f6-11e7-8933-9a8c76cb93e4.png)

<a id="ID_2-6-3"></a>

#### (iii) b^2 - 4ac = 0 のとき
![twitter_ _2-6_170316](https://user-images.githubusercontent.com/25688193/29313875-b51326f0-81f6-11e7-9158-ea23630bdc12.png)
![twitter_ _2-7_170316](https://user-images.githubusercontent.com/25688193/29313877-b51cc322-81f6-11e7-9a3f-2648846ab92d.png)
![twitter_ _2-8_170316](https://user-images.githubusercontent.com/25688193/29313876-b51bbca2-81f6-11e7-9481-37fa1d74bfd2.png)
![twitter_ _2-9_170316](https://user-images.githubusercontent.com/25688193/29313878-b52cdb72-81f6-11e7-92ae-1e070846dc83.png)

<a id="ID_2-7"></a>

### ２階変係数斉次線形微分方程式 [Inhomogeneous linear differential equation]

<a id="ID_2-7-1"></a>

#### 定数変化法 [variation of constants]
![twitter_ _3-1_170318](https://user-images.githubusercontent.com/25688193/29313879-b5366bba-81f6-11e7-894d-97aeafd8cb03.png)
![twitter_ _3-2_170318](https://user-images.githubusercontent.com/25688193/29313880-b53783ce-81f6-11e7-9072-c523a88b7f42.png)
![twitter_ _3-3_170318](https://user-images.githubusercontent.com/25688193/29313881-b53bacce-81f6-11e7-8cb8-5b3c1a94020d.png)
![twitter_ _3-4_170318](https://user-images.githubusercontent.com/25688193/29313883-b542d166-81f6-11e7-99be-11d8eb83f076.png)

<a id="ID_2-7-2"></a>

#### 代入法

<a id="ID_2-7-2-1"></a>

#### ① 右辺が多項式の形をしている場合
![twitter_ _3-5_170320](https://user-images.githubusercontent.com/25688193/29313882-b541abec-81f6-11e7-9289-5613a77df3ff.png)
![twitter_ _3-6_170320](https://user-images.githubusercontent.com/25688193/29313884-b5550656-81f6-11e7-9488-58b2b586b50c.png)
![twitter_ _3-7_170320](https://user-images.githubusercontent.com/25688193/29313886-b55ae864-81f6-11e7-8488-dc514f1eba6e.png)

<a id="ID_2-7-2-2"></a>

#### ② 右辺が（多項式×指数関数）の形をしている場合
![twitter_ _3-8_170321](https://user-images.githubusercontent.com/25688193/29313885-b559e5d6-81f6-11e7-9fb7-0635cb9edc2a.png)
![twitter_ _3-9_170321](https://user-images.githubusercontent.com/25688193/29313887-b5648126-81f6-11e7-9158-f9982afa80d6.png)

<a id="ID_2-7-2-3"></a>

#### ③ 右辺が（多項式×三角関数）になっている場合
![twitter_ _3-10_170322](https://user-images.githubusercontent.com/25688193/29313888-b5666496-81f6-11e7-86c1-0f76399e23e8.png)
![twitter_ _3-11_170322](https://user-images.githubusercontent.com/25688193/29313889-b5670860-81f6-11e7-98ab-16f3fb983959.png)

</br>
<a id="ID_2-8"></a>

### 級数解 [Series solution]
![twitter_ _4-1_170323](https://user-images.githubusercontent.com/25688193/29313890-b57a565e-81f6-11e7-95db-f2d809e75c84.png)
![twitter_ _4-2_170323](https://user-images.githubusercontent.com/25688193/29313891-b57c38ca-81f6-11e7-8b17-79fb4372dacd.png)
![twitter_ _4-3_170323](https://user-images.githubusercontent.com/25688193/29313892-b57d05fc-81f6-11e7-833c-d60c6b1f3ea4.png)
![twitter_ _4-4_170323](https://user-images.githubusercontent.com/25688193/29313893-b587ec92-81f6-11e7-8930-d77d0a227323.png)

</br>
<a id="ID_2-9"></a>

### べき級数 [series] とその性質

<a id="ID_2-9-1"></a>

#### 収束半径と収束、発散、及びCauchyの判定法による収束半径の決定
![twitter_ _5-1_170323](https://user-images.githubusercontent.com/25688193/29313894-b58a63fa-81f6-11e7-8fb5-af6278acf6da.png)

<a id="ID_2-9-2"></a>

#### Tayler 展開
![twitter_ _5-2_170324](https://user-images.githubusercontent.com/25688193/29313895-b58f2e1c-81f6-11e7-9bd3-476f3b9dab28.png)


</br>
<a id="ID_2-10"></a>

### 特異点 [singularity] 、オイラーの方程式

<a id="ID_2-10-1"></a>

#### （特異点が t0=0 の場合で） t > 0 のとき
![twitter_ _6-1_170325](https://user-images.githubusercontent.com/25688193/29313896-b59ee564-81f6-11e7-8ecc-13c22d1a060d.png)
![twitter_ _6-2_170325](https://user-images.githubusercontent.com/25688193/29313897-b59f52f6-81f6-11e7-83a0-e2e637d6c1f3.png)
![twitter_ _6-3_170325](https://user-images.githubusercontent.com/25688193/29313898-b5a1617c-81f6-11e7-96c5-7a60bb1e433f.png)

<a id="ID_2-10-2"></a>

#### （特異点が t0=0 の場合で）t < 0 のとき
![twitter_ _6-4_170325](https://user-images.githubusercontent.com/25688193/29313899-b5aba772-81f6-11e7-829f-711b033de645.png)
![twitter_ _6-5_170325](https://user-images.githubusercontent.com/25688193/29313900-b5add844-81f6-11e7-8425-93a3ad0f66d1.png)
![twitter_ _6-6_170325](https://user-images.githubusercontent.com/25688193/29313901-b5b1c31e-81f6-11e7-8923-7e5d4c5d65a7.png)
![twitter_ _6-7_170325](https://user-images.githubusercontent.com/25688193/29313903-b5c36cf4-81f6-11e7-8e97-07e90d36997f.png)
![twitter_ _6-8_170325](https://user-images.githubusercontent.com/25688193/29313902-b5c31d94-81f6-11e7-9548-90caba54880a.png)

<a id="ID_2-11"></a>

### 確定特異点 [fixed singular point]、フロベニウスの方法 [Frobenius method]

<a id="ID_2-11-1"></a>

#### 確定特異点 [fixed singular point]
![twitter_ _6-9_170325](https://user-images.githubusercontent.com/25688193/29313904-b5c8616e-81f6-11e7-9b64-11816d27d783.png)
![twitter_ _6-10_170325](https://user-images.githubusercontent.com/25688193/29313905-b5d1d636-81f6-11e7-9fcc-752907e600ce.png)

<a id="ID_2-11-2"></a>

#### プロベニウスの方法 [Frobenius method]
![twitter_ _6-11_170325](https://user-images.githubusercontent.com/25688193/29313906-b5d28ac2-81f6-11e7-9a3a-39ee437046f8.png)

<a id="ID_2-11-2-1"></a>

##### １つの例の場合
![twitter_ _6-12_170326](https://user-images.githubusercontent.com/25688193/29313907-b5da0482-81f6-11e7-82f2-39374cc9da00.png)
![twitter_ _6-13_170326](https://user-images.githubusercontent.com/25688193/29313908-b5ed52da-81f6-11e7-8e77-c1c33888eb2c.png)
![twitter_ _6-14_170326](https://user-images.githubusercontent.com/25688193/29313912-b5f3f176-81f6-11e7-917a-7a54bedb87bd.png)

<a id="ID_2-11-2-2"></a>

##### 一般的な場合
![twitter_ _6-15_170327](https://user-images.githubusercontent.com/25688193/29313909-b5ef900e-81f6-11e7-88a9-8d79794418d9.png)

<a id="ID_2-11-2-2-1"></a>

##### 決定方程式

<a id="ID_2-11-2-2-2"></a>

##### 決定方程式における r1, r2 の差が整数になる場合の、１次独立な２つの解と一般解
![twitter_ _6-16_170327](https://user-images.githubusercontent.com/25688193/29313913-b5f443c4-81f6-11e7-8f31-6d39d0043cf3.png)
![twitter_ _6-17_170327](https://user-images.githubusercontent.com/25688193/29313914-b5f47fce-81f6-11e7-8640-7c2bf5c0d923.png)
![twitter_ _6-18_170327](https://user-images.githubusercontent.com/25688193/29313918-b61705bc-81f6-11e7-89ec-b00abf9d62b9.png)

<a id="ID_2-11-2-2-3"></a>

##### 決定方程式が重解になる場合の、１次独立な２つ目の解
![twitter_ _6-19_170328](https://user-images.githubusercontent.com/25688193/29313919-b6175daa-81f6-11e7-90bf-e54799b3ab84.png)
![twitter_ _6-20_170328](https://user-images.githubusercontent.com/25688193/29313915-b61531c4-81f6-11e7-9548-9b31a5180542.png)
![twitter_ _6-21_170328](https://user-images.githubusercontent.com/25688193/29313916-b6162502-81f6-11e7-858f-a0ed0cea1116.png)

</br>

<a id="ID_3"></a>

## 関数解析 [functional analysis] と常微分方程式

<a id="ID_3-1"></a>

### ラプラス変換 [Laplace transform]
![twitter_ _7-1_170329](https://user-images.githubusercontent.com/25688193/29313917-b616e56e-81f6-11e7-849f-4ec20c55605b.png)
![twitter_ _7-2_170330](https://user-images.githubusercontent.com/25688193/29313920-b6174388-81f6-11e7-8805-02de58a48273.png)
![twitter_ _7-3_170330](https://user-images.githubusercontent.com/25688193/29313921-b639b9cc-81f6-11e7-8d5c-a8be8920e674.png)

<a id="ID_3-1-1"></a>

#### ラプラス変換を使用した微分方程式の解法
![twitter_ _7-4_170330](https://user-images.githubusercontent.com/25688193/29313926-b63d4c86-81f6-11e7-9162-c01238a30893.png)
![twitter_ _7-5_170330](https://user-images.githubusercontent.com/25688193/29313924-b63cffce-81f6-11e7-9eae-3b245ffca0aa.png)


</br>
<a id="ID_3-2"></a>

### フーリエ解析 [Fourier analysis]

<a id="ID_3-2-1"></a>

#### フーリエ級数 [Fourier series]、フーリエ級数展開
![twitter_ _7-6_170331](https://user-images.githubusercontent.com/25688193/29313922-b63c0c90-81f6-11e7-974d-a102eed03cbc.png)
![twitter_ _7-7_170401](https://user-images.githubusercontent.com/25688193/29313923-b63c5aec-81f6-11e7-8186-65657de4dc22.png)


<a id="ID_3-2-2"></a>

#### 複素フーリエ級数
![_ _ _170914](https://user-images.githubusercontent.com/25688193/30384732-1138d43e-98e0-11e7-914b-ed54e7dc6193.png)

<a id="ID_3-2-3"></a>

#### フーリエ変換 [Fourier transform]
![twitter_ _7-8_170401](https://user-images.githubusercontent.com/25688193/29313925-b63d1694-81f6-11e7-91ab-22ac163d6329.png)
![twitter_ _7-9_170402](https://user-images.githubusercontent.com/25688193/29313933-b672819e-81f6-11e7-9aeb-42f5e4863513.png)
![twitter_ _7-10_170402](https://user-images.githubusercontent.com/25688193/29313929-b6602aa8-81f6-11e7-9f6b-ff80ff91e14e.png)

<a id="ID_3-2-4"></a>

#### フーリエ解析を使用した微分方程式の解法

<a id="ID_3-2-4-1"></a>

##### 熱伝導方程式
![twitter_ _7-11_170402](https://user-images.githubusercontent.com/25688193/29313930-b6610a54-81f6-11e7-8ff4-5edd3f400ead.png)
![twitter_ _7-12_170402](https://user-images.githubusercontent.com/25688193/29313932-b6621728-81f6-11e7-82c6-ee1707ff1157.png)

</br>
<a id="ID_4"></a>

## 連立常微分方程式 [simultaneous ordinary differential equations]

<a id="ID_4-1"></a>

### 線形系の解の代数的性質
![twitter_ _8-1_170403](https://user-images.githubusercontent.com/25688193/29313931-b661d632-81f6-11e7-9ad3-c69420b3a1e3.png)
![twitter_ _8-2_170403](https://user-images.githubusercontent.com/25688193/29313928-b65fba64-81f6-11e7-999e-7884f7f8ddc4.png)
![twitter_ _8-3_170403](https://user-images.githubusercontent.com/25688193/29313934-b68219ce-81f6-11e7-933c-08b0badf527d.png)

<a id="ID_4-2"></a>

### 線形代数の微分方程式への応用
![twitter_ _9-1_170404](https://user-images.githubusercontent.com/25688193/29313939-b69877dc-81f6-11e7-86b8-33080b72bdc7.png)
![twitter_ _9-2_170404](https://user-images.githubusercontent.com/25688193/29313942-b6bc1c00-81f6-11e7-8097-bd41020ebe19.png)
![twitter_ _9-3_170405](https://user-images.githubusercontent.com/25688193/29313940-b6a7e848-81f6-11e7-8b2f-58d16e7c9916.png)

<a id="ID_4-3"></a>

### １階の線形斉次連立微分方程式の解を見つける方法
![twitter_ _10-1_170406](https://user-images.githubusercontent.com/25688193/29313941-b6ad0b84-81f6-11e7-8c29-5944ae34b0a0.png)
![twitter_ _10-2_170406](https://user-images.githubusercontent.com/25688193/29313945-b6c1058a-81f6-11e7-9215-7f550614adaf.png)
![twitter_ _10-3_170406](https://user-images.githubusercontent.com/25688193/29313943-b6bc7e8e-81f6-11e7-8be6-45f7ac0fbe77.png)
![twitter_ _10-4_170406](https://user-images.githubusercontent.com/25688193/29313944-b6bdd5cc-81f6-11e7-9009-9a606f78cba8.png)

<a id="ID_4-3-1"></a>

#### 固有値 λ が複素数解の場合
![twitter_ _10-5_170407](https://user-images.githubusercontent.com/25688193/29313946-b6cc9850-81f6-11e7-8a4c-c3f55b727ad7.png)
![twitter_ _10-6_170407](https://user-images.githubusercontent.com/25688193/29313947-b6d07df8-81f6-11e7-9272-c393a1cc058c.png)
![twitter_ _10-7_170407](https://user-images.githubusercontent.com/25688193/29313948-b6de7c14-81f6-11e7-916a-964080dc0530.png)

<a id="ID_4-3-2"></a>

#### 固有値 λ が重解の場合
![twitter_ _10-8_170407](https://user-images.githubusercontent.com/25688193/29313949-b6df3a28-81f6-11e7-99ef-c46349948261.png)
![twitter_ _10-9_170408](https://user-images.githubusercontent.com/25688193/29313951-b6e3f694-81f6-11e7-8d24-294e925fab26.png)
![twitter_ _10-10_170408](https://user-images.githubusercontent.com/25688193/29313950-b6e2dffc-81f6-11e7-8593-c1dd8146f448.png)
![twitter_ _10-11_170408](https://user-images.githubusercontent.com/25688193/29313952-b6ef9c38-81f6-11e7-8c05-48790b13261f.png)

<a id="ID_4-4"></a>

### 基本解行列 [fundamental matrix solution]
![twitter_ _10-12_170408](https://user-images.githubusercontent.com/25688193/29313953-b6f30a4e-81f6-11e7-8131-b1980c4aeedb.png)
![twitter_ _10-13_170409](https://user-images.githubusercontent.com/25688193/29313955-b7058c82-81f6-11e7-8015-f13079536a49.png)
![twitter_ _10-14_170410](https://user-images.githubusercontent.com/25688193/29313954-b70598b2-81f6-11e7-8247-9be83b954060.png)
![twitter_ _10-15_170410](https://user-images.githubusercontent.com/25688193/29313956-b706287c-81f6-11e7-88c7-55f611b38ac5.png)
![twitter_ _10-16_170410](https://user-images.githubusercontent.com/25688193/29313957-b707b0fc-81f6-11e7-8b21-35ecd27dda84.png)
![twitter_ _10-17_170410](https://user-images.githubusercontent.com/25688193/29313958-b712e86e-81f6-11e7-8409-de1bb78ce957.png)

<a id="ID_4-5"></a>

### 非斉次線形連立方程式（定数変化法）
![twitter_ _11-1_170412](https://user-images.githubusercontent.com/25688193/29313959-b718b424-81f6-11e7-94db-ec607ea9b5e2.png)
![twitter_ _11-2_170412](https://user-images.githubusercontent.com/25688193/29313961-b72b08b8-81f6-11e7-8061-b8231cf9320b.png)
![twitter_ _11-3_170412](https://user-images.githubusercontent.com/25688193/29313962-b72b40f8-81f6-11e7-9361-a0eb3b3f30e8.png)
![twitter_ _11-4_170412](https://user-images.githubusercontent.com/25688193/29313960-b7292e62-81f6-11e7-90e8-ecd719a58993.png)

</br>
<a id="ID_5"></a>

## 微分方程式の定性的性質 [qualitative properties of differential equation] と力学系 [dynamical system]
![twitter_ _12-1_170417](https://user-images.githubusercontent.com/25688193/29313963-b72d8e3a-81f6-11e7-9770-db7195035de8.png)

<a id="ID_5-1"></a>

### 自律系微分方程式 [autonomous system of differential equation] と線形システムにおける安定性
![twitter_ _12-2_170422](https://user-images.githubusercontent.com/25688193/29313964-b7376eb4-81f6-11e7-8746-218fa8f87f7d.png)
![twitter_ _12-3_170422](https://user-images.githubusercontent.com/25688193/29313966-b74e3522-81f6-11e7-88fc-0d46739afda6.png)
![twitter_ _12-4_170423](https://user-images.githubusercontent.com/25688193/29313965-b74c4406-81f6-11e7-9f52-c9bb5a0453e5.png)
![twitter_ _12-5_170423](https://user-images.githubusercontent.com/25688193/29313967-b74edc0c-81f6-11e7-98f7-b0f77e9af0e0.png)
![twitter_ _12-6_170423](https://user-images.githubusercontent.com/25688193/29313969-b76559d2-81f6-11e7-9dc2-bd2695fec93d.png)
![twitter_ _12-7_170423](https://user-images.githubusercontent.com/25688193/29313968-b750835e-81f6-11e7-98ff-08daf86cd629.png)
![twitter_ _12-8_170424](https://user-images.githubusercontent.com/25688193/29313970-b770ad5a-81f6-11e7-87d7-d5e0c4c4c2ee.png)
![twitter_ _12-9_170424](https://user-images.githubusercontent.com/25688193/29313973-b7724dae-81f6-11e7-85f1-42513b621ca9.png)

<a id="ID_5-2"></a>

### 平衡解の安定性
![twitter_ _13-1_170425](https://user-images.githubusercontent.com/25688193/29313972-b771d964-81f6-11e7-9328-9221288e30af.png)
![twitter_ _13-2_170425](https://user-images.githubusercontent.com/25688193/29313971-b77129ce-81f6-11e7-8954-e46f07ae0a69.png)
![twitter_ _13-3_170426](https://user-images.githubusercontent.com/25688193/29313974-b773bb58-81f6-11e7-80b8-660d5c322b30.png)

<a id="ID_5-2-1"></a>

#### 自律系微分方程式の平衡解の安定性
![twitter_ _14-1_170426](https://user-images.githubusercontent.com/25688193/29313975-b788bcb0-81f6-11e7-9751-13b248e96a9b.png)
![twitter_ _14-2_170427](https://user-images.githubusercontent.com/25688193/29313980-b7980134-81f6-11e7-8078-0ac05bae9ffa.png)
![twitter_ _14-3_170427](https://user-images.githubusercontent.com/25688193/29313977-b79619d2-81f6-11e7-80b9-f944e5c2cba8.png)
![twitter_ _14-4_170427](https://user-images.githubusercontent.com/25688193/29313979-b7968fd4-81f6-11e7-8142-371e79131a97.png)

<a id="ID_5-3"></a>

### 相平面 [phase plane]
![twitter_ _15-1_170428](https://user-images.githubusercontent.com/25688193/29313976-b795bdc0-81f6-11e7-825f-0768c6aa5fd9.png)
![twitter_ _15-2_170428](https://user-images.githubusercontent.com/25688193/29313978-b79616ee-81f6-11e7-8ce5-97851d4dc4a5.png)
![twitter_ _15-3_170428](https://user-images.githubusercontent.com/25688193/29313981-b7aee12e-81f6-11e7-9036-fcd22800547a.png)
![twitter_ _15-4_170428](https://user-images.githubusercontent.com/25688193/29313982-b7b85d1c-81f6-11e7-8836-32c14c83b4c2.png)


## 参考文献

> キーポイント微分方程式 (理工系数学のキーポイント 5) </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%AD%E3%83%BC%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E5%BE%AE%E5%88%86%E6%96%B9%E7%A8%8B%E5%BC%8F-%E7%90%86%E5%B7%A5%E7%B3%BB%E6%95%B0%E5%AD%A6%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88-5-%E4%BD%90%E9%87%8E-%E7%90%86/dp/4000078658?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4000078658)</br>

> キーポイントフーリエ解析 (理工系数学のキーポイント (9))</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%AD%E3%83%BC%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%83%95%E3%83%BC%E3%83%AA%E3%82%A8%E8%A7%A3%E6%9E%90-%E7%90%86%E5%B7%A5%E7%B3%BB%E6%95%B0%E5%AD%A6%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88-9-%E8%88%B9%E8%B6%8A-%E6%BA%80%E6%98%8E/dp/4000078690)</br>
