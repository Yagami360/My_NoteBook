# カーネル法
非線形データに対する多変数解析の一種であるカーネル法の基本事項を記載したマイノートです。随時追記中。<br>

## 目次 [Contents]

1. [概要](#ID_1)
1. [カーネル法の基本的なアイデア](#ID_2)
1. [正定値カーネル](#ID_3)
    1. [実数の正定値カーネル](#ID_3-1)
    1. [複素数の正定値カーネル](#ID_3-2)
    1. [正定値カーネルの基本的な性質](#ID_3-3)
    1. [関数の内積で表現される正定値カーネル](#ID_3-4)
    1. [正定値カーネルの例](#ID_3-5)
        1. [線形カーネル（＝通常のユークリッド空間上での内積）](#ID_3-5-1)
        1. [指数型カーネル](#ID_3-5-2)
        1. [動径基底関数カーネル（RBFカーネル）[radial bases function kernel]](#ID_3-5-3)
        1. [ラプラスカーネル](#ID_3-5-4)
        1. [多項式カーネル](#ID_3-5-5)
1. [再生核ヒルベルト空間](#ID_4)
    1. [再生核の性質](#ID_4-1)
        1. [再生核のテンソル積](#ID_4-1-1)
    1. [再生核ヒルベルト空間の線形汎関数を用いた特徴付けとリースの表現定理](#ID_4-2)
        1. 【補足】リースの表現定理
    1. [Moore-Aronszajn の定理](#ID_4-3)
        1. [特徴写像とカーネルトリック（Moore - Aronszajn の定理kあらの帰着）](#ID_4-3-1)
    1. [再生核ヒルベルト空間の具体的な構成](#ID_4-4)
        1. [線形カーネルの再生核ヒルベルト空間](#ID_4-4-1)
        1. [有限集合上の（エルミート行列の）再生核ヒルベルト空間](#ID_4-4-2)
        1. [多項式カーネルの再生核ヒルベルト空間](#ID_4-4-3)
        1. [ヒルベルト空間への埋め込み写像による再生核ヒルベルト空間の構成](#ID_4-4-4)
            1. RBF カーネルの再生核ヒルベルト空間
            1. ラプラスカーネルの再生核ヒルベルト空間
            1. 【補足】埋め込み写像
            1. 【補足】測度論
        1. ソボレフ空間 [Sobolev space]
1. [正定値カーネルの理論](#ID_5)
    1. 負定値カーネル
    1. Schoenberg の定理
    1. Bochner の定理
    1. Mercer（マーセル、マーサー）の定理
        1. 【補足】積分作用素
        1. 【補足】スペクトル分解
1. 汎化性能と正則化
    1. リプレゼンター定理
1. 各種カーネル法
    1. [【外部リンク】サポートベクターマシン [SVM : Support Vector Machine]](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_9)
    1. [【外部リンク】カーネル主成分分析 [kernel PCA : kernel Principal Component Analysis]](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_2-5-2)
1. 補足
    1. [【外部リンク】関数解析とヒルベルト空間](http://yagami12.hatenablog.com/entry/2018/10/03/134340)
    1. [【外部リンク】最適化問題](http://yagami12.hatenablog.com/entry/2017/09/17/101739)
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## ■ 概要
> 記載中...


<a id="ID_2"></a>

## ■ カーネル法の基本的なアイデア
![image](https://user-images.githubusercontent.com/25688193/46556230-fcaaf980-c920-11e8-9140-fcab41de7260.png)<br>

> 記載中...


<a id="ID_3"></a>

## ■ 正定値カーネル

<a id="ID_3-1"></a>

### ◎ 実数の正定値カーネル
![image](https://user-images.githubusercontent.com/25688193/46555969-1a2b9380-c920-11e8-8a72-0b7941f3841c.png)<br>

![image](https://user-images.githubusercontent.com/25688193/46429746-32fe4280-c782-11e8-99e4-8c0f2b30e128.png)<br>


<a id="ID_3-2"></a>

### ◎ 複素数の正定値カーネル
実数ではなく複素数で扱うことにより、理論を展開する上での見通しがよくなることがあるが、これは正定値カーネルに関しても同様である。（例えば、後述の Bochner の定理など）<br>
そのため、複素数の正定値カーネルなるものを定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/46556410-88248a80-c921-11e8-9aa3-685f45c0ca2b.png)<br>

ここで、複素数の正定値カーネルでは、実数の正定値カーネルとは異なり、<br>
（実数の正定値カーネルのときの）対称性の条件 ![image](https://user-images.githubusercontent.com/25688193/46447227-99538700-c7bb-11e8-9e01-0a479bd3116a.png) にあたるエルミート性の条件 ![image](https://user-images.githubusercontent.com/25688193/46447250-acfeed80-c7bb-11e8-90fd-e2a5b850f9df.png) は不要となる。<br>
これは、エルミート性が正定値性の帰着として導かれるためである。<br>

そのことを以下に示す。<br>

任意の１点 ![image](https://user-images.githubusercontent.com/25688193/46447395-842b2800-c7bc-11e8-8745-927b9d6ab367.png) に対する正定値性は、<br>
![image](https://user-images.githubusercontent.com/25688193/46447432-c3597900-c7bc-11e8-958a-624a34494448.png)<br>
より非負の実数である。<br>
又、任意の２点 ![image](https://user-images.githubusercontent.com/25688193/46447450-d79d7600-c7bc-11e8-9428-c14d5017901b.png)l と複素数定数 ![image](https://user-images.githubusercontent.com/25688193/46447470-f13ebd80-c7bc-11e8-9c46-746d8b738159.png) に対する正定値性は、<br>
![image](https://user-images.githubusercontent.com/25688193/46447789-c6556900-c7be-11e8-8f0d-16126b75810c.png)<br>
この式の複素数部分に対して、その複素共役を取ると、<br>
![image](https://user-images.githubusercontent.com/25688193/46447823-edac3600-c7be-11e8-8ece-733c5d46e338.png)<br>
両式の差をとると、<br>
![image](https://user-images.githubusercontent.com/25688193/46448473-f3efe180-c7c1-11e8-8bb8-577ba23472fc.png)<br>


<a id="ID_3-3"></a>

### ◎ 正定値カーネルの基本的な性質
次に、この正定値カーネルに関して成り立つ性質をいくつか見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/46507390-358c9500-c873-11e8-88d8-85f6350ab6e5.png)<br>

- （証明略）<br>


<a id="ID_3-4"></a>

### ◎ 関数の内積で表現される正定値カーネル
以下の定理で示すように、内積空間上での関数の内積は、正定値カーネルになる。
![image](https://user-images.githubusercontent.com/25688193/46456509-1990e100-c7ea-11e8-802f-f2fa5be6af6a.png)<br>

- （証明）<br>
    正定値性を示すために、正定値性の条件<br>
    ![image](https://user-images.githubusercontent.com/25688193/46456569-49d87f80-c7ea-11e8-8d0a-51e4c1d2156e.png)<br>
    の左辺に ![image](https://user-images.githubusercontent.com/25688193/46456587-5957c880-c7ea-11e8-9a8f-ad95d81a94bd.png) を代入すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46456601-6a083e80-c7ea-11e8-875c-11befdaa839a.png)<br>
    ノルムの２乗は必ず正になるので、
    ![image](https://user-images.githubusercontent.com/25688193/46456620-78565a80-c7ea-11e8-9ddc-91993ea1979f.png)<br>
    の関係が成り立ち、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46456587-5957c880-c7ea-11e8-9a8f-ad95d81a94bd.png) が、正定値カーネルになることがわかる。<br>


<a id="ID_3-5"></a>

### ◎ 正定値カーネルの例
m 次元ユークリッド空間 ![image](https://user-images.githubusercontent.com/25688193/46507423-5fde5280-c873-11e8-8fe5-45cf58eaab55.png) 上で定義されるいくつかの正定値カーネルの例を見ていく。<br>


<a id="ID_3-5-1"></a>

#### ☆ 線形カーネル（＝通常のユークリッド空間上での内積）
![image](https://user-images.githubusercontent.com/25688193/46507919-00357680-c876-11e8-90a8-17315d452ee3.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46507904-e136e480-c875-11e8-8600-fc8920433b6c.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46507932-0f1c2900-c876-11e8-8156-f9c43f67c316.png)<br>

ここで、このカーネルが、確かに正定値カーネルになることを示す。<br>
この線形カーネルは、先の関数の内積で表現される正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/46512384-9d9ca480-c88e-11e8-9165-8b894c760bb2.png) より、明らかに正定値カーネルであることが分かる。<br>


<a id="ID_3-5-2"></a>

#### ☆ 指数型カーネル
![image](https://user-images.githubusercontent.com/25688193/46508077-b305d480-c876-11e8-8771-3895d12834a9.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46507973-48ed2f80-c876-11e8-9da6-42c785117c49.png)<br>

ここで、このカーネルが、確かに正定値カーネルになることを示す。<br>
この指数型カーネルを、Tayler 展開すると、<br>
![image](https://user-images.githubusercontent.com/25688193/46512515-55ca4d00-c88f-11e8-9c12-e0852d81e7ba.png)<br>
先の正定値カーネルの性質（カーネル線形結合、カーネルの積）より、この展開式の各項の点列<br>
![image](https://user-images.githubusercontent.com/25688193/46512531-6da1d100-c88f-11e8-9d96-aa859dfbbc42.png)<br>
の和もまた正定値カーネルとなる。<br>
更に、![image](https://user-images.githubusercontent.com/25688193/46512561-975af800-c88f-11e8-9e02-ec4b9bb2abd2.png) は、この点列の極限となるが、<br>
先の正定値カーネルの性質（カーネルの点列の極限）より、この指数型カーネル ![image](https://user-images.githubusercontent.com/25688193/46512572-af327c00-c88f-11e8-819e-14bb53d04cec.png) は、正定値カーネルであることが分かる。<br>


<a id="ID_3-5-3"></a>

#### ☆　動径基底関数カーネル（RBFカーネル）[radial bases function kernel]<br>
![image](https://user-images.githubusercontent.com/25688193/46508767-0299cf80-c87a-11e8-8b5b-5f44c5e5f5b6.png)<br>
ここで、上式のパラメータ σ は、関数の広がりを制御するパラメータである。<br>

![image](https://user-images.githubusercontent.com/25688193/46509874-45f73c80-c880-11e8-84b3-e014a9bd7397.png)<br>

ここで、この RBF カーネル関数を、例えば、SVM（サポートベクターマシン）に適用した場合、このカーネル関数の制御パラメータ σ に関して、一般的に、以下のような関係が成り立つ。<br>

1. 制御パラメータ σ が大きい <br>
    ⇒ 写像後の特徴ベクトルが離れた位置に写像される<br>
    ⇒ 入力データ（特徴ベクトル）から離れている広範囲のサポートベクトルが識別関数に寄与する。<br>
1. 制御パラメータ σ が小さい<br>
    ⇒ 写像後の特徴ベクトルが近い位置に写像される<br>
    ⇒ 入力データ（特徴ベクトル）近傍のサポートベクトルが識別関数に寄与する。<br>

![image](https://user-images.githubusercontent.com/25688193/46510437-e9961c00-c883-11e8-895c-0c7e3ae47da6.png)<br>

ここで、このカーネルが、確かに正定値カーネルになることを示す。<br>
この RBF カーネルを変形すると、<br>
![image](https://user-images.githubusercontent.com/25688193/46512708-616a4380-c890-11e8-8080-0a7458bc4ad2.png)<br>
となるが、先の指数型カーネル ![image](https://user-images.githubusercontent.com/25688193/46512737-7e9f1200-c890-11e8-97c7-b2d6a40d0140.png) が正定値カーネルであったことを利用すると、<br>
正定値カーネルの性質より、この RBF カーネルも正定値カーネルであることが分かる。<br>


<a id="ID_3-5-4"></a>

#### ☆ ラプラスカーネル
![image](https://user-images.githubusercontent.com/25688193/46509900-7b038f00-c880-11e8-9710-f5e2fbd19028.png)<br>


<a id="ID_3-5-5"></a>

#### ☆ 多項式カーネル
![image](https://user-images.githubusercontent.com/25688193/46509968-f5341380-c880-11e8-97b9-2ff815ffb52c.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46509952-d897db80-c880-11e8-9543-8fc0cb0fa2fb.png)<br>

この関数は、例えば d=2 で、c=1 の場合、<br>
![image](https://user-images.githubusercontent.com/25688193/46510579-d6378080-c884-11e8-8a81-9f697c431700.png)<br>
上式の ![image](https://user-images.githubusercontent.com/25688193/46511394-611a7a00-c889-11e8-8ebe-3234348ee96c.png) のみ依存する項目を、<br>
![image](https://user-images.githubusercontent.com/25688193/46511597-85c32180-c88a-11e8-8453-e69301233521.png)<br>
のように分離すると、多項式カーネルを<br>
![image](https://user-images.githubusercontent.com/25688193/46511639-ac815800-c88a-11e8-9fed-6948e84b589e.png)<br>
の様な６次元の内積演算の形となる。<br>
即ち、逆に言い換えれば、<br>
６次元空間でのベクトルの内積演算 ![image](https://user-images.githubusercontent.com/25688193/46511663-d175cb00-c88a-11e8-856d-d9b8cab7f304.png) が、<br>
先の２次元ベクトルの内積とスカラー積<br>
![image](https://user-images.githubusercontent.com/25688193/46511690-fc601f00-c88a-11e8-9e5f-985a2ed72757.png)<br>
の計算で出来ることになる！⇒ 計算量を削減出来る！<br>

次に、（次数が）一般の場合 d では、<br>
多項式カーネル ![image](https://user-images.githubusercontent.com/25688193/46511996-ae4c1b00-c88c-11e8-9066-d73e8da61096.png) を２項定理を用いて展開すると、<br>
![image](https://user-images.githubusercontent.com/25688193/46512023-d9366f00-c88c-11e8-96ec-e7398cd8f209.png)<br>
即ち、多項数カーネルの使用した時の２つのベクトル ![image](https://user-images.githubusercontent.com/25688193/46524114-bc1c9300-c8c2-11e8-85b1-e96c2d3f3488.png) の次元（次数）の上限は ∑ の形で求めることが出来る！<br>


<a id="ID_4"></a>

## ■ 再生核ヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/46570892-a84a5d00-c9a6-11e8-9afd-fa2ca50310fe.png)<br>

> 【メモ】<br>
> 正定値カーネルや再生核ヒルベルト空間での定義で、入力データとなる集合 X が単なる集合じゃなくてベクトル空間のほうがいいのでは？と思ったけど、入力データによっては、ベクトル空間であったり、内積空間であったり、ノルム空間であったりし得えるから、一般性を確保するために集合で定義しているという理解でいいんかいな？<br>


- 【参考】<br>
    - [再生核ヒルベルト空間をなんとなく理解する - 備忘録とか あと あれとか それとか](http://d.hatena.ne.jp/hgshrs/20130331/1364707361)<br>
    - [カーネルトリックと関数解析についてまとめてみた](https://qiita.com/muripo_life/items/ac186f740f493c2b2058)<br>
    - [Reproducing Kernel Hilbert Spaceの数理とMercerの定理 - Obey Your MATHEMATICS.](http://mathetake.hatenablog.com/entry/2016/12/29/223101)<br>
    - [線形汎関数を用いた再生カーネルヒルベルト空間の特徴付けとリースの表現定理](http://ibisforest.org/index.php?plugin=attach&refer=K-NEL%2Faddenda%2Fchap6&openfile=riesz.pdf)<br>
    - [リースの表現定理](http://yagami12.hatenablog.com/entry/2018/10/03/134340#ID_A-4)<br>


<a id="ID_4-1"></a>

### ◎ 再生核の性質
![image](https://user-images.githubusercontent.com/25688193/46570786-e5adeb00-c9a4-11e8-9808-6a488d874f47.png)<br>

- （証明）<br>
    正定値カーネルの対称性 ![image](https://user-images.githubusercontent.com/25688193/46570313-0eca7d80-c99d-11e8-98ec-3288108ed8b6.png) やエルミート性 ![image](https://user-images.githubusercontent.com/25688193/46570542-c1500f80-c9a0-11e8-93ee-5054f426b100.png) を利用すると、<br>
    ２つの再生核 ![image](https://user-images.githubusercontent.com/25688193/46570562-f8262580-c9a0-11e8-8ab7-9be3a8dfa647.png) に対して、再生性の条件より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46570574-20ae1f80-c9a1-11e8-9443-e0be84e7bd0b.png)<br>
    の関係より、この２つの再生核は同一であるので、再生核は一意に存在することが分かる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/46570791-f78f8e00-c9a4-11e8-85ae-e04b611ede56.png)<br>

- （証明）<br>
    （複素数の）正定値カーネルの定義の正定性は、<br>
    任意の整数 ![image](https://user-images.githubusercontent.com/25688193/46570749-64eeef00-c9a4-11e8-9a64-75c92d5e5c62.png) と ![image](https://user-images.githubusercontent.com/25688193/46570752-720bde00-c9a4-11e8-91ea-0fce8c44c128.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46570759-82bc5400-c9a4-11e8-83db-528190290ead.png)<br>
    であったが、この左辺は、再生核 ![image](https://user-images.githubusercontent.com/25688193/46570796-0d9d4e80-c9a5-11e8-9c81-c746fad53676.png) を用いて、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46570808-2c9be080-c9a5-11e8-9125-defa211438af.png)<br>
    従って、再生核 ![image](https://user-images.githubusercontent.com/25688193/46570796-0d9d4e80-c9a5-11e8-9c81-c746fad53676.png) は、正定値カーネルである。<br>


<a id="ID_4-1-1"></a>

#### ☆ 再生核のテンソル積
再生核のテンソル積が、また再生核になることを示すために、まず、再生核ヒルベルト空間のテンソル積なるものを定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/46578354-72a28400-ca39-11e8-9004-3b4754ba6357.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46577331-27c84280-ca20-11e8-9356-df87675ac8f3.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/46578434-e2fdd500-ca3a-11e8-89ac-6a4dabe401c4.png)<br>

- （証明）<br>
    テンソル積の定義 ![image](https://user-images.githubusercontent.com/25688193/46578493-c367ac00-ca3c-11e8-91ab-64e46469f925.png) より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46578496-d4182200-ca3c-11e8-9520-18001ccbe5bc.png)<br>
    内積の式は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46578498-e6925b80-ca3c-11e8-884a-d3b279cea5ff.png)<br>
    となり、再生性の条件が成り立つので、<br>
    この ![image](https://user-images.githubusercontent.com/25688193/46578501-fdd14900-ca3c-11e8-9fd7-5f6157301d36.png) は再生核となる。<br>


<a id="ID_4-2"></a>

### ◎ 再生核ヒルベルト空間の線形汎関数を用いた特徴付けとリースの表現定理
![image](https://user-images.githubusercontent.com/25688193/46570901-d334b100-c9a6-11e8-91c5-563dbbdfbcad.png)<br>

- （証明）<br>
    リースの表現定理より、線形汎関数が連続（＝有界）であるならば、<br>
    ヒルベルト空間上の要素（関数）g∈H が存在して、任意のヒルベルト空間上の要素（関数）∀f∈H に対して、有界線形汎関数は内積で表現出来る。即ち、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46566067-1402da80-c953-11e8-8a4c-645e12e4dc4c.png)<br>
    と表現できる。<br>
    従って、この中に、L(f) が f(x) となるような ![image](https://user-images.githubusercontent.com/25688193/46566079-27ae4100-c953-11e8-8053-f6418bd97033.png) が存在し、 <br>
    ![image](https://user-images.githubusercontent.com/25688193/46566091-63490b00-c953-11e8-9c3c-2f0f209f3238.png)<br>
    の関係が成り立つ。<br>

> 【メモ】<br>
> 再生性の条件 ![image](https://user-images.githubusercontent.com/25688193/46566137-dce0f900-c953-11e8-8416-0c4d02397343.png) と、リースの表現定理の内積表現 ![image](https://user-images.githubusercontent.com/25688193/46566178-b2dc0680-c954-11e8-882e-54adb5a8e531.png) が対応していることに注目。<br>


<a id="ID_4-2-1"></a>

#### 【補足】リースの表現定理
![image](https://user-images.githubusercontent.com/25688193/45737382-a05d8f80-bc28-11e8-8e4d-fcc7fe93f3cf.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45734425-781d6300-bc1f-11e8-8202-603d2e2e08de.png)<br>

> 【メモ】<br>
> 簡単言えば、このリースの表現定理は、射影定理によって直交補空間から非零元を取ってきて、それをグラムシュミットの方法で正規直交化している流れになっている。<br>


<a id="ID_4-3"></a>

### ◎ Moore-Aronszajn の定理
![image](https://user-images.githubusercontent.com/25688193/46570911-02e3b900-c9a7-11e8-8e65-117f1f0c4c3b.png)<br>

> 【メモ】<br>
> 再生核ヒルベルト空間、定義だけみても意味分かんないけど、Moore-Aronszajn の定理まで見てみればようやく意味がわかってくる印象<br>


先の再生核ヒルベルト空間の線形汎関数を用いた特徴付けと、<br>
Moore-Aronszajn の定理より、再生核ヒルベルト空間を再解釈（＝特徴付け）したのが以下の図である。
<br>

![image](https://user-images.githubusercontent.com/25688193/46566609-ba9fa900-c95c-11e8-8c28-a89da4de0f5d.png)<br>


<a id="ID_4-3-1"></a>

#### ☆ 特徴写像とカーネルトリック（Moore - Aronszajn の定理からの帰着）
特徴写像 Φ は、集合 X から再生核ヒルベルト空間への写像 ![image](https://user-images.githubusercontent.com/25688193/46576774-175a9c80-ca0d-11e8-8ca6-4e36fe4365db.png) である。<br>
このとき、Moore - Aronszajn の定理より、再生核ヒルベルト空間上の任意の２つの要素（関数）∀f,g ∈H の内積は、<br>
![image](https://user-images.githubusercontent.com/25688193/46576776-3b1de280-ca0d-11e8-9347-0963c4cea248.png)<br>

従って、<br>
![image](https://user-images.githubusercontent.com/25688193/46576790-81734180-ca0d-11e8-8986-c8112e774a42.png)<br>
となり、カーネルトリックが成り立っていることが分かる。<br>
つまり、カーネルトリックは、Moore - Aronszajn の定理からの帰着で自然に導かれる。<br>


<a id="ID_4-4"></a>

### ◎ 再生核ヒルベルト空間の具体的構成
先の Moore-Aronszanの定理より、正定値カーネルにより、再生核ヒルベルト空間の基底が定まり、再生核ヒルベルト空間が構成されることを見てきたが、ここでは、具体的に、幾何学的に表現が可能な場合の再生核ヒルベルト空間を見ていく。<br>


<a id="ID_4-4-1"></a>

#### ☆ 線形カーネルの再生核ヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/46706205-36a43480-cc6e-11e8-84b3-925f0f2a6427.png)<br>

- （証明）<br>
    線形カーネルは、先に示したように正定値カーネルである。<br>
    又、Moore-Aronszanの定理より、再生核ヒルベルト空間の任意の要素（関数）f∈H は、線形写像である線形カーネルを基底とする線形結合<br>
    ![image](https://user-images.githubusercontent.com/25688193/46660738-a674d980-cbf2-11e8-9872-2fdcbe2d7d37.png)<br>
	で表現できるので、<br>
	この再生核ヒルベルト空間中の任意の要素 f もまた線形写像であることが分かる。<br>
    <br>
    更に、この再生核ヒルベルト空間中の任意の２つの要素（＝関数）∀f,g∈H の内積は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46660767-b68cb900-cbf2-11e8-9803-13cc744ec119.png)<br>
	となり、ユークリッド空間の内積そのものとなるので、<br>
	この線形カーネルによる再生核ヒルベルト空間は、ユークリッド空間そのものであることが分かる。<br>

<br>

尚、カーネル PCA の手法においては、この線形カーネルを用いることにより、<br>
主成分が非線形になるようなデータに対し、（より高次元空間の再生核ヒルベルト空間における）線形な通常の主成分分析に落とし込むことを実現している。（詳細は後述）<br>

![image](https://user-images.githubusercontent.com/25688193/46661275-d4a6e900-cbf3-11e8-99ea-2309216fd480.png)<br>


- 【参考】<br>
    - [線形カーネル](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#ID_3-5-1)<br>
    - [カーネル主成分分析](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_2-5-2)<br>


<a id="ID_4-4-2"></a>

#### ☆ 有限集合上の（エルミート行列の）再生核ヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/46671094-d92ccb00-cc0e-11e8-9f01-04d3f510c204.png)<br>

- （証明略）証明の方針のみ記載<br>
    内積が再生性の条件を満たすことを示せばよい。<br>
    即ち、例えば、エルミート行列 K の第 i 行である ![image](https://user-images.githubusercontent.com/25688193/46670837-3b390080-cc0e-11e8-8c88-a77035efdeda.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46672092-843e8400-cc11-11e8-9920-9c9aac9852d6.png)<br>
    を示せばよい。<br>


<a id="ID_4-4-3"></a>

#### ☆ 多項式カーネルの再生核ヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/46706510-cb5b6200-cc6f-11e8-8770-1f77a4cfc12c.png)<br>

- （証明略）<br>


<a id="ID_4-4-4"></a>

#### ☆ ヒルベルト埋め込み写像による再生核ヒルベルト空間の構成
再生核ヒルベルト空間を、他のヒルベルト空間の部分空間として構成する一般的な方法に、埋め込み写像による構成方法が存在する。<br>

- X : 集合<br>
- ![image](https://user-images.githubusercontent.com/25688193/46723566-1ea2d400-ccb3-11e8-8109-3219a99dd431.png) : 集合 X 上の全ての複素数値関数からなる関数空間<br>
    各点収束による位相構造を加える。<br>
- ![image](https://user-images.githubusercontent.com/25688193/46723610-35492b00-ccb3-11e8-9881-fbbf37e0056f.png) : 測度空間<br>
- ![image](https://user-images.githubusercontent.com/25688193/46723804-a4bf1a80-ccb3-11e8-90eb-06dfdacec36a.png) : L2 空間？<br>
- H : T×X 上の可測関数。以下の関係が成り立つと仮定する。<br>
    - ![image](https://user-images.githubusercontent.com/25688193/46723879-d1733200-ccb3-11e8-865f-346a39b17eea.png)<br>
    - このを基底とした空間が、![image](https://user-images.githubusercontent.com/25688193/46723804-a4bf1a80-ccb3-11e8-90eb-06dfdacec36a.png) になる。即ち、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46723909-e8198900-ccb3-11e8-88c3-e521e3fc3e31.png)<br>
- ![image](https://user-images.githubusercontent.com/25688193/46723978-097a7500-ccb4-11e8-94d1-73400a0d6330.png) : 以下定義により、埋め込み写像になる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/46724014-1c8d4500-ccb4-11e8-9d31-9f654472601c.png)<br>
- ![image](https://user-images.githubusercontent.com/25688193/46724098-47779900-ccb4-11e8-81d6-faa0442713df.png) : 埋め込み写像 J の像で与えられるの ![image](https://user-images.githubusercontent.com/25688193/46723566-1ea2d400-ccb3-11e8-8109-3219a99dd431.png) 部分空間<br>
    埋め込み写像 J が、![image](https://user-images.githubusercontent.com/25688193/46723804-a4bf1a80-ccb3-11e8-90eb-06dfdacec36a.png) と部分空間 ![image](https://user-images.githubusercontent.com/25688193/46724216-83aaf980-ccb4-11e8-8c6e-aba84128c709.png) の間のヒルベルト空間として同型を与える。<br>


> 記載中...

>【Memo】<br>
> 前提知識として、以下の項目が必要？<br>
> - 埋め込み写像<br>
> - 測度論（測度空間、測度関数）<br>


<a id="ID_4-4-5"></a>

#### ☆ ソボレフ空間 [Soboveb space]
再生核ヒルベルト空間の重要な例として、ソボレフ空間がある。<br>


> 記載中...



<a id="ID_5"></a>

## ■ 正定値カーネルの理論
ここでは、正定値カーネルの理論と称して、以下のようなトピックを取り上げる。<br>

- 負定値カーネルと正定値カーネルを関連づける定理である Schoenberg の定理<br>
- Schoenberg の定理を用いて、正定値カーネルや負定値カーネルから、様々な正定値カーネルを系統的に生成出来ること。<br>
- ユークリッド空間上での平行移動（アフィン変換）に対して不変な正定値カーネル全体を、その正定値カーネルのフーリエ変換により特徴づけることを主張している Bochner の定理。<br>
- 正定値カーネルに対する固有値分解である Mercer の定理<br>



---

<a id="参考文献"></a>

## ■ 参考文献

- カーネル法入門―正定値カーネルによるデータ解析 (シリーズ 多変量データの統計科学)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95%E5%85%A5%E9%96%80%E2%80%95%E6%AD%A3%E5%AE%9A%E5%80%A4%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E5%A4%9A%E5%A4%89%E9%87%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%B5%B1%E8%A8%88%E7%A7%91%E5%AD%A6-%E7%A6%8F%E6%B0%B4-%E5%81%A5%E6%AC%A1/dp/4254128088?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4254128088)<br>

- カーネル多変量解析―非線形データ解析の新しい展開 (シリーズ確率と情報の科学)<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90%E2%80%95%E9%9D%9E%E7%B7%9A%E5%BD%A2%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90%E3%81%AE%E6%96%B0%E3%81%97%E3%81%84%E5%B1%95%E9%96%8B-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA%E7%A2%BA%E7%8E%87%E3%81%A8%E6%83%85%E5%A0%B1%E3%81%AE%E7%A7%91%E5%AD%A6-%E8%B5%A4%E7%A9%82-%E6%98%AD%E5%A4%AA%E9%83%8E/dp/4000069713?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4000069713)<br>

- サポートベクターマシン入門<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%83%99%E3%82%AF%E3%82%BF%E3%83%BC%E3%83%9E%E3%82%B7%E3%83%B3%E5%85%A5%E9%96%80-%E3%83%8D%E3%83%AD-%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%86%E3%82%A3%E3%82%A2%E3%83%8B%E3%83%BC%E3%83%8B/dp/4320121341?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320121341)<br>

- はじめてのパターン認識 <br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)<br>
