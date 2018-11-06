# カーネル法
非線形データに対する多変数解析の一種であるカーネル法の数理面について勉強したことをまとめたノート（忘備録）です。随時追記中。<br>

## 目次 [Contents]

1. [概要](#概要)
    1. [カーネル法の基本的なアイデア](#カーネル法の基本的なアイデア)
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
        1. 【補足】リースの表現定理
    1. [Moore-Aronszajn の定理](#Moore-Aronszajnの定理)
        1. [特徴写像とカーネルトリック（Moore - Aronszajn の定理からの帰着）](#特徴写像とカーネルトリック（Moore-Aronszajnの定理からの帰着）)
    1. [再生核ヒルベルト空間の具体的な構成](#再生核ヒルベルト空間の具体的な構成)
        1. [線形カーネルの再生核ヒルベルト空間](#線形カーネルの再生核ヒルベルト空間)
        1. [有限集合上の（エルミート行列の）再生核ヒルベルト空間](#有限集合上の（エルミート行列の）再生核ヒルベルト空間)
        1. [多項式カーネルの再生核ヒルベルト空間](#多項式カーネルの再生核ヒルベルト空間)
    1. [ヒルベルト空間の埋め込み写像による再生核ヒルベルト空間の構成](#ヒルベルト空間への埋め込み写像による再生核ヒルベルト空間の構成)
        1. [フーリエ変換と埋め込み写像](#フーリエ変換と埋め込み写像)
        1. RBF カーネルの再生核ヒルベルト空間
        1. ラプラスカーネルの再生核ヒルベルト空間
    1. ソボレフ空間 [Sobolev space]
1. [正定値カーネルの理論](#正定値カーネルの理論)
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
1. 補足事項
    1. [【外部リンク】関数解析とヒルベルト空間](http://yagami12.hatenablog.com/entry/2018/10/03/134340)
    1. [【外部リンク】最適化問題](http://yagami12.hatenablog.com/entry/2017/09/17/101739)
    1. [【外部リンク】測度論](http://yagami12.hatenablog.com/entry/2018/11/04/232957)
1. [参考文献](#参考文献)
    1. [使用コード](#使用コード)

---

<a id="概要"></a>

## ■ 概要
> 記載中...


<a id="カーネル法の基本的なアイデア"></a>

### ◎ カーネル法の基本的なアイデア
> 記載中...

- カーネルトリック<br>
    ![image](https://user-images.githubusercontent.com/25688193/48049190-3b162b80-e1e1-11e8-88ec-ef2b67018faf.png)<br>

    > 【Memo】<br>
    > カーネルトリックは、Moore - Aronszajn の定理からの帰着で自然に導かれる。<br>

<br>

- カーネル法の１つであるカーネル主成分分析<br>
    ![image](https://user-images.githubusercontent.com/25688193/48049315-93e5c400-e1e1-11e8-9e8f-2aaccaf9e961.png)<br>


<a id="正定値カーネル"></a>

## ■ 正定値カーネル

<a id="実数の正定値カーネル"></a>

### ◎ 実数の正定値カーネル
![image](https://user-images.githubusercontent.com/25688193/48049488-30a86180-e1e2-11e8-8ee8-bf89a0216943.png)<br>

> 正定値カーネルの解釈図を要追記

![image](https://user-images.githubusercontent.com/25688193/46429746-32fe4280-c782-11e8-99e4-8c0f2b30e128.png)<br>


<a id="複素数の正定値カーネル"></a>

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


<a id="正定値カーネルの基本的な性質"></a>

### ◎ 正定値カーネルの基本的な性質
次に、この正定値カーネルに関して成り立つ基本的な性質をいくつか見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/46507390-358c9500-c873-11e8-88d8-85f6350ab6e5.png)<br>

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
の計算で出来ることになる！⇒ 計算量を削減出来る！<br>

次に、（次数が）一般の場合 d では、<br>
多項式カーネル ![image](https://user-images.githubusercontent.com/25688193/46511996-ae4c1b00-c88c-11e8-9066-d73e8da61096.png) を２項定理を用いて展開すると、<br>
![image](https://user-images.githubusercontent.com/25688193/46512023-d9366f00-c88c-11e8-96ec-e7398cd8f209.png)<br>
即ち、多項数カーネルの使用した時の２つのベクトル ![image](https://user-images.githubusercontent.com/25688193/46524114-bc1c9300-c8c2-11e8-85b1-e96c2d3f3488.png) の次元（次数）の上限は ∑ の形で求めることが出来る！<br>


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
![image](https://user-images.githubusercontent.com/25688193/48042862-eb2a6b00-e1c6-11e8-9743-90584feee90d.png)<br>

先の再生核ヒルベルト空間の線形汎関数を用いた特徴付けと、<br>
Moore-Aronszajn の定理より、再生核ヒルベルト空間を再解釈（＝特徴付け）したのが以下の図である。<br>
正定値カーネルが、再生核ヒルベルト空間の基底になっており、それを元に再生核ヒルベルト空間が構築されていることと、再生性の条件 ⟨ f,k( ∙ ,x ⃗ )  ⟩_H=f(x ⃗ )    (∀x ⃗∈X ;∀f∈H)  が、元のベクトル空間での入力値の写像後の値に対応している点がポイントである。<br>

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


<a id="再生核ヒルベルト空間の具体的構成"></a>

### ◎ 再生核ヒルベルト空間の具体的構成
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


<a id="ヒルベルト埋め込み写像による再生核ヒルベルト空間の構成"></a>

### ◎ ヒルベルト埋め込み写像による再生核ヒルベルト空間の構成
再生核ヒルベルト空間を、他の一般的な関数空間（例えば、ヒルベルト空間）の部分空間として構成する一般的な方法に、関数空間へのヒルベルト空間の埋め込み写像（＝ヒルベルト埋め込み写像）による構成方法が存在する。<br>

> 【Memo】ヒルベルト埋め込み写像による再生核ヒルベルト空間の構成<br>
> 埋め込み写像とは、数学的な構造を保ちながら、写像元より一般的で広い空間の部分空間に埋め込むような写像（例えば、２次元ユークリッド空間の３次元ユークリッド空間への埋め込み。正数の実数への埋め込みなど）であるが、<br>
> L２空間の部分空間を、より一般的な関数空間（例えば、ヒルベルト空間）の部分空間として埋め込みような埋め込み写像を考えると、この埋め込みんだ部分空間は、再生核ヒルベルト空間になる。<br>
> 言い換えると、再生核ヒルベルト空間を他の一般的な関数空間（例えば、ヒルベルト空間）の部分空間として実現できる。<br>
> - 埋め込まれた部分空間が、再生核ヒルベルト空間になる理由<br>
>    記載中...<br>
> - 埋め込み写像が、フーリエ変換によって表現出来ること<br>
>    記載中...<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/48049645-9ac10680-e1e2-11e8-8da7-35c06bceedc3.png)<br>

> 以下の事項を、１つの定理としてまとめること。<br>

- X : 集合<br>
- ![image](https://user-images.githubusercontent.com/25688193/46723566-1ea2d400-ccb3-11e8-8109-3219a99dd431.png) : 集合 X 上の全ての複素数値関数からなる関数空間<br>
    各点収束による位相構造を持つ。１つの具体的な例として、ヒルベルト空間でもあるとする。<br>
- ![image](https://user-images.githubusercontent.com/25688193/47996447-f4bac100-e13b-11e8-85e9-7a888c44c054.png) : σ-加法族？
- ![image](https://user-images.githubusercontent.com/25688193/47996123-d607fa80-e13a-11e8-8bb5-654c3e819fbc.png) : 測度空間<br>
- ![image](https://user-images.githubusercontent.com/25688193/47996156-f0da6f00-e13a-11e8-9732-300e8c004bc5.png) : L2 空間（＝完備測度空間）<br>
- ![image](https://user-images.githubusercontent.com/25688193/47996329-837b0e00-e13b-11e8-9181-429e4cd11b8f.png) : ![image](https://user-images.githubusercontent.com/25688193/47996363-97bf0b00-e13b-11e8-9391-86655669ee8f.png) 上の可測関数。以下の関係が成り立つと仮定する。<br>
    - ![image](https://user-images.githubusercontent.com/25688193/47996500-1e73e800-e13c-11e8-903f-27627eee2f50.png)<br>
    - この可測関数 ![image](https://user-images.githubusercontent.com/25688193/47996329-837b0e00-e13b-11e8-9181-429e4cd11b8f.png) を基底とした空間が、![image](https://user-images.githubusercontent.com/25688193/47996156-f0da6f00-e13a-11e8-9732-300e8c004bc5.png) になる。即ち、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48049676-bc21f280-e1e2-11e8-9707-0adb0e94c4fa.png) が、L2空間 ![image](https://user-images.githubusercontent.com/25688193/47996156-f0da6f00-e13a-11e8-9732-300e8c004bc5.png) で稠密<br>
- J：埋め込み写像（L2空間 ![image](https://user-images.githubusercontent.com/25688193/47996156-f0da6f00-e13a-11e8-9732-300e8c004bc5.png) から関数空間 ![image](https://user-images.githubusercontent.com/25688193/46723566-1ea2d400-ccb3-11e8-8109-3219a99dd431.png) へのヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/46724098-47779900-ccb4-11e8-81d6-faa0442713df.png) の埋め込み）<br>
    ![image](https://user-images.githubusercontent.com/25688193/47996727-d0abaf80-e13c-11e8-94ab-021fe4def259.png)<br>
- ![image](https://user-images.githubusercontent.com/25688193/46724098-47779900-ccb4-11e8-81d6-faa0442713df.png) : 埋め込み写像 J により、関数空間 ![image](https://user-images.githubusercontent.com/25688193/46723566-1ea2d400-ccb3-11e8-8109-3219a99dd431.png) の部分空間に埋め込まれるヒルベルト空間。<br>
    ※ 関数空間 ![image](https://user-images.githubusercontent.com/25688193/46723566-1ea2d400-ccb3-11e8-8109-3219a99dd431.png) は、ヒルベルト空間 H より広範囲の一般的な空間なので、埋め込み写像により、ヒルベルト空間を部分空間として埋め込むことが出来る。<br>
    <br>
    この埋め込まれたヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/46724098-47779900-ccb4-11e8-81d6-faa0442713df.png) は、先の埋め込み写像<br>
    ![image](https://user-images.githubusercontent.com/25688193/47996839-3e57db80-e13d-11e8-9915-47fa46eafe37.png)<br>
    の関係より、以下のような具体的な表示を持つ。<br>
    ![image](https://user-images.githubusercontent.com/25688193/47996939-9393ed00-e13d-11e8-9e98-6d41674156a1.png)<br>
    <br>
	更に、このヒルベルト空間は、上の再生核ヒルベルト空間でもあり、その再生核は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/48049718-dcea4800-e1e2-11e8-9d57-23a3ea676435.png)<br>
    で与えられる。<br>
	※ 再生性の条件 ![image](https://user-images.githubusercontent.com/25688193/48049808-3488b380-e1e3-11e8-90f3-6ca627879b30.png) において、<br>
	関数 ![image](https://user-images.githubusercontent.com/25688193/48049851-52561880-e1e3-11e8-83cb-45b70a801f95.png) の中で、![image](https://user-images.githubusercontent.com/25688193/48049929-a3fea300-e1e3-11e8-92cb-be2a39bd70d3.png) となるような正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48050063-212a1800-e1e4-11e8-9333-ce2c3bdf625d.png) が再生核であるが、<br>
	今の場合、この再生性の条件が、ヒルベルト空間の埋め込み前のL2空間での条件を経由して、<br>
	![image](https://user-images.githubusercontent.com/25688193/48050085-3737d880-e1e4-11e8-827c-b29a99f7a569.png)<br>
	となるので、![image](https://user-images.githubusercontent.com/25688193/48050151-723a0c00-e1e4-11e8-9640-1d8e71703a7e.png) が再生核になっていることが分かる。<br>


<br>

> 【Memo】埋め込み写像<br>
> 数学的な構造を保ちながら、写像元より一般的で広い空間の部分空間に埋め込むような写像。<br>
> 例えば、以下のような埋め込みは、埋め込み写像である。<br>
> - 例１（図形）：平面（２次元ユークリッド空間）は立体的空間（３次元ユークリッド空間）への埋め込み。<br>
> - 例２（図形）：球面や球体の、立体的空間への埋め込み。<br>
> - 例３（数）：整数の有理数への埋め込み。<br>
> - 例４（集合）：集合 X の部分集合 A の、X への埋め込み。<br>


<a id="フーリエ変換と埋め込み写像"></a>

#### ☆ フーリエ変換と埋め込み写像
次に、この埋め込み写像がフーリエ変換によって与えられることを見ていく。

> 以下の事項を、１つの定理としてまとめること。<br>

先のヒルベルト埋め込み写像による再生核ヒルベルト空間の構成で使われた記号に対して、以下のような具体的な形を与える。<br>

- 測度空間：![image](https://user-images.githubusercontent.com/25688193/48050333-ea083680-e1e4-11e8-889e-5dad6f8d9f70.png)<br>
    - 抽象集合：![image](https://user-images.githubusercontent.com/25688193/48050353-fdb39d00-e1e4-11e8-9ef9-ab3c593a63d4.png)<br>
    - ボレル可測集合族：![image](https://user-images.githubusercontent.com/25688193/48050381-13c15d80-e1e5-11e8-870d-7b0382a9d7d3.png)<br>
    - R 上の連続関数（＝密度関数）：![image](https://user-images.githubusercontent.com/25688193/48050415-276cc400-e1e5-11e8-9b8e-248935e993d4.png)<br>
- 可測関数：![image](https://user-images.githubusercontent.com/25688193/48050445-410e0b80-e1e5-11e8-8d8f-b14912a6f4a6.png)<br>

このとき、先のとヒルベルト埋め込み写像のときと同様にして、<br>
この可測集合 ![image](https://user-images.githubusercontent.com/25688193/48050445-410e0b80-e1e5-11e8-8d8f-b14912a6f4a6.png) を基底とした空間が、![image](https://user-images.githubusercontent.com/25688193/48050488-5b47e980-e1e5-11e8-9d0b-712b0c892e22.png) になる。即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/48050519-761a5e00-e1e5-11e8-8afa-671030486016.png) が ![image](https://user-images.githubusercontent.com/25688193/48050488-5b47e980-e1e5-11e8-9d0b-712b0c892e22.png) で稠密であることを示す。<br>


> 記載中...


<a id="ソボレフ空間"></a>

#### ☆ ソボレフ空間 [Soboveb space]
再生核ヒルベルト空間の重要な例として、ソボレフ空間がある。<br>


> 記載中...



<a id="正定値カーネルの理論"></a>

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
    - 前半に各種カーネル法（カーネル主成分分析、SVMなど）の説明があって、最後の方に、正定値カーネル、再生核ヒルベルト空間についての（関数解析用語での）理論的な説明。加えて、正定値カーネルの情報幾何的な解釈、リプレゼンター定理の説明がある。<br>

- サポートベクターマシン入門<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%83%99%E3%82%AF%E3%82%BF%E3%83%BC%E3%83%9E%E3%82%B7%E3%83%B3%E5%85%A5%E9%96%80-%E3%83%8D%E3%83%AD-%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%86%E3%82%A3%E3%82%A2%E3%83%8B%E3%83%BC%E3%83%8B/dp/4320121341?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320121341)<br>
    - 原書は英語の本。カーネル法の1種であるSVMのみのタイトルだが、3章のカーネル誘導特徴空間の章で、より一般的な、正定値カーネル、再生核ヒルベルト空間の理論的な説明。及び、マーセルの定理（カーネルと積分作用素、スペクトル分解が関連する話？）の説明。<br>
    加えて、カーネルとガウス過程の話がある。更に（カーネル法の話題からは話が逸れる？が）4章の汎化理論で、PAC学習、VC理論（※これらに関しては全然知らない）の説明もある。<br>

- 機械学習のエッセンス -実装しながら学ぶPython,数学,アルゴリズム- (Machine Learning)<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%81%AE%E3%82%A8%E3%83%83%E3%82%BB%E3%83%B3%E3%82%B9-%E5%AE%9F%E8%A3%85%E3%81%97%E3%81%AA%E3%81%8C%E3%82%89%E5%AD%A6%E3%81%B6Python-%E3%82%A2%E3%83%AB%E3%82%B4%E3%83%AA%E3%82%BA%E3%83%A0-Machine-Learning/dp/4797393963/ref=sr_1_1?ie=UTF8&qid=1541355307&sr=8-1&keywords=%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%81%AE%E3%82%A8%E3%83%83%E3%82%BB%E3%83%B3%E3%82%B9)
    - 5-7章にカーネル法の1種であるSVMのアルゴリズムを構成するマージン最大化と最適化問題の丁寧な式変形での解説と、scikit-learn などの機械学習フレームワークを使用せず、numpyだけを使用したPythonでのスクラッチ実装コードとその丁寧なコード説明がある。<br>

- はじめてのパターン認識 <br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)<br>


<a id="使用コード"></a>

### ◎ 使用コード
この記事で使われている各種図のコードは、以下の場所に置いてあります。参考までに<br>

- サポートベクターマシン（SVM）<br>
    - [GitHub/Yagami360/MachineLearning_Exercises_Python_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/SVM_scikit-learn/SVM_scikit-learn)<br>

- カーネル主成分分析<br>
    - [GitHub/Yagami360/MachineLearning_Exercises_Python_scikit-learn/kernelPCA_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/kernelPCA_scikit-learn)

