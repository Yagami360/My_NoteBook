# カーネル法
非線形データに対する多変数解析の一種であるカーネル法の、主に数理面について勉強したことをまとめたノート（忘備録）です。随時追記中。<br>

## 目次 [Contents]

1. [概要](#概要)
    1. [特徴写像と再生核ヒルベルト空間](#概要_特徴写像と再生核ヒルベルト空間)
    1. [カーネルトリック](#概要_カーネルトリック)
    1. [リプレゼンター定理](#概要_リプレゼンター定理)
    1. [カーネル法を利用した各種データ解析手法に共通する手順](#概要_カーネル法を利用した各種データ解析手法に共通する手順)
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
    1. 構造化データに対する正定値カーネル
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
1. [正則化とカーネル法](#正則化とカーネル法)
    1. [リプレゼンター定理](#リプレゼンター定理)
    1. [【補足（外部リンク）】正則化 [Regularization] による過学習への対応](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_3-1-4)
1. [各種カーネル法](#各種カーネル法)
    1. カーネルリッジ回帰
    1. [カーネル主成分分析（kernel PCA）](#カーネル主成分分析)
        1. [【補足（外部リンク）】主成分分析 [PCA : Principal Component Analysis]](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_2-5-1))
        1. [【補足（外部リンク）】カーネル主成分分析 [kernel PCA : kernel Principal Component Analysis]](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_2-5-2)
        1. [カーネル主成分分析の再生核ヒルベルト空間を用いた議論](#カーネル主成分分析の再生核ヒルベルト空間を用いた議論)
    1. [正準相関分析](#正準相関分析)
        1. [線形正準相関分析（CCA）](#線形正準相関分析)
        1. [カーネル正準相関分析（kernel CCA）](#カーネル正準相関分析)
    1. カーネル Fisher 判別分析
    1. [サポートベクターマシン（SVM）](#サポートベクターマシン（SVM）)
        1. [ハードマージンSVM（マージン最大化を実現する線形識別器）](#ハードマージンSVM（マージン最大化を実現する線形識別器）)
        1. [ソフトマージンSVM（スラッグ変数の導入と正則化）](#ソフトマージンSVM（スラッグ変数の導入と正則化）)
        1. [ヒンジ損失関数を用いた正則化法としての SVM](#ヒンジ損失関数を用いた正則化法としてのSVM)
        1. [マージン最大化を実現する線形識別器のカーネル化](#マージン最大化を実現する線形識別器のカーネル化)
        1. SVM の最適化問題の解法
        1. [【補足（外部リンク）】サポートベクターマシン [SVM : Support Vector Machine]](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_9)
    1. サポートベクトル回帰
    1. カーネルロジスティクス回帰
1. カーネルの設定
    1. 構造化データに対するカーネル
    1. ストリングカーネル（文字列に対するカーネル）
1. カーネル法との関連
    1. 平均による確率分布の特徴付け
        1. 再生核ヒルベルト空間における平均
        1. 確率分布を特徴付ける正定値カーネル
    1. 正定値カーネルによる依存性、独立性
        1. 再生核ヒルベルト空間上の共分散作用素
    1. 確率過程と再生核ヒルベルト空間
1. [ニューラルネットワークとカーネル法](#ニューラルネットワークとカーネル法)
1. 補足事項
    1. [【外部リンク】関数解析とヒルベルト空間](http://yagami12.hatenablog.com/entry/2018/10/03/134340)
    1. [【外部リンク】測度論](http://yagami12.hatenablog.com/entry/2018/11/04/232957)
    1. [【外部リンク】最適化問題](http://yagami12.hatenablog.com/entry/2017/09/17/101739)
    1. [【外部リンク】機械学習](http://yagami12.hatenablog.com/entry/2017/09/17/111400)
1. [参考文献](#参考文献)
    1. [使用コード](#使用コード)

---

<a id="概要"></a>

## ■ 概要
カーネル法は、非線形データに対する多変量解析の手法の１つであるが、その特徴としては、非線形データを正定値カーネルの形に応じて定まる再生核ヒルベルト空間上の線形データに持ち込んで解析する点にある。<br>

ここでは、以下のような観点から、カーネル法全体の概要を見ている。<br>

- 特徴写像と再生核ヒルベルト空間<br>
- カーネルトリック<br>
- リプレゼンター定理<br>
- カーネル法を利用した各種データ解析手法に共通する手順<br>


<a id="概要_特徴写像と再生核ヒルベルト空間"></a>

### ◎ 特徴写像と再生核ヒルベルト空間
![image](https://user-images.githubusercontent.com/25688193/49068931-5a95f680-f26b-11e8-8347-eb67fa17ddf8.png)<br>
有限次元のユークリッド空間上での線形なデータ解析手法は、左上図のように、データの分布が線形でない場合うまくいかない。<br>
このような場合、右上図のように、データをより高次元の空間に持ち込み、その空間上で、線形なデータ解析手法を適用するという解決策が考えられる。<br>
カーネル法では、このようなデータをより高次元の空間に持ち込む写像を、特徴写像として定式化し、この特徴写像の写像先の特徴空間を、再生核ヒルベルト空間として定式化する。<br>

> 詳細は、[再生核ヒルベルト空間](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#%E5%86%8D%E7%94%9F%E6%A0%B8%E3%83%92%E3%83%AB%E3%83%99%E3%83%AB%E3%83%88%E7%A9%BA%E9%96%93) に記載<br>


<a id="概要_カーネルトリック"></a>

### ◎ カーネルトリック 
![image](https://user-images.githubusercontent.com/25688193/49130072-7950c780-f315-11e8-860d-368559dd82e3.png)<br>
カーネル法では、特徴写像 Φ により、ユークリッド空間上のデータを、より高次元の特徴空間へ写像するが、この際に、カーネル関数 k は、特徴空間内の２つの特徴ベクトルの内積、即ち、![image](https://user-images.githubusercontent.com/25688193/49225878-87dbd380-f428-11e8-8305-c0af2a36dd2b.png) によって定まる。<br>
従って、特徴空間での内積を計算したい場合（例えば、データ解析手法において共分散分散行列を計算したい場合など）において、特徴空間の次数に依存して膨大になる特徴ベクトルの計算ではなく、カーネル関数をそのまま使って計算できる。<br>
このような計算量の削減手法を、カーネルトリックという。<br>
尚、このカーネルトリックの元になるの ![image](https://user-images.githubusercontent.com/25688193/49225878-87dbd380-f428-11e8-8305-c0af2a36dd2b.png) 関係は、Moore - Aronszajn の定理からの帰着から得られる。<br>

> 詳細は、[Moore-Aronszajn の定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#Moore-Aronszajn%E3%81%AE%E5%AE%9A%E7%90%86)、[ 特徴写像とカーネルトリック（Moore - Aronszajn の定理からの帰着）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#%E7%89%B9%E5%BE%B4%E5%86%99%E5%83%8F%E3%81%A8%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%83%88%E3%83%AA%E3%83%83%E3%82%AF%EF%BC%88Moore-Aronszajn%E3%81%AE%E5%AE%9A%E7%90%86%E3%81%8B%E3%82%89%E3%81%AE%E5%B8%B0%E7%9D%80%EF%BC%89) に記載<br>


<a id="概要_リプレゼンター定理"></a>

### ◎ リプレゼンター定理
特徴写像の写像先である再生核ヒルベルト空間内で、各種データ解析手法で線形解析を行う際に、再生核ヒルベルト空間が、無限次元空間であるために、実際上には、計算機で計算不可能であるという問題がある。<br>
このような問題は、リプレゼンター定理により、解決できる。<br>
即ち、この無限次元である再生核ヒルベルト空間内での最適化問題は、データの張る有限次元部分空間の中での最適化問題に帰着できる。<br>

> 詳細は、[リプレゼンター定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#%E3%83%AA%E3%83%97%E3%83%AC%E3%82%BC%E3%83%B3%E3%82%BF%E3%83%BC%E5%AE%9A%E7%90%86) に記載<br>

<a id="概要_カーネル法を利用した各種データ解析手法に共通する手順"></a>

### ◎ カーネル法を利用した各種データ解析手法に共通する手順
カーネル法を利用したデータ解析手法には、サポートベクターマシン、カーネル主成分分析など、様々な手法が存在するが、いずれもその基本的なコンセプトに一貫した３つの共通ポイントが見られる。<br>
1. １つ目のポイントは、ユークリッド空間上での線形解析手法を、特徴写像により再生核ヒルベルト空間に持ち込み、その再生核ヒルベルト空間上で、線形解析手法を適用することで、ユークリッド空間では線形分離不可能であった問題を、線形分離可能な問題に落とし込むいう点である。<br>
2. ２つ目のポイントは、この再生核ヒルベルト空間上での線形解析手法を適用する際に、再生核ヒルベルト空間が無限次元空間であるが故に、実際上計算機で計算不可能な問題が発生するが、リプレゼンター定理により、データより張られる有限次元部分空間上でのデータ解析手法に置き換えるという点である。<br>
3. ３つ目のポイントは、このリプレゼンター定理により有限次元化されたデータ解析手法において、分散共分散行列などの計算で、内積演算が必要になるケースが多々あるが、この再生核ヒルベルト空間上での内積演算を２つの特徴ベクトルの内積を計算することなく、カーネル関数で表せるという、カーネルトリックを用いて、計算負荷を削減する点にある。<br>

> カーネル法を利用した各種データ解析手法の詳細は、[各種カーネル法](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95_Note.md#%E5%90%84%E7%A8%AE%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95) に記載<br>

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
となり、カーネルトリックの元になる関係式が成り立っていることが分かる。<br>
つまり、カーネルトリックは、Moore - Aronszajn の定理からの帰着で導かれる。<br>


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



<a id="正則化とカーネル法"></a>

## ■ 正則化とカーネル法
機械学習における（損失関数の）正則化は、主に、汎化性能を向上させ、過学習を抑制するために行われる手法の１つであるが、カーネル法における正則化は、この汎化性能の向上の目的だけではなく、後述のリプリゼンター定理によって、無限次元である再生核ヒルベルト空間内でのモデルをカーネル関数の有限次元での線形結合のモデルに限定するという別の大きな目的がある。<br>


- 【参考】<br>
    - [正則化 [Regularization] による過学習への対応](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_3-1-4)<br>


<a id="リプレゼンター定理"></a>

### ☆ リプレゼンター定理
以下、この無限次元である再生核ヒルベルト空間内でのモデルをカーネル関数の有限次元での線形結合のモデルに限定するリプリゼンター定理を導く。<br>

まず、与えられたデータ ![image](https://user-images.githubusercontent.com/25688193/48832622-e9fb5f80-edbc-11e8-9e51-61a40962ea75.png) に対して、最適化問題の解を再生核ヒルベルト空間中の関数 ![image](https://user-images.githubusercontent.com/25688193/48832659-05666a80-edbd-11e8-8681-611473b2f549.png) とするような、以下のような最適化問題を考える。<br>

![image](https://user-images.githubusercontent.com/25688193/48832701-1911d100-edbd-11e8-874a-f486e1c30c1a.png)<br>

ここで、L は任意の損失関数で、![image](https://user-images.githubusercontent.com/25688193/48832763-45c5e880-edbd-11e8-8f97-d1e4e7932a2c.png) は、与えられたデータ ![image](https://user-images.githubusercontent.com/25688193/48832622-e9fb5f80-edbc-11e8-9e51-61a40962ea75.png) と再生核ヒルベルト空間中の関数 ![image](https://user-images.githubusercontent.com/25688193/48832659-05666a80-edbd-11e8-8681-611473b2f549.png) に依存するという意味。<br>
又、![image](https://user-images.githubusercontent.com/25688193/48832850-79a10e00-edbd-11e8-9ae3-65f349677185.png) は、以下の図のように、最適化問題のL2正則化項となっている。（λは、正則化パラメータ）<br>
（※図では、![image](https://user-images.githubusercontent.com/25688193/48832931-a48b6200-edbd-11e8-9a0c-0e8e28fce2ad.png) で対応）<br>

![image](https://user-images.githubusercontent.com/25688193/48832960-b5d46e80-edbd-11e8-8823-85795e412004.png)<br>

この最適化問題をより一般化して、以下のような最適化問題を考える。<br>

![image](https://user-images.githubusercontent.com/25688193/48833039-e74d3a00-edbd-11e8-8779-aa5a834e683a.png)<br>

このような最適化問題は、再生核ヒルベルト空間内での最適化問題なので、無限次元空間での最適化問題になっているために、現実的に計算機での計算が困難であるように思える。<br>
しかしながら、以下のリプリゼンター定理により、このような無限次元空間である再生核ヒルベルト空間での最適化問題が、再生核ヒルベルト空間の再生性を用いることで、有限次元での最適化問題に置き換えられるので、計算可能な最適化問題となる。<br>

![image](https://user-images.githubusercontent.com/25688193/49068720-cc217500-f26a-11e8-92e9-23a75b392cc4.png)<br>

- （証明）<br>
    - 級数展開の式<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833178-28454e80-edbe-11e8-96b7-ce253a60b59e.png)<br>
        において、基底となる正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48833222-3b581e80-edbe-11e8-9bf4-ee5aa2fce389.png) の組より生成される有限次元の部分空間<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833274-5d51a100-edbe-11e8-9814-c76da14fb867.png)<br>
        とその直交補空間 ![image](https://user-images.githubusercontent.com/25688193/48833323-70fd0780-edbe-11e8-8197-d369616dfb7d.png) を用いて、<br>
        再生核ヒルベルト空間は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833393-9be75b80-edbe-11e8-951e-adba053e5636.png)<br>
        のように表現できる。<br>
        従って、最適化問題の解である再生核ヒルベルト空間の要素（＝関数）に対しても、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833427-ae619500-edbe-11e8-9284-9d02d397eb3d.png)<br>
        の関係が成り立つ。<br>
    - ここで、再生核ヒルベルト空間における再生性の条件<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833490-ce915400-edbe-11e8-8e7c-db4226a1307d.png)<br>
        を考えると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833533-e79a0500-edbe-11e8-89f7-0afafddfe710.png)<br>
        従って、![image](https://user-images.githubusercontent.com/25688193/48833798-845ca280-edbf-11e8-9a1d-d814bfdc43d6.png) を ![image](https://user-images.githubusercontent.com/25688193/48833741-68590100-edbf-11e8-946c-58164364d489.png) に変更しても最適化関数 L の値は変わらず、![image](https://user-images.githubusercontent.com/25688193/48833583-07c9c400-edbf-11e8-95ed-15b1c0cc6ced.png) である。<br>
    - 更に、直交性から、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833627-1e701b00-edbf-11e8-854d-7c09b8eb770b.png)<br>
        となるが、Ψ は単調増加関数なので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833685-419aca80-edbf-11e8-821b-0e6d4dc5830a.png)<br>
    - 従って、この最適化問題の min の中身は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833816-92aabe80-edbf-11e8-9935-eb666b45ef75.png)<br>
        という関係が成り立つので、この級数展開の式<br>
        ![image](https://user-images.githubusercontent.com/25688193/48833178-28454e80-edbe-11e8-96b7-ce253a60b59e.png)<br>
        で与えられる関数 ![image](https://user-images.githubusercontent.com/25688193/48833741-68590100-edbf-11e8-946c-58164364d489.png) は、最適化問題の最小値を達成する解であることが分かる。<br>



<a id="各種カーネル法"></a>

## ■ 各種カーネル法
カーネル法を利用したデータ解析手法には、サポートベクターマシン、カーネル主成分分析など、様々な手法が存在するが、いずれもその基本的なコンセプトに一貫した３つの共通ポイントが見られる。<br>

1. １つ目のポイントは、ユークリッド空間上での線形解析手法を、特徴写像により再生核ヒルベルト空間に持ち込み、その再生核ヒルベルト空間上で、線形解析手法を適用することで、ユークリッド空間では線形分離不可能であった問題を、線形分離可能な問題に落とし込むいう点である。<br>
2. ２つ目のポイントは、この再生核ヒルベルト空間上での線形解析手法を適用する際に、再生核ヒルベルト空間が無限次元空間であるが故に、実際上計算機で計算不可能な問題が発生するが、リプレゼンター定理により、データより張られる有限次元部分空間上でのデータ解析手法に置き換えるという点である。<br>
3. ３つ目のポイントは、このリプレゼンター定理により有限次元化されたデータ解析手法において、分散共分散行列などの計算で、内積演算が必要になるケースが多々あるが、この再生核ヒルベルト空間上での内積演算を２つの特徴ベクトルの内積を計算することなく、カーネル関数で表せるという、カーネルトリックを用いて、計算負荷を削減する点にある。<br>


<a id="カーネル主成分分析"></a>

## ■ カーネル主成分分析（kernel PCA）
カーネル主成分分析は、カーネル法を用いて、線形分離不可能な問題を、より高次元の線形分離可能な再生核ヒルベルト空間持ち込んで、この再生核ヒルベルト空間内で主成分分析を行う手法であるが（下図参照）、ここでは、このカーネル主成分分析を、再生核ヒルベルト空間の概念で捉え直し、より一般的な視点で見ていく。<br>

![image](https://user-images.githubusercontent.com/25688193/49130432-3859b280-f317-11e8-8eb0-a108b14f145d.png)<br>

まず、このカーネル主成分分析の基本となる、通常の主成分分析（PCA）については、以下のページを参照。<br>

- 【参考】<br>
    - [主成分分析 [PCA : Principal Component Analysis]](http://yagami12.hatenablog.com/entry/2017/09/17/111400#ID_2-5-1)<br>

次に、カーネル主成分分析の再生核ヒルベルト空間の概念を（表立って）用いない内容については、以下のページを参照<br>

- 【参考】<br>
    - [カーネル主成分分析 [kernel PCA : kernel Principal Component Analysis]]()<br>


<a id="カーネル主成分分析の再生核ヒルベルト空間を用いた議論"></a>

### ◎ カーネル主成分分析の再生核ヒルベルト空間を用いた議論
集合 X 上の与えられたデータ ![image](https://user-images.githubusercontent.com/25688193/48967961-92aef680-f02b-11e8-8cb3-f6540e8e53cf.png) に対して、X×X 上の正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48967968-beca7780-f02b-11e8-985d-739230889e74.png) を用意し、この正定値カーネル k の組を基底として張られる再生核ヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/48967969-cf7aed80-f02b-11e8-9c70-aa8b311ce2fe.png) において、<br>

特徴写像 ![image](https://user-images.githubusercontent.com/25688193/48967978-f802e780-f02b-11e8-8fe9-3211f830fd9f.png) により、![image](https://user-images.githubusercontent.com/25688193/48967982-0fda6b80-f02c-11e8-8936-50176f09be60.png) という再生核ヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/48967969-cf7aed80-f02b-11e8-9c70-aa8b311ce2fe.png) 中のデータが生成されているようなケースを考える。<br>

カーネル主成分分析は、この再生核ヒルベルト空間内で主成分分析を行うのであるが、通常の主成分分析の際の、第１主成分の軸 ![image](https://user-images.githubusercontent.com/25688193/48967995-31d3ee00-f02c-11e8-9ee5-e18f80c2dd68.png) へのデータの射影 ![image](https://user-images.githubusercontent.com/25688193/48968000-4adc9f00-f02c-11e8-91de-884e327fded1.png) の分散値<br>
![image](https://user-images.githubusercontent.com/25688193/48968012-6e074e80-f02c-11e8-9997-780369673966.png)<br>
の最大化（＝最適化問題）<br>
![image](https://user-images.githubusercontent.com/25688193/48969533-71f29b00-f043-11e8-97dd-3bde641aebb5.png)<br>
に対応するものとして、再生核ヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/48967969-cf7aed80-f02b-11e8-9c70-aa8b311ce2fe.png) 中の主成分軸 f に対して、<br>
![image](https://user-images.githubusercontent.com/25688193/48968030-b7f03480-f02c-11e8-964d-4d9bf0a66e8d.png)<br>
を考える。<br>
※ ![image](https://user-images.githubusercontent.com/25688193/48968034-c8a0aa80-f02c-11e8-9819-81f4a707252f.png) は、主成分軸 f のデータの射影の意味合いとなっており、通常の主成分分析の内積演算 ![image](https://user-images.githubusercontent.com/25688193/48968038-d9512080-f02c-11e8-8fe5-461ae819d21d.png) に対応するものである。<br>

ここで、主成分分析は、標準化されたデータ（平均０，分散値１）で行う必要があるので、<br>
この再生核ヒルベルト空間内でのデータを中心化した<br>
![image](https://user-images.githubusercontent.com/25688193/48968108-5b414980-f02d-11e8-8857-928379874e69.png)<br>
で考える。<br>

このとき、先のリプレゼンター定理より、この最適化問題の解（＝再生核ヒルベルト空間中の関数）![image](https://user-images.githubusercontent.com/25688193/48969454-107dfc80-f042-11e8-8b63-f4e4419b2089.png) は、X×X 上の正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/48969467-520ea780-f042-11e8-928d-7840a32722df.png) から求まる ![image](https://user-images.githubusercontent.com/25688193/48969491-b3367b00-f042-11e8-948f-35810409387a.png) を用いて、<br>
![image](https://user-images.githubusercontent.com/25688193/48969496-c2b5c400-f042-11e8-9899-76a4609a1d09.png)<br>
と表現できる。<br>
即ち、第 p 主成分の軸は、<br>
![image](https://user-images.githubusercontent.com/25688193/48969554-98b0d180-f043-11e8-847d-d3e3c018037a.png)<br>
の式から求めることが出来る。<br>

更に、再生核ヒルベルト空間の再生性の条件<br>
![image](https://user-images.githubusercontent.com/25688193/48969678-45d81980-f045-11e8-9aac-c3498eb01ed1.png)<br>
を用いると、先の最適化問題の式は、<br>
![image](https://user-images.githubusercontent.com/25688193/48969681-56888f80-f045-11e8-9908-b88ac857aca2.png)<br>
という、一般化固有値問題の形に置き換えられる。（計算略）<br>

この固有方程式において、グラム行列 ![image](https://user-images.githubusercontent.com/25688193/48969745-576df100-f046-11e8-8520-6e2b4443cb71.png) の固有値を ![image](https://user-images.githubusercontent.com/25688193/48969737-3907f580-f046-11e8-896c-3515af4264c7.png) とし、対応する固有ベクトルを ![image](https://user-images.githubusercontent.com/25688193/48969779-d6fbc000-f046-11e8-81e6-b1f5ee581076.png) とし、以上の議論をまとめると、主成分 f は、以下のようにして求まる。<br>

- 第 p 主成分の軸：<br>
    ![image](https://user-images.githubusercontent.com/25688193/48969796-04e10480-f047-11e8-92e1-7443ecdde272.png)<br>

- 第 p 主成分<br>
    ![image](https://user-images.githubusercontent.com/25688193/48969801-10ccc680-f047-11e8-88a8-8cc69ce0a48e.png)<br>


<a id="正準相関分析"></a>

## ■ 正準相関分析

<a id="線形正準相関分析"></a>

### ◎ 線形正準相関分析（CCA）
> 記載中...

線形正準相関分析は、２つの多変量データを線形変換した後の、互いの相関係数が最大になるような、線形変換のパラメータを求める手法と見なすことも出来る。<br>

今、原因と結果となる２種類の多変量データ ![image](https://user-images.githubusercontent.com/25688193/48978544-31049000-f0f0-11e8-8d43-056ab7da628a.png) とし、線形変換 ![image](https://user-images.githubusercontent.com/25688193/48978590-dae41c80-f0f0-11e8-9bb8-7935637b4ba4.png) を考える。ここで、![image](https://user-images.githubusercontent.com/25688193/48978601-06ff9d80-f0f1-11e8-8e7f-978c7c22de8f.png) は、線形変換のパラメータになっており、後述の相関係数が最大になるように、正準相関分析で求めるパラメータである。<br>

この線形変換後のデータ ![image](https://user-images.githubusercontent.com/25688193/48978615-678eda80-f0f1-11e8-974c-49c3057de87b.png) に対して、共分散を各々の標準偏差で割ったものが相関係数、<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/48978617-783f5080-f0f1-11e8-8a14-4ad9aef79940.png)<br>
であるが、更に、これの最大値を、正準相関という。<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/48978625-84c3a900-f0f1-11e8-93a5-181341091b7e.png)<br>

ここで、簡単のため、<br>
２種類の多変量データ ![image](https://user-images.githubusercontent.com/25688193/48978544-31049000-f0f0-11e8-8d43-056ab7da628a.png) の平均を０とすると、この正準相関は、<br>
![image](https://user-images.githubusercontent.com/25688193/48978629-95741f00-f0f1-11e8-9fdc-7a9edc4ff2cd.png)<br>
この式において、線形変換のパラメータ ![image](https://user-images.githubusercontent.com/25688193/48978601-06ff9d80-f0f1-11e8-8e7f-978c7c22de8f.png) に対して、正の数を掛けても、分母と分子で打ち消しあうので、この最大化問題は、以下の最適化問題に置き換えられる。<br>
![image](https://user-images.githubusercontent.com/25688193/48978633-a45ad180-f0f1-11e8-90dd-35044753ede5.png)<br>

この最適化問題を解くために、ラグランジュの未定乗数法を用いると、<br>
![image](https://user-images.githubusercontent.com/25688193/48978780-71fea380-f0f4-11e8-89b0-cf878e27f526.png)<br>

![image](https://user-images.githubusercontent.com/25688193/48978785-7e82fc00-f0f4-11e8-97d1-183db1dbe8ab.png)<br>

従って、この最適化問題は、以下のような固有値問題に帰着される。<br>
![image](https://user-images.githubusercontent.com/25688193/48978788-8cd11800-f0f4-11e8-95df-207e219ac050.png)<br>

この固有値問題において、固有値に対応する固有ベクトルが、線形変換のパラメータ ![image](https://user-images.githubusercontent.com/25688193/48978601-06ff9d80-f0f1-11e8-8e7f-978c7c22de8f.png) となるが、今、求めたいのは、正準相関を最大化する線形変換のパラメータ ![image](https://user-images.githubusercontent.com/25688193/48978601-06ff9d80-f0f1-11e8-8e7f-978c7c22de8f.png) であったので、
最も大きい固有値に対応する固有ベクトルを求めれば、ここでは目的値 ![image](https://user-images.githubusercontent.com/25688193/48978601-06ff9d80-f0f1-11e8-8e7f-978c7c22de8f.png) が得られることがわかる。<br>


<a id="カーネル正準相関分析"></a>

### ◎ カーネル正準相関分析（kernel CCA）
先の線形正準相関分析がユークリッド空間上での相関分析であったのに対し、カーネル正準相関分析は、再生核ヒルベルト空間上での正準相関分析になっている。<br>

今、先の線形正準相関分析のときと同様にして、原因と結果となる２種類の多変量データ ![image](https://user-images.githubusercontent.com/25688193/48978544-31049000-f0f0-11e8-8d43-056ab7da628a.png) とする。<br>
このとき、この２種類の多変量データに対応した正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/49014229-cd976280-f1c2-11e8-9361-4b27be7082bd.png) 及び ![image](https://user-images.githubusercontent.com/25688193/49014256-e43db980-f1c2-11e8-90e0-281db10f2d10.png) を導入し、この正定値カーネルによって張られる再生核ヒルベルト空間をそれぞれ ![image](https://user-images.githubusercontent.com/25688193/49014277-f4ee2f80-f1c2-11e8-8aea-14847600ace9.png) とする。<br>
そして、元のユークリッド空間から再生核ヒルベルト空間への特徴写像 ![image](https://user-images.githubusercontent.com/25688193/49014326-1818df00-f1c3-11e8-9eb2-03dac35b020d.png) により、２つの再生核ヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/49014277-f4ee2f80-f1c2-11e8-8aea-14847600ace9.png) 上の多変量データ ![image](https://user-images.githubusercontent.com/25688193/49014787-99bd3c80-f1c4-11e8-9471-928806c1c374.png) へと写像されるケースを考える。<br>
（※２種類の多変量データ ![image](https://user-images.githubusercontent.com/25688193/48978544-31049000-f0f0-11e8-8d43-056ab7da628a.png) は、異なる種類のデータなので、特徴抽出も別の特徴写像 ![image](https://user-images.githubusercontent.com/25688193/49014396-57473000-f1c3-11e8-82e2-15f04572cd5b.png) で行う。）

その上で、先の線形正準相関分析のときと同様にして、この再生核ヒルベルト空間内での線形変換後のデータ ![image](https://user-images.githubusercontent.com/25688193/49016865-b8263680-f1ca-11e8-98eb-d07c0fbddde6.png) に対して、後述の相関係数（＝正準相関）が最大になるように、この線形変換のパラメーター ![image](https://user-images.githubusercontent.com/25688193/49014515-bdcc4e00-f1c3-11e8-9eb4-fdef0477b07e.png) を求めることを考える。<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/49014929-fd476a00-f1c4-11e8-958e-2c1f76f2cbdc.png)<br>

ここで、簡単のため、この再生核ヒルベルト空間内でのデータ点を中心化（＝平均０）した<br>
![image](https://user-images.githubusercontent.com/25688193/49017379-143d8a80-f1cc-11e8-8f8a-1c548613d49d.png)<br>
で考えると、この正準相関は、以下のように書き換えられる。<br>
![image](https://user-images.githubusercontent.com/25688193/49017415-23bcd380-f1cc-11e8-8242-46e28312612c.png)<br>

より一般的には、パラメーター ![image](https://user-images.githubusercontent.com/25688193/49014515-bdcc4e00-f1c3-11e8-9eb4-fdef0477b07e.png) による線形変換に対応した再生核ヒルベルト空間の要素（関数） ![image](https://user-images.githubusercontent.com/25688193/49017460-3df6b180-f1cc-11e8-8159-7075f670888a.png) と再生核ヒルベルト空間中の内積を用いて表現すると、この正準相関は、以下のように書き換えられる。<br>
![image](https://user-images.githubusercontent.com/25688193/49017484-4ea72780-f1cc-11e8-8d24-17fd63283d70.png)<br>

ここで、リプレゼンター定理より、この最適化問題の解（＝再生核ヒルベルト空間中の関数）![image](https://user-images.githubusercontent.com/25688193/49017460-3df6b180-f1cc-11e8-8159-7075f670888a.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/49017661-c1180780-f1cc-11e8-8000-d08e91db32e5.png)<br>
のような有限次元の級数展開の式で表現できるが、これを元の正準相関の式に代入すると、以下のように変形できる。（途中計算略）<br>
![image](https://user-images.githubusercontent.com/25688193/49023355-65ed1180-f1da-11e8-8109-a6ce3ccdf6fd.png)<br>

ここで、この最適化問題の定性的な議論として、再生核ヒルベルト空間という関数の自由度が高すぎる空間での最適化、より詳細には、サンプル数に対して、パラメーター数が多すぎる最適化となっているために、過学習が発生してしまい、その結果として、相関係数が１になるような意味のないパラメーター ![image](https://user-images.githubusercontent.com/25688193/49014515-bdcc4e00-f1c3-11e8-9eb4-fdef0477b07e.png) の解が求まってしまうという問題がある。<br>

この過学習を回避するために、目的関数に対して正則化項を付け加えることを考える。<br>
即ち、以下のような正則化項付きの最適化問題を考える。<br>
![image](https://user-images.githubusercontent.com/25688193/49025440-05140800-f1df-11e8-8199-f4b449bcf74f.png)<br>

先と同様にして、関数 f,g をレプリゼンター定理にもとづく級数展開式、及び、グラム行列 K で書き換えると、<br>
![image](https://user-images.githubusercontent.com/25688193/49025504-2e349880-f1df-11e8-8e8c-7d0fe949f1c2.png)<br>

この最適化問題を解くために、線形正準相関分析のときと同様にして、ラグランジュの未定乗数法を用いて変形すると、最終的に、この最適化問題は、以下のような固有値問題に帰着される。<br>
![image](https://user-images.githubusercontent.com/25688193/49025528-3db3e180-f1df-11e8-86b4-9b7a6bce5451.png)<br>

この固有方程式において、固有値 ρ が正準相関係数に対応するので、最も大きい値となる固有値 ![image](https://user-images.githubusercontent.com/25688193/49025570-558b6580-f1df-11e8-835e-d46ae3fc7a36.png) に対応する固有ベクトルが、求めるべきパラメーター ![image](https://user-images.githubusercontent.com/25688193/49025621-6a67f900-f1df-11e8-9441-36d7e3a2c096.png) となる。<br>


<a id="サポートベクターマシン（SVM）"></a>

## ■ サポートベクターマシン（SVM）
サポートベクターマシンは、カーネル法を利用したパターン認識アルゴリズムの１つであるが、主に、以下のような特徴がある。<br>

- マージン最大化を行う線形識別器：<br>
    ![image](https://user-images.githubusercontent.com/25688193/49068898-481bbd00-f26b-11e8-9eea-c5d2dec5bf75.png)<br>
    サポートベクターマシンは、線形識別器の１種であるが、マージンと呼ばれる線形識別器（＝分離超平面になる）からのノイズを取り除くための余白領域を最大化するように、線形識別器（＝ハードマージンSVM）を構成する。（上図参照）<br>
    そして、このマージン最大化は、最適化問題として定式化される。<br>

- カーネル法とカーネルトリック、リプレゼンター定理（カーネル化）：<br>
    ![image](https://user-images.githubusercontent.com/25688193/49068931-5a95f680-f26b-11e8-8347-eb67fa17ddf8.png)<br>
    サポートベクターマシンでも他のカーネル法と同様にして、ユークリッド空間において線形分離不可能な問題を、より高次元の再生核ヒルベルト空間内での線形識別問題に置き換える。（上図参照）<br>
	そして、リプレゼンター定理により、再生核ヒルベルト空間という無限次元空間での最適化問題が、サンプル数に応じた有限次元空間での最適化問題に置き換えられる。<br>
    更に、カーネルトリックにより、有限次元である２つの特徴ベクトルの内積演算をカーネル関数で計算可能とする。<br>

- サポートベクトルとスパーズ性：<br>
    ![image](https://user-images.githubusercontent.com/25688193/49068954-6a153f80-f26b-11e8-9ea1-2fcf8f95201d.png)<br>
    先のリプレゼンター定理により、無限次元である再生核ヒルベルト空間内での最適化問題は、有限次元の最適化問題に置き換えられることが出来た。<br>
    しかしながら、サンプル数が膨大な場合、依然として、計算が困難であるという問題は残る。<br>
    サポートベクターマシンでは、全サンプル数の内、サポートベクトルと呼ばれる分離超平面付近のサンプルのみを利用して識別を行うというスパーズな表現になっており、結果として、計算量やメモリの節約が出来るというメリットが存在する。<br>

- 損失関数の正則化（ソフトマージンとハードマージン）：<br>
    > 記載中...<br>

<br>

> 【Memo】サポートベクターマシンの定式化スタイル<br>
> サポートベクターマシンの定式化は、マージン最大化を実現する線形識別器（ハードマージン）→スラッグ変数の導入しての正則化（ソフトマージン）→最適化問題への置き換え→・・・という順に議論していくスタイルが基本であるが、直接ヒンジ損失関数の正則化の議論から定式化する方法もある。<br>
> 赤穂「カーネル多変量解析」の本では後者で話を展開している。<br>

> ソフトマージンSVMの最適化問題が、ヒンジ損失関数の和と正則化項を目的関数とする制約条件のない最適化問題に置き換えられるので、サポートベクターマシンは、最小２乗誤差関数ではなく、ヒンジ損失関数を損失関数とするカーネル２乗推定法であるとも言え、これはつまり、ヒンジ損失関数の議論からもサポートベクターマシンを定式化出来ることを意味している。<br>


<a id="ハードマージンSVM（マージン最大化を実現する線形識別器）"></a>

### ◎ ハードマージンSVM（マージン最大化を実現する線形識別器）
前述のように、サポートベクターマシンは、マージン最大化を実現する線形識別器であり、このマージン最大化の問題は、最適化問題として定式化される。<br>
以下このことの詳細を見ていく。<br>

d 次元のユークリッド空間 ![image](https://user-images.githubusercontent.com/25688193/49069031-97fa8400-f26b-11e8-9d3a-fdf5835e93af.png) において、以下のような教師データ付きの学習データの集合 ![image](https://user-images.githubusercontent.com/25688193/49069060-b06a9e80-f26b-11e8-8fdc-85ed908067bd.png) が与えられたケースを考える。<br>
![image](https://user-images.githubusercontent.com/25688193/49069085-c11b1480-f26b-11e8-89e4-b1c47a7a362d.png)<br>

このとき、上図のように、線形識別器の関数 ![image](https://user-images.githubusercontent.com/25688193/49069152-e4de5a80-f26b-11e8-8185-733b7a036306.png) のマージンを h>0 に設定すると、全ての学習データ ![image](https://user-images.githubusercontent.com/25688193/49069203-fd4e7500-f26b-11e8-9ecc-faf9589ba51f.png) に対して、このマージン分 h だけ離れた値の関係<br>
![image](https://user-images.githubusercontent.com/25688193/49069222-0e978180-f26c-11e8-9d78-7a1d0c940029.png)<br>
が成り立つ。<br>
両辺を h で割って、線形識別関数の係数ベクトルとバイアス項を正規化し、それらを同じ記号で表記すると、<br>
![image](https://user-images.githubusercontent.com/25688193/49069241-1eaf6100-f26c-11e8-9e5c-e501061e88b3.png)<br>

ここで、上図のように、クラス間マージン ρ は、正負のクラスのデータを、重みの係数ベクトル ![image](https://user-images.githubusercontent.com/25688193/49069279-3ab30280-f26c-11e8-900c-2e716e2d2f9c.png)（＝分離超平面の法線ベクトル）の方向へ直交射影した長さの差の最小値で与えられる。<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/49069305-4e5e6900-f26c-11e8-9ac1-0e264b46693e.png)<br>

マージン最大化を実現する最適な分離超平面の式を<br>
![image](https://user-images.githubusercontent.com/25688193/49069359-6df59180-f26c-11e8-8d15-1a7f1de309f9.png)<br>
とすると、この超平面は、最大クラス間マージン<br>
![image](https://user-images.githubusercontent.com/25688193/49069388-81a0f800-f26c-11e8-90e2-a7407f07f88b.png)<br>
を与えるので、ここでの目的であった最大化マージンは、以下のように書けることがわかる。<br>
![image](https://user-images.githubusercontent.com/25688193/49069441-9b423f80-f26c-11e8-8995-5d52a6be734b.png)<br>

ここで、バイアス項 b は定数なので、マージンを最大化、即ち ![image](https://user-images.githubusercontent.com/25688193/49069513-c6c52a00-f26c-11e8-99b0-293731823084.png) とする分離超平面 ![image](https://user-images.githubusercontent.com/25688193/49069550-de9cae00-f26c-11e8-926c-a6cfdd57d262.png) は、先の制約条件 ![image](https://user-images.githubusercontent.com/25688193/49069587-f116e780-f26c-11e8-8887-516045a3b988.png) のもとでの、係数ベクトル ![image](https://user-images.githubusercontent.com/25688193/49069619-0d1a8900-f26d-11e8-95ff-378bdf4aa009.png) を最小化する解、即ち、以下のような２次凸最適化問題の解として定式化される。<br>
![image](https://user-images.githubusercontent.com/25688193/49069646-202d5900-f26d-11e8-86c1-d6cb00d22c42.png)<br>

そして、このような最適化問題による識別関数を、ハードマージンSVMという。<br>
（※このハードマージンSVMという言葉は、後述の正則化項も考えたソフトマージンSVMとの対比から）<br>

ここで、この最適化問題に寄与する学習データは、上図のように、<br>
正のクラスに属する分離超平面近くにあるベクトル（＝サポートベクトルという）![image](https://user-images.githubusercontent.com/25688193/49069711-4eab3400-f26d-11e8-86c5-df55fbfa3ef6.png) と
負のクラスに属する分離超平面近くにあるベクトル（＝サポートベクトルという）![image](https://user-images.githubusercontent.com/25688193/49069746-61be0400-f26d-11e8-83ba-f26563afa2ff.png) のみである。<br>
（言い換えると、これらのサポートベクトルによって、マージン h がマージン最大化される。）<br>

つまり、N 個の学習データの内、一部のサンプルしか利用していないスパーズな表現となっており、その結果として、計算量やメモリの消費の節約が行える。<br>


<a id="ソフトマージンSVM（スラッグ変数の導入と正則化）"></a>

### ◎ ソフトマージンSVM（スラッグ変数の導入と正則化）
先のハードマージンSVMの最適化問題<br>
![image](https://user-images.githubusercontent.com/25688193/49089067-09ebc100-f29e-11e8-9653-1f40d680c16b.png)<br>
において、<br>
制約条件 ![image](https://user-images.githubusercontent.com/25688193/49089096-1d972780-f29e-11e8-9c90-51582a99ed36.png) は、線形分離可能性の条件になっているが、線形分離不可能な系においては、この最適化問題の解が存在しないことになってしまう。<br>

そこで、制限の緩和を考える。<br>
具体的には、スラック変数 ξ なるものを導入することにより、線形分離不可能な系においても、最適化問題の制約条件を満たすような解が存在するようにする。<br>
即ち、制約条件は、このスラック変数を用いて、以下のように置き換わる。<br>
![image](https://user-images.githubusercontent.com/25688193/49089158-428b9a80-f29e-11e8-8444-c65f5fbd519c.png)<br>

このスラック変数の導入による効果は、以下の図のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/49089220-67800d80-f29e-11e8-9631-b313662d4cda.png)<br>

ここで、スラック変数の値はデータの分布に応じて、以下のような意味を持つ。（上図参照）<br>

- ![image](https://user-images.githubusercontent.com/25688193/49129593-b6b45580-f313-11e8-8167-78680c7a1e30.png)：設定したマージンで、正と負のクラスのデータが正しく識別できている。<br>
- ![image](https://user-images.githubusercontent.com/25688193/49129619-cd5aac80-f313-11e8-877a-d16358440ce8.png)：設定したマージンを超えているが、識別境界は超えておらず、正と負のクラスのデータを正しく識別できている。<br>
- ![image](https://user-images.githubusercontent.com/25688193/49129631-dd728c00-f313-11e8-98d2-02775397ce37.png)：設定したマージンを超えており、識別境界も超えているので、正と負のクラスのデータを正しく識別できていない。<br>

このように、スラック変数は、データがうまく分類できていない度合いを表すパラメーターになっているので、損失関数の正則化項として利用することが出来る。<br>
即ち、先の正則化なしの最適化問題を、以下のような正則化項ありの最適化問題に変更することが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/49140667-33f1c180-f338-11e8-8759-54d4bafde06e.png)<br>

ここで、正則化項の係数（パラメーター）C は、誤識別数に対するペナルティーの強さを表しており、値が大きいほど、係数ベクトルのノルム ![image](https://user-images.githubusercontent.com/25688193/49129747-46f29a80-f314-11e8-822c-3680cc7c108c.png) の最小値（＝マージン最大化 ![image](https://user-images.githubusercontent.com/25688193/49129769-6984b380-f314-11e8-8e75-785c162d79fc.png) ）よりも、誤識別数を小さくする解が得られる。<br>

このようなパラメーター C による正則化項付きの最適化問題の解による識別関数を、ソフトマージンSVM、或いは、C-SVM と呼ぶ。<br>
※ この最適化問題の正則化パラメーターは、１つのパラメーターCのみであることに注目。<br>
※ 最適なパラメーター C の値は、クロスバリデーションなどで問題に応じて検討する必要がある。<br>


<a id="ヒンジ損失関数を用いた正則化法としてのSVM"></a>

### ◎ ヒンジ損失関数を用いた正則化法としての SVM
先に導出した、ソフトマージンSVMの最適化問題<br>
![image](https://user-images.githubusercontent.com/25688193/49140725-58e63480-f338-11e8-9dce-a56ff8888931.png)<br>
は、目的関数をヒンジ損失関数の和と正則化項とするような制約条件のない最適化問題に置き換えることが出来る。以下、そのことを見ていく。<br>

まず、![image](https://user-images.githubusercontent.com/25688193/49140762-77e4c680-f338-11e8-84eb-b9747a6d0e28.png) なる関数ものを導入すると、ソフトマージンSVMの最適化問題の制約条件は、![image](https://user-images.githubusercontent.com/25688193/49140822-98148580-f338-11e8-8ca7-cec2addc477f.png)と書き換えられので、λ=1/C とおくと、最適化問題は<br>
![image](https://user-images.githubusercontent.com/25688193/49140866-ad89af80-f338-11e8-97cf-a791683e8412.png)<br>

ここで、このスラック変数 ![image](https://user-images.githubusercontent.com/25688193/49140920-c5f9ca00-f338-11e8-966e-d9cd86545569.png) に対する最適化問題 ![image](https://user-images.githubusercontent.com/25688193/49140956-db6ef400-f338-11e8-981e-a3dc6fd18181.png) は、![image](https://user-images.githubusercontent.com/25688193/49140996-f6416880-f338-11e8-84b9-1747073ce5df.png) のとき達成されるので、この最適化問題は、以下のような制約条件のない最適化問題に置き換えることが出来る。<br>
![image](https://user-images.githubusercontent.com/25688193/49141042-0d805600-f339-11e8-82e7-ea3a2857c9b2.png)<br>

この最適化問題における目的関数は、ヒンジ損失関数 ![image](https://user-images.githubusercontent.com/25688193/49141111-33a5f600-f339-11e8-8e87-45f635645cb4.png) を導入すると、<br>
![image](https://user-images.githubusercontent.com/25688193/49141153-4b7d7a00-f339-11e8-8117-6470e19806b7.png)<br>
と書き換えられ、ヒンジ損失関数の和と正則化項を目的関数とする最適化問となっていることが分かる。<br>

それ故に、サポートベクターマシンは、（カーネル２乗推定法において、）最小２乗誤差関数ではなく、ヒンジ損失関数を損失関数とするカーネル２乗推定法であるとも言える。<br>
（※ これはつまり、ヒンジ損失関数の議論からもサポートベクターマシンを定式化出来ることを意味している。）<br>


<a id="マージン最大化を実現する線形識別器のカーネル化"></a>

### ◎ マージン最大化を実現する線形識別器のカーネル化
ここまでのSVMは、ユークリッド空間上でマージン最大化を実現する線形識別器であったが、これをカーネル化、即ち、以下の図のように、特徴写像により、ユークリッド空間から再生核ヒルベルト空間へという、より高次元でデータを線形分離可能な空間へと写像し、この再生核ヒルベルト空間内で、線形識別を行う。<br>
※ 一般的に、SVMというと、このカーネル化も含めてSVMという。<br>
![image](https://user-images.githubusercontent.com/25688193/49141210-75cf3780-f339-11e8-9f27-0aac31e9aa63.png)<br>

- X : 可測集合<br>
- ![image](https://user-images.githubusercontent.com/25688193/49141558-36edb180-f33a-11e8-936b-37d29efb23bb.png) : X 上の正定値カーネル<br>
- ![image](https://user-images.githubusercontent.com/25688193/49141678-7ddba700-f33a-11e8-9228-89eca507c4ae.png) : この正定値カーネル ![image](https://user-images.githubusercontent.com/25688193/49141644-67cde680-f33a-11e8-8322-66cecb3585bd.png) の組を基底として張られる再生核ヒルベルト空間<br>
- ![image](https://user-images.githubusercontent.com/25688193/49141704-8df38680-f33a-11e8-9825-18f8290f0c90.png) : 特徴写像 ![image](https://user-images.githubusercontent.com/25688193/49141738-a368b080-f33a-11e8-93b9-0a1c7e085f04.png)<br>

とする。<br>
このとき、再生核ヒルベルト空間内での線形識別関数は、<br>
![image](https://user-images.githubusercontent.com/25688193/49141793-c5623300-f33a-11e8-9b58-1edf7c4c83fb.png)<br>
従って、先のユークリッド空間内でのソフトマージンSVMの最適化問題<br>
![image](https://user-images.githubusercontent.com/25688193/49141821-d6ab3f80-f33a-11e8-8738-cedd9abe67a0.png)<br>
は、この再生核ヒルベルト空間内では、以下のように置き換わる。<br>
![image](https://user-images.githubusercontent.com/25688193/49141860-ef1b5a00-f33a-11e8-9303-5aa9da61b828.png)<br>

或いは、同様の意味だがヒンジ損失関数 L を用いて、<br>
![image](https://user-images.githubusercontent.com/25688193/49141973-24c04300-f33b-11e8-832f-e0e000a1a1c2.png)<br>

この最適化問題は、再生核ヒルベルト空間が無限次元空間であるために、計算機で具体的に計算可能ではないという問題がある。<br>
従って、リプレゼンター定理を適用する。<br>
即ち、ユークリッド空間での重みベクトル ![image](https://user-images.githubusercontent.com/25688193/49142032-3f92b780-f33b-11e8-9cf6-c276a84268b9.png) に対応する再生核ヒルベルト空間中の関数 ![image](https://user-images.githubusercontent.com/25688193/49142092-5e914980-f33b-11e8-8be0-a3eeddcd072e.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/49142115-6e109280-f33b-11e8-8b46-5e08372de567.png)<br>
と表現できるので、更に、カーネルトリック ![image](https://user-images.githubusercontent.com/25688193/49142357-eaa37100-f33b-11e8-9eaf-c23a9cfb01ce.png) も使用すると、<br>
![image](https://user-images.githubusercontent.com/25688193/49142140-7e287200-f33b-11e8-8707-3cee00e588f8.png)<br>
となり、元の再生核ヒルベルト空間における最適化問題は、<br>
![image](https://user-images.githubusercontent.com/25688193/49142229-a617d580-f33b-11e8-8916-1edda786cfbc.png)<br>
のようなデータ数 N に応じた有限次元での最適化問題に書き換えられる。<br>


<a id="SVMの最適化問題の解法"></a>

### ◎ SVM の最適化問題の解法
> 記載中...



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

- パターン認識と機械学習 下<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98%E3%81%A8%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92-%E4%B8%8B-%E3%83%99%E3%82%A4%E3%82%BA%E7%90%86%E8%AB%96%E3%81%AB%E3%82%88%E3%82%8B%E7%B5%B1%E8%A8%88%E7%9A%84%E4%BA%88%E6%B8%AC-C-M-%E3%83%93%E3%82%B7%E3%83%A7%E3%83%83%E3%83%97/dp/4621061240/ref=pd_lpo_sbs_14_t_1?_encoding=UTF8&psc=1&refRID=K2ESPX1T44YFERG3T27T)
    - いわずと知れた機械学習の定番書。6章にカーネル法、7章にサポートベクターマシン、12章にカーネル主成分分析の説明がある。<br>

- はじめてのパターン認識<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)<br>
    - 「パターン認識と機械学習」の内容がコンパクトにまとまっていて分かりやすい。

- サポートベクターマシン入門<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%83%99%E3%82%AF%E3%82%BF%E3%83%BC%E3%83%9E%E3%82%B7%E3%83%B3%E5%85%A5%E9%96%80-%E3%83%8D%E3%83%AD-%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%86%E3%82%A3%E3%82%A2%E3%83%8B%E3%83%BC%E3%83%8B/dp/4320121341?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320121341)<br>
    - 原書は英語の本。カーネル法の1種であるSVMのみのタイトルだが、3章のカーネル誘導特徴空間の章で、より一般的な、正定値カーネル、再生核ヒルベルト空間の理論的な説明。及び、マーセルの定理の説明。
    加えて、カーネルとガウス過程の話がある。更に（カーネル法の話題からは話が逸れる？が）4章の汎化理論で、PAC学習、VC理論（※これらに関しては全然知らない）の説明もある。<br>

- 機械学習のエッセンス -実装しながら学ぶPython,数学,アルゴリズム- (Machine Learning)<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%81%AE%E3%82%A8%E3%83%83%E3%82%BB%E3%83%B3%E3%82%B9-%E5%AE%9F%E8%A3%85%E3%81%97%E3%81%AA%E3%81%8C%E3%82%89%E5%AD%A6%E3%81%B6Python-%E3%82%A2%E3%83%AB%E3%82%B4%E3%83%AA%E3%82%BA%E3%83%A0-Machine-Learning/dp/4797393963/ref=sr_1_1?ie=UTF8&qid=1541355307&sr=8-1&keywords=%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%81%AE%E3%82%A8%E3%83%83%E3%82%BB%E3%83%B3%E3%82%B9)
    - 5-7章にカーネル法の1種であるSVMのアルゴリズムを構成するマージン最大化と最適化問題の丁寧な式変形での解説と、scikit-learn などの機械学習フレームワークを使用せず、numpyだけを使用したPythonでのスクラッチ実装コードとその丁寧なコード説明がある。<br>

- 数学セミナー12月号<br>
    - [数学セミナー2018年12月号｜日本評論社](https://www.nippyo.co.jp/shop/magazines/latest/4.html)<br>
    - 連載特集に機械学習の数理として、カーネル法とニューラルネットワークの関連性について書かれた記事がある。

<a id="使用コード"></a>

### ◎ 使用コード
この記事で使われている一部の図や解析内容のコードは、以下の場所に置いてあります。参考までに<br>

- サポートベクターマシン（SVM）<br>
    - [GitHub/Yagami360/MachineLearning_Exercises_Python_scikit-learn/SVM_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/SVM_scikit-learn)<br>

- カーネル主成分分析<br>
    - [GitHub/Yagami360/MachineLearning_Exercises_Python_scikit-learn/kernelPCA_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/kernelPCA_scikit-learn)

