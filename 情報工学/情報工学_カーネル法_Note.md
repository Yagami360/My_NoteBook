# カーネル法
非線形データに対する多変数解析の一種であるカーネル法の数理面について勉強したことをまとめたノート（忘備録）です。随時追記中。<br>

## 目次 [Contents]

1. [概要](#概要)
    1. [カーネル法の基本的なアイデアとカーネルトリック](#カーネル法の基本的なアイデアとカーネルトリック)
1. [正定値カーネル](#正定値カーネル)
    1. [実数の正定値カーネル](#実数の正定値カーネル)
    1. [複素数の正定値カーネル](#複素数の正定値カーネル)
    1. [正定値カーネルの基本的な性質](#正定値カーネルの基本的な性質)
    1. [関数の内積で表現される正定値カーネル](#関数の内積で表現される正定値カーネル)
    1. [正定値カーネルの例](#正定値カーネルの例)
        1. [線形カーネル（＝通常のユークリッド空間上での内積）](#線形カーネル（＝通常のユークリッド空間上での内積）)
        1. [指数型カーネル](#指数型カーネル)
        1. [動径基底関数カーネル（RBFカーネル）[radial bases function kernel]](#動径基底関数カーネル（RBFカーネル）)
        1. [ラプラスカーネル](#ラプラスカーネル)
        1. [多項式カーネル](#多項式カーネル)
1. [再生核ヒルベルト空間](#再生核ヒルベルト空間)
    1. [再生核の性質](#再生核の性質)
        1. [再生核のテンソル積](#再生核のテンソル積)
    1. [再生核ヒルベルト空間の線形汎関数を用いた特徴付けとリースの表現定理](#再生核ヒルベルト空間の線形汎関数を用いた特徴付けとリースの表現定理)
        1. [【補足】リースの表現定理](#【補足】リースの表現定理)
    1. [Moore-Aronszajn の定理](#Moore-Aronszajnの定理)
        1. [特徴写像とカーネルトリック（Moore - Aronszajn の定理からの帰着）](#特徴写像とカーネルトリック（Moore-Aronszajnの定理からの帰着）)
    1. [再生核ヒルベルト空間の具体的な構成](#再生核ヒルベルト空間の具体的な構成)
        1. [線形カーネルの再生核ヒルベルト空間](#線形カーネルの再生核ヒルベルト空間)
        1. [有限集合上の（エルミート行列の）再生核ヒルベルト空間](#有限集合上の（エルミート行列の）再生核ヒルベルト空間)
        1. [多項式カーネルの再生核ヒルベルト空間](#多項式カーネルの再生核ヒルベルト空間)
    1. [埋め込み写像による再生核ヒルベルト空間の構成](#埋め込み写像による再生核ヒルベルト空間の構成)
        1. [フーリエ変換の形をした埋め込み写像による再生核ヒルベルト空間の構成](#フーリエ変換の形をした埋め込み写像による再生核ヒルベルト空間の構成)
        1. [RBF カーネルの再生核ヒルベルト空間](#RBFカーネルの再生核ヒルベルト空間)
        1. [ラプラスカーネルの再生核ヒルベルト空間](#ラプラスカーネルの再生核ヒルベルト空間)
    1. [ソボレフ空間 [Sobolev space]](#ソボレフ空間)
1. [正定値カーネルの理論](#正定値カーネルの理論)
    1. [負定値カーネル](#負定値カーネル)
        1. [負定値カーネルの基本的な性質](#負定値カーネルの基本的な性質)
        1. [負定値カーネルの基本的な例](#負定値カーネルの基本的な例)
    1. [Schoenberg の定理](#Schoenbergの定理)
    1. [カーネルを生成する操作](#カーネルを生成する操作)
    1. [Bochner の定理](#Bochnerの定理)
    1. [Mercer（マーセル、マーサー）の定理](#Mercerの定理)
        1. [積分作用素、積分核](#積分作用素、積分核)
        1. [積分作用素とヒルベルト＝シュミット作用素](#積分作用素とヒルベルト＝シュミット作用素)
        1. [積分核のヒルベルト＝シュミット展開](#積分核のヒルベルト＝シュミット展開)
        1. [正値積分核（Mercer核）と Mercer の定理](#正値積分核（Mercer核）とMercerの定理)
        1. [Mercer 核が定める再生核ヒルベルト空間の具体的な構成](#Mercer核が定める再生核ヒルベルト空間の具体的な構成)
        1. [【補足】ヒルベルト空間上の線形作用素のトーレス、ヒルベルト＝シュミット作用素](#【補足】ヒルベルト空間上の線形作用素のトーレス、ヒルベルト＝シュミット作用素)
        1. [【補足】共役作用素と正値性](#【補足】共役作用素と正値性)
        1. 【補足】ハウスドルフ空間
1. 汎化性能と正則化
    1. リプレゼンター定理
1. 各種カーネル法
    1. [【外部リンク】サポートベクターマシン [SVM : Support Vector Machine]](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_9)
    1. [【外部リンク】カーネル主成分分析 [kernel PCA : kernel Principal Component Analysis]](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_2-5-2)
1. [ニューラルネットワークとカーネル法](#ニューラルネットワークとカーネル法)
1. 補足事項
    1. [【外部リンク】関数解析とヒルベルト空間](http://yagami12.hatenablog.com/entry/2018/10/03/134340)
    1. [【外部リンク】測度論](http://yagami12.hatenablog.com/entry/2018/11/04/232957)
    1. [【外部リンク】最適化問題](http://yagami12.hatenablog.com/entry/2017/09/17/101739)
1. [参考文献](#参考文献)
    1. [使用コード](#使用コード)

---

<a id="概要"></a>

## ■ 概要
> 記載中...

カーネル法は、非線形データに対する多変量解析の手法の１つであるが、
その特徴としては、非線形データを正定値カーネルの形に応じて定まる再生核ヒルベルト空間上の線形データに持ち込んで解析する点にある。<br>

ここでは、以下のような観点から、カーネル法全体の概要を見ている。<br>

- カーネル法の基本的なアイデアとカーネルトリック<br>
- カーネル法の１つであるサポートベクターマシン<br>
- カーネル法の１つであるカーネル主成分主成分<br>

<a id="カーネル法の基本的なアイデアとカーネルトリック"></a>

### ◎ カーネル法の基本的なアイデアとカーネルトリック（Moore - Aronszajn の定理からの帰着）
詳細は、[特徴写像とカーネルトリック（Moore - Aronszajn の定理からの帰着）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#-%E7%89%B9%E5%BE%B4%E5%86%99%E5%83%8F%E3%81%A8%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%83%88%E3%83%AA%E3%83%83%E3%82%AFmoore---aronszajn-%E3%81%AE%E5%AE%9A%E7%90%86%E3%81%8B%E3%82%89%E3%81%AE%E5%B8%B0%E7%9D%80) に記載。以下はその概要説明。<br>

> 記載中...

<!--
- カーネルトリック<br>
    ![image](https://user-images.githubusercontent.com/25688193/48049190-3b162b80-e1e1-11e8-88ec-ef2b67018faf.png)<br>

    > 【Memo】<br>
    > カーネルトリックは、Moore - Aronszajn の定理からの帰着で自然に導かれる。<br>

<br>

- カーネル法の１つであるカーネル主成分分析<br>
    ![image](https://user-images.githubusercontent.com/25688193/48049315-93e5c400-e1e1-11e8-9e8f-2aaccaf9e961.png)<br>
-->


<a id="正定値カーネル"></a>

## ■ 正定値カーネル

<a id="実数の正定値カーネル"></a>

### ◎ 実数の正定値カーネル
![image](https://user-images.githubusercontent.com/25688193/48116490-a4617180-e2a9-11e8-840e-84fd9d7bb2a3.png)<br>

> 正定値カーネルの解釈図を要追記

![image](https://user-images.githubusercontent.com/25688193/46429746-32fe4280-c782-11e8-99e4-8c0f2b30e128.png)<br>


<a id="複素数の正定値カーネル"></a>

### ◎ 複素数の正定値カーネル
実数ではなく複素数で扱うことにより、理論を展開する上での見通しがよくなることがあるが、これは正定値カーネルに関しても同様である。（例えば、後述の Bochner の定理など）<br>
そのため、複素数の正定値カーネルなるものを定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/48116531-bcd18c00-e2a9-11e8-9d61-691dbe821c41.png)<br>

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


<a id="正定値カーネルの基本的な性質"></a>

### ◎ 正定値カーネルの基本的な性質
次に、この正定値カーネルに関して成り立つ基本的な性質をいくつか見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/48708515-20629e80-ec46-11e8-8b1c-d0939495e4ae.png)<br>

- （証明略）<br>


<a id="関数の内積で表現される正定値カーネル"></a>

### ◎ 関数の内積で表現される正定値カーネル
以下の定理で示すように、内積空間上での関数の内積は、正定値カーネルになる。
![image](https://user-images.githubusercontent.com/25688193/46456509-1990e100-c7ea-11e8-802f-f2fa5be6af6a.png)<br>

- （証明）<br>
    正定値性を示すために、正定値性の条件<br>
    ![image](https://user-images.githubusercontent.com/25688193/46456569-49d87f80-c7ea-11e8-8d0a-51e4c1d2156e.png)<br>
    の左辺に ![image](https://user-images.githubusercontent.com/25688193/46456587-5957c880-c7ea-11e8-9a8f-ad95d81a94bd.png) を代入すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46456601-6a083e80-c7ea-11e8-875c-11befdaa839a.png)<br>
    ノルムの２乗は必ず正になるので、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46456620-78565a80-c7ea-11e8-9ddc-91993ea1979f.png)<br>
    の関係が成り立ち、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46456587-5957c880-c7ea-11e8-9a8f-ad95d81a94bd.png) が、正定値カーネルになることがわかる。<br>


<a id="正定値カーネルの例"></a>

### ◎ 正定値カーネルの例
m 次元ユークリッド空間 ![image](https://user-images.githubusercontent.com/25688193/46507423-5fde5280-c873-11e8-8fe5-45cf58eaab55.png) 上で定義されるいくつかの正定値カーネルの例を見ていく。<br>


<a id="線形カーネル（＝通常のユークリッド空間上での内積）"></a>

#### ☆ 線形カーネル（＝通常のユークリッド空間上での内積）
![image](https://user-images.githubusercontent.com/25688193/46507919-00357680-c876-11e8-90a8-17315d452ee3.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46507904-e136e480-c875-11e8-8600-fc8920433b6c.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46507932-0f1c2900-c876-11e8-8156-f9c43f67c316.png)<br>

ここで、このカーネルが、確かに正定値カーネルになることを示す。<br>
この線形カーネルは、先の関数の内積で表現される正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/46512384-9d9ca480-c88e-11e8-9165-8b894c760bb2.png) より、明らかに正定値カーネルであることが分かる。<br>


<a id="指数型カーネル"></a>

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


<a id="動径基底関数カーネル（RBFカーネル）"></a>

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


<a id="ラプラスカーネル"></a>

#### ☆ ラプラスカーネル
![image](https://user-images.githubusercontent.com/25688193/46509900-7b038f00-c880-11e8-9710-f5e2fbd19028.png)<br>


<a id="多項式カーネル"></a>

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
の計算で出来ることになる。⇒ 計算量を削減出来る。<br>

次に、（次数が）一般の場合 d では、<br>
多項式カーネル ![image](https://user-images.githubusercontent.com/25688193/46511996-ae4c1b00-c88c-11e8-9066-d73e8da61096.png) を２項定理を用いて展開すると、<br>
![image](https://user-images.githubusercontent.com/25688193/46512023-d9366f00-c88c-11e8-96ec-e7398cd8f209.png)<br>
即ち、多項数カーネルの使用した時の２つのベクトル ![image](https://user-images.githubusercontent.com/25688193/46524114-bc1c9300-c8c2-11e8-85b1-e96c2d3f3488.png) の次元（次数）の上限は ∑ の形で求めることが出来る。<br>


<a id="再生核ヒルベルト空間"></a>

## ■ 再生核ヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/46570892-a84a5d00-c9a6-11e8-9afd-fa2ca50310fe.png)<br>

> 【Memo】<br>
> この定義単体だけでは、再生核ヒルベルト空間の意味は分かりにくいが、後述の [Moore-Aronszajn の定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#-moore-aronszajn-%E3%81%AE%E5%AE%9A%E7%90%86)まで飛ばして見てみれば、その幾何学的な意味を理解しやすい。<br>


- 【参考】<br>
    - [再生核ヒルベルト空間をなんとなく理解する - 備忘録とか あと あれとか それとか](http://d.hatena.ne.jp/hgshrs/20130331/1364707361)<br>
    - [カーネルトリックと関数解析についてまとめてみた](https://qiita.com/muripo_life/items/ac186f740f493c2b2058)<br>
    - [Reproducing Kernel Hilbert Spaceの数理とMercerの定理 - Obey Your MATHEMATICS.](http://mathetake.hatenablog.com/entry/2016/12/29/223101)<br>
    - [線形汎関数を用いた再生カーネルヒルベルト空間の特徴付けとリースの表現定理](http://ibisforest.org/index.php?plugin=attach&refer=K-NEL%2Faddenda%2Fchap6&openfile=riesz.pdf)<br>
    - [リースの表現定理](http://yagami12.hatenablog.com/entry/2018/10/03/134340#ID_A-4)<br>


<a id="再生核の性質"></a>

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


<a id="再生核のテンソル積"></a>

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


<a id="再生核ヒルベルト空間の線形汎関数を用いた特徴付けとリースの表現定理"></a>

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


<a id="【補足】リースの表現定理"></a>

#### 【補足】リースの表現定理
![image](https://user-images.githubusercontent.com/25688193/45737382-a05d8f80-bc28-11e8-8e4d-fcc7fe93f3cf.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45734425-781d6300-bc1f-11e8-8202-603d2e2e08de.png)<br>

> 【メモ】<br>
> 簡単言えば、このリースの表現定理は、射影定理によって直交補空間から非零元を取ってきて、それをグラムシュミットの方法で正規直交化している流れになっている。<br>


<a id="Moore-Aronszajnの定理"></a>

### ◎ Moore-Aronszajn の定理
![image](https://user-images.githubusercontent.com/25688193/48116589-e68ab300-e2a9-11e8-8052-8ad1d1159536.png)<br>

先の再生核ヒルベルト空間の線形汎関数を用いた特徴付けと、<br>
Moore-Aronszajn の定理より、再生核ヒルベルト空間を再解釈（＝特徴付け）したのが以下の図である。<br>
正定値カーネルが、再生核ヒルベルト空間の基底になっており、それを元に再生核ヒルベルト空間が構築されていることと、再生性の条件 ![image](https://user-images.githubusercontent.com/25688193/48708417-dbd70300-ec45-11e8-9edc-9ad09734cc4d.png) が、元のベクトル空間での入力値の写像後の値に対応している点がポイントである。<br>

![image](https://user-images.githubusercontent.com/25688193/46566609-ba9fa900-c95c-11e8-8c28-a89da4de0f5d.png)<br>


<a id="特徴写像とカーネルトリック（Moore-Aronszajnの定理からの帰着）"></a>

#### ☆ 特徴写像とカーネルトリック（Moore - Aronszajn の定理からの帰着）
特徴写像 Φ は、集合 X から再生核ヒルベルト空間への写像 ![image](https://user-images.githubusercontent.com/25688193/46576774-175a9c80-ca0d-11e8-8ca6-4e36fe4365db.png) である。<br>
このとき、Moore - Aronszajn の定理より、再生核ヒルベルト空間上の任意の２つの要素（関数）∀f,g ∈H の内積は、<br>
![image](https://user-images.githubusercontent.com/25688193/46576776-3b1de280-ca0d-11e8-9347-0963c4cea248.png)<br>

![image](https://user-images.githubusercontent.com/25688193/48049547-60576980-e1e2-11e8-99fa-a0109a4e5b15.png)<br>

従って、<br>
![image](https://user-images.githubusercontent.com/25688193/48049584-78c78400-e1e2-11e8-90ff-6f5c0755a520.png)<br>
となり、カーネルトリックが成り立っていることが分かる。<br>
つまり、カーネルトリックは、Moore - Aronszajn の定理からの帰着で自然に導かれる。<br>


<a id="再生核ヒルベルト空間の具体的な構成"></a>

### ◎ 再生核ヒルベルト空間の具体的な構成
先の Moore-Aronszanの定理より、正定値カーネルにより、再生核ヒルベルト空間の基底が定まり、再生核ヒルベルト空間が構成されることを見てきたが、ここでは、具体的に、幾何学的に表現が可能な場合の再生核ヒルベルト空間を見ていく。<br>


<a id="線形カーネルの再生核ヒルベルト空間"></a>

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
    - [線形カーネル](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#-%E7%B7%9A%E5%BD%A2%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E9%80%9A%E5%B8%B8%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%AF%E3%83%AA%E3%83%83%E3%83%89%E7%A9%BA%E9%96%93%E4%B8%8A%E3%81%A7%E3%81%AE%E5%86%85%E7%A9%8D)<br>
    - [カーネル主成分分析](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_2-5-2)<br>


<a id="有限集合上の（エルミート行列の）再生核ヒルベルト空間"></a>

#### ☆ 有限集合上の（エルミート行列の）再生核ヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/46671094-d92ccb00-cc0e-11e8-9f01-04d3f510c204.png)<br>

- （証明略）証明の方針のみ記載<br>
    内積が再生性の条件を満たすことを示せばよい。<br>
    即ち、例えば、エルミート行列 K の第 i 行である ![image](https://user-images.githubusercontent.com/25688193/46670837-3b390080-cc0e-11e8-8c88-a77035efdeda.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46672092-843e8400-cc11-11e8-9920-9c9aac9852d6.png)<br>
    を示せばよい。<br>


<a id="多項式カーネルの再生核ヒルベルト空間"></a>

#### ☆ 多項式カーネルの再生核ヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/46706510-cb5b6200-cc6f-11e8-8770-1f77a4cfc12c.png)<br>

- （証明略）<br>


<a id="埋め込み写像による再生核ヒルベルト空間の構成"></a>

### ◎ 埋め込み写像による再生核ヒルベルト空間の構成
再生核ヒルベルト空間を、他の一般的な関数空間（例えば、ヒルベルト空間）の部分空間として構成する一般的な方法に、関数空間へのヒルベルト空間の埋め込み写像（＝ヒルベルト埋め込み写像）による構成方法が存在する。<br>

> 【Memo】ヒルベルト埋め込み写像による再生核ヒルベルト空間の構成と再生核ヒルベルト空間のフーリエ変換による表示<br>
> - 埋め込み写像とは、数学的な構造を保ちながら、写像元より一般的で広い空間の部分空間に埋め込むような写像（例えば、２次元ユークリッド空間の３次元ユークリッド空間への埋め込み。正数の実数への埋め込みなど）であるが、<br>
> - 可測関数を基底ベクトルとするL２空間の部分空間を、より一般的な関数空間（例えば、ヒルベルト空間）の部分空間として埋め込むような埋め込み写像を考えると、この埋め込んだ部分空間は、再生核ヒルベルト空間になり、その具体的な表示が得られる。（内積は、写像元のL2空間での内積で定義。再生核は、写像元のL2空間での再生性を経由して得られる）<br>
> 言い換えると、埋め込み写像により、再生核ヒルベルト空間を他の一般的な関数空間（例えば、ヒルベルト空間）の部分空間として実現できる。
> - 次に、この可測関数として、e^(ixt) の形を採用すると、埋め込み写像がフーリエ変換の形となる。（＝埋め込み写像の１つの具体的な例が、フーリエ変換となる）<br>
> そして、先の議論と同様にして、このフーリエ変換の形をした埋め込み写像により、部分空間としての再生核ヒルベルト空間の具体的表示が得られる。<br>
> - 最後に、このフーリエ変換の形をした埋め込み写像により得られる再生核ヒルベルト空間の具体的な表示を構成する確率密度関数に、各々の正定値カーネル（RBFカーネル等）の確率密度関数の式を適用すると、各々の正定値カーネル（RBFカーネル等）の再生核ヒルベルト空間のフーリエ変換による表示が得られる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/48071077-bea13e00-e21c-11e8-9ab2-e25f3c4a2875.png)<br>
![image](https://user-images.githubusercontent.com/25688193/48073166-818b7a80-e221-11e8-9e1e-8c8f10395e3a.png)<br>

<br>

> 【Memo】埋め込み写像<br>
> 数学的な構造を保ちながら、写像元より一般的で広い空間の部分空間に埋め込むような写像。<br>
> 例えば、以下のような埋め込みは、埋め込み写像である。<br>
> - 例１（図形）：平面（２次元ユークリッド空間）は立体的空間（３次元ユークリッド空間）への埋め込み。<br>
> - 例２（図形）：球面や球体の、立体的空間への埋め込み。<br>
> - 例３（数）：整数の有理数への埋め込み。<br>
> - 例４（集合）：集合 X の部分集合 A の、X への埋め込み。<br>


<a id="フーリエ変換の形をした埋め込み写像による再生核ヒルベルト空間の構成"></a>

#### ☆ フーリエ変換の形をした埋め込み写像による再生核ヒルベルト空間の構成
次に、この埋め込み写像がフーリエ変換によって与えられることを見ていく。

![image](https://user-images.githubusercontent.com/25688193/48070689-d1ffd980-e21b-11e8-8267-57173ec20566.png)<br>
![image](https://user-images.githubusercontent.com/25688193/48116661-1d60c900-e2aa-11e8-9a10-c4f2e87587a3.png)<br>
![image](https://user-images.githubusercontent.com/25688193/48073456-260dbc80-e222-11e8-9bb4-1ac78b895446.png)<br>

この定理（フーリエ変換の形をした埋め込み写像による再生核ヒルベルト空間の構成）を用いれば、各々の正定値カーネル（RBFカーネル等）に対しての再生核ヒルベルトのフーリエ変換での具体的な表示を得ることが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/48116692-3d908800-e2aa-11e8-818d-94cd7ed7e41f.png)<br>


<a id="RBFカーネルの再生核ヒルベルト空間"></a>

#### ☆ RBF カーネルの再生核ヒルベルト空間
先の定理（フーリエ変換の形をした埋め込み写像による再生核ヒルベルト空間の構成）の密度関数に対して、正定値カーネルの１つの例として、RBFカーネルの確率密度関数の式を代入するとこで、RBFカーネルの再生核ヒルベルトのフーリエ変換での具体的な表示を得ることが出来る。<br>

RBFカーネルの確率密度関数 ![image](https://user-images.githubusercontent.com/25688193/48116736-5ef17400-e2aa-11e8-88e3-7a514371f65e.png) を以下のように定める。<br>
![image](https://user-images.githubusercontent.com/25688193/48116773-79c3e880-e2aa-11e8-94d0-fe29f8f81ec0.png)<br>
これを先のフーリエ変換での再生核ヒルベルトの具体的な表示の式に代入すると、<br>
RBFカーネルの再生核ヒルベルト空間の具体的な形は、<br>
![image](https://user-images.githubusercontent.com/25688193/48116800-89433180-e2aa-11e8-96b4-ab9973dfe5ae.png)<br>
同様にして、内積は、<br>
![image](https://user-images.githubusercontent.com/25688193/48116854-ad067780-e2aa-11e8-8c30-0a0320dd37ef.png)<br>
又、再生核は、<br>
![image](https://user-images.githubusercontent.com/25688193/48116909-dc1ce900-e2aa-11e8-9bf0-3e7c1866a890.png)<br>
となる。<br>
即ち、埋め込み写像により定まる再生核ヒルベルト空間は、RBFカーネルの定める再生核ヒルベルト空間に一致することが分かる。<br>

そして、このRBFカーネルの再生核ヒルベルト空間の具体的な表示<br>
![image](https://user-images.githubusercontent.com/25688193/48116982-0d95b480-e2ab-11e8-8425-a3a73db0523a.png)<br>
より、このRFBカーネルの再生核ヒルベルト空間に含まれる関数（＝再生核ヒルベルト空間の要素）は、周波数領域で指数関数的に減衰するものに限られることも分かる。<br>

尚、後述の Bochner の定理からも、RBF カーネルが正定値カーネルであることを導くことが出来る。<br>


<a id="ラプラスカーネルの再生核ヒルベルト空間"></a>

#### ☆ ラプラスカーネルの再生核ヒルベルト空間
同様にして、先の定理（フーリエ変換の形をした埋め込み写像による再生核ヒルベルト空間の構成）の密度関数に対して、正定値カーネルの１つの例として、ラプラスカーネルの確率密度関数の式を代入するとこで、ラプラスカーネルの再生核ヒルベルトのフーリエ変換での具体的な表示を得ることが出来る。<br>

ラプラスカーネルの確率密度関数 ![image](https://user-images.githubusercontent.com/25688193/48116736-5ef17400-e2aa-11e8-88e3-7a514371f65e.png) を、以下のように定める。<br>
![image](https://user-images.githubusercontent.com/25688193/48117050-42a20700-e2ab-11e8-8472-437621b98067.png)<br>
これを先のフーリエ変換での再生核ヒルベルトの具体的な表示の式に代入すると、<br>
ラプラスカーネルの再生核ヒルベルト空間の具体的な形は、<br>
![image](https://user-images.githubusercontent.com/25688193/48117069-577e9a80-e2ab-11e8-99d7-eced9ebe98e5.png)<br>
同様にして、内積は、<br>
![image](https://user-images.githubusercontent.com/25688193/48117117-7f6dfe00-e2ab-11e8-890d-b6ffc4a4caad.png)<br>
又、再生核は、<br>
![image](https://user-images.githubusercontent.com/25688193/48117141-8c8aed00-e2ab-11e8-96fb-0be6366fc794.png)<br>
となる。<br>
即ち、埋め込み写像により定まる再生核ヒルベルト空間は、ラプラスカーネルの定める再生核ヒルベルト空間に一致することが分かる。<br>

そして、このラプラスカーネルの再生核ヒルベルト空間の具体的な表示<br>
![image](https://user-images.githubusercontent.com/25688193/48117235-e7244900-e2ab-11e8-8d71-86f78be06e59.png)<br>
より、このラプラスカーネルの再生核ヒルベルト空間に含まれる関数（＝再生核ヒルベルト空間の要素）は、先のRBFカーネルと比べて、周波数領域（＝波数）でより緩やかに減衰するものに限られることも分かる。<br>

尚、後述の Bochner の定理からも、ラプラスカーネルが正定値カーネルであることを導くことが出来る。<br>


<a id="ソボレフ空間"></a>

#### ☆ ソボレフ空間 [Soboveb space]
再生核ヒルベルト空間の重要な例の１つに、ソボレフ空間がある。<br>

このソボレフ空間は、関数とその導関数を要素とする関数空間であり、又、完備距離空間、即ち、バナッハ空間でもある。<br>
ノルムは、関数とその導関数のLpノルムで定まる。<br>

> 記載中...



<a id="正定値カーネルの理論"></a>

## ■ 正定値カーネルの理論
ここでは、正定値カーネルの理論と称して、以下のようなトピックを取り上げる。<br>

- 負定値カーネルと正定値カーネルを関連づける定理である Schoenberg の定理<br>

- Schoenberg の定理を用いて、正定値カーネルや負定値カーネルから、様々な正定値カーネルを系統的に生成出来ること。<br>

- ユークリッド空間上での平行移動（アフィン変換）に対して不変な正定値カーネル全体を、その正定値カーネルのフーリエ変換により特徴づけることを主張している Bochner の定理。<br>

- 正定値カーネルに対する固有値分解である Mercer の定理。<br>
    より厳密には、正定値カーネルを積分作用素のスペクトル分解によって表現する Mercer の定理。<br>


<a id="負定値カーネル"></a>

### ◎ 負定値カーネル
まず、先の正定値カーネルとの対比で、負定値カーネルなるものを導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/48117273-0327ea80-e2ac-11e8-8056-883f92ba8c42.png)<br>

![image](https://user-images.githubusercontent.com/25688193/48117294-13d86080-e2ac-11e8-9c06-6fbe6d162d9a.png)<br>

以下、断り書きがない限り、負定値カーネルといえば、この複素数の負定値カーネルを表すものとする。<br>


<a id="負定値カーネルの基本的な性質"></a>

#### ☆ 負定値カーネルの基本的な性質
次に、この負定値カーネルに関して成り立つ基本的な性質をいくつか見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/48117352-42eed200-e2ac-11e8-85f2-c96da871711f.png)<br>

- （証明略）負定値カーネルの定義より成り立つ。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/48117411-7b8eab80-e2ac-11e8-9813-b7222a1f3bfd.png)<br>

- （証明略）正定値カーネルのときと同様<br>


<a id="負定値カーネルの基本的な例"></a>

#### ☆ 負定値カーネルの基本的な例

- （例）負定値カーネルの例<br>
    集合 X から内積空間 V への写像 ![image](https://user-images.githubusercontent.com/25688193/48117475-b1339480-e2ac-11e8-884f-ca5bb94c10a8.png) に対して、<br>
    以下のような定義される関数は、集合 X 上の負定値カーネルであることを示す。<br>
    ![image](https://user-images.githubusercontent.com/25688193/48117497-c0b2dd80-e2ac-11e8-943f-67e3af7432f8.png)<br>
    <br>
    この関数に対して負定値カーネルの非負性の条件を確認すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48117525-d1fbea00-e2ac-11e8-989e-93a7e92f6a6a.png)<br>
    従って、負正値の条件が成り立つので、この関数 ψ は負定値カーネルである。<br>


<a id="Schoenbergの定理"></a>

### ◎ Schoenberg の定理
Schoenberg の定理は、先に導入した負定値カーネルと正定値カーネルを関連付ける定理であるが、そのための前段階として、以下の補題を示す。<br>

![image](https://user-images.githubusercontent.com/25688193/48117583-07083c80-e2ad-11e8-984b-a809e114c28f.png)<br>

- （証明）<br>
    - 「⇐」 方向の証明<br>
        作られた関数 ![image](https://user-images.githubusercontent.com/25688193/48117675-46368d80-e2ad-11e8-9557-3bbe7485eab9.png) は、正定値カーネルなので、<br>
        正定性の条件より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48117703-5b132100-e2ad-11e8-9e0e-87a9f6ea6104.png)<br>
        ここで、関数 ![image](https://user-images.githubusercontent.com/25688193/48117735-767e2c00-e2ad-11e8-8d20-2cea83caeacc.png) のエルミート性 ![image](https://user-images.githubusercontent.com/25688193/48117762-8ac22900-e2ad-11e8-8149-ac3bfa19e66a.png) より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48117829-c2c96c00-e2ad-11e8-89a7-2561fa4c34c6.png)<br>
        となるので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48117847-d1b01e80-e2ad-11e8-90e6-e7192180a3ae.png)<br>
        となり、関数 ![image](https://user-images.githubusercontent.com/25688193/48117735-767e2c00-e2ad-11e8-8d20-2cea83caeacc.png) は負定値カーネルであることが分かる。<br>
        <br>
    - 「⇒」 方向の証明<br>
        元の関数 ![image](https://user-images.githubusercontent.com/25688193/48117735-767e2c00-e2ad-11e8-8d20-2cea83caeacc.png) は、負定値カーネルなので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48117971-2489d600-e2ae-11e8-85cd-b35621850774.png)<br>
        従って、作られた関数 ![image](https://user-images.githubusercontent.com/25688193/48117675-46368d80-e2ad-11e8-9557-3bbe7485eab9.png) は正定値カーネルである。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/48127546-5491a300-e2c7-11e8-861d-a764fb62f132.png)<br>

- （証明）<br>
    - 「⇐」 の方向証明<br>
        ![image](https://user-images.githubusercontent.com/25688193/48133038-d3430c00-e2d8-11e8-8f08-18f63e090f53.png) を Tayler 展開すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48133060-e950cc80-e2d8-11e8-998c-9c0c780ee2bf.png)<br>
        １次の項まで採用して、変形すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48133109-0ab1b880-e2d9-11e8-8758-264cc274406d.png)<br>
        今、![image](https://user-images.githubusercontent.com/25688193/48133038-d3430c00-e2d8-11e8-8f08-18f63e090f53.png) は負定値カーネルであるので、この逆符号の関数をもつ上式は、正定値カーネルとなる。<br>
        <br>
    - 「⇒」 の方向の証明<br>
        先の補題（正定値カーネルと負定値カーネルの同値関係）に対応した関数<br>
        ![image](https://user-images.githubusercontent.com/25688193/48133167-451b5580-e2d9-11e8-8a7e-8e76ab239374.png)<br>
        を定義すると、この関数 ![image](https://user-images.githubusercontent.com/25688193/48133187-582e2580-e2d9-11e8-80a7-aa8589f32d36.png) は正定値カーネルであるが、
        この関数 ![image](https://user-images.githubusercontent.com/25688193/48133187-582e2580-e2d9-11e8-80a7-aa8589f32d36.png) に対して、exp をとった ![image](https://user-images.githubusercontent.com/25688193/48133187-582e2580-e2d9-11e8-80a7-aa8589f32d36.png) は、
        ラプラスカーネル ![image](https://user-images.githubusercontent.com/25688193/48133232-7d229880-e2d9-11e8-9d0c-b5c363a7fc37.png) の形になるので、正定値カーネルになる。<br>
        <br>
        正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48133187-582e2580-e2d9-11e8-80a7-aa8589f32d36.png) を展開すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48133339-d1c61380-e2d9-11e8-8d88-6403e518440f.png)<br>
        ここで、一般の正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48133389-f3bf9600-e2d9-11e8-8e2d-388342f9e0c3.png) に対して、任意の関数 f ではさみうちした関数<br>
        ![image](https://user-images.githubusercontent.com/25688193/48133418-0d60dd80-e2da-11e8-8c37-5f965fe21c7f.png)<br>
        は、正定値カーネルとなるという関係（証明略）と対比すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48133306-b529db80-e2d9-11e8-806c-6e11d570c54d.png) も正定値カーネルとなることが分かる。<br>


<a id="カーネルを生成する操作"></a>

### ◎ カーネルを生成する操作
この Schoenberg の定理を用いて、負定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48184321-f8855800-e374-11e8-874e-f94490355da0.png) から作られる関数が、負定値カーネル or 正定値カーネルであるかを示すことが出来る。<br>
（言い換えると、負定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48184321-f8855800-e374-11e8-874e-f94490355da0.png) から、別の負定値カーネル or 正定値カーネルを生成することが出来る。）<br>
尚、この Schoenberg の定理を用いて、負定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48184321-f8855800-e374-11e8-874e-f94490355da0.png) から別の負定値カーネル or 正定値カーネルを生成する際には、いずれも、その関数が、![image](https://user-images.githubusercontent.com/25688193/48184371-28ccf680-e375-11e8-8efc-4a46e3bb85ec.png) の形に変形できるかがポイントとなる。<br>

![image](https://user-images.githubusercontent.com/25688193/48184422-48fcb580-e375-11e8-95fc-af405892543b.png)<br>

- （証明）Schoenberg の定理を用いて証明できる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/48184438-5e71df80-e375-11e8-86fd-e6b4ec8169a0.png)<br>
    の関係を用いると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48184610-e657e980-e375-11e8-9c4a-fccda9c43319.png)<br>
    上式の ![image](https://user-images.githubusercontent.com/25688193/48184511-97aa4f80-e375-11e8-8c73-97b008e15792.png) の部分は、Scohenberg の定理より、正定値カーネルである。<br>
    更に、被積分関数部分全体 ![image](https://user-images.githubusercontent.com/25688193/48184632-fb347d00-e375-11e8-88e6-beaf9682e741.png) は、正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48184511-97aa4f80-e375-11e8-8c73-97b008e15792.png) に関しての逆符号になっているので、負定値カーネルである。<br>
    そして、積分はリーマン和の極限なので、負定値カーネルの性質（カーネルの点列の極限）より、上式も負定値カーネルである。<br>
    従って、![image](https://user-images.githubusercontent.com/25688193/48184682-169f8800-e376-11e8-8d7c-50321f7c1294.png) も負定値カーネルとなることが分かる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/48184735-3767dd80-e376-11e8-9473-fb8865dd4bda.png)<br>

- （証明）Schoenberg の定理を用いて証明できる。<br>
    先の負定値カーネルの例<br>
    ![image](https://user-images.githubusercontent.com/25688193/48184790-5f574100-e376-11e8-9408-a5ffca51cb4f.png)<br>
    において、集合 X を ![image](https://user-images.githubusercontent.com/25688193/48184816-70a04d80-e376-11e8-95c1-6d128105ef01.png) とすると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48184827-7dbd3c80-e376-11e8-8d51-dbe05f9673c1.png)<br>
    に対して、先の命題（負定値カーネルの階上関数）を適用すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185450-5d8e7d00-e378-11e8-9000-cee9bf7e6e24.png)<br>
    も、負定値カーネルであることが分かる。<br>
    <br>
    更に、この関数に exp をとった<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185471-6c752f80-e378-11e8-882d-6a6f79c77641.png)<br>
    は、Scoenberg の定理より、正定値カーネルとなる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/48185541-9dedfb00-e378-11e8-8dad-b03cb5bf6a79.png)<br>

- （証明）Schoenberg の定理を用いて証明できる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185568-bbbb6000-e378-11e8-960c-d08ed958ff8d.png) を積分表示すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185607-e9a0a480-e378-11e8-89a1-311852c6b42e.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/48184371-28ccf680-e375-11e8-8efc-4a46e3bb85ec.png) の形に展開できているので、<br>
    先の命題（負定値カーネルの階上関数）の証明と同様にして、上式の右辺の積分項は、負定値カーネルであるといえ、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185568-bbbb6000-e378-11e8-960c-d08ed958ff8d.png) は、負定値カーネルであることが分かる。<br>
    そして、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185675-1fde2400-e379-11e8-9f17-847c6f81d06e.png)<br>
    と変形できるが、負定値カーネルの性質より、![image](https://user-images.githubusercontent.com/25688193/48185708-3a180200-e379-11e8-9b90-d76a7c2478c7.png) は、負定値カーネルであることが分かる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/48185749-5ae05780-e379-11e8-8e66-38fa4dc7dce0.png)<br>

- （証明）Schoenberg の定理を用いて証明できる。<br>
    対象関数を積分表示すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185792-7cd9da00-e379-11e8-8313-07bc59ea32f3.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185840-a1ce4d00-e379-11e8-9e9d-ef1e35c240a7.png) の形に展開できているので、<br>
    先の命題（負定値カーネルの階上関数、負定値カーネルのlog関数）の証明と同様にして、<br>
    上式の右辺の積分項は、正定値カーネルであるといえ、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48185923-dc37ea00-e379-11e8-90b8-afd95e941690.png)<br>
    は正定値カーネルであることが分かる。<br>


<a id="Bochnerの定理"></a>

### ◎ Bochner の定理
Bochner の定理は、ユークリッド空間上での平行移動（アフィン変換）に対して不変な正定値カーネル全体を、その正定値カーネルのフーリエ変換により特徴づけることを主張している定理である。<br>

まず、カーネル関数の平行移動不変性、及び、そこから定義される正値とはどのようなものなのかを定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/48185992-0d181f00-e37a-11e8-97ee-e0e3c235d44b.png)<br>

このように定義した平行移動不変性、及び、正値の概念に関連して、以下の Bochner の定理が成り立つ。<br>

![image](https://user-images.githubusercontent.com/25688193/48256007-a2d2ad80-e451-11e8-88fe-e393a783eb8a.png)<br>
![image](https://user-images.githubusercontent.com/25688193/48256041-bf6ee580-e451-11e8-92d1-97717296463f.png)<br>

- （証明略）十分条件（⇐）の証明み記載する。<br>
    このフーリエ変換の式<br>
    ![image](https://user-images.githubusercontent.com/25688193/48256081-e4635880-e451-11e8-966f-0f058740e855.png)<br>
	の積分は、これら各々の ![image](https://user-images.githubusercontent.com/25688193/48256097-f0e7b100-e451-11e8-82e8-c80ae565c992.png) に対しての ![image](https://user-images.githubusercontent.com/25688193/48256120-02c95400-e452-11e8-800c-f710bd8e1737.png) の線形結合の極限和で表せる。即ち、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48256210-43c16880-e452-11e8-8245-c51aa80e8667.png)<br>
    <br>
    ここで、正値の条件 ![image](https://user-images.githubusercontent.com/25688193/48256800-11186f80-e454-11e8-892d-41332765bcca.png)、及び ![image](https://user-images.githubusercontent.com/25688193/48256245-5a67bf80-e452-11e8-99d2-4bf8d73fc629.png)の関係より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48256501-293bbf00-e453-11e8-9a0c-97d77f2865ec.png) は正値関数となるが、<br>
    これは、先の線形結合の極限和の式の基底に対応しており、正定値カーネルの性質（線形結合もまた正定値カーネル、極限も正定値カーネル）より、この線形結合の極限和である ![image](https://user-images.githubusercontent.com/25688193/48256838-2b524d80-e454-11e8-852d-b8b6c20a87ce.png) も正値であることが分かる。<br>


<a id="Mercerの定理"></a>

### ◎ Mercer（マーサー、マーセル）の定理
Mercer の定理は、正定値カーネルに対する固有値分解の定理である。
より厳密に言えば、正定値カーネルを積分作用素のスペクトル分解によって表現する定理となってる。<br>

> 【Memo】 Mercer の定理<br>
> Supp(μ)=Ω である、言い換えると、ハウスドルフ空間 Ω 全体が、測度 μ が非ゼロで有効なものの集合（＝測度の台 Supp(μ)）から構成されている）ような、ハウスドルフ空間 Ω と Ω 上のラドン測度 μ とにおいて、<br>
> このハウスドルフ空間上の正定値カーネル（＝正値積分核となる）K:Ω×Ω→R によって定まる積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48720142-6af21400-ec62-11e8-9d17-87c1d7825f43.png)（より一般的には、正定値カーネルによって定まる作用素）は、正値作用素でもある。<br>
> 更に、積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48720142-6af21400-ec62-11e8-9d17-87c1d7825f43.png) は、ヒルベルト＝シュミット作用素でもあり、又、正値作用素は自己共役作用素でもあるので、自己共役なヒルベルト＝シュミット作用素と同様にして、この積分作用素の固有値は、全て非負の実数値となり、この非負の固有値 ![image](https://user-images.githubusercontent.com/25688193/48707360-8ea56200-ec42-11e8-934e-45d6b487342c.png) とこれに対応する固有ベクトル ![image](https://user-images.githubusercontent.com/25688193/48707387-a250c880-ec42-11e8-81b4-9f9968848678.png) を用いて、<br>
> 積分作用素を定める積分核を、固有値分解（＝スペクトル分解）<br>
> ![image](https://user-images.githubusercontent.com/25688193/48720329-d3d98c00-ec62-11e8-8a28-af65e416073a.png)<br>
> で表現することが出来る。<br>
> そして、この級数展開の式（＝固有値分解の式）は、一様絶対収束する。<br>

<br>

- 【参考】<br>
    - [Reproducing Kernel Hilbert Spaceの数理とMercerの定理 - Obey Your MATHEMATICS.](http://mathetake.hatenablog.com/entry/2016/12/29/223101)<br>



<a id="積分作用素、積分核"></a>

#### ☆ 積分作用素、積分核
まずは、この積分作用素、積分核とはどのようなものなのかを見ていく。<br>

![image](https://user-images.githubusercontent.com/25688193/48553751-cbf6b080-e91f-11e8-97ea-bc4a18e46242.png)<br>


<a id="積分作用素とヒルベルト＝シュミット作用素"></a>

#### ☆ 積分作用素とヒルベルト＝シュミット作用素
以下の定理で示すように、積分作用素は、ヒルベルト＝シュミット作用素でもある。<br>
一方、自己共役なヒルベルト＝シュミット作用素は、固有値分解が可能である。（後述）<br>
そしてこれら２つの事実が、正定値カーネルを積分作用素のスペクトル分解によって表現する Mercerの定理に結びつく。<br>

![image](https://user-images.githubusercontent.com/25688193/48612310-fa31ca00-e9cb-11e8-8014-adbd2cbf9f0f.png)<br>

- （証明）<br>
	まず前提として、L2空間 ![image](https://user-images.githubusercontent.com/25688193/48555220-e5016080-e923-11e8-8971-6cac9d4605a1.png) は、ヒルベルト空間でもあるので（![image](https://user-images.githubusercontent.com/25688193/48555294-242fb180-e924-11e8-84d9-52a3ea137621.png)）、この空間上のヒルベルト＝シュミット作用素なるものが導入出来る。<br>
    <br>
    次に、積分核 K の２乗可積分性より、<br>
    ほとんどいたるところの x∈Ω に対して、![image](https://user-images.githubusercontent.com/25688193/48555356-517c5f80-e924-11e8-9a2e-3b87d37c67d6.png) の関係が成り立つ。<br>
    <br>
	![image](https://user-images.githubusercontent.com/25688193/48555435-930d0a80-e924-11e8-9531-71c6baa06aad.png) をL2空間 ![image](https://user-images.githubusercontent.com/25688193/48555294-242fb180-e924-11e8-84d9-52a3ea137621.png) の完全正規直交系とすると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48555750-72918000-e925-11e8-9cb8-f6dd8312f6d6.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/48555435-930d0a80-e924-11e8-9531-71c6baa06aad.png) の複素共役をとった ![image](https://user-images.githubusercontent.com/25688193/48556058-2bf05580-e926-11e8-8ba6-3dcd668c7d78.png) もL2空間 ![image](https://user-images.githubusercontent.com/25688193/48555294-242fb180-e924-11e8-84d9-52a3ea137621.png) の完全正規直交系となるので、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48556204-a7520700-e926-11e8-99f6-2de365bc7c15.png)<br>


<a id="積分核のヒルベルト＝シュミット展開"></a>

#### ☆ 積分核のヒルベルト＝シュミット展開
自己共役なヒルベルト＝シュミット作用素は、固有値分解可能であるという事実を、ヒルベルト＝シュミット作用素である積分作用素にも適用するために、自己共役な積分作用素なるものを導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/48612348-1d5c7980-e9cc-11e8-8e0f-a69da409ad79.png)<br>

- （証明）<br>
    積分核 ![image](https://user-images.githubusercontent.com/25688193/48612394-4250ec80-e9cc-11e8-8c9f-281da9a529c8.png) がエルミート性の条件 ![image](https://user-images.githubusercontent.com/25688193/48612423-51d03580-e9cc-11e8-8056-4386aa241ca9.png) を満たす場合、<br>
    積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48612467-71fff480-e9cc-11e8-8034-92460da3c758.png) とある関数 ![image](https://user-images.githubusercontent.com/25688193/48612504-85ab5b00-e9cc-11e8-847f-aaa665f4ccc5.png) の内積演算に関して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48612539-9f4ca280-e9cc-11e8-94cb-d7ce23076909.png)<br>
    の関係が成り立つので、この積分作用素は自己共役作用素となっていることが分かる。<br>

<br>

積分作用素は、ヒルベルトシュミット作用素であり、<br>
又、自己共役なヒルベルトシュミット作用素は、固有値展開可能（ヒルベルトシュミットの展開定理）であることより、自己共役な積分作用素も、以下の定理のように固有値で展開表現可能となる。<br>

![image](https://user-images.githubusercontent.com/25688193/48612597-c99e6000-e9cc-11e8-9ddb-663fe19d4405.png)<br>

- （証明略）<br>

<br>

更に、![image](https://user-images.githubusercontent.com/25688193/48612645-ed61a600-e9cc-11e8-8f2b-b375d77a26eb.png) ではなく ![image](https://user-images.githubusercontent.com/25688193/48612667-ff434900-e9cc-11e8-83ba-f477a8b6e568.png) においては、積分核は、以下の定理のように固有値で展開表現できる。<br>

![image](https://user-images.githubusercontent.com/25688193/48613055-074fb880-e9ce-11e8-95d2-34b58a1a509d.png)

- （証明）<br>
    積分核 K の２乗可積分性より、<br>
    ほとんどいたるところの ![image](https://user-images.githubusercontent.com/25688193/48613188-63b2d800-e9ce-11e8-8844-085ffc324b05.png) に対して、![image](https://user-images.githubusercontent.com/25688193/48613109-2d755880-e9ce-11e8-9daf-0b298dfb3911.png) の関係が成り立つ。<br>
    <br>
    ここで、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48613217-775e3e80-e9ce-11e8-9d15-15aa32fb576b.png)<br>
    の関係式？より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48613257-8e049580-e9ce-11e8-874a-f4cc474b4166.png)<br>
    の関係が成り立つが、更に、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48613279-9f4da200-e9ce-11e8-9171-36c1b546844c.png)<br>
    となるので、測度 μ に関して？、ほとんどいたるところの ![image](https://user-images.githubusercontent.com/25688193/48613188-63b2d800-e9ce-11e8-8844-085ffc324b05.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48613349-cf954080-e9ce-11e8-9a2e-34e46b5a3c5d.png)<br>
    というL2空間 ![image](https://user-images.githubusercontent.com/25688193/48612645-ed61a600-e9cc-11e8-8f2b-b375d77a26eb.png) におけるフーリエ展開の関係が成り立つ。<br>
    <br>
    次に、この展開式の i=1~N までの項をとった展開式 ![image](https://user-images.githubusercontent.com/25688193/48613406-f784a400-e9ce-11e8-817d-77b096c6c232.png) 及び ![image](https://user-images.githubusercontent.com/25688193/48613438-0bc8a100-e9cf-11e8-9d90-360ea2023c0c.png) の収束性について調べる。<br>
    フビニの定理より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48613493-416d8a00-e9cf-11e8-8815-d84495a8aae1.png)<br>
	の関係が成り立つ？が、右辺の被積分関数（赤字部分）は、先のフーリエ展開の式より、ほとんどいたるところの ![image](https://user-images.githubusercontent.com/25688193/48613188-63b2d800-e9ce-11e8-8844-085ffc324b05.png) に関して、N→∞ で０に収束する。<br>
    更に、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48613531-58ac7780-e9cf-11e8-9f91-bd6e44f42a11.png)<br>
    のように、N に依存しない被積分関数 ![image](https://user-images.githubusercontent.com/25688193/48613565-7a0d6380-e9cf-11e8-820e-f51be651b03a.png) で上限を定められるので、ルベーグの収束定理より、先のフビニの定理からの式が、N→∞ で０に収束する。<br>
    ![image](https://user-images.githubusercontent.com/25688193/48613612-96a99b80-e9cf-11e8-8d67-f0fc8009e44e.png)<br>
    従って、青字部分の N を ∞ にした展開式<br>
    ![image](https://user-images.githubusercontent.com/25688193/48613633-a75a1180-e9cf-11e8-900c-cf90f98be6af.png)<br>
    が成り立つことが分かる。<br>


<a id="正値積分核（Mercer核）とMercerの定理"></a>

#### ☆ 正値積分核（Mercer核）と Mercer の定理
まず、積分核と積分作用素の正値性の関連を示す。<br>

![image](https://user-images.githubusercontent.com/25688193/48762175-d46b3480-eced-11e8-8a05-e12fc525a68d.png)<br>

<br>

次に、前段階として、測度の台の概念を導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/48659244-65919f80-ea91-11e8-83c9-10b99d00658d.png)<br>

![image](https://user-images.githubusercontent.com/25688193/48692323-ecbd4f80-ec18-11e8-864f-c770ab10bb6a.png)<br>

<br>

以下の定理は、ハウスドルフ空間上のラドン測度上のカーネル関数を元にした作用素が、正値作用素となることを述べたものであり、この定理と先の積分作用素の正値性の定義と組合わせ、更にヒルベルト＝シュミット作用素が積分作用素でもある事実を利用することで、積分作用素の固有値の正値性が示せ、最終的に Mercer の定理に結びつく。<br>

![image](https://user-images.githubusercontent.com/25688193/48704664-88ab8300-ec3a-11e8-9ec4-a7844a66c7ac.png)<br>

- （証明）<br>
    - 「⇒」方向の証明<br>
        ![image](https://user-images.githubusercontent.com/25688193/48693212-11ff8d00-ec1c-11e8-9c43-b18673f45b86.png) は正定値カーネルであるので、<br>
		ハウスドルフ空間 Ω 上の任意の連続関数 ∀g∈Ω と、ハウスドルフ空間 Ω の分割された可測集合 ![image](https://user-images.githubusercontent.com/25688193/48693244-2ba0d480-ec1c-11e8-8cef-399666cdaf2d.png) を考えると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48693287-568b2880-ec1c-11e8-8a90-634bbbd42fce.png)<br>
		の関係が成り立つ。<br>
        積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48693334-7de1f580-ec1c-11e8-91c1-ee8e85bbd53a.png) の正値性の条件式の積分<br>
        ![image](https://user-images.githubusercontent.com/25688193/48693362-8df9d500-ec1c-11e8-9832-0577bfc97d9e.png)<br>
        は、この和の極限として与えるものになっているので、非負である。即ち、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48693479-ec26b800-ec1c-11e8-92cd-8dfa84d55244.png)<br>
        となり、積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48693334-7de1f580-ec1c-11e8-91c1-ee8e85bbd53a.png) は、正値作用素となることが分かる。<br>
        <br>
        ※ 尚、今の場合、ハウスドルフ空間 Ω 上の連続関数 ∀g∈Ω で考えて、![image](https://user-images.githubusercontent.com/25688193/48693560-25f7be80-ec1d-11e8-96f0-53b0b3c8b99c.png) と積分作用素の正値性の条件 ![image](https://user-images.githubusercontent.com/25688193/48693589-3d36ac00-ec1d-11e8-93b7-05b095776ca7.png) を対応付けたが、より厳密には、![image](https://user-images.githubusercontent.com/25688193/48693620-59d2e400-ec1d-11e8-8199-d8a9cb27fc83.png) において、任意の ε>0 に対して、![image](https://user-images.githubusercontent.com/25688193/48693652-7ff88400-ec1d-11e8-82b5-3e26f01c4bc3.png) となるような連続関数 g∈Ω を考え、積分作用素の正値性の条件 ![image](https://user-images.githubusercontent.com/25688193/48693589-3d36ac00-ec1d-11e8-93b7-05b095776ca7.png) を対応付ければよい。<br>
        <br>
    - 「⇐」方向の証明<br>
        背理法で示す。<br>
        - まず、非正定値カーネルの条件として、ある ![image](https://user-images.githubusercontent.com/25688193/48695984-f8624380-ec23-11e8-8577-e7e0757809ce.png) に対して、<br>
            ![image](https://user-images.githubusercontent.com/25688193/48696007-09ab5000-ec24-11e8-8fe6-1659d25dacd7.png)<br>
            が成り立つと仮定する。<br>
        - カーネル関数 ![image](https://user-images.githubusercontent.com/25688193/48696067-3495a400-ec24-11e8-91e5-f68e9a558b68.png) の連続性と、ハウスドルフ空間 Ω のハウスドルフ性（＝空間中の異なる点がそれらの近傍によって分離可能）より、各点 ![image](https://user-images.githubusercontent.com/25688193/48696095-49723780-ec24-11e8-8418-bf710cf17173.png) の開近傍 ![image](https://user-images.githubusercontent.com/25688193/48696134-63137f00-ec24-11e8-869d-5ea2e7cbeb42.png) が存在して、<br>
            ![image](https://user-images.githubusercontent.com/25688193/48696159-7292c800-ec24-11e8-9012-be5efe31be56.png)<br>
            の関係が成り立つ。<br>
        - ここで、![image](https://user-images.githubusercontent.com/25688193/48696296-dfa65d80-ec24-11e8-9e45-dd8b80e9d486.png) の条件より、![image](https://user-images.githubusercontent.com/25688193/48696365-167c7380-ec25-11e8-9ecf-cd4bff0e1202.png) の関係が成り立つ。<br>
            （＝このハウスドルフ空間 Ω は、測度 μ が非ゼロな集合から構成されているので、このハウスドルフ空間 Ω の近傍 ![image](https://user-images.githubusercontent.com/25688193/48696406-33b14200-ec25-11e8-8ba3-ffb907f5ee6f.png) に対しても、測度は非ゼロで、![image](https://user-images.githubusercontent.com/25688193/48696365-167c7380-ec25-11e8-9ecf-cd4bff0e1202.png) となる。）<br>
        - 関数 ![image](https://user-images.githubusercontent.com/25688193/48696490-6824fe00-ec25-11e8-96f3-fed4ab59dcd2.png) において、<br>
            ![image](https://user-images.githubusercontent.com/25688193/48696505-76731a00-ec25-11e8-9b0b-6c9a6f03d066.png)<br>
            とおくと、<br>
            積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48693334-7de1f580-ec1c-11e8-91c1-ee8e85bbd53a.png) の正値性の条件式の積分 ![image](https://user-images.githubusercontent.com/25688193/48696577-9e627d80-ec25-11e8-87f8-5cf8fcbd7ed0.png) は、<br>
            ![image](https://user-images.githubusercontent.com/25688193/48696662-e681a000-ec25-11e8-8fc2-c27e65b48a26.png)<br>
            となり、仮定（正値作用素）に矛盾するので、命題は成り立つ。<br>

<br>

この定理（カーネル関数と正値作用素）と先の定義（正値積分核）と組合わせる。<br>
具体例には、<br>
定義（正値積分核）において、定理（カーネル関数と正値作用素）のように、<br>

- 位相空間 Ω を、Supp(μ)=Ω を満たすハウスドルフ空間 Ω<br>
- 測度 μ を、ハウスドルフ空間 Ω 上のラドン測度 μ<br>

と置き換えると、定理（カーネル関数と正値作用素）において、<br>

- カーネル関数 ![image](https://user-images.githubusercontent.com/25688193/48707192-fdce8680-ec41-11e8-929b-43379d939705.png) によって定まる作用素 ![image](https://user-images.githubusercontent.com/25688193/48707126-cc55bb00-ec41-11e8-8095-281cf2819a7c.png) が、ハウスドルフ空間 Ω 上の正定値カーネル（＝積分核）![image](https://user-images.githubusercontent.com/25688193/48707192-fdce8680-ec41-11e8-929b-43379d939705.png) によって定まる積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48707126-cc55bb00-ec41-11e8-8095-281cf2819a7c.png)<br>

のようになり、この積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48707126-cc55bb00-ec41-11e8-8095-281cf2819a7c.png) が、必要十分条件により、正値作用素にもなる。<br>

更に、積分作用素は、ヒルベルト＝シュミット作用素でもあり、又、正値作用素がは自己共役作用素であるので、
自己共役なヒルベルトシュミット作用素の固有値が全て実数である事実と同様にして、積分作用素 ![image](https://user-images.githubusercontent.com/25688193/48707126-cc55bb00-ec41-11e8-8095-281cf2819a7c.png) は固有値展開可能であり、それらの全ての固有値は非負の実数となることが分かる。<br>
即ち、非負の実数の固有値 ![image](https://user-images.githubusercontent.com/25688193/48707360-8ea56200-ec42-11e8-934e-45d6b487342c.png) が存在し、これに対応する固有ベクトル ![image](https://user-images.githubusercontent.com/25688193/48707387-a250c880-ec42-11e8-81b4-9f9968848678.png) が存在する。<br>

これらのことをまとめて、更に収束性に関する内容を加えた定理が、以下に示す Mercer の定理となる。<br>

![image](https://user-images.githubusercontent.com/25688193/48721198-be656180-ec64-11e8-9b6b-89c5726dc9e3.png)<br>

- （証明略）収束性に関する主張の証明は略<br>
    前半の内容はこれまでの議論（積分核のヒルベルト＝シュミット展開～定理（カーネル関数と正値作用素）まで）より、成り立つことが分かる。<br>


<a id="Mercer核が定める再生核ヒルベルト空間の具体的な構成"></a>

#### ☆ Mercer 核が定める再生核ヒルベルト空間の具体的な構成
Mercer の定理を用いれば、再生核ヒルベルト空間とその空間上で定義される内積の具体的な表示を構成することが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/48762227-f1076c80-eced-11e8-8a23-aaee6f4e59d6.png)<br>
![image](https://user-images.githubusercontent.com/25688193/48762262-02507900-ecee-11e8-8307-c782e7a4955a.png)<br>

- （証明略）(b) の証明のみ記載<br>
    - (a) ヒルベルト空間の証明<br>
        この空間の完備性を示せばよい。<br>
        <br>
    - (b) 再生核ヒルベルト空間の証明<br>
        積分核 K は、Mercer の定理より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48763015-a850b300-ecef-11e8-87ff-ded5be6a15da.png)<br>
        と書けるが、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48763062-bef70a00-ecef-11e8-9fe4-683a31ff3f95.png)<br>
        であるので、この積分核 K が、ヒルベルト空間中の要素（関数）であり、![image](https://user-images.githubusercontent.com/25688193/48762442-66733d00-ecee-11e8-8d12-c8e481c998b8.png) である。<br>
        従って、ヒルベルト空間中の要素（関数）![image](https://user-images.githubusercontent.com/25688193/48762578-ab976f00-ecee-11e8-8d27-dc688fca4ad1.png) との内積 ![image](https://user-images.githubusercontent.com/25688193/48762824-35dfd300-ecef-11e8-8049-38c6f141ce22.png) が定義でき、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48763111-d635f780-ecef-11e8-9e61-ad1dd66ad922.png)<br>
        のように再生性の条件を満たすので、<br>
        積分核 K は再生核であり、この部分空間 H が、再生核ヒルベルト空間となることが分かる。<br>


<a id="【補足】ヒルベルト空間上の線形作用素のトーレス、ヒルベルト＝シュミット作用素"></a>

#### 【補足】ヒルベルト空間上の線形作用素のトーレス、ヒルベルト＝シュミット作用素
![image](https://user-images.githubusercontent.com/25688193/48547065-21759200-e90d-11e8-8b5a-d474d3452254.png)<br>

![image](https://user-images.githubusercontent.com/25688193/48547105-37835280-e90d-11e8-8322-2bcbd99ba5b4.png)<br>

- （証明）<br>
    以下の関係式より成り立つ。<br>
    ![image](https://user-images.githubusercontent.com/25688193/48547197-613c7980-e90d-11e8-83cd-714a0a68cd60.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/48547237-7e714800-e90d-11e8-8897-11143ad32315.png)<br>

![image](https://user-images.githubusercontent.com/25688193/48547279-93e67200-e90d-11e8-83bb-3a1dfe7c269c.png)<br>

- （証明）<br>
    以下の関係式より成り立つ。<br>
    ![image](https://user-images.githubusercontent.com/25688193/48547316-ae205000-e90d-11e8-956c-5869c28db93d.png)<br>

![image](https://user-images.githubusercontent.com/25688193/48547358-c55f3d80-e90d-11e8-9f7d-3ef5715f8206.png)<br>

- （証明）<br>
    ヒルベルト＝シュミットノルムは、![image](https://user-images.githubusercontent.com/25688193/48547428-f17abe80-e90d-11e8-8644-dd7e6743c12d.png) で定義されるが、<br>
    パーシバルの等式より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48547473-0e16f680-e90e-11e8-9562-14b67e666e5a.png)<br>
	の関係が成り立つので、ヒルベルト＝シュミットノルムに対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48547521-30a90f80-e90e-11e8-86b8-17930a58d1f6.png)<br>
    の関係が成り立つ。<br>

<br>

- 【参考】<br>
    - [作用素ノルム](http://yagami12.hatenablog.com/entry/2018/10/03/134340#ID_A-2-1)<br>


<a id="【補足】共役作用素と正値性"></a>

#### 【補足】共役作用素と正値性
![image](https://user-images.githubusercontent.com/25688193/48625514-d59d1880-e9f2-11e8-9e9d-1770a91e2252.png)<br>

![image](https://user-images.githubusercontent.com/25688193/48626742-0a5e9f00-e9f6-11e8-81c1-9237c5da92a6.png)<br>

- （証明略）<br>


<a id="ニューラルネットワークとカーネル法"></a>

## ■ ニューラルネットワークとカーネル法

> 【Memo】ニューラルネットワークとカーネル法<br>
> ニューラルネットワークの中間層からの出力<br>
> ![image](https://user-images.githubusercontent.com/25688193/48778018-810ddc00-ed17-11e8-9d64-b3cad6fde018.png)<br>
> 再生核ヒルベルト空間上の関数<br>
> ![image](https://user-images.githubusercontent.com/25688193/48778086-a7cc1280-ed17-11e8-933c-40e831425368.png)<br>
> の２つの式が、形式的には同じ形となっているので、浅いニューラルネットワークは、カーネル法と似た構造を持つことが分かる。<br>
> <br>
> ニューラルネットワークの中間層からの出力 ![image](https://user-images.githubusercontent.com/25688193/48778174-d77b1a80-ed17-11e8-8d60-95e90e6316c8.png) を用いた関数<br>
> ![image](https://user-images.githubusercontent.com/25688193/48778200-e6fa6380-ed17-11e8-8081-5fbff948d3a5.png)<br>
> が、正定値カーネルとなるから、これらを直交基底とする再生核ヒルベルト空間が生成できるので、<br>
> ニューラルネットワークの中間層からの出力は、再生核ヒルベルト空間の要素（関数）となっていると言える。<br>
> つまり、ニューラルネットワークは、マルチプルカーネル学習（＝係数である重みベクトルa,bも学習してカーネル関数自体も学習）を行うカーネル法ともみなせる。<br>



---


<a id="参考文献"></a>

## ■ 参考文献

- カーネル法入門―正定値カーネルによるデータ解析 (シリーズ 多変量データの統計科学)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95%E5%85%A5%E9%96%80%E2%80%95%E6%AD%A3%E5%AE%9A%E5%80%A4%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E5%A4%9A%E5%A4%89%E9%87%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%B5%B1%E8%A8%88%E7%A7%91%E5%AD%A6-%E7%A6%8F%E6%B0%B4-%E5%81%A5%E6%AC%A1/dp/4254128088?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4254128088)<br>

- カーネル多変量解析―非線形データ解析の新しい展開 (シリーズ確率と情報の科学)<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90%E2%80%95%E9%9D%9E%E7%B7%9A%E5%BD%A2%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90%E3%81%AE%E6%96%B0%E3%81%97%E3%81%84%E5%B1%95%E9%96%8B-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA%E7%A2%BA%E7%8E%87%E3%81%A8%E6%83%85%E5%A0%B1%E3%81%AE%E7%A7%91%E5%AD%A6-%E8%B5%A4%E7%A9%82-%E6%98%AD%E5%A4%AA%E9%83%8E/dp/4000069713?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4000069713)<br>
    - 前半に各種カーネル法（カーネル主成分分析、SVMなど）の説明があって、最後の方に、正定値カーネル、再生核ヒルベルト空間についての（関数解析用語での）理論的な説明。加えて、正定値カーネルの情報幾何的な解釈、リプレゼンター定理の説明がある。<br>

- サポートベクターマシン入門<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%83%99%E3%82%AF%E3%82%BF%E3%83%BC%E3%83%9E%E3%82%B7%E3%83%B3%E5%85%A5%E9%96%80-%E3%83%8D%E3%83%AD-%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%86%E3%82%A3%E3%82%A2%E3%83%8B%E3%83%BC%E3%83%8B/dp/4320121341?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320121341)<br>
    - 原書は英語の本。カーネル法の1種であるSVMのみのタイトルだが、3章のカーネル誘導特徴空間の章で、より一般的な、正定値カーネル、再生核ヒルベルト空間の理論的な説明。及び、マーセルの定理の説明。
    加えて、カーネルとガウス過程の話がある。更に（カーネル法の話題からは話が逸れる？が）4章の汎化理論で、PAC学習、VC理論（※これらに関しては全然知らない）の説明もある。<br>

- 機械学習のエッセンス -実装しながら学ぶPython,数学,アルゴリズム- (Machine Learning)<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%81%AE%E3%82%A8%E3%83%83%E3%82%BB%E3%83%B3%E3%82%B9-%E5%AE%9F%E8%A3%85%E3%81%97%E3%81%AA%E3%81%8C%E3%82%89%E5%AD%A6%E3%81%B6Python-%E3%82%A2%E3%83%AB%E3%82%B4%E3%83%AA%E3%82%BA%E3%83%A0-Machine-Learning/dp/4797393963/ref=sr_1_1?ie=UTF8&qid=1541355307&sr=8-1&keywords=%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%81%AE%E3%82%A8%E3%83%83%E3%82%BB%E3%83%B3%E3%82%B9)
    - 5-7章にカーネル法の1種であるSVMのアルゴリズムを構成するマージン最大化と最適化問題の丁寧な式変形での解説と、scikit-learn などの機械学習フレームワークを使用せず、numpyだけを使用したPythonでのスクラッチ実装コードとその丁寧なコード説明がある。<br>

- はじめてのパターン認識<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)<br>

- 数学セミナー12月号 機械学習の数理 (2)<br>
    - [数学セミナー2018年12月号｜日本評論社](https://www.nippyo.co.jp/shop/magazines/latest/4.html)<br>


<a id="使用コード"></a>

### ◎ 使用コード
この記事で使われている一部の各種図や解析内容のコードは、以下の場所に置いてあります。参考までに<br>

- サポートベクターマシン（SVM）<br>
    - [GitHub/Yagami360/MachineLearning_Exercises_Python_scikit-learn/SVM_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/SVM_scikit-learn)<br>

- カーネル主成分分析<br>
    - [GitHub/Yagami360/MachineLearning_Exercises_Python_scikit-learn/kernelPCA_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/kernelPCA_scikit-learn)

