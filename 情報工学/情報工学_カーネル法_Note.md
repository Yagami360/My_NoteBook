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
1. [再生カーネルヒルベルト空間](#ID_4)
    1. [再生核の性質](#ID_4-1)
    1. [再生カーネルヒルベルト空間の線形汎関数を用いた特徴付けとリースの表現定理](#ID_4-2)
        1. 【補足】リースの表現定理
    1. [Moore-Aronszajn の定理](#ID_4-3)
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

## ■ 再生カーネルヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/46570783-d4fd7500-c9a4-11e8-8c10-ff42bb8edb7f.png)<br>

> 【メモ】<br>
> 正定値カーネルの定義、入力データとなる写像元が単なる集合じゃなくてベクトル空間のほうがいいのでは？と思ったけど、入力データによっては、ベクトル空間であったり、内積空間であったり、ノルム空間であったりし得えるから、一般性を確保するために集合で定義しているという理解でいいんかいな？<br>


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


<a id="ID_4-2"></a>

### ◎ 再生カーネルヒルベルト空間の線形汎関数を用いた特徴付けとリースの表現定理
![image](https://user-images.githubusercontent.com/25688193/46566361-de142500-c957-11e8-9e54-c964cfbcfbdc.png)<br>

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
![image](https://user-images.githubusercontent.com/25688193/46570820-4fc69000-c9a5-11e8-9eda-9681add6a50f.png)<br>

> 【メモ】<br>
> 再生カーネルヒルベルト空間、定義だけみても意味分かんないけど、Moore-Aronszajn の定理まで見てみればようやく意味がわかってくる印象<br>


先の再生カーネルヒルベルト空間の線形汎関数を用いた特徴付けと、<br>
Moore-Aronszajn の定理より、再生カーネルヒルベルト空間を再解釈（＝特徴付け）したのが以下の図である。
<br>

![image](https://user-images.githubusercontent.com/25688193/46566609-ba9fa900-c95c-11e8-8c28-a89da4de0f5d.png)<br>



---

<a id="参考文献"></a>

## ■ 参考文献

- カーネル法入門―正定値カーネルによるデータ解析 (シリーズ 多変量データの統計科学)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95%E5%85%A5%E9%96%80%E2%80%95%E6%AD%A3%E5%AE%9A%E5%80%A4%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E5%A4%9A%E5%A4%89%E9%87%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%B5%B1%E8%A8%88%E7%A7%91%E5%AD%A6-%E7%A6%8F%E6%B0%B4-%E5%81%A5%E6%AC%A1/dp/4254128088?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4254128088)<br>

- はじめてのパターン認識 <br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)<br>
