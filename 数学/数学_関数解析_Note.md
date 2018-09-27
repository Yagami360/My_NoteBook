# 関数解析
関数解析の基本事項を記載したマイノートです。随時追記中。<br>

## 目次 [Contents]

1. [概要](#ID_1)
1. 位相空間
1. ハウスドルフ空間
1. [線形空間（ベクトル空間）](#ID_2)
    1. [張る（生成する）](#ID_2-1)
    1. [線形独立（一次独立）と線形従属（一次従属）](#ID_2-2)
        1. [線形独立（一次独立）と線形従属（一次従属）の幾何学的イメージ](#ID_2-2-1)    
    1. [基底ベクトル](#ID_2-3)
    1. [ベクトルの次元](#ID_2-4)
1. [点列の収束と極限](#ID_3)
    1. [点列の収束と極限に関する有用な性質](#ID_3-1)
    1. [上極限と下極限](#ID_3-2)
1. [距離空間](#ID_4)
    1. [距離空間の例](#ID_4-1)
    1. [距離空間における収束、極限とコーシー列（基本列）](#ID_4-2)
    1. [完備距離空間](#ID_4-3)
        1. [完備距離空間の例](#ID_4-3-1)
        1. 【補足】開集合、閉集合
        1. [写像の連続性](#ID_4-3-3)
        1. [コンパクト集合](#ID_4-3-4)
        1. [縮小写像の不動点定理](#ID_4-3-5)
        1. [ベールの定理](#ID_4-3-6)
        1. [稠密 [dense]、可分性 [separable]](#ID_4-3-7)
1. [ノルム空間](#ID_5)
    1. [ノルム空間の例](#ID_5-1)
    1. [ノルム空間における収束、極限とコーシー列（基本列）](#ID_5-2)
    1. [ノルム空間における完備性](#ID_5-3)
    1. [ノルム空間における写像の連続性](#ID_5-4)
    1. [ノルムの等価性](#ID_5-5)
    1. [ノルム空間における閉部分空間、線形多様体、閉凸集合](#ID_5-6)
    1. [ノルム空間上での写像の微分（ガトー微分とフレッシェ微分）](#ID_5-7)
        1. [ガトー微分](#ID_5-7-1)
        1. [フレッシェ微分](#ID_5-7-2)
        1. [ガトー微分とフレッシェ微分の性質](#ID_5-7-3)
        1. [ガトー微分とフレッシェ微分の例](#ID_5-7-4)
1. [内積空間](#ID_6)
    1. [内積空間におけるベクトルの直交性](#ID_6-1)
    1. [内積空間の性質と内積から誘導されるノルム](#ID_6-2)
    1. [内積空間における正規直交系](#ID_6-3)
        1. [グラム・シュミットの直交化法](#ID_6-3-1)
        1. [ベッセルの不等式](#ID_6-3-2)
1. [バナッハ空間 [Banach space]](#ID_7)
    1. [バナッハ空間の例](#ID_7-1)
    1. [有界線形写像全体の集合が作るバナッハ空間と共役空間](#ID_7-2)
    1. [一様有界性の定理](#ID_7-3)
    1. [開写像定理](#ID_7-4)
    1. [閉グラフ定理](#ID_7-5)
    1. [バナッハ空間における基底（シャウダー基底）](#ID_7-6)
1. [ヒルベルト空間 [Hilbert space]](#ID_8)
    1. [ヒルベルト空間の例](#ID_8-1)
    1. ヒルベルト空間における三平方の定理、中線定理
    1. [自己共役作用素（エルミート作用素）と有界性＜閉グラフ定理の応用＞](#ID_8-3)
    1. [ヒルベルト空間における正規直交系とフーリエ級数](#ID_8-4)
    1. [ヒルベルト空間における極大な正規直交系](#ID_8-5)
    1. [可分なヒルベルト空間と完全正規直交系](#ID_8-6)
        1. [ヒルベルト空間における完全正規直交系の例](#ID_8-6-1)
    1. [ヒルベルト空間における強収束と弱収束](#ID_8-7)
1. [ヒルベルト空間と射影定理](#ID_B)
    1. [ヒルベルト空間における凸射影定理と直交射影定理](#ID_B-1)
        1. [ヒルベルト空間における凸射影の非拡大性](#ID_B-1-1)
        1. [ヒルベルト空間における直交分解](#ID_B-1-2)
        1. [ヒルベルト空間の閉部分空間への直交射影の線形性・冪等性・自己共役性](#ID_B-1-3)
        1. [ヒルベルト空間における和空間への直交射影](#ID_B-1-4)
    1. [ヒルベルト空間における線形多様体への直交射影と正規方程式](#ID_B-2)
        1. [ヒルベルト空間における直交射影と正規方程式・グラム行列](#ID_B-2-1)
        1. [ヒルベルト空間における線形多様体への直交写像と最小ノルム点](#ID_B-2-2)
        1. [ヒルベルト空間における等式線形制約条件下での線形方程式の解集合と線形多様体への射影](#ID_B-2-3)
1. [作用素](#ID_A)
    1. 線形作用素
    1. [ノルム空間における有界線形作用素](#ID_A-2)
        1. [作用素ノルム](#ID_A-2-1)
        1. [有界線形汎関数](#ID_A-2-2)
        1. [線形写像の連続性](#ID_A-2-3)
        1. [【補足】逆写像の存在性](#ID_A-2-4)
        1. [有界線形写像全体が作るノルム空間](#ID_A-2-5)
        1. [行列の作用素ノルム](#ID_A-2-6)
    1. [ムーア・ペンローズの一般化逆写像](#ID_A-3)
        1. [ムーア・ペンローズの一般化逆写像の特異値分解表現](#ID_A-3-1)
            1. 【補足】特異値分解
    1. [リースの表現定理](#ID_A-4)
    1. [内積空間中の線形汎関数の表現](#ID_A-5)
    1. [ハーン・バナッハの定理](#ID_A-6)
    1. [有界線形作用素の共役作用素](#ID_A-7)
        1. [共役作用素の行列表現（表現行列）](#ID_A-7-1)
    1. [自己共役作用素（エルミート作用素）](#ID_A-8)
    1. コンパクト作用素
1. [凸最適化理論への応用](#ID_C)
    1. [ヒルベルト空間における弱点列コンパクト性と凸集合](#ID_C-1)
    1. [ヒルベルト空間における凸関数と基本性質](#ID_C-2)
    1. [ヒルベルト空間における凸関数の最小値の存在性](#ID_C-3)
    1. [凸関数の微分の単調性](#ID_C-4)
    1. [凸最適化問題と変分不等式問題と不動点問題](#ID_C-5)
    1. [射影勾配法](#ID_C-6)
    1. [射影勾配法の一般化](#ID_C-7)
        1. [Mann の不動点近似定理と射影勾配法の弱収束定理](#ID_C-7-1)
        1. [射影 Landweber 法](#ID_C-7-2)
        1. [並列射影法](#ID_C-7-3)
        1. ハイブリッド最急降下法
        1. アンカー法
1. スペクトル理論への応用
    1. レゾルベント集合
    1. コンパクト作用素のスペクトル理論
1. 機械学習への応用
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## ■ 概要
![image](https://user-images.githubusercontent.com/25688193/45209187-44f5de00-b2c7-11e8-8848-f4f064c81b99.png)<br>

<!--
![image](https://user-images.githubusercontent.com/25688193/44618903-c3ab4e00-a8b9-11e8-8426-59eda8f1af4a.png)<br>
-->

---

<a id="ID_2"></a>

## ■ 線形空間（ベクトル空間）
![image](https://user-images.githubusercontent.com/25688193/44356650-e40a8f80-a4ea-11e8-8401-40d46d43542a.png)<br>

- （例）<br>
    １階の線形微分方程式<br>
    ![image](https://user-images.githubusercontent.com/25688193/44380172-d124a900-a544-11e8-93d9-0f34dac15bec.png)<br>
    において、方程式の解（ベクトル）<br>
    ![image](https://user-images.githubusercontent.com/25688193/44380222-03cea180-a545-11e8-8ef5-f24a5abc5996.png)<br>
    のすべてからなる集合 V はベクトル空間であることを示す。<br>
    <br>
	- １階の線形微分方程式の解 ![image](https://user-images.githubusercontent.com/25688193/44384028-b7d82880-a555-11e8-9d88-7d0f64fc95a6.png) に対して、公理 (1),(2),(7),(8) は自明に成り立つ。<br>
	また、【定理１】より (5),(6) も成り立つ。<br>
    公理 (3) は、![image](https://user-images.githubusercontent.com/25688193/44384118-084f8600-a556-11e8-9dcd-cde4884ed788.png) に対して、![image](https://user-images.githubusercontent.com/25688193/44384210-61b7b500-a556-11e8-8c6f-65f5c606f41c.png)<br>
    公理 (4) は、![image](https://user-images.githubusercontent.com/25688193/44384499-5a44db80-a557-11e8-964a-d60c4c174b52.png) とすると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44384542-7fd1e500-a557-11e8-8bf2-358cd892d0f5.png)<br>
    つまり、![image](https://user-images.githubusercontent.com/25688193/44384499-5a44db80-a557-11e8-964a-d60c4c174b52.png) は、この微分方程式の解であり、集合 V に含まれるので成り立つ。（公理(4)を満たす）<br>
    よって、１階の線形微分方程式の解全体の集合はベクトル空間となる。<br>

<a id="ID_2-1"></a>

### ◎ 張る（生成する）
![image](https://user-images.githubusercontent.com/25688193/44385335-0b4c7580-a55a-11e8-8b6a-25c436815b9d.png)<br>

- （例）実数空間を張る（生成する）<br>
    n 次元実数空間を ![image](https://user-images.githubusercontent.com/25688193/44386510-aabf3780-a55d-11e8-96c3-e0d07161078c.png) とし、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44386547-c0ccf800-a55d-11e8-9299-7f4b0c8837b6.png)<br>
    とする。<br>
    このとき、![image](https://user-images.githubusercontent.com/25688193/44386590-e0642080-a55d-11e8-8503-46bea93f6a93.png) の任意の ![image](https://user-images.githubusercontent.com/25688193/44386621-fffb4900-a55d-11e8-99f0-d4ac9ce5a860.png) は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44388424-0cce6b80-a563-11e8-87a1-0f4af15834b3.png)<br>
    と書けるので、これらのベクトル ![image](https://user-images.githubusercontent.com/25688193/44388482-28d20d00-a563-11e8-901e-d03342fa0f7b.png) は、n 次元実数空間 ![image](https://user-images.githubusercontent.com/25688193/44388520-3d160a00-a563-11e8-9d95-529dada1360a.png) を張る（生成する）。<br>


<a id="ID_2-2"></a>

### ◎ 線形独立（一次独立）と線形従属（一次従属）
![image](https://user-images.githubusercontent.com/25688193/44389280-6041b900-a565-11e8-9fdf-c8e9e6d3db3b.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44393396-84a29300-a56f-11e8-97a2-7edf617efd01.png)<br>

- （例）<br>
    ベクトル空間として、３次元実数空間 ![image](https://user-images.githubusercontent.com/25688193/44393805-9d5f7880-a570-11e8-879c-d75dcebf965b.png) を考え、この空間内のベクトル<br>
    ![image](https://user-images.githubusercontent.com/25688193/44393695-5bcecd80-a570-11e8-9595-f2204b1af3d1.png)<br>
    のベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44393768-8456c780-a570-11e8-9695-43aad8df20d0.png) が線形従属か線形独立かを調べる。<br>

    - ベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44393768-8456c780-a570-11e8-9695-43aad8df20d0.png) が線形従属か線形独立かを調べるために、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44394448-2dea8880-a572-11e8-8231-c18875f04b9d.png) を書き下してみると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44394613-9b96b480-a572-11e8-8c5d-8e571c6314a2.png)<br>
    ② 式より、![image](https://user-images.githubusercontent.com/25688193/44394965-7bb3c080-a573-11e8-833f-6883df4a5fdb.png)<br>
	よって、![image](https://user-images.githubusercontent.com/25688193/44395002-90905400-a573-11e8-81b7-457afdbe0403.png)<br>
	よって、例えば ![image](https://user-images.githubusercontent.com/25688193/44395161-08f71500-a574-11e8-82e6-293f18356a53.png) ならば c_3=1,c_1=−2 となり、![image](https://user-images.githubusercontent.com/25688193/44395196-1a402180-a574-11e8-8fe9-06bb7bc63a27.png) なので、<br>
    このベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44395223-2af09780-a574-11e8-8ddc-d76d1e4edcd9.png) は、線形従属である。<br>


<a id="ID_2-2-1"></a>

#### ☆ 線形独立（一次独立）と線形従属（一次従属）の幾何学的イメージ
例えば、以下のような３つのベクトルを考える。<br>
![image](https://user-images.githubusercontent.com/25688193/44440453-17404200-a603-11e8-82da-66281cf26f6b.png)<br>
![image](https://user-images.githubusercontent.com/25688193/44440472-2d4e0280-a603-11e8-9f03-1cb50f407041.png)<br>
これらの３つのベクトルは、何れも z 軸成分が０なので、上図のように、x-y 平面に存在することになる。<br>
これらのベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44440787-ac900600-a604-11e8-800a-adbc4885f3df.png) に対して、<br>
![image](https://user-images.githubusercontent.com/25688193/44440816-cdf0f200-a604-11e8-9fb1-61ac25d71a9b.png) が成り立つことは、直接代入してみれば分かる。<br>
ここで重要なのは、この ![image](https://user-images.githubusercontent.com/25688193/44440841-eb25c080-a604-11e8-97c5-5b3a9da6fff1.png) という結果が、例えば、<br>
![image](https://user-images.githubusercontent.com/25688193/44440861-07296200-a605-11e8-8f77-a85393c57e4c.png) とかけ、<br>
**３つのベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44440787-ac900600-a604-11e8-800a-adbc4885f3df.png) の内、１つが他の２つのベクトルに依存（従属）していることを示しているということである。**<br>
即ち、これら３つのベクトルの組は、xyz 空間において、特に xy 平面上で互いに無関係ではありえないことを示している。<br>

<br>

次に、以下のような３つのベクトルを考える。<br>
![image](https://user-images.githubusercontent.com/25688193/44443705-267bbb80-a614-11e8-95fa-42633b4e272c.png)<br>
![image](https://user-images.githubusercontent.com/25688193/44443719-398e8b80-a614-11e8-9e5c-7dd1a94c47b8.png)<br>
このとき、先の関係式と同じ式は、<br>
![image](https://user-images.githubusercontent.com/25688193/44443765-60e55880-a614-11e8-9611-e6cfe250dfd1.png)<br>
z 成分が０でないのは、![image](https://user-images.githubusercontent.com/25688193/44443953-55466180-a615-11e8-9081-128332c17f6b.png) のみなので、この式において ![image](https://user-images.githubusercontent.com/25688193/44443966-67c09b00-a615-11e8-8cc9-9cb3dc6720bd.png) でなくてはならない。<br>
![image](https://user-images.githubusercontent.com/25688193/44444019-a6565580-a615-11e8-90fe-d8856a835ad9.png) については、<br>
![image](https://user-images.githubusercontent.com/25688193/44444030-b5d59e80-a615-11e8-911f-330ba46129cd.png)<br>
この式は、![image](https://user-images.githubusercontent.com/25688193/44444065-daca1180-a615-11e8-85d6-b07d352495d0.png) のときのみ成り立つ。<br>

**このように、![image](https://user-images.githubusercontent.com/25688193/44444257-f2ee6080-a616-11e8-95c7-8c8846c3e718.png) という条件は、３つのベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44444282-08fc2100-a617-11e8-80fc-1a574e3a918e.png) が、３つのベクトルがそれぞれ独立しており、xyz 空間において互いに無関係である（＝独立している）ことを示している。**<br>


<a id="ID_2-3"></a>

### ◎ 基底ベクトル
![image](https://user-images.githubusercontent.com/25688193/44444655-db17dc00-a618-11e8-8e80-25a0d91b4ffe.png)<br>
空間中のベクトルを考える。<br>
以下のベクトルは、上図のようにそれぞれ ![image](https://user-images.githubusercontent.com/25688193/44444670-eec34280-a618-11e8-9bbd-3d48f084124c.png) 軸方向の **単位ベクトル [unit vector]** となっている。<br>
![image](https://user-images.githubusercontent.com/25688193/44444730-42ce2700-a619-11e8-8aa8-eab461533b3b.png)<br>

３次元空間中の任意のベクトルは、この単位ベクトル（基底ベクトルとなる）を用いて、<br>
![image](https://user-images.githubusercontent.com/25688193/44445126-c9373880-a61a-11e8-8e53-fdff3fc0f138.png)<br>
のように、**線形結合の形で表現することが出来る！**<br>

この単位ベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44445535-3f886a80-a61c-11e8-9b8d-ff77b4fa6a08.png) は、上図から明らかなように、線形独立である。<br>
つまり、![image](https://user-images.githubusercontent.com/25688193/44445553-57f88500-a61c-11e8-814e-231d84c68e44.png) が成り立つ。<br>
実際に代入してみると、<br>
![image](https://user-images.githubusercontent.com/25688193/44446125-b1fa4a00-a61e-11e8-82c4-85065a852c3a.png)<br>
となり、この式が成立するのは、自明に ![image](https://user-images.githubusercontent.com/25688193/44446154-ce968200-a61e-11e8-9f0f-693893ae3375.png) のときのみである。<br>

今、３次元空間を考えているが、他に別のベクトル<br>
![image](https://user-images.githubusercontent.com/25688193/44448771-318c1700-a627-11e8-97d6-75ef1c463896.png)<br>
を付け加えてみる。<br>
すると、この４つのベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44448892-8f206380-a627-11e8-9749-9d05d5ca24a0.png) に対し、<br>
![image](https://user-images.githubusercontent.com/25688193/44448932-b0814f80-a627-11e8-90e4-5becc30d2a95.png)<br>
が成り立つので、このベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44448892-8f206380-a627-11e8-9749-9d05d5ca24a0.png) は線形独立ではない。<br>

逆に、ベクトルの数を減らしてみると、各々の２つのベクトルの組の線形結合、<br>
例えば、![image](https://user-images.githubusercontent.com/25688193/44449016-e6becf00-a627-11e8-8ef8-cc7d2710dc84.png) は、z 成分が０なので、線形独立ではない。<br>
そして、任意の３次元ベクトルを表現できない。<br>

つまり、３次元ベクトル空間の任意のベクトルを表現するには、３つのベクトル ![image](https://user-images.githubusercontent.com/25688193/44449079-12da5000-a628-11e8-9754-a565875b5e33.png) のどれも欠かせないのである！<br>
このように、３次元空間に対して、これらの３つのベクトルが重要な役割を果たしていることが分かる。<br>
そして、このようなベクトルを **基底ベクトル [basis vector]** という。<br>

一般に、n 次元ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/44449296-aa3fa300-a628-11e8-8d4d-c73b1d90ca2a.png) に対し、<br>
この空間内の任意のベクトルが n 個の線形独立なベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44449448-23d79100-a629-11e8-9892-bd586de03bee.png) の線形結合でかける時、これらのベクトルを n 次元ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/44449296-aa3fa300-a628-11e8-8d4d-c73b1d90ca2a.png) に対する **基底** という。<br>


<a id="ID_2-4"></a>

### ◎ ベクトルの次元
基底ベクトルに関して前項で記述したように、３次元ベクトル全体（ベクトル空間）R^3  の基底の数は３であった。そして、このベクトル空間内で基底ベクトルの候補となりうるベクトルを１つ付け加えようとすると、これらベクトルの組は線形独立でなくなり、又、基底ベクトルを減らそうとすると任意の３次元ベクトルを表せなく成る。<br>

つまり、与えられたベクトル空間に対し、組み合わせの異なる基底ベクトルの組を考えることはできるが、基底ベクトルの数は変わることがないのである！<br>
このように定まる **基底の数の事を、そのベクトル空間 V の次元といい dim V で表す。**<br>

※ ３次元直交直交系のベクトルは３次元であると直感的に使用しているが、ベクトル空間の明確な公理に基づくと次元の考え方は上記のように考えられる。<br>

- （例）２次の多項式とベクトル空間の基底（ベクトル空間の公理に基づいた例）<br>
    x に関しての２次の多項式 ![image](https://user-images.githubusercontent.com/25688193/44450274-7619b180-a62b-11e8-8ba0-5d740c468387.png) を考える。<br>
    <br>
    この２次の多項式は、定数項 ![image](https://user-images.githubusercontent.com/25688193/44453402-ecbaad00-a633-11e8-8d3e-4e64b1d976d8.png)、x の１次の項、x の２次の項から成り立っている。<br>
	ここで、各項をベクトルとみなし、![image](https://user-images.githubusercontent.com/25688193/44453459-0e1b9900-a634-11e8-91cd-096bdc7404cc.png) とすると、<br>
    任意のベクトルは、![image](https://user-images.githubusercontent.com/25688193/44453511-21c6ff80-a634-11e8-8696-e7f5a1eae24f.png) とかける。<br>
	このベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44453641-83876980-a634-11e8-8c50-16ce538ff36e.png) の内、１つでも欠けると任意の２次の多項式を表現できない。<br>
	又、![image](https://user-images.githubusercontent.com/25688193/44453641-83876980-a634-11e8-8c50-16ce538ff36e.png) は、x に関して次数が異なるので、線形独立でもある。<br>
	従って、このベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44453641-83876980-a634-11e8-8c50-16ce538ff36e.png) は、この２次の多項式によって張られる（生成される）ベクトル空間の基底ベクトルであり、その次元は dimV=3 である。<br>

- （例）行列とベクトル空間の基底（ベクトル空間の公理に基づいた例）<br>
    ２×２の正方行列<br>
    ![image](https://user-images.githubusercontent.com/25688193/44454058-7dde5380-a635-11e8-9af9-0442aa8a4536.png)<br>
    を考える。<br>

    この行列を表現するためには、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44454620-ebd74a80-a636-11e8-94fe-7df04abd9e80.png)<br>
	の４つのベクトルを用意すればよい。<br>
    すると、この行列 A は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44454672-132e1780-a637-11e8-9e23-6aa2c3bc4bea.png) とかける。<br>
	このベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44454707-2c36c880-a637-11e8-92bb-512e4217dd44.png) の内、１つでも欠けると２×２の正方行列を表現できない。<br>
	又、![image](https://user-images.githubusercontent.com/25688193/44454707-2c36c880-a637-11e8-92bb-512e4217dd44.png) はそれぞれ、要素が１となる場所が異なり、それ以外の要素は０なので、線形独立でもある。<br>
	従って、このベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44454707-2c36c880-a637-11e8-92bb-512e4217dd44.png) は、この２×２の正方行列によって張られる（生成される）ベクトル空間の基底ベクトルであり、その次元は dimV=4 である。


<!--
## ■ 関数空間
関数解析で扱う関数空間は、収束の概念などの位相的な性質をもつベクトル空間である。<br>
ここで、この収束の概念とは、
有次元ベクトル空間において、ベクトルの列 ![image](https://user-images.githubusercontent.com/25688193/44466778-1c7dab00-a65c-11e8-89d8-4f7f0ee1b465.png) とあるベクトル ![image](https://user-images.githubusercontent.com/25688193/44467081-ee4c9b00-a65c-11e8-9a34-44426b74fa69.png) の距離 ![image](https://user-images.githubusercontent.com/25688193/44467213-3ff52580-a65d-11e8-92f7-09f40d909d8c.png) が０に収束することである。
（このとき、ベクトルの列 ![image](https://user-images.githubusercontent.com/25688193/44466778-1c7dab00-a65c-11e8-89d8-4f7f0ee1b465.png) あるベクトル ![image](https://user-images.githubusercontent.com/25688193/44467081-ee4c9b00-a65c-11e8-9a34-44426b74fa69.png) に収束するという。）<br>
-->

<a id="ID_3"></a>

## ■ 点列の収束と極限
世の中には、有限回の計算で完全な解が求まらないような問題が多く存在する。<br>
このような問題では、厳密解への収束が保証される数列（点列）が利用される。<br>

すべての収束や極限概念の基本は、実数列にあるので、
ここでは、この最も単純な実数列を例に収束や極限の概念を定義している。<br>
（数ある数列や点列のうち、具体的に実数列のみを扱うことで一般性は失われるが、実数列で考えたほうがわかりやすいのと、実数列での収束、極限の概念は他の点列でも当てはまることが多いので、実数列のみを取り扱う。）<br>

実数列 ![image](https://user-images.githubusercontent.com/25688193/44614560-53bda900-a862-11e8-8512-e98571abd5a3.png) がある極限値 α に収束することを、<br>
![image](https://user-images.githubusercontent.com/25688193/44614571-6df78700-a862-11e8-8c04-4c6c4dd63caf.png) や ![image](https://user-images.githubusercontent.com/25688193/44614627-32a98800-a863-11e8-84ae-bfa683351626.png)<br>
などで表現するが、この意味を曖昧さがないように説明するにはどのようにしたら良いだろうか？<br>
この答えとして、以下に定義する ε−N 論法 による定義がある。<br>

![image](https://user-images.githubusercontent.com/25688193/44616438-8085b680-a88a-11e8-8f6a-840bb7368a56.png)<br>


<a id="ID_3-1"></a>

### ◎ 点列の収束・極限に関しての有用な性質
次に、実数列の収束・極限に関して、いくつかの有用な性質を見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/44615364-b3708000-a873-11e8-9e8a-10a7e7e08907.png)<br>

- （証明）<br>
	実数列の定義（ ![image](https://user-images.githubusercontent.com/25688193/44615381-2a0d7d80-a874-11e8-91b0-119d3c29143d.png) ）において、ε=1 としても、ある有限な ![image](https://user-images.githubusercontent.com/25688193/44615392-617c2a00-a874-11e8-9bc9-2c26c65dd682.png) が存在し、<br>
	![image](https://user-images.githubusercontent.com/25688193/44615397-71940980-a874-11e8-93e6-43d3c4cf0f7a.png) が成り立つので、絶対値の部分を変形すると、<br>
	![image](https://user-images.githubusercontent.com/25688193/44615400-82447f80-a874-11e8-8176-ca5c246e89c3.png) を得る。<br>
    <br>
	一方、![image](https://user-images.githubusercontent.com/25688193/44615410-a99b4c80-a874-11e8-9dff-774b8a59f419.png) は、有限個の実数なので、<br>
	これら ![image](https://user-images.githubusercontent.com/25688193/44615413-c0da3a00-a874-11e8-9a8d-7e27e36f39e8.png) の最小値は、![image](https://user-images.githubusercontent.com/25688193/44615418-d3ed0a00-a874-11e8-9bb8-ea93c28f13dd.png) であり、下に有界である。<br>
	逆に、これら ![image](https://user-images.githubusercontent.com/25688193/44615413-c0da3a00-a874-11e8-9a8d-7e27e36f39e8.png) の最大値は、![image](https://user-images.githubusercontent.com/25688193/44615423-e5cead00-a874-11e8-8797-126466180caf.png) であり、上に有界である。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/44615573-ffbdbf00-a877-11e8-8402-cfa20c0730fa.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44615576-23810500-a878-11e8-822a-d3e24400fb5d.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/44615736-6ba22680-a87c-11e8-8fca-00085e6f01b0.png)<br>

> 【メモ】<br>
> このコーシー列の判定条件と、ε−N 論法におよる収束の定義の違いは？


<a id="ID_3-2"></a>

### ◎ 上極限と下極限
ここで、実数列が収束するという条件は、厳しい条件になるが、これより弱い条件として、上極限と下極限という概念が存在する。<br>
これは、収束するかわからないような実数列に対しても、大きな n に対して振る舞いを把握した場合に用いることが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/44616010-c474bd80-a882-11e8-91ed-488b16d67d9b.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44616016-d6eef700-a882-11e8-93e8-c092dda07dec.png)<br>


<a id="ID_4"></a>

## ■ 距離空間
距離を用いると、一般の点列の収束や極限の議論が、実数列のときと同じようにすることが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/44616678-23403400-a88f-11e8-8136-761bf039e318.png)<br>

ここで、距離空間は、ベクトル空間ではなく集合に対して定義されることに注意。<br>
（後述のノルム空間は、ベクトル空間に対して定義される。）<br>

<!--
【メモ】
![image](https://user-images.githubusercontent.com/25688193/44616618-07885e00-a88e-11e8-84c8-d465f53a53af.png)<br>
-->

<a id="ID_4-1"></a>

### ◎ 距離空間の例
- （例）１次元の実数での距離空間 ![image](https://user-images.githubusercontent.com/25688193/44617235-3a385380-a89a-11e8-872c-d2e044880018.png)<br>
	実数全体の集合 R において、任意の点 ![image](https://user-images.githubusercontent.com/25688193/44617249-4e7c5080-a89a-11e8-95f9-47423b364be4.png) に対して、<br>
	距離を ![image](https://user-images.githubusercontent.com/25688193/44617257-5e943000-a89a-11e8-8dcb-58a20c8cadfb.png) で定義することにより、この写像 d が距離の３つの条件を満たすので（計算略）、<br>
	![image](https://user-images.githubusercontent.com/25688193/44617235-3a385380-a89a-11e8-872c-d2e044880018.png) は距離空間になる。<br>

- （例）N 次元の実数での距離空間 ![image](https://user-images.githubusercontent.com/25688193/44617266-8daaa180-a89a-11e8-8dd4-ff92f7fd6397.png)<br>
	N 次元実ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/44617289-dc583b80-a89a-11e8-8aa7-c23db4796daa.png) において、任意のベクトル ![image](https://user-images.githubusercontent.com/25688193/44617282-c77ba800-a89a-11e8-8a9a-4202f21bb577.png) に対して、<br>
	距離を<br>
    ![image](https://user-images.githubusercontent.com/25688193/44617296-f3972900-a89a-11e8-9c4f-84456a0f5820.png)<br>
    で定義することにより、この写像 d が距離の３つの条件を満たすので（計算略）、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44617266-8daaa180-a89a-11e8-8dd4-ff92f7fd6397.png) は距離空間になる。<br>

- （例）距離空間 ![image](https://user-images.githubusercontent.com/25688193/44642760-a5079d00-aa08-11e8-9f88-55859165e6a2.png)<br>
    実数 p≥1 に対して、条件 ![image](https://user-images.githubusercontent.com/25688193/44642855-0d567e80-aa09-11e8-8601-903c43c32f43.png) （和が有限の値で絶対可積分）を満たすような、<br>
    すべての実数列 ![image](https://user-images.githubusercontent.com/25688193/44642948-98d00f80-aa09-11e8-8860-408390d55e3d.png) からなる集合を ![image](https://user-images.githubusercontent.com/25688193/44642986-c321cd00-aa09-11e8-9fff-cce6ba905fc8.png) と定義する。<br>
    すると、この集合 ![image](https://user-images.githubusercontent.com/25688193/44642986-c321cd00-aa09-11e8-9fff-cce6ba905fc8.png) 内の任意の ![image](https://user-images.githubusercontent.com/25688193/44646432-ea7e9700-aa15-11e8-8af7-23045c1b86e7.png) に対して、![image](https://user-images.githubusercontent.com/25688193/44643286-ec8f2880-aa0a-11e8-970b-d87f93af6709.png) となり、<br>
    距離<br>
    ![image](https://user-images.githubusercontent.com/25688193/44643304-003a8f00-aa0b-11e8-856a-e720c9ad681b.png)<br>
    が定義出来る。<br>
    そして、そこから構成される、![image](https://user-images.githubusercontent.com/25688193/44642760-a5079d00-aa08-11e8-9f88-55859165e6a2.png) は距離空間となる。（計算略）<br>


<a id="ID_4-2"></a>

### ◎ 距離空間における収束、極限とコーシー列（基本列）
距離空間における点列 ![image](https://user-images.githubusercontent.com/25688193/44617800-89838180-a8a4-11e8-8d8f-8ccfd7ed20de.png) の収束の概念は、以下のコーシー列（基本列）により定義される。<br>

![image](https://user-images.githubusercontent.com/25688193/44617805-9b652480-a8a4-11e8-9652-7dcf608922ef.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44617838-9bb1ef80-a8a5-11e8-8adb-6d6356c9c82a.png)<br>

そして、**”点列が実数列であるとき、実数列がコーシー列であることと、この実数列がある実数に収束することは等価である！”**（証明略）<br>
逆に、一般の点列に対しては、必ずしもこの関係は成り立たない。（証明略）<br>

因みに、点列がある極限に収束するためには、当然ながら極限の情報が必要となるが、<br>
コーシー列の定義では、この極限の情報を必要としていないので、点列がコーシー列であることを示すのに原理上は極限の情報は必要ないことに注意。<br>


<a id="ID_4-3"></a>

### ◎ 完備距離空間
先の議論で、距離空間 X におけて点列が収束するとはどういう意味であるかはわかったが、<br>
距離空間 X が与えられたときに、ある点列の極限が、その距離空間に存在するか？という問題の解決方法として、極限の候補にあたりをつけ、都度先の収束・極限の条件を満たすか確認する方法も考えられるが、この方法は不便である。<br>

そのような場合に、実数列の場合のとき（＝実数列がコーシー列なら収束する）と同じように、点列の情報だけで極限の存在性が判別できれば便利である。<br>
そのために以下のような、完備な空間というものを考える。<br>

![image](https://user-images.githubusercontent.com/25688193/44618533-a0c96b80-a8b2-11e8-8ea6-c1169b348985.png)<br>


<a id="ID_4-3-1"></a>

#### ☆ 完備距離空間の例
- （例）完備距離空間ではない例<br>
    有理数の実数列 ![image](https://user-images.githubusercontent.com/25688193/44628101-d040ac80-a974-11e8-8bd0-68c1e88eb2f0.png) は、距離空間 ![image](https://user-images.githubusercontent.com/25688193/44624893-f8f58180-a935-11e8-94da-3e66b3aab318.png) 内において、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44624896-162a5000-a936-11e8-88d7-c8282479014c.png) に収束するので、この収束先に一意に決まり（収束先の一意性の性質）、![image](https://user-images.githubusercontent.com/25688193/44624898-27735c80-a936-11e8-87a7-4e98bbff916b.png) 以外のいかなる実数にも収束しない。<br>
    また、この実数列 ![image](https://user-images.githubusercontent.com/25688193/44628126-4218f600-a975-11e8-8a7d-b09460299143.png) は、有理数 Q の如何なる点にも収束しない。<br>
    <br>
	ここで、距離空間において、点列がある点に収束するならば、その点列は（コーシー列の基本性質より）コーシー列になるので、<br>
	この実数列 ![image](https://user-images.githubusercontent.com/25688193/44628126-4218f600-a975-11e8-8a7d-b09460299143.png) は、距離空間 ![image](https://user-images.githubusercontent.com/25688193/44624893-f8f58180-a935-11e8-94da-3e66b3aab318.png) のコーシー列になる。<br>
    そして、有理数の距離空間 ![image](https://user-images.githubusercontent.com/25688193/44628393-e00ebf80-a979-11e8-89a8-c7235400f083.png) のコーシー列でもある。<br>
    <br>
	従って、この有理数の距離空間 ![image](https://user-images.githubusercontent.com/25688193/44628393-e00ebf80-a979-11e8-89a8-c7235400f083.png) は、完備”でない”距離空間になる。<br>
	（一方、実数の距離空間 ![image](https://user-images.githubusercontent.com/25688193/44628399-f61c8000-a979-11e8-9d00-97e43453a8d2.png) は、完備な距離空間である。）<br>

- （例）距離空間 ![image](https://user-images.githubusercontent.com/25688193/44646962-b1472680-aa17-11e8-9714-156772648b3b.png)<br>
    距離空間 ![image](https://user-images.githubusercontent.com/25688193/44646962-b1472680-aa17-11e8-9714-156772648b3b.png) が完備であるかを調べる。<br>
	- コーシー列と完備性の関係（＝任意のコーシー列が収束するなら、その距離空間は完備）より、<br>
	    ![image](https://user-images.githubusercontent.com/25688193/44647032-dfc50180-aa17-11e8-8cb0-9f117108eceb.png) からなる点列 ![image](https://user-images.githubusercontent.com/25688193/44647082-084cfb80-aa18-11e8-99c2-4bea7f707284.png) が ![image](https://user-images.githubusercontent.com/25688193/44647178-45b18900-aa18-11e8-84d0-a95c09eb3802.png) のコーシー列であるとき、<br>
	    この点列が ![image](https://user-images.githubusercontent.com/25688193/44647178-45b18900-aa18-11e8-84d0-a95c09eb3802.png) 内のある点に収束するのか調べれば良い。（収束すれば完備）<br>
        <br>
	    点列 ![image](https://user-images.githubusercontent.com/25688193/44647082-084cfb80-aa18-11e8-99c2-4bea7f707284.png) はコーシー列であるので、<br>
	    任意の ε>0 に対して、ある ![image](https://user-images.githubusercontent.com/25688193/44647279-92955f80-aa18-11e8-938c-5b8abfd535dc.png) が存在して、n,m>N ならば、<br>
        ![image](https://user-images.githubusercontent.com/25688193/44647299-a345d580-aa18-11e8-9567-6d0e00e54bf7.png)<br>
        従って、任意の j に対して、（ j = 1 ~ ∞ の無限和なので、）<br>
        ![image](https://user-images.githubusercontent.com/25688193/44647344-c3759480-aa18-11e8-801d-ee3aad97cdf4.png)<br>
	    ここで、j を固定し、実数列 ![image](https://user-images.githubusercontent.com/25688193/44648575-6c71be80-aa1c-11e8-89b9-a9c0d34e6c1e.png) を定義すると、<br>
	    上記の関係より、この実数列 ![image](https://user-images.githubusercontent.com/25688193/44648575-6c71be80-aa1c-11e8-89b9-a9c0d34e6c1e.png) は、実数空間 R のコーシー列になっていることが分かる。<br>
        そして、実数空間 R は完備であるので、![image](https://user-images.githubusercontent.com/25688193/44648575-6c71be80-aa1c-11e8-89b9-a9c0d34e6c1e.png) は収束し、<br>
        ![image](https://user-images.githubusercontent.com/25688193/44705309-347c8100-aad9-11e8-9c0d-85483e02a86c.png)<br>
        が成り立つ。<br>
	- 次に、![image](https://user-images.githubusercontent.com/25688193/44706125-8c1bec00-aadb-11e8-89b0-8098ca2878d9.png) は、点列 ![image](https://user-images.githubusercontent.com/25688193/44706144-9ccc6200-aadb-11e8-8903-9fee78b58ce4.png) の有力な収束先の候補であるが、<br>
	    実際に、![image](https://user-images.githubusercontent.com/25688193/44706403-6fcc7f00-aadc-11e8-81ab-41b553dbf8bc.png) となり ![image](https://user-images.githubusercontent.com/25688193/44706436-870b6c80-aadc-11e8-9777-e2bf8eaa7821.png) となることを示す。<br>
        先の<br>
        ![image](https://user-images.githubusercontent.com/25688193/44706612-23357380-aadd-11e8-90df-a38964ed9fd9.png)<br>
        の関係より、任意の ![image](https://user-images.githubusercontent.com/25688193/44706659-4d873100-aadd-11e8-9e0d-cb982747ab0b.png) に対して、n,m>N ならば、<br>
        ![image](https://user-images.githubusercontent.com/25688193/44706677-61cb2e00-aadd-11e8-8dd6-5a0fd65f6aff.png)<br>
        > 記載中...<br>

<!--
<a id="ID_4-3-2"></a>

#### ☆ 開集合、閉集合
> 記載中...
-->


<a id="ID_4-3-3"></a>

#### ☆ 写像の連続性
関数の連続性や微分可能性を調べる際に、変数がある値に限りなく近づく状況を想定し、対応する関数値 f の振る舞いを調べることになる。<br>
この際に、変数が連続的で離散データのように順番を表すインデックスが存在しないので、「変数がある値に限りなく近づく」ということを、予め明確に定義しておく必要がある。<br>

![image](https://user-images.githubusercontent.com/25688193/44725301-ed5db280-ab0f-11e8-9933-b9041b208836.png)<br>
    ※ この定義の条件（ ![image](https://user-images.githubusercontent.com/25688193/44718323-ac0ed800-aafa-11e8-9ab1-0d736b9693de.png) ）は、<br>
    　 距離空間 X,Y の開球 ![image](https://user-images.githubusercontent.com/25688193/44718354-c2b52f00-aafa-11e8-9630-fcf49a817304.png) の言葉を用いると、以下のように表現できる。<br>
    　 ![image](https://user-images.githubusercontent.com/25688193/44718384-d52f6880-aafa-11e8-902c-8a537bf9ba79.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44723739-d2893f00-ab0b-11e8-8c8c-171c4188b519.png)<br>
- （証明略）<br>

![image](https://user-images.githubusercontent.com/25688193/44723791-f2206780-ab0b-11e8-91b7-551ae48a92cf.png)<br>
- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/44960739-c522e900-af3f-11e8-9573-c87a694ef08e.png)<br>
    ※ この定義の条件（ ![image](https://user-images.githubusercontent.com/25688193/44724450-b38bac80-ab0d-11e8-95ea-535fa99872bf.png) ）は、<br>
    　 距離空間 X,Y の開球 ![image](https://user-images.githubusercontent.com/25688193/44724481-c7371300-ab0d-11e8-99df-03d73a5cbb91.png) の言葉を用いると、以下のように表現できる。<br>
    　 ![image](https://user-images.githubusercontent.com/25688193/44724516-df0e9700-ab0d-11e8-8536-bcb83b5b82ac.png)<br>


<a id="ID_4-3-4"></a>

#### ☆ コンパクト集合
コンパクト性は、距離空間の部分集合に関する性質である。<br>

> 【Memo】 コンパクトだと、なぜ嬉しいか？<br>
> ・コンパクト集合上の連続関数は、最大値と最小値を持つ。（後述の最大値と最小値の定理）<br>
> → これにより、最適化の議論が行える。<br>
> ・コンパクト集合上の連続関数は、一様連続。<br>
> → これにより、近似の議論が可能となる。<br>

![image](https://user-images.githubusercontent.com/25688193/44733911-8e099d80-ab23-11e8-838b-be35918cd437.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44734971-1f7a0f00-ab26-11e8-847d-ec63b7523f8a.png)<br>
    ※ 特に、距離空間 X 自身がコンパクト集合であるとき、この距離空間 X をコンパクト空間という。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/44763247-56cbd880-ab85-11e8-9109-835ed48b7623.png)<br>
- （証明略）<br>

![image](https://user-images.githubusercontent.com/25688193/44763268-6f3bf300-ab85-11e8-9e60-f1125c5ed413.png)<br>
    ※ 先の「距離空間のコンパクト」に関する定理は、一般の距離空間で成り立っていたが、この定理では、距離空間 ![image](https://user-images.githubusercontent.com/25688193/44763302-a7433600-ab85-11e8-9896-dd19ae8f33ad.png) に限定することで、３つ目の命題も必要十分条件の関係で成り立つようになる。<br>
- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/44764917-fd67a780-ab8c-11e8-96af-c34e8824b8a7.png)
- （証明）<br>
    ![image](https://user-images.githubusercontent.com/25688193/44770055-b1732d80-aba1-11e8-951b-408a9011c688.png) を連続写像 f による S の像 f(S) の開被覆とする。即ち、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44770075-c6e85780-aba1-11e8-8838-bfb9482108d0.png)<br>
	が成り立つとする。<br>
	このとき、U から適当な有限個の開集合を選ぶことにより、f(S) が被覆できることを示せばよい。<br>
	（このとき、f(S) はコンパクト集合）<br>
    <br>
    ![image](https://user-images.githubusercontent.com/25688193/44770117-e8e1da00-aba1-11e8-88a0-770aa91af7e5.png)<br>
    まず、写像 f を逆写像した ![image](https://user-images.githubusercontent.com/25688193/44770145-04e57b80-aba2-11e8-87e7-e3d86e0bc55c.png) は、”X の” 開集合となり（証明略）、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44770195-33fbed00-aba2-11e8-8049-80dbd7eafbf8.png)<br>
    の関係が成り立つので、この逆写像による集合族 ![image](https://user-images.githubusercontent.com/25688193/44770703-d7013680-aba3-11e8-9b96-781d99548470.png) は、元の部分集合 S の開被覆になっていることが分かる。<br>
    ここで、S は X のコンパクト集合なので、この開被覆からうまく選んだ有限個の開集合<br>
    ![image](https://user-images.githubusercontent.com/25688193/44770747-f730f580-aba3-11e8-8a12-82b113870218.png) から、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44770789-1af43b80-aba4-11e8-8fbf-25cafdb4c8fa.png)<br>
    とすることが出来る。<br>
    従って、f(S) は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44770927-7faf9600-aba4-11e8-889c-197792af9ad3.png)<br>
    この ![image](https://user-images.githubusercontent.com/25688193/44770946-90600c00-aba4-11e8-8997-4c736656f108.png) の関係より、f(S) はコンパクト集合であると言える。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/44784468-bf887480-abc8-11e8-92a0-bbc72ca57c33.png)<br>
- （証明）<br>
    まず、最大値の存在について示す。<br>
	先の定理（連続写像によるコンパクト集合の像）より、コンパクトな部分集合 S の像 f(S) は、写像先の集合 R のコンパクト集合になる。<br>
	このことと、先の定理（距離空間のコンパクト性と点列コンパクト）より、R は有界集合となる。<br>
	従って、ワイエルシュトラスの公理（上に有界な任意の部分集合 A⊂R に対し、上限 ![image](https://user-images.githubusercontent.com/25688193/44784560-0d04e180-abc9-11e8-8a71-304bdd0fe19a.png) が存在する）より、f(S)∈R（有界集合）に上限 ![image](https://user-images.githubusercontent.com/25688193/44784589-273ebf80-abc9-11e8-8bac-de32bff6a446.png) が存在する。<br>
    <br>
	最大値の存在証明のためには、この上限 ![image](https://user-images.githubusercontent.com/25688193/44784633-49d0d880-abc9-11e8-87ce-adf864d8c4d4.png) が ![image](https://user-images.githubusercontent.com/25688193/44784672-68cf6a80-abc9-11e8-9e0c-91974dd7c5f1.png) となることを示せばよい。<br>
	上限の定義から、任意の x∈S に対し、![image](https://user-images.githubusercontent.com/25688193/44784694-7be23a80-abc9-11e8-9218-14961cc01341.png) が成り立つが、<br>
	![image](https://user-images.githubusercontent.com/25688193/44784714-8d2b4700-abc9-11e8-99bb-64918b2b9f5c.png)<br>
	となる実数列 ![image](https://user-images.githubusercontent.com/25688193/44784742-a03e1700-abc9-11e8-85f2-53af2983c799.png) をとることが出来る。<br>
    この実数列 ![image](https://user-images.githubusercontent.com/25688193/44784742-a03e1700-abc9-11e8-85f2-53af2983c799.png) は、![image](https://user-images.githubusercontent.com/25688193/44785291-59e9b780-abcb-11e8-9793-6cd0f859f7df.png) を満たす。<br>
	更に、先の定理（距離空間のコンパクト性と点列コンパクト）は、f(S) が（有界）閉集合であることを保証しているので、![image](https://user-images.githubusercontent.com/25688193/44785351-8c93b000-abcb-11e8-95af-1a92807ec999.png) となる ![image](https://user-images.githubusercontent.com/25688193/44785387-aa611500-abcb-11e8-8360-36efc1131baa.png) が存在する。<br>
    <br>
    最小値の存在証明に関しても、同様の方法で示せる。<br>

<br>

- 【参考
    - [コンパクト性、開被覆 - 大人になってからの再学習](http://zellij.hatenablog.com/entry/20120515/p1)<br>
    - [有界閉とコンパクト](http://www.misojiro.t.u-tokyo.ac.jp/~murota/lect-kisosuri/compactRn041202.pdf)<br>


<a id="ID_4-3-5"></a>

#### ☆ 縮小写像の不動点定理
集合 X で定義された写像 T:X→X に対して、<br>
z∈X が存在して、T(z)=z（＝写像後も変わらず自分自身に写像される点）となるとき、<br>
この点 z は、写像 T の不動点 [fixed point] であるという。 <br>
ここでは、写像 T の不動点全体からなる集合を ![image](https://user-images.githubusercontent.com/25688193/44793963-6e857a00-abe2-11e8-9d1f-d94fdbb2d8b9.png) と表記することにする。<br>

![image](https://user-images.githubusercontent.com/25688193/44796509-0b96e180-abe8-11e8-810f-32a26474697a.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44797201-91675c80-abe9-11e8-97e4-5acb35ee9793.png)<br>

この縮小写像を用いれば、繰り返し縮小写像することでどんどん距離が短くなるので、<br>
以下の図のように極限となる不動点が表現できる。<br>
![image](https://user-images.githubusercontent.com/25688193/44799479-f5d8ea80-abee-11e8-93b4-da643ea9b6d2.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44804319-f4fa8580-abfb-11e8-8857-45d9e57a34ed.png)<br>
※ この縮小写像の不動点定理は、方程式（微分方程式や積分方程式）の解の一意な存在性を示すのに、よく利用される。<br>

この縮小写像の不動点定理の有用性は、写像が縮小写像の場合に限定されるものではなく、<br>
T:X→X が、必ずしも縮小写像ではないリプシッツ連続な写像であっても、T の累乗が縮小写像になる場合には適用される。<br>

![image](https://user-images.githubusercontent.com/25688193/44829129-2142f000-ac56-11e8-8d4c-a4461cb96057.png)<br>


<a id="ID_4-3-6"></a>

#### ☆ ベールの定理
関数解析の線形理論には、corner stones （礎石、基本理念）と呼ばれる４大定理（一様有界性の定理、開写像定理、閉グラフ定理、ハーン・バナッハの定理）が存在する。<br>
この内、ハーン・バナッハの定理以外の３定理は、いずれも完備性がポイントとなっており、以下のベールの定理から導かれる。<br>

![image](https://user-images.githubusercontent.com/25688193/44831928-90731100-ac63-11e8-9dc0-4c571952e53b.png)<br>

このベールの定理（ベールのカテゴリ定理）は、<br>
「完備な距離空間における部分集合を、その閉包（閉集合）が内点を持つか否かという基準で分類すると、2 種類（第１類集合＜疎な集合の和集合で表せる＞、第２種類集合＜疎な集合の和集合で表せない＞）しかない」
ということを主張している。<br>

- 【参考】[極私的関数解析：ベールの範疇定理](http://www.ne.jp/asahi/music/marinkyo/funkcionala-analitiko/kategorio.html.ja)


<a id="ID_4-3-7"></a>

#### ☆ 稠密 [dense]、可分性 [separable]
実数は、有限桁の小数でいくらでも精度より近似できる。<br>
このことは、非加算無限集合 R が 「”稠密な”可算部分集合 Q の点列の極限」 をもつことに由来しているとも解釈できる。<br>
同様にして、距離空間が稠密な可算部分集合を持てば、本質的には類似の表現が出来ると考えられる。<br>

![image](https://user-images.githubusercontent.com/25688193/44834514-61ad6880-ac6c-11e8-8fdc-e596c0840428.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44836036-d4204780-ac70-11e8-9794-6f7be283fb49.png)<br>

- 【参考】[rhidetoのblog : 例16. 稠密性](http://blog.livedoor.jp/rhideto/archives/26364842.html)

- 【参考】[位相空間・質問箱 | 読者からの質問と回答](http://www12.plala.or.jp/echohta/top/QA/QA004.html)


<a id="ID_5"></a>

## ■ ノルム空間
ベクトルの長さに相当するいくつかの基本的性質のみ抽出すれば、より抽象的な概念として、より一般的な空間にも、ベクトルの長さに相当する概念を導入することが出来る。<br>
この概念こそが **ノルム** となる。<br>
そして、ノルム空間の２つのベクトル間の距離は、２つのベクトルの差を表すベクトルのノルムとして定義され、この距離によってノルム空間は距離空間になる。<br>

![image](https://user-images.githubusercontent.com/25688193/44925102-54859c00-ad88-11e8-891d-f565e25d9101.png)<br>

<!--
ベクトルの長さに相当するいくつかの基本的性質のみ抽出すれば、より抽象的な概念として、より一般的な空間にも、ベクトルの長さに相当する概念を導入することが出来る。<br>
そしてその概念こそがノルムとなる。<br>

![image](https://user-images.githubusercontent.com/25688193/44467877-f6a5d580-a65e-11e8-8c5b-a6b1180245e6.png)<br>
-->


<a id="ID_5-1"></a>

### ◎ ノルム、ノルム空間の例

- （例）<br>
    n 次元の複素ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/44469680-ff000f80-a662-11e8-9b4b-d78dddceadbb.png) において、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44469744-2060fb80-a663-11e8-8631-6e7cff12570a.png)<br>
    を定義すれば、ノルムの４つの条件式が成り立つので（計算略）、この ![image](https://user-images.githubusercontent.com/25688193/44469772-2d7dea80-a663-11e8-83c1-6eab48dc62ac.png) はノルムである。<br>
    <br>
    又、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44470057-c9a7f180-a663-11e8-8d28-3b68b64d6d41.png)<br>
	もノルムの４つの条件式が成り立つので（計算略）、ノルムとなる。<br>
	
	このように１つの空間に導入し得るノルムは１つとは限らない。<br>


<a id="ID_5-2"></a>

### ◎ ノルム空間における収束、極限と Cauchy 列（基本列）
ノルムの定義から、距離が ”自然に” 構築できるので、ノルム空間における点列の収束の概念を構築できる。<br>

![image](https://user-images.githubusercontent.com/25688193/44844517-1b650300-ac86-11e8-9740-c18397b74c52.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44845191-d93cc100-ac87-11e8-85b4-9c617a70a0f4.png)<br>


<a id="ID_5-3"></a>

### ◎ ノルム空間における完備性
次に、このように定義した Cauchy 列は、収束列であるかを考える。<br>
実数体 R ではこのことは成り立つ。（＝Cauchy 列は、収束列である。）<br>
従って、コーシー列は、実数体 R の中に極限を持ち、このことが、実数体 R の完備性（＝hole がない）となる。<br>

![image](https://user-images.githubusercontent.com/25688193/44507865-1d0f5380-a6e7-11e8-9eb2-0523dae14153.png)<br>

実数体 R は、コーシー列が収束し極限をもつので、完備であったが、<br>
一般のノルム空間は、必ずしも、コーシー列が収束し完備であるとは限らない。<br>

<!--
<a id="ID_x"></a>

### ◎ ノルム空間における Cauchy 列（基本列）と完備性
ノルム空間 X 内の点列 {u_n }={u_1,u_2,…}  が X の収束列であるならば、ノルム空間の４つ目の条件に対応する式は０に近づく。即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/44506078-c2262e00-a6df-11e8-9237-94053a895f5f.png)<br>
書き換えると、<br>
![image](https://user-images.githubusercontent.com/25688193/44506126-e4b84700-a6df-11e8-877d-8d85b606ad1b.png)<br>

ここで、このような条件を満たす点列に対して、以下のような Caucy 列が定義される。<br>
![image](https://user-images.githubusercontent.com/25688193/44507810-f05b3c00-a6e6-11e8-9f6f-713e2c6c4424.png)<br>

次に、このように定義した Cauchy 列は、収束列であるかを考える。<br>
実数体 R ではこのことは成り立つ。（＝Cauchy 列は、収束列である。）<br>
従って、コーシー列は、実数体 R の中に極限を持ち、このことが、実数体 R の完備性（＝hole がない）となる。<br>
![image](https://user-images.githubusercontent.com/25688193/44507865-1d0f5380-a6e7-11e8-9eb2-0523dae14153.png)<br>

実数体 R は、コーシー列が収束し極限をもつので、完備であったが、<br>
一般のノルム空間は、必ずしも、コーシー列が収束し完備であるとは限らない。<br>
-->


<a id="ID_5-4"></a>

### ◎ ノルム空間における写像の連続性
![image](https://user-images.githubusercontent.com/25688193/44960785-7b86ce00-af40-11e8-8d20-04b5b623bfb3.png)<br>

- 【参考】 [距離空間における写像の連続性](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#ID_4-3-3)<br>
<!--
![image](https://user-images.githubusercontent.com/25688193/44855533-3a738d00-aca6-11e8-9851-f1a5531731da.png)<br>
-->

<a id="ID_5-5"></a>

### ◎ ノルムの等価性
２種類のノルムに対して、互いに等価であるということを、<br>
「等価なノルムを用いる限り、点列がある点に収束するか否かの結論は不変」という視点で定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/44864413-8e886c80-acba-11e8-948d-53e45a7cf86c.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44864603-06569700-acbb-11e8-9800-aa3aeb66f289.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/44892843-0342c180-ad22-11e8-9657-ffd7106ec69b.png)<br>

- （証明）<br>
    A) まず、前提準備として以下のようなことを考える。<br>
	ベクトル空間 X の基底 ![image](https://user-images.githubusercontent.com/25688193/44892896-5157c500-ad22-11e8-841a-61f229306a47.png) を１つ固定すると、任意の ![image](https://user-images.githubusercontent.com/25688193/44892929-6df3fd00-ad22-11e8-8133-d1160a56f393.png) は、![image](https://user-images.githubusercontent.com/25688193/44892954-95e36080-ad22-11e8-849d-38d1a4441265.png) と表現でき、![image](https://user-images.githubusercontent.com/25688193/44893055-55381700-ad23-11e8-9450-c263fcde0c58.png) が一意に決まり、ノルムとして、以下のようなノルム（ノルムの公理を満たす）が定まる。![image](https://user-images.githubusercontent.com/25688193/44893200-c6c49500-ad24-11e8-977c-05d9a41d8fc8.png)<br>
    <br>

    B) 次に、ベクトル空間 X に定義可能なノルムを任意に選び、これを関数 ![image](https://user-images.githubusercontent.com/25688193/44893104-ced00500-ad23-11e8-8107-e5da96e7324e.png) で表現することにする。この定理の主張（有限次元空間のノルムはすべて等価）を確認するためには、
    ２つの正数 ![image](https://user-images.githubusercontent.com/25688193/44893230-04c1b900-ad25-11e8-85f0-12804f126e4d.png) が存在して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44893251-1905b600-ad25-11e8-9d73-457932c7e66b.png)<br>
    が成り立つことを示せばよい。<br>
    <br>
        i. ベクトル空間 X の基底 ![image](https://user-images.githubusercontent.com/25688193/44892896-5157c500-ad22-11e8-841a-61f229306a47.png) で表現される任意の ![image](https://user-images.githubusercontent.com/25688193/44893285-4fdbcc00-ad25-11e8-9576-5637c06bdb56.png) に対して、<br>
        その ![image](https://user-images.githubusercontent.com/25688193/44893104-ced00500-ad23-11e8-8107-e5da96e7324e.png) によるノルムは、以下のように変形できる。<br>
        ![image](https://user-images.githubusercontent.com/25688193/44894109-2a50c180-ad29-11e8-8ed7-8ae11e92b47f.png)<br>
        従って、![image](https://user-images.githubusercontent.com/25688193/44894168-6ab03f80-ad29-11e8-9aae-fdd118fca47e.png) と比較すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/44894190-9b907480-ad29-11e8-9fe5-8b248284e119.png)<br>
        が成り立つことが分かる。<br>
        <br>
        ii. ノルムに対して成り立つ性質（![image](https://user-images.githubusercontent.com/25688193/44894430-abf51f00-ad2a-11e8-93b6-697fd2ef2861.png)）より、<br>
        任意の ![image](https://user-images.githubusercontent.com/25688193/44894462-ce873800-ad2a-11e8-8401-302e774a9419.png) に対して、（先の (B.i) の関係式より）<br>
        ![image](https://user-images.githubusercontent.com/25688193/44894523-1dcd6880-ad2b-11e8-801c-ad81eb6843cd.png)<br>
        となる。<br>
        従って、ノルム関数 ![image](https://user-images.githubusercontent.com/25688193/44893104-ced00500-ad23-11e8-8107-e5da96e7324e.png) の写像先を有限にした、関数 ![image](https://user-images.githubusercontent.com/25688193/44901306-fafa7e80-ad41-11e8-9bb1-b570ee588293.png) は、<br>
        ユークリッド空間 ![image](https://user-images.githubusercontent.com/25688193/44898809-e5358b00-ad3a-11e8-8078-3ca2333badc9.png) 上で定義された連続関数になり、<br>
        更に、![image](https://user-images.githubusercontent.com/25688193/44898762-c8995300-ad3a-11e8-9ef4-7cf3e9c5ee40.png) の関係も成り立つ。<br>
        <br>
        iii. ここで、<br>
        ![image](https://user-images.githubusercontent.com/25688193/44900850-b02c3700-ad40-11e8-9c93-f7fda511faa4.png)<br>
        ![image](https://user-images.githubusercontent.com/25688193/44900866-c33f0700-ad40-11e8-92ec-e41b02748f3b.png)<br>
        を定義すると、<br>
        この ![image](https://user-images.githubusercontent.com/25688193/44900904-e23d9900-ad40-11e8-8fa0-4e2b9f6555e3.png) は、![image](https://user-images.githubusercontent.com/25688193/44906024-cfca5c00-ad4e-11e8-827e-f65bd7830e69.png) の有限閉集合なので、先のハイネ・ボネルの被覆定理より、コンパクト集合となり、<br>
        更に、先の最大値・最小値の定理より、関数 ![image](https://user-images.githubusercontent.com/25688193/44900946-04cfb200-ad41-11e8-82ef-6d43cebbfa13.png) は、![image](https://user-images.githubusercontent.com/25688193/44901115-77d92880-ad41-11e8-9aaf-b6c31115b031.png) で ![image](https://user-images.githubusercontent.com/25688193/44900904-e23d9900-ad40-11e8-8fa0-4e2b9f6555e3.png) 内の最小値を持つことが保証されている。<br>
        従って、<br>
        ![image](https://user-images.githubusercontent.com/25688193/44901915-950ef680-ad43-11e8-9101-74df09ff5c50.png)<br>
        の関係が成り立つ。この関係式を変形すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/44902047-ee772580-ad43-11e8-80b7-9083d503d5ff.png)<br>
    <br>
    まとえると、![image](https://user-images.githubusercontent.com/25688193/44902014-d1daed80-ad43-11e8-9ff3-a12952ed5778.png) 及び ![image](https://user-images.githubusercontent.com/25688193/44902047-ee772580-ad43-11e8-80b7-9083d503d5ff.png) の関係より、<br>
	![image](https://user-images.githubusercontent.com/25688193/44902084-0189f580-ad44-11e8-9d97-991fe33a2005.png) の関係が成り立ち、これはノルムの等価性の条件となるので、<br>
	ベクトル空間 X の有限次元空間 ![image](https://user-images.githubusercontent.com/25688193/44906024-cfca5c00-ad4e-11e8-827e-f65bd7830e69.png) の任意のノルムは、等価になるといえる。<br>


<a id="ID_5-6"></a>

### ◎ ノルム空間における閉部分空間、線形多様体、閉凸集合
ノルム空間は、ベクトル空間でもあるので、部分空間や凸集合といった概念を自然に定義することが出来る。
更に距離空間としての性質も兼ね備えているので、開集合や閉集合といった概念も自然に定義することが出来る。このような概念から構築される、（ノルム空間における）閉凸集合、閉部分空間、線形多様体といった概念は、応用上においても極めて重要な概念となる。<br>

![image](https://user-images.githubusercontent.com/25688193/44905992-b2958d80-ad4e-11e8-8d35-5221bd45efd9.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44921490-a674f480-ad7d-11e8-9766-197427c89368.png)<br>

> 【メモ】<br>
> この線形多様体の定義と一般の多様体との関係性は？<br>
> → 線形多様体はアフィン空間のことであり、アフィン空間は最も単純な多様体でもあるため、線形多様体ともいう。<br>

![image](https://user-images.githubusercontent.com/25688193/44922224-c5748600-ad7f-11e8-80c4-2660fef723d5.png)<br>


<a id="ID_5-7"></a>

### ◎ ノルム空間上での写像の微分（ガトー微分とフレッシェ微分）
ここまで、特に無限次元の空間中の点列の収束・極限を考えてきたが、<br>
この収束・極限の概念の延長線上にある微分の概念を、ノルム空間上の写像に対して適用することを考える。<br>

そのためにまず、１変数の実数値関数の微分の定義を簡単に復習する。<br>

![image](https://user-images.githubusercontent.com/25688193/45567811-c20bef00-b895-11e8-8c3a-bc97f3d28acc.png)<br>

![image](https://user-images.githubusercontent.com/25688193/45540933-9dd5f100-b848-11e8-8f35-515acd78d789.png)<br>
- （証明略）図より自明<br>

<br>

先に見てきた「１変数の実数値関数の微分」は、「多変数の実数値関数の微分である全微分・方向微分、勾配」 などに一般化出来る。<br>
更に、これらの微分の概念をユークリッド空間からノルム空間に対して一般化したものとして、「ノルム空間上に定義された写像の微分であるガトー微分/
フレッシェ微分」を見ていく。<br>

これらの概念は、最適化問題や変分法に関する議論を行う際に、都合の良い概念になっており、先に見た、「【性質】（１変数の実数値関数の）微分係数の線形近似による特徴づけ」 と基本的な考えは変わらない。<br>

まず、これらの議論に便利な記法（ランダウの記法）から導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/45551603-70e60600-b869-11e8-8f38-7547b1897ea1.png)<br>


<a id="ID_5-7-1"></a>

#### ☆ ガトー微分
![image](https://user-images.githubusercontent.com/25688193/45589310-4f1a7b00-b95e-11e8-93cb-14c0f7e4ba48.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45585306-3342b500-b91d-11e8-9a3f-e284ee7dd92b.png)<br>

- 【参考】<br>
    - [ガトー微分とフレッシェ微分：方向微分と勾配の一般化 - 初級Mathマニアの寝言](http://ogyahogya.hatenablog.com/entry/2018/08/29/%E3%82%AC%E3%83%88%E3%83%BC%E5%BE%AE%E5%88%86%E3%81%A8%E3%83%95%E3%83%AC%E3%83%83%E3%82%B7%E3%82%A7%E5%BE%AE%E5%88%86%EF%BC%9A%E6%96%B9%E5%90%91%E5%BE%AE%E5%88%86%E3%81%A8%E5%8B%BE%E9%85%8D%E3%81%AE)<br>
    - [方向微分 [物理のかぎしっぽ]](http://hooktail.sub.jp/vectoranalysis/DirectionalDerivative/)<br>
    - [ノルム空間における有界線形作用素](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E6%9C%89%E7%95%8C%E7%B7%9A%E5%BD%A2%E4%BD%9C%E7%94%A8%E7%B4%A0)<br>


<a id="ID_5-7-2"></a>

#### ☆ フレッシェ微分
![image](https://user-images.githubusercontent.com/25688193/45585204-b19e5780-b91b-11e8-95bf-11f33eb74fb9.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45588277-2ccc3180-b94d-11e8-803f-c6f5da3c2e4a.png)<br>


<a id="ID_5-7-3"></a>

#### ☆ ガトー微分とフレッシェ微分の性質
![image](https://user-images.githubusercontent.com/25688193/45585321-7e5cc800-b91d-11e8-8425-50a3eaf529ed.png)<br>
- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45588220-5042ac80-b94c-11e8-8e88-9a4ff7bc6160.png)<br>
- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45588387-0b6c4500-b94f-11e8-9d7d-afcb1d505c72.png)<br>
- （証明）<br>
    - (a) の証明<br>
        フレッシェ微分の定義<br>
        ![image](https://user-images.githubusercontent.com/25688193/45588507-d234d480-b950-11e8-9a73-6440c4813d3b.png)<br>
        を書き換えると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45588511-e1b41d80-b950-11e8-92e6-86665ceaaf65.png)<br>
        となるようなある有界線形写像 ![image](https://user-images.githubusercontent.com/25688193/45588531-28a21300-b951-11e8-91fa-67e27b3862ed.png) が存在し、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45588581-e3caac00-b951-11e8-855e-0b4a0b327243.png)<br>
        となるので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45589232-45444800-b95d-11e8-9fcf-56d3bc25767c.png)<br>
        写像の連続性の条件（写像先での収束 ![image](https://user-images.githubusercontent.com/25688193/45589155-ec27e480-b95b-11e8-873c-c617f5b3f61b.png) ）を満たすので、<br>
        写像 Φ は連続である。<br>
        <br>
    - (b) の証明<br>
        点 ![image](https://user-images.githubusercontent.com/25688193/45589397-ed5b1080-b95f-11e8-882d-b0234a7156cf.png) における写像 Φ のフレッシェ微分 ![image](https://user-images.githubusercontent.com/25688193/45589407-006de080-b960-11e8-8e50-bc548bed3074.png) を用いると、<br>
        任意の![image](https://user-images.githubusercontent.com/25688193/45589415-1aa7be80-b960-11e8-8c33-fffa7de12499.png) と ![image](https://user-images.githubusercontent.com/25688193/45589422-2abf9e00-b960-11e8-9769-76ec2d0e0dfd.png) に対して、<br>
        ガトー微分の定義<br>
        ![image](https://user-images.githubusercontent.com/25688193/45589429-3dd26e00-b960-11e8-939f-bdaa734f736a.png)<br>
        の左辺の lim の中身は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45589434-55a9f200-b960-11e8-8579-c090cb890240.png)<br>
        となり、ガトー微分の条件<br>
        ![image](https://user-images.githubusercontent.com/25688193/45589441-812cdc80-b960-11e8-94bc-1186d5a2b02a.png)<br>
        が成り立つので、フレッシェ微分 ![image](https://user-images.githubusercontent.com/25688193/45589449-9570d980-b960-11e8-8e04-c464d1e00f31.png) は、ガトー微分にもなる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45590250-b1c84280-b96f-11e8-8b5b-64c2d8cd0580.png)

>【メモ】<br>
> ノルム空間 Y が内積空間である必要性は？<br>
> → 一般化された平均値の定理の写像先の対象空間が内積空間であるため。<br>

- （証明）<br>
    D は開集合で、ガトー導関数 Φ′ は連続なので、<br>
    任意の ε>0 に対して、十分小さな開球<br>
    ![image](https://user-images.githubusercontent.com/25688193/45595059-bf69e080-b9e0-11e8-8328-6795aab264ed.png)<br>
    が存在して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45595084-31dac080-b9e1-11e8-9a87-c46101682378.png)<br>
	となる。（下図参照）
    ![image](https://user-images.githubusercontent.com/25688193/45594989-38683880-b9df-11e8-8c0a-6700a7be7cea.png)<br>
    又、任意の ![image](https://user-images.githubusercontent.com/25688193/45596817-04037500-b9fd-11e8-9589-7be1f35b7f75.png) に対して、一般化された平均値の定理の関係（計算略）<br>
    ![image](https://user-images.githubusercontent.com/25688193/45596821-18e00880-b9fd-11e8-8cb9-967937732afa.png)<br>
    が適用出来るので、この式を変形すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45596829-2ac1ab80-b9fd-11e8-8044-582ef3a878be.png)<br>
    従って、先の ![image](https://user-images.githubusercontent.com/25688193/45596845-73796480-b9fd-11e8-8c3a-6f2d39a20214.png) の関係と合わせると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45596848-85f39e00-b9fd-11e8-9502-8a4ea2d38045.png)<br>
    ガトー微分 ![image](https://user-images.githubusercontent.com/25688193/45596914-bab42500-b9fe-11e8-90f0-69e9e6e89458.png) は、フレッシェ微分の条件<br>
    ![image](https://user-images.githubusercontent.com/25688193/45596935-0961bf00-b9ff-11e8-8a07-a8624ca69c60.png)<br>
    も満たすことになり、この場合、ガトー微分はフレッシェ微分でもある。<br>


<a id="ID_5-7-4"></a>

#### ☆ ガトー微分とフレッシェ微分の例
> 記載中...


<a id="ID_6"></a>

## ■ 内積空間
次に、実数体 R 上のベクトル空間に内積を構築することを考える。<br>
この内積を用いると、ベクトル空間の要素（点）間に直交性などの幾何学的構造を持ち込むことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/44925593-cb6f6480-ad89-11e8-91de-e4abf8523652.png)<br>


<a id="ID_6-1"></a>

### ◎ 内積空間におけるベクトルの直交性
![image](https://user-images.githubusercontent.com/25688193/44925622-d9bd8080-ad89-11e8-9d4a-adb9c86c635d.png)<br>


<a id="ID_6-2"></a>

### ◎ 内積空間の性質と内積から誘導されるノルム
内積空間 X の任意の ![image](https://user-images.githubusercontent.com/25688193/44941811-43687980-ade0-11e8-80ef-94b721dfb524.png) に対して、![image](https://user-images.githubusercontent.com/25688193/44941844-ee793300-ade0-11e8-963b-b191f96c492e.png) を定義するとき、この写像 ![image](https://user-images.githubusercontent.com/25688193/44941848-0b156b00-ade1-11e8-9095-47fca2878f90.png) は、ノルムの公理を満たし、ノルムとなる。<br>
このとこを内積から誘導される（＝自然に道簿行かれる）ノルムというが、このノルムの公理を満たすことを示すために、以下の性質が使用される。<br>

![image](https://user-images.githubusercontent.com/25688193/44941979-d0143700-ade2-11e8-9135-6ce7834c6d13.png)<br>
- （証明略）<br>

![image](https://user-images.githubusercontent.com/25688193/44942057-7f9dd900-ade4-11e8-842a-7df1e49d26d5.png)<br>
- （証明略）<br>

![image](https://user-images.githubusercontent.com/25688193/44942070-b542c200-ade4-11e8-825c-b0b561922960.png)
- （証明略）<br>

この三平方の定理は、任意の内積空間で成り立つが、n→∞ として級数を無限和、即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/44942079-e28f7000-ade4-11e8-8998-80d3afeec3c2.png)<br>
とした場合には、完備性の条件を課さなければならない（級数和が収束するため）。<br>

![image](https://user-images.githubusercontent.com/25688193/44942232-6565fa00-ade8-11e8-9690-404f4b6a3245.png)<br>
- （証明略）<br>

ここで、内積空間 ![image](https://user-images.githubusercontent.com/25688193/44942349-baeed680-ade9-11e8-9ca8-f7a578df0cd3.png) において、任意の ![image](https://user-images.githubusercontent.com/25688193/44942352-cb9f4c80-ade9-11e8-8205-bc45e188cc9d.png) に対して ![image](https://user-images.githubusercontent.com/25688193/44942354-dc4fc280-ade9-11e8-958d-8f0eb5d00b65.png) がノルムの公理を満たし、ノルムになることを示す。<br>
まず、公理の条件１（ ![image](https://user-images.githubusercontent.com/25688193/44942361-f9849100-ade9-11e8-9e64-4340c78d62af.png) ）と条件２（ ![image](https://user-images.githubusercontent.com/25688193/44942367-115c1500-adea-11e8-9e65-ece98f880b27.png) ）は明らかである。<br>
条件３（ ![image](https://user-images.githubusercontent.com/25688193/44942369-2a64c600-adea-11e8-9645-d0fefbd0c777.png) ）は、![image](https://user-images.githubusercontent.com/25688193/44942375-41a3b380-adea-11e8-9427-89789b912bb6.png) の関係より成り立つことが分かる。<br>
条件４（ ![image](https://user-images.githubusercontent.com/25688193/44942382-74e64280-adea-11e8-9f91-0ae040565ba5.png) ）は、三角不等式となっており、先の（内積空間における）三角不等式の関係から成り立つ。（尚、この三角不等式自体は、シュワルツの不等式から導かれる。）<br>
従って、ノルムの公理が成り立つので、![image](https://user-images.githubusercontent.com/25688193/44942354-dc4fc280-ade9-11e8-958d-8f0eb5d00b65.png) はノルムである。<br>
そして、このようなノルムを、**内積から誘導されるノルム** という。<br>


<a id="ID_6-3"></a>

### ◎ 内積空間における正規直交系
![image](https://user-images.githubusercontent.com/25688193/44946011-b39dec00-ae2e-11e8-9557-325771dc9dc5.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44946017-c44e6200-ae2e-11e8-81d1-4ab4d5f88cda.png)<br>

ここで、内積空間 X が無限次元の場合には、一般に「極大な正規直交系」は、内積空間 X の基底（線形独立なベクトルの極大系）にはならない。<br>
「極大な正規直交系」と「内積空間の基底」が同じ無限次元のベクトルであっても、「極大な正規直交系」の濃度は、「内積空間 X の基底（線形独立なベクトルの極大系）」に比べて小さくなるのが一般的である。<br>

又、この極大な正規直交系は、内積空間が完備であれば（＝ヒルベルト空間においては）、完全正規直交基底となる。<br>

- 【参考】完全直交系 : [My_NoteBook/数学/数学_フーリエ解析_Note.md/直交級数としてのフーリエ級数](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E3%83%95%E3%83%BC%E3%83%AA%E3%82%A8%E8%A7%A3%E6%9E%90_Note.md#ID_4)<br>


<a id="ID_6-3-1"></a>

#### ☆ グラム・シュミットの直交化法
![image](https://user-images.githubusercontent.com/25688193/44955677-4fdcf700-aef2-11e8-953f-e551f0c186b9.png)<br>

- 【参考】 [【線形空間編】シュミットの直交化法を画像で直感的に解説](https://oguemon.com/study/linear-algebra/gram-schmidt/)<br>


<a id="ID_6-3-2"></a>

#### ☆ ベッセルの不等式
![image](https://user-images.githubusercontent.com/25688193/44955992-9f71f180-aef7-11e8-9c79-cabbe0c0230b.png)<br>

> 【メモ】<br>
> フーリエ級数の平均収束から導出されるベッセルの不等式と、この内積空間における正規直交系視点のベッセルの不等式が結びつく。<br>

- 【参考】[フーリエ級数におけるベッセルの不等式](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E3%83%95%E3%83%BC%E3%83%AA%E3%82%A8%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%95%E3%83%BC%E3%83%AA%E3%82%A8%E7%B4%9A%E6%95%B0%E3%81%AE%E5%8F%8E%E6%9D%9F%E6%80%A7)

- 【参考】[２．フーリエ解析入門(２) | Besselの不等式とParsevalの等式](http://math-lab.main.jp/fourier02.html)
    - 【問題2.2】の(1)と(2)、2.3 Besselの不等式とParsevalの等式とで、フーリエ級数の平均収束から導出されるベッセルの不等式と、正規直交系視点のベッセルの不等式が結びつく。<br>

<a id="ID_7"></a>

## ■ バナッハ空間 [Banach space]
先に述べたように、世の中には、有限回の計算で完全な解が求まらないような問題が多く存在する。<br>
このような問題では、厳密解への収束が保証される数列（点列）が利用されることになる。<br>
そういったケースでは、収束先が保証されるように、空間に完備性の構造を課した空間を考えることになる。<br>

![image](https://user-images.githubusercontent.com/25688193/45199412-7b6f3100-b2a6-11e8-8a3b-a1d74334ba8b.png)<br>

![image](https://user-images.githubusercontent.com/25688193/45199525-1d8f1900-b2a7-11e8-8a61-52ae9dc98b9c.png)<br>

- 【参考】[ノルム空間の完備性](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#ID_5-3)


<a id="ID_7-1"></a>

### ◎ バナッハ空間の例

- （例）バナッハ空間の例（有限次元ベクトル空間）<br>
    ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/45046215-7779be00-b0b0-11e8-8be8-3093850e941c.png) は、任意の種類のノルムのノルム空間で完備であり、<br>
    バナッハ空間であることを示す。<br>

	- 完備であることを示すためには、ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/45046215-7779be00-b0b0-11e8-8be8-3093850e941c.png) における任意のコーシー列が収束し、極限を持つことを示せばよい。<br>
        まずは、簡単のため１次元のベクトル空間 R で考える。<br>
        コーシー列を ![image](https://user-images.githubusercontent.com/25688193/45071170-ef2b0580-b10f-11e8-94b4-397f58010905.png) と記述すると、この点列は有界である（コーシー列の性質）ので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45046359-dfc89f80-b0b0-11e8-9375-575d5dfe998b.png) から構成される点列 ![image](https://user-images.githubusercontent.com/25688193/45071190-0833b680-b110-11e8-8b88-553593ae2452.png) も有界な単調減少点列となり、ある有限な確定値に収束する。<br>
        従って、![image](https://user-images.githubusercontent.com/25688193/45071220-2c8f9300-b110-11e8-8adc-5edb4c0dea76.png) と書ける。<br>
    - 次に、![image](https://user-images.githubusercontent.com/25688193/45046748-118e3600-b0b2-11e8-9c2b-8d9a8ae2b41d.png) となることを示す。<br>
        コーシー列 ![image](https://user-images.githubusercontent.com/25688193/45077847-45587280-b129-11e8-8c5c-51de4be224c5.png) に関しては、任意の正数 ε に対して、ある正の正数 ![image](https://user-images.githubusercontent.com/25688193/45077885-69b44f00-b129-11e8-8fbb-79de07bb28ea.png) が存在し、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45077930-88b2e100-b129-11e8-99ef-f2c8c7679e1c.png)<br>
        特に、上限 sup で定義されている ![image](https://user-images.githubusercontent.com/25688193/45077960-a41dec00-b129-11e8-93ab-be8e914b690d.png) で書き換えると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45077994-bc8e0680-b129-11e8-8e5c-a76d58d18491.png)<br>
        更に、n→∞ とすると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45078588-60c47d00-b12b-11e8-8d14-d032c22c345c.png)<br>
        を得る。（途中計算略）<br>
        <br>
        一方で、先の不等号 ![image](https://user-images.githubusercontent.com/25688193/45077885-69b44f00-b129-11e8-8fbb-79de07bb28ea.png) が上限であることを示しており、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45079253-ff9da900-b12c-11e8-9fd1-541372ef98d9.png) が成り立つことがわかる。<br>
        更に、n→∞ とすると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45079284-15ab6980-b12d-11e8-928e-ab2a5884fb94.png)<br>
        従って、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45079308-29ef6680-b12d-11e8-9692-e18565287f30.png)<br>
        となるので、結果として、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45079347-48edf880-b12d-11e8-9b0f-de9c64735c10.png) を得る。<br>
        即ち、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45081177-98cebe80-b131-11e8-9f2b-11fedd13e218.png)<br>
        のように収束することが示される。<br>
    - 次に、先の上限 sup を下限 inf に置き換えて、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45081006-24941b00-b131-11e8-8ab4-f3d2f954bbd3.png) から構成される点列 ![image](https://user-images.githubusercontent.com/25688193/45081036-3fff2600-b131-11e8-910b-523f23d28292.png) が有界な単調増加点列となり、ある確定値に収束する。<br>
        即ち、コーシー列 ![image](https://user-images.githubusercontent.com/25688193/45081126-75a40f00-b131-11e8-852b-786bc34a21b6.png) の下極限 ![image](https://user-images.githubusercontent.com/25688193/45081280-d59ab580-b131-11e8-80ba-735ec982fa58.png) となることを利用すると、先の証明と同様にして、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45081736-d08a3600-b132-11e8-809e-16050296bed3.png)<br>
        となる。（途中計算略）<br>
        最後に、コーシー列の収束先の一意性の性質より、この極限値は一致し、α=β となることがわかる。<br>
    - 一般の N 次元ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/45081839-fe6f7a80-b132-11e8-9d10-88f2775d0629.png) に対しても、同様の議論が成り立ち、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45081839-fe6f7a80-b132-11e8-9d10-88f2775d0629.png) における任意のコーシー列<br>
        ![image](https://user-images.githubusercontent.com/25688193/45082508-725e5280-b134-11e8-958c-244ad93ebaeb.png)<br>
	    が収束し、極限を持つので、<br>
	    N 次元ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/45081839-fe6f7a80-b132-11e8-9d10-88f2775d0629.png) は、完備であり、バナッハ空間となる。<br>

<br>

- （例）バナッハ空間の例（距離空間 ![image](https://user-images.githubusercontent.com/25688193/45082619-adf91c80-b134-11e8-8532-67f2d5202b03.png)）<br>
    距離空間 ![image](https://user-images.githubusercontent.com/25688193/45082619-adf91c80-b134-11e8-8532-67f2d5202b03.png) は、バナッハ空間であることを示す。<br>
    ![image](https://user-images.githubusercontent.com/25688193/45083357-8dca5d00-b136-11e8-9470-eb0a111801c7.png)<br>
    - 距離空間 ![image](https://user-images.githubusercontent.com/25688193/45082619-adf91c80-b134-11e8-8532-67f2d5202b03.png) は、完備距離空間である。（証明略）<br>
    又、任意の要素に対して、和とスカラー倍の演算（線形結合）が成り立つので、ベクトル空間でもある。<br>
    更に、この距離 ![image](https://user-images.githubusercontent.com/25688193/45083151-f9f89100-b135-11e8-93e2-979af6abb402.png) から誘導される<br>
    ![image](https://user-images.githubusercontent.com/25688193/45083397-ab97c200-b136-11e8-94a0-f319f430abf8.png)<br>
	は、ノルムの公理を満たすので、ノルムとなり、ノルム空間になる。<br>
	そして、その完備性から、バナッハ空間になる。<br>

<!--
- （例）<br>
    閉区間 [a,b] 内の複数空間 C[a,b] は、ノルム<br>
    ![image](https://user-images.githubusercontent.com/25688193/44508696-2b12a380-a6ea-11e8-8b80-66ec7343808d.png)<br>
    に関して、完備であるか調べる。<br>
    <br>
    > 記載中...
-->


<a id="ID_7-2"></a>

### ◎ 有界線形写像全体の集合が作るバナッハ空間と共役空間
有界線形作用素としては様々なもの（行列、微分、積分、フーリエ変換など）が考えられるが、これらの有界線形作用素をかき集めて空間とみなすと、(内積空間やノルム空間を考えたときと同様に）この空間内でのノルム（＝有界線形作用素ノルム）が考えられる。<br>
そして、この有界線形写像全体はベクトル空間となるが、この作用素ノルムによってノルム空間になる。<br>
（[【参考】有界線形写像全体の集合が作るノルム空間](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E6%9C%89%E7%95%8C%E7%B7%9A%E5%BD%A2%E5%86%99%E5%83%8F%E5%85%A8%E4%BD%93%E3%81%8C%E4%BD%9C%E3%82%8B%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93)）<br>
更に、以下の定理で示すように、有界線形写像の写像先がバナッハ空間である場合においては、
この作用素ノルムにより構築されるノルム空間は、完備であり、バナッハ空間にもなる。<br>

![image](https://user-images.githubusercontent.com/25688193/45089152-421faf80-b146-11e8-9d2e-d7f839747de9.png)<br>
- （証明略）証明の方針のみ<br>
	    B(X,Y) がバナッハ空間であることを示すには、B(X,Y) が完備になることを示せばよい。<br>
	    そして、完備であることを示すためには、B(X,Y) における任意のコーシー列 ![image](https://user-images.githubusercontent.com/25688193/45089454-341e5e80-b147-11e8-85ea-55d504a66dd1.png)  が収束し、極限を持つことを示せばよい。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45091389-40a5b580-b14d-11e8-83e0-d2ccce407df3.png)<br>

> 【メモ】<br>
> なぜ、数あるバナッハ空間の中でも、わざわざ有界線形汎関数全体上で共役空間を定義しているのか？<br>
> → （Wikipedia から引用）「一般に双対空間には、代数的双対と連続的双対の二種類が用いられており、代数的双対は任意のベクトル空間に対して定義することができるが、位相線型空間を扱うときは代数的双対よりもその部分線型空間として、連続線型汎関数全体の成す連続的双対空間を考えるのが自然である。」<br>

- 【参考】
    - [作用素ノルム](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E4%BD%9C%E7%94%A8%E7%B4%A0%E3%83%8E%E3%83%AB%E3%83%A0)
    - [有界線形写像全体の集合が作るノルム空間](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E6%9C%89%E7%95%8C%E7%B7%9A%E5%BD%A2%E5%86%99%E5%83%8F%E5%85%A8%E4%BD%93%E3%81%8C%E4%BD%9C%E3%82%8B%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93)
    - [物理のかぎしっぽ | 双対空間](http://hooktail.sub.jp/vectoranalysis/DualSpace/)
    - [双対ベクトル空間](https://ja.wikipedia.org/wiki/%E5%8F%8C%E5%AF%BE%E3%83%99%E3%82%AF%E3%83%88%E3%83%AB%E7%A9%BA%E9%96%93)
    - [檜山正幸のキマイラ飼育記 | 本日の線形代数：双対空間と共役空間](http://d.hatena.ne.jp/m-hiyama/20080911/1221106941)


<a id="ID_7-3"></a>

### ◎ 一様有界性の定理
先に見たように、関数解析の線形理論には、corner stones （礎石、基本理念）と呼ばれる４大定理（一様有界性の定理、開写像定理、閉グラフ定理、ハーン・バナッハの定理）が存在する。<br>
この内、ハーン・バナッハの定理以外の３定理は、いずれも完備性がポイントとなっており、ベールの定理から導かれる。<br>
ここでは、まず、１つ目の一様有界性の定理を見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/45143431-4905fb00-b1f6-11e8-9652-515f54e0f038.png)<br>

> 【メモ】<br>
> この一様有界性の定理は、バナッハ空間からノルム空間への有界線形関数の各点列での有界性が、そのまま一様有界性（共通の有界づける定数の存在）になることを主張している。<br>

- （証明）<br>
    - まず、有界線形写像の点列のインデックス n∈N とノルム値の上のしきい値 k∈N に依存する<br>
        バナッハ空間 X の部分集合<br>
        ![image](https://user-images.githubusercontent.com/25688193/45143623-b6b22700-b1f6-11e8-9911-8017c404bc4c.png)<br>
        を導入する。<br>
    - バナッハ空間 X からノルム空間 Y への有界線形写像 ![image](https://user-images.githubusercontent.com/25688193/45108347-5334e480-b177-11e8-9e99-329409f32755.png) が、連続写像（＝区間幅から区間幅への写像）であること、<br>
        又、![image](https://user-images.githubusercontent.com/25688193/45108473-a4dd6f00-b177-11e8-97ad-eec552ade6f6.png) の関係を利用すると、<br>
	    バナッハ空間 X の部分集合 ![image](https://user-images.githubusercontent.com/25688193/45108404-765f9400-b177-11e8-8bbe-a4792438e531.png) が閉部分集合であることが導かれる。（途中計算略）<br>
	    更に、有界線形写像の点列のインデックス n∈N に対しての積集合<br>
        ![image](https://user-images.githubusercontent.com/25688193/45143665-d34e5f00-b1f6-11e8-8a54-5855f2835bd1.png)<br>
        も閉集合になることが導びかれる。（途中計算略）<br>
    - このバナッハ空間 X の部分積集合 ![image](https://user-images.githubusercontent.com/25688193/45108701-511f5580-b178-11e8-89b0-d449e4de12d3.png) が閉集合であることと、<br>
        定理の条件（任意の ![image](https://user-images.githubusercontent.com/25688193/45109246-f4249f00-b179-11e8-89ab-bf7452e615a7.png) に対して、ある正数 M>0 が存在）より、<br>
        任意の ![image](https://user-images.githubusercontent.com/25688193/45109246-f4249f00-b179-11e8-89ab-bf7452e615a7.png) に対して、ある正数 ![image](https://user-images.githubusercontent.com/25688193/45109287-0e5e7d00-b17a-11e8-86d5-c3903d95c7df.png) が存在し、<br>
        更に、![image](https://user-images.githubusercontent.com/25688193/45109324-27672e00-b17a-11e8-9181-3f95a62648ab.png) に対して ![image](https://user-images.githubusercontent.com/25688193/45109346-3a79fe00-b17a-11e8-8131-77ad019c119e.png) となるので、<br>
        ベールの定理が適用できる条件<br>
        ![image](https://user-images.githubusercontent.com/25688193/45108733-65fbe900-b178-11e8-8b2f-79b00b723249.png)<br>
        が導びかれる。<br>
    - ベールの定理より、部分集合 ![image](https://user-images.githubusercontent.com/25688193/45146124-2deab980-b1fd-11e8-9938-30e4d65579c8.png) は少なくとも１つの内点を持つので、<br>
        少なくとも１つの（内点を与える）正のインデックス ![image](https://user-images.githubusercontent.com/25688193/45146160-46f36a80-b1fd-11e8-927a-090f4d12ece5.png) に対して、<br>
        ある内点 ![image](https://user-images.githubusercontent.com/25688193/45146242-70ac9180-b1fd-11e8-8bcb-1ae8fa4e714b.png) と r>0 が存在して、![image](https://user-images.githubusercontent.com/25688193/45146392-c6813980-b1fd-11e8-8940-3f6e5ab57a89.png) となり、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45146335-a6517a80-b1fd-11e8-9b87-e05b97f77402.png)<br>
		を得る。<br>
		このことから、全ての n∈N について、以下の関係が成り立つ。<br>
        ![image](https://user-images.githubusercontent.com/25688193/45146459-def15400-b1fd-11e8-89e5-e6a730cc507b.png)<br>
        更に、作用素ノルムの表現の等価性の関係<br>
        ![image](https://user-images.githubusercontent.com/25688193/45146848-96866600-b1fe-11e8-95d6-e0db0af1c408.png)<br>
        から、全ての n に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45146873-a736dc00-b1fe-11e8-92e1-20fc1b41ddd2.png)<br>
        が成り立つので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45146905-b7e75200-b1fe-11e8-8b5c-fed8b8ffa400.png)<br>
        となる。<br>
        従って、全ての作用素ノルムを有界づける共通の定数 M が存在するので、バナッハ空間からノルム空間への有界線形写像全体の点列は一様有界である。<br>

- 【参考】
    - [ベールの定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%99%E3%83%BC%E3%83%AB%E3%81%AE%E5%AE%9A%E7%90%86)
    - [一様有界性 [Wikipedia]](https://ja.wikipedia.org/wiki/%E4%B8%80%E6%A7%98%E6%9C%89%E7%95%8C%E6%80%A7)


<a id="ID_7-4"></a>

### ◎ 開写像定理
次に、関数解析の線形理論の４大定理の２つ目の定理として、開写像定理をみていく。<br>
この定理は、有界線形写像により開集合が開集合へ写されるための条件を述べている。<br>
更に、定理の後半部分は、有界線形写像が全単射の場合には、その逆写像も有界線形写像になることを示している。<br>

![image](https://user-images.githubusercontent.com/25688193/45153628-a3f81c00-b20f-11e8-9a6b-816971200671.png)<br>

- （証明略）ベールの定理を利用して証明できる<br>


<a id="ID_7-5"></a>

### ◎ 閉グラフ定理
次に、関数解析の線形理論の４大定理の２つ目の定理として、閉グラフ定理をみていく。<br>
この定理は、線形写像の有界性を示すための定理になっており、微分方程式の解析や量子力学などで広く応用されている。<br>

![image](https://user-images.githubusercontent.com/25688193/45208471-9f8e3a80-b2c5-11e8-827d-0f1e9d059cc1.png)<br>

> 【メモ】<br>
> ノルム空間 X からノルム空間 Y への連続線型作用素 A のグラフ<br>
> ![image](https://user-images.githubusercontent.com/25688193/45208511-b765be80-b2c5-11e8-9d31-4cd78f904701.png)<br>
> が閉集合であることは容易に確認できるが、<br>
> その逆（閉集合⇒有界線形写像）を主張するのが閉グラフ定理であり、作用素の連続性の証明に多用される。<br>

- （証明略）ベールの定理を利用して証明できる<br>


<a id="ID_7-6"></a>

### ◎ バナッハ空間における基底（シャウダー基底）
線形代数におけるベクトル空間の基底は、有限次元で議論されてきた。<br>
一方、関数解析で扱う無限次元のベクトル空間の場合は、線形独立な無限個のベクトルの組の線形結合を扱うので、収束・極限の概念が必要になってくるのが、線形代数での基底の議論と異なる点である。<br>

![image](https://user-images.githubusercontent.com/25688193/45221443-6e753080-b2ec-11e8-8d66-2cc119580749.png)<br>


<a id="ID_8"></a>

## ■ ヒルベルト空間 [Hilbert space]
先に述べたように、世の中には、有限回の計算で完全な解が求まらないような問題が多く存在する。<br>
このような問題では、厳密解への収束が保証される数列（点列）が利用されることになる。<br>
そういったケースでは、収束先が保証されるように、空間に完備性の構造を課した空間を考えることになる。<br>

![image](https://user-images.githubusercontent.com/25688193/45199568-5a5b1000-b2a7-11e8-9523-4e552f6aab91.png)<br>

![image](https://user-images.githubusercontent.com/25688193/45199581-765eb180-b2a7-11e8-9171-6a50764a667c.png)<br>


<!--
## ■ （旧）ヒルベルト空間 [Hilbert space]
> 要書き換え...

ユークリッド空間では、先に定義した長さ（ノルム）の概念の他に、２つのベクトル間の角度を表す内積の概念も兼ね備える。<br>
この内積の概念は、例えば、３次元空間では、<br>
![image](https://user-images.githubusercontent.com/25688193/44511871-c52b1980-a6f3-11e8-8e51-3bf5afd7c130.png)<br>
のように、ノルムが内積を通じて定められる。<br>
このように、ノルムが内積を通じて定められるようなバナッハ空間を、ヒルベルト空間という。<br>

![image](https://user-images.githubusercontent.com/25688193/44518819-38d62200-a706-11e8-829a-10f7967dc564.png)<br>

ここで、ベクトル空間 X に内積が定義されている時、<br>
任意の ![image](https://user-images.githubusercontent.com/25688193/44531321-78fbcb80-a72b-11e8-8542-d431a3ab53a2.png) に対して、![image](https://user-images.githubusercontent.com/25688193/44531371-90d34f80-a72b-11e8-952a-9bf26f7b9318.png) がノルムの４つの条件を満たし、ノルムになることを示す。<br>
まず、条件１（ ![image](https://user-images.githubusercontent.com/25688193/44531471-d7c14500-a72b-11e8-8eab-e85687dd6ade.png) ）と条件２（ ![image](https://user-images.githubusercontent.com/25688193/44531513-ec9dd880-a72b-11e8-80a8-ca09b03c8b8b.png) ）は明らかである。<br>
条件３（ ![image](https://user-images.githubusercontent.com/25688193/44531898-d0e70200-a72c-11e8-95af-f2c755fb5bd8.png) ）は、<br>
![image](https://user-images.githubusercontent.com/25688193/44532128-523e9480-a72d-11e8-9e05-3b6cd795a874.png)<br>
の関係より成り立つことが分かる。<br>
条件４（ ![image](https://user-images.githubusercontent.com/25688193/44531818-a137fa00-a72c-11e8-9500-8b314f5da5ec.png) ）は、三角不等式であるが、この３角不等式を証明するにあって以下のシュワルツの不等式と利用する。<br>

![image](https://user-images.githubusercontent.com/25688193/44531557-0a6b3d80-a72c-11e8-89f9-e0e0a8001433.png)<br>
    （証明略）<br>

このシュワルツの不等式より、ノルムの４つ目の条件は、<br>
![image](https://user-images.githubusercontent.com/25688193/44532622-78b0ff80-a72e-11e8-8af4-621f813582a6.png)<br>
従って、ノルムの４つの条件が成り立つので、![image](https://user-images.githubusercontent.com/25688193/44532645-89fa0c00-a72e-11e8-9c5f-1468a9db78e1.png) はノルムである。<br>

![image](https://user-images.githubusercontent.com/25688193/44565493-53120d80-a7a3-11e8-86f1-0446f8ddec71.png)<br>

この定義から分かるように、ヒルベルト空間はバナッハ空間の一種であり、<br>
ヒルベルト空間の位相構造は、バナッハ空間と同様にしてノルムから構築されている。<br>

![image](https://user-images.githubusercontent.com/25688193/44565319-77211f00-a7a2-11e8-9ff2-157b150aae9d.png)<br>

-->

<a id="ID_8-1"></a>

### ◎ ヒルベルト空間の例

- （例）N 次元ユークリッド空間<br>
    N 次元ユークリッド空間<br>
    ![image](https://user-images.githubusercontent.com/25688193/45200576-80cf7a00-b2ac-11e8-9b0c-d0ae76de35ae.png) において、任意の ![image](https://user-images.githubusercontent.com/25688193/45200657-c68c4280-b2ac-11e8-8091-5df4225a1b07.png) に対して、<br>
	内積を、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45200799-7e215480-b2ad-11e8-8b60-daef005efc72.png)<br>
    内積から誘導されるノルム<br>
    ![image](https://user-images.githubusercontent.com/25688193/45200826-972a0580-b2ad-11e8-9319-539c53b80464.png)<br>
    を定義すると、ヒルベルト空間になることを示す。<br>
    <br>
    - 先のバナッハ空間の例（[参照](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%90%E3%83%8A%E3%83%83%E3%83%8F%E7%A9%BA%E9%96%93%E3%81%AE%E4%BE%8B)）より、N 次元ベクトル空間は、バナッハ空間である。<br>
    従って、ユークリッド空間はバナッハ空間であり、<br>
    更に、内積 ![image](https://user-images.githubusercontent.com/25688193/45200799-7e215480-b2ad-11e8-8b60-daef005efc72.png) を定義しているので、ヒルベルト空間になる。<br>
    
<br>

- （例）距離空間 ![image](https://user-images.githubusercontent.com/25688193/45201471-731bf380-b2b0-11e8-9f17-9c0e6fcfc356.png)<br>
    距離空間 ![image](https://user-images.githubusercontent.com/25688193/45082619-adf91c80-b134-11e8-8532-67f2d5202b03.png) の p=2 のときの距離空間 ![image](https://user-images.githubusercontent.com/25688193/45201471-731bf380-b2b0-11e8-9f17-9c0e6fcfc356.png) は、ヒルベルト空間であることを示す。<br>
    ![image](https://user-images.githubusercontent.com/25688193/45201505-a52d5580-b2b0-11e8-926f-445009032369.png)<br>
    <br>
    - 先のバナッハ空間の例（[参照](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%90%E3%83%8A%E3%83%83%E3%83%8F%E7%A9%BA%E9%96%93%E3%81%AE%E4%BE%8B)）より、この距離空間 ![image](https://user-images.githubusercontent.com/25688193/45082619-adf91c80-b134-11e8-8532-67f2d5202b03.png) は、バナッハ空間である。<br>
        従って、p=2 のときの距離空間 ![image](https://user-images.githubusercontent.com/25688193/45201471-731bf380-b2b0-11e8-9f17-9c0e6fcfc356.png) もバナッハ空間である。<br>
    - ここで、p=2 のときの内積とノルムを<br>
        ![image](https://user-images.githubusercontent.com/25688193/45201595-1836cc00-b2b1-11e8-9ea2-b053db2a09b7.png)<br>
        のように定義すると、<br>
        これらはノルムと内積の公理を満たすので、![image](https://user-images.githubusercontent.com/25688193/45201471-731bf380-b2b0-11e8-9f17-9c0e6fcfc356.png) は、ヒルベルト空間となる。<br>


<a id="ID_8-2"></a>

### ◎ （旧）３平方の定理や中線定理
> 要書き換え...

ヒルベルト空間においては、以下のような３平方の定理や中線定理が成り立つ。<br>

![image](https://user-images.githubusercontent.com/25688193/44566141-d41ed400-a7a6-11e8-86a9-c370cd2db070.png)<br>

この３平方の定理は、任意の内積空間で成り立つが、n → ∞ として級数を無限和、即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/44566225-4f808580-a7a7-11e8-8475-9083683bf956.png)<br>
とした場合には、完備性の条件を課さなければならない（級数和が収束するため）。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/44568472-e7836c80-a7b1-11e8-89c2-63ae4db871e5.png)<br>

この中線定理が成り立つ時、２つのベクトル ![image](https://user-images.githubusercontent.com/25688193/44566449-9753dc80-a7a8-11e8-87f7-04b594781c87.png) は、内積の条件を満たすので、内積となる。<br>
更に、![image](https://user-images.githubusercontent.com/25688193/44566466-b488ab00-a7a8-11e8-9dca-1e1a237722f9.png) と一致するので、<br>
**バナッハ空間がヒルベルト空間であるための必要十分条件は、（バナッハ空間を構築している）ノルムに対し、中線定理が成り立っていることである。**<br>


<a id="ID_8-3"></a>

### ◎ 自己共役作用素（エルミート作用素）と有界性＜閉グラフ定理の応用＞
ここでは、（バナッハ空間の項目で述べた）閉グラフ定理の簡単な応用で導かれる定理を見ていく。<br>

![image](https://user-images.githubusercontent.com/25688193/45207851-1f1b0a00-b2c4-11e8-98f1-78ff8ce4c3b2.png)<br>

- （証明略）証明の方針のみ記載<br>
    ヒルベルト空間 X の直積集合 X×X のグラフ<br>
    ![image](https://user-images.githubusercontent.com/25688193/45209311-a0c06700-b2c7-11e8-9c94-7686ea80fbd5.png)<br>
    が、閉集合になることを示せばよい。<br>


- 【参照】<br>
    - [閉グラフ定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E9%96%89%E3%82%B0%E3%83%A9%E3%83%95%E5%AE%9A%E7%90%86)<br>


<a id="ID_8-4"></a>

### ◎ ヒルベルト空間の正規直交系とフーリエ級数
![image](https://user-images.githubusercontent.com/25688193/45229497-eb120a00-b300-11e8-9118-6f3ca25e0f98.png)<br>

- （証明略）<br>

<!--
![image](https://user-images.githubusercontent.com/25688193/45229532-fc5b1680-b300-11e8-8081-594bffdf3d04.png)<br>
-->

- 【参考】
    - [フーリエ解析](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E3%83%95%E3%83%BC%E3%83%AA%E3%82%A8%E8%A7%A3%E6%9E%90_Note.md)
    - [ヒルベルト空間での強収束と弱収束](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#ID_8-7)


<a id="ID_8-5"></a>

### ◎ ヒルベルト空間における極大な正規直交系
![image](https://user-images.githubusercontent.com/25688193/45236142-00ddfa00-b316-11e8-98f6-e6f8f3bf899e.png)

> 【メモ】<br>
> フーリエ級数の平均収束から導出されるパーシバルの等式と、このヒルベルト空間における正規直交系視点のパーシバルの等式が結びつく。<br>
> この関係性は、同じく先のフーリエ級数の平均収束から導出されるパーシバルの等式と、内積空間における正規直交系視点のベッセルの不等式が結びつく関係と同じとなっている。<br>

- （証明略）<br>

- 【参考】<br>
    - [フーリエ級数の収束性（パーシバルの等式）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E3%83%95%E3%83%BC%E3%83%AA%E3%82%A8%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%95%E3%83%BC%E3%83%AA%E3%82%A8%E7%B4%9A%E6%95%B0%E3%81%AE%E5%8F%8E%E6%9D%9F%E6%80%A7)<br>
    - [（内積空間における）ベッセルの不等式](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%99%E3%83%83%E3%82%BB%E3%83%AB%E3%81%AE%E4%B8%8D%E7%AD%89%E5%BC%8F)<br>


<a id="ID_8-6"></a>

### ◎ 可分なヒルベルト空間における完全正規直交系
![image](https://user-images.githubusercontent.com/25688193/45251309-d8d6b100-b37e-11e8-9799-05b699f540ef.png)<br>

- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45251338-5995ad00-b37f-11e8-8cc7-8b93fe74f246.png)<br>

- （証明）<br>
    - まず、a ⇒ b の関係（無限次元のヒルベルト空間が可分ならば、このヒルベルト空間は可算個の極大な正規直交系を持つ）を証明する。<br>
        - ヒルベルト空間における可分性の定義は、ヒルベルト空間の稠密な部分集合として、可算集合が存在することであるので、<br>
            ヒルベルト空間 H の稠密な可算集合（部分集合になる）![image](https://user-images.githubusercontent.com/25688193/45251356-a8dbdd80-b37f-11e8-9f48-d60ad5a486ce.png) が存在する。<br>
            この稠密な可算集合 D から、適当にベクトルを選び、ベクトルの組を作ると、<br>
            任意の正数 m∈N に対して、これらベクトルの組で張られるベクトル空間<br>
            ![image](https://user-images.githubusercontent.com/25688193/45251463-7501b780-b381-11e8-8318-d19b910f1d46.png)<br>
            から、線形独立なベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/45251467-8945b480-b381-11e8-8553-46b2511c58f9.png) を得ることが出来る。<br>
            こうして得られた線形独立なベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/45251467-8945b480-b381-11e8-8553-46b2511c58f9.png) に対して、グラム・シュミットの直交化法を適用すれば、正規直交系 ![image](https://user-images.githubusercontent.com/25688193/45251476-b6926280-b381-11e8-988e-437f05dd2171.png) を構成することが出来る。<br>
        - 以下、この正規直交系 U が、極大な正規直交系であることを示すために、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45251558-2523f000-b383-11e8-880a-1ebd577c7619.png) の存在（極大な正規直交系に直交する他のベクトル）を仮定した上で、その矛盾を導く。（極大な正規直交系に対して、直交する他のこの直交系に含まれないベクトルは存在しないため）<br>
        - まず、極大な正規直交系に直交するならば、稠密な可算集合 ![image](https://user-images.githubusercontent.com/25688193/45251356-a8dbdd80-b37f-11e8-9f48-d60ad5a486ce.png) にも直交するので、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45251571-64ead780-b383-11e8-9a25-6e878f399f97.png) である。<br>
        - 又、稠密な可算集合 D の稠密性（＝ヒルベルト空間に触する）より、<br>
            この稠密な部分集合 D 内の点列 ![image](https://user-images.githubusercontent.com/25688193/45251632-649f0c00-b384-11e8-9195-b9fb4d1105ba.png) の中に、<br>
            極大な正規直交系と直交するベクトル ![image](https://user-images.githubusercontent.com/25688193/45251648-94e6aa80-b384-11e8-8061-9c2a3a5b9041.png) に収束する、即ち、![image](https://user-images.githubusercontent.com/25688193/45251656-b8a9f080-b384-11e8-970f-95240b3584aa.png) となるものが存在する。<br>
        - しかしながら、これらのことは（![image](https://user-images.githubusercontent.com/25688193/45251732-1c80e900-b386-11e8-90ea-cc5e71513ea5.png) ）、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45251747-53ef9580-b386-11e8-8afa-98614d692856.png)<br>
            の関係より、矛盾する。<br>
            従って、このような ![image](https://user-images.githubusercontent.com/25688193/45251648-94e6aa80-b384-11e8-8061-9c2a3a5b9041.png) は存在せず、正規直交系 U が、極大な正規直交系である。<br>
            そして、a ⇒ b の関係（無限次元のヒルベルト空間が可分ならば、このヒルベルト空間は可算個の極大な正規直交系を持つ）が成り立つ。<br>
            <br>
    - 次に、b ⇒ a の関係（無限次元のヒルベルト空間が可算個の極大な正規直交系をもつならば、このヒルベルト空間は可分）を証明する。<br>
        - このときは、無限次元のヒルベルト空間 H は、可算個のベクトルの組からなる極大な正規直交系 ![image](https://user-images.githubusercontent.com/25688193/45251476-b6926280-b381-11e8-988e-437f05dd2171.png) を持つので、これらの線形結合全体の集合 E も、また可算集合になり、稠密な部分集合になる。<br>
            従って、b ⇒ a の関係（無限次元のヒルベルト空間が可算個の極大な正規直交系をもつならば、このヒルベルト空間は可分）が成り立つ。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45250799-ecc9e500-b375-11e8-95ef-8f565e73cc59.png)

- （証明略）<br>

<br>

- 【参考】<br>
    - [稠密、可分性](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E7%A8%A0%E5%AF%86-dense%E5%8F%AF%E5%88%86%E6%80%A7-separable)<br>
    - [バナッハ空間における基底（シャウダー基底）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%90%E3%83%8A%E3%83%83%E3%83%8F%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E5%9F%BA%E5%BA%95%E3%82%B7%E3%83%A3%E3%82%A6%E3%83%80%E3%83%BC%E5%9F%BA%E5%BA%95)<br>

<a id="ID_8-6-1"></a>

#### ☆ ヒルベルト空間における完全正規直交系の例

- （例）ヒルベルト空間における完全正規直交系の例（L2ノルム）<br>
    可算個の点列 ![image](https://user-images.githubusercontent.com/25688193/45254506-5c5ec500-b3b4-11e8-8227-42c18856423f.png) を以下のように定義する。<br>
    ![image](https://user-images.githubusercontent.com/25688193/45254379-0db02b80-b3b2-11e8-9a13-d478a52886b7.png)<br>
    <br>
    このとき、この点列から構成されるベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/45254389-228cbf00-b3b2-11e8-9836-db3b275d32fc.png) は、<br>
    ヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/45254392-451ed800-b3b2-11e8-88c7-0f528f9203ab.png)（＝ノルムが、![image](https://user-images.githubusercontent.com/25688193/45254401-65e72d80-b3b2-11e8-87c7-3c364a0d3e44.png) で定義）の正規直交系となる。（計算略）<br>
    更に、このヒルベルト空間内の任意のベクトル ![image](https://user-images.githubusercontent.com/25688193/45254409-89aa7380-b3b2-11e8-9dc0-292f2667f88c.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45254415-af377d00-b3b2-11e8-85ab-cacaaa1b3232.png)<br>
    が成り立つので、パーシバルの等式<br>
    ![image](https://user-images.githubusercontent.com/25688193/45254428-ed34a100-b3b2-11e8-9838-2983215137d4.png)<br>
	が成り立ち、ヒルベルト空間における正規直交系の定義より、<br>
	この正規直交系 ![image](https://user-images.githubusercontent.com/25688193/45254389-228cbf00-b3b2-11e8-9836-db3b275d32fc.png) は、極大な正規直交系であり、完全正規直交系になる。<br>

<br>

- （例）ヒルベルト空間における完全正規直交系の例（フーリエ正弦級数展開）<br>
	区間 [0:1] の可算個の点列（関数列） ![image](https://user-images.githubusercontent.com/25688193/45254506-5c5ec500-b3b4-11e8-8227-42c18856423f.png) を以下のように定義する。<br>
    ![image](https://user-images.githubusercontent.com/25688193/45254576-895fa780-b3b5-11e8-89cc-e1d4ca0982eb.png)<br>
    <br>
    このとき、この点列から構成されるベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/45254389-228cbf00-b3b2-11e8-9836-db3b275d32fc.png) は、<br>
    ヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/45254587-a6947600-b3b5-11e8-86b7-2a3ddb12fc52.png)（＝ノルムが、![image](https://user-images.githubusercontent.com/25688193/45254401-65e72d80-b3b2-11e8-87c7-3c364a0d3e44.png) で定義）の正規直交系となる。（計算略）<br>
    更に、この正規直交系 ![image](https://user-images.githubusercontent.com/25688193/45254389-228cbf00-b3b2-11e8-9836-db3b275d32fc.png) は、このヒルベルト空間 ![image](https://user-images.githubusercontent.com/25688193/45254587-a6947600-b3b5-11e8-86b7-2a3ddb12fc52.png) の完全正規直交系にもなる。（計算略）<br>
    従って、このヒルベルト空間内の任意のベクトル ![image](https://user-images.githubusercontent.com/25688193/45254601-ea877b00-b3b5-11e8-9919-8b7ea3b0732a.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45254725-d3498d00-b3b7-11e8-9bb9-3a18261dd337.png)<br>
	の強収束の関係が成り立つので、<br>
	ヒルベルト空間内の任意のベクトル ![image](https://user-images.githubusercontent.com/25688193/45254601-ea877b00-b3b5-11e8-9919-8b7ea3b0732a.png) は、以下のような線形結合の形で表現できる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/45254734-01c76800-b3b8-11e8-89ce-f3245c657608.png)<br>
    この内積を積分の形で表現しなおすと、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45254742-16a3fb80-b3b8-11e8-846f-a58af46d1340.png)<br>
    この式は、フーリエ正弦級数展開に他ならない。<br>


<a id="ID_8-7"></a>

### ◎ ヒルベルト空間における強収束と弱収束
無限次元空間を扱う関数解析においては、有限次元を扱う線形代数とは異なり、線形独立な無限個のベクトルの組の線形結合を扱うので、空間内の点列の収束性を議論する必要がある。<br>
この際に、強収束の意味での収束を議論することは、扱う対象によっては必ずしも簡単ではないケースも存在する。そこで、この強収束よりも弱い概念である弱収束なるものを導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/45256784-70b3b980-b3d6-11e8-93b0-3efd274a5455.png)<br>

![image](https://user-images.githubusercontent.com/25688193/45257182-ed499680-b3dc-11e8-8bf2-8c33312dadf0.png)<br>

- 【参考】
    - [弱位相 | Wikipedia](https://ja.wikipedia.org/wiki/%E5%BC%B1%E4%BD%8D%E7%9B%B8)


<a id="ID_B"></a>

## ■ ヒルベルト空間と射影定理
関数解析の最も広く応用展開されるているものの１つとして、ヒルベルト空間における直交射影定理というものが存在する。この直交射影定理は、ピタゴラスの定理の高次元版であり、ユークリッド空間における幾何学的な直感が、高次元空間でも通用することを示している。<br>

更に、直交射影定理は、最も基本的な最適化原理になっており、
対象となるヒルベルト空間や閉部分集合をうまく設定することにより、多くの応用が可能となる。<br>
これは例えば、フーリエ級数展開が、正規直交系が張る閉部分集合への直交射影の単純な表現を与えていることや、最小２乗推定や一般逆写像やカルマンフィルタの基本的なアイデアも、直交射影定理の応用の１つとなっている。<br>

又、凸射影定理は、直交射影定理を拡張して得られる非線形版であるが、凸最適化問題の基礎となっている。<br>

<!--
> 【メモ】<br>
> 射影定理は「平面への射影成分と直交成分にへ分解すること」。解析とは分解することである。<br>
> 射影定理は完備性（点列コンパクト性）と同義でもある。平面で切って切って切りまくっていく先に収束していく。解析＝分解＝射影定理＝点列完閉性。<br>
-->

<a id="ID_B-1"></a>

### ◎ ヒルベルト空間における凸射影定理と直交射影定理
![image](https://user-images.githubusercontent.com/25688193/45264455-a78ddc00-b477-11e8-8c97-5311a8adfb66.png)<br>

![image](https://user-images.githubusercontent.com/25688193/45264645-cc378300-b47a-11e8-9f5e-480c549c5173.png)<br>


<a id="ID_B-1-1"></a>

#### ☆ ヒルベルト空間における凸射影の非拡大性
![image](https://user-images.githubusercontent.com/25688193/45267002-66a9bd80-b49f-11e8-91ce-8f078411836f.png)<br>

以下の定理は、凸射影が非拡大写像の一例になっていることを示している。<br>

![image](https://user-images.githubusercontent.com/25688193/45278610-e0c25c80-b508-11e8-85a3-0c28538550d4.png)<br>

- （証明略）(3) に関しては、図より自明<br>

- 参考<br>
    - [縮小写像](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E7%B8%AE%E5%B0%8F%E5%86%99%E5%83%8F%E3%81%AE%E4%B8%8D%E5%8B%95%E7%82%B9%E5%AE%9A%E7%90%86)<br>


<a id="ID_B-1-2"></a>

#### ☆ ヒルベルト空間における直交分解
![image](https://user-images.githubusercontent.com/25688193/45293044-03b53680-b532-11e8-8fa4-50285f17059c.png)<br>

![image](https://user-images.githubusercontent.com/25688193/45293072-1465ac80-b532-11e8-94b6-23cc5a039979.png)<br>
- （証明略）３次元空間においては、図より自明に成り立つ。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45293239-876f2300-b532-11e8-8fc7-501c438abe1c.png)<br>
- （証明略）３次元空間においては、図より自明に成り立つ。<br>


<a id="ID_B-1-3"></a>

#### ☆ ヒルベルト空間の閉部分空間への直交射影の線形性・冪等性・自己共役性
![image](https://user-images.githubusercontent.com/25688193/45298996-21d86200-b545-11e8-8113-6a420f7be1cc.png)<br>
- （証明略）３次元空間においては、図より自明に成り立つ。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45299702-5baa6800-b547-11e8-8428-fce63d1314de.png)<br>
- （証明）<br>
    - 直交分解の定理より、直交写像 ![image](https://user-images.githubusercontent.com/25688193/45300772-38cd8300-b54a-11e8-97fc-13546c7bce2b.png) に関して、任意のベクトル ![image](https://user-images.githubusercontent.com/25688193/45300804-4d118000-b54a-11e8-85ff-f1def170b5f6.png) は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45300858-6fa39900-b54a-11e8-84d4-52cec0876a4e.png)<br>
        のように、一意に分解出来る。<br>
        これを利用すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45300906-8fd35800-b54a-11e8-9fcc-3a9bc667da54.png)<br>
    - 更に、任意の ![image](https://user-images.githubusercontent.com/25688193/45301084-1c7e1600-b54b-11e8-84d9-5498a12d214b.png) に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45301279-94e4d700-b54b-11e8-9de2-97404cfd70bf.png) となるので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45301328-b5149600-b54b-11e8-8392-0fab15e6894c.png)<br>
        となり、この定理は成り立つ。<br>

- 【参考】<br>
    - [ノルム空間における有界線形作用素](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E6%9C%89%E7%95%8C%E7%B7%9A%E5%BD%A2%E4%BD%9C%E7%94%A8%E7%B4%A0)<br>
    - [ノルム空間における作用素ノルム](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E4%BD%9C%E7%94%A8%E7%B4%A0%E3%83%8E%E3%83%AB%E3%83%A0)

<br>

![image](https://user-images.githubusercontent.com/25688193/45302140-7f70ac80-b54d-11e8-98eb-fa2c1aa68ce8.png)<br>

- 【参考】<br>
    - [自己共役作用素（エルミート作用素）と有界性＜閉グラフ定理の応用＞](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E8%87%AA%E5%B7%B1%E5%85%B1%E5%BD%B9%E4%BD%9C%E7%94%A8%E7%B4%A0%E3%82%A8%E3%83%AB%E3%83%9F%E3%83%BC%E3%83%88%E4%BD%9C%E7%94%A8%E7%B4%A0%E3%81%A8%E6%9C%89%E7%95%8C%E6%80%A7%E9%96%89%E3%82%B0%E3%83%A9%E3%83%95%E5%AE%9A%E7%90%86%E3%81%AE%E5%BF%9C%E7%94%A8)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45305156-ad0d2400-b554-11e8-93e5-3c34a1da5dd8.png)<br>
- （証明）<br>
    > 記載中...<br>


<a id="ID_B-1-4"></a>

#### ☆ ヒルベルト空間における和空間への直交写像
![image](https://user-images.githubusercontent.com/25688193/45313302-7d1c4b80-b569-11e8-881d-bdf402ddf0cb.png)<br>
- （証明略）３次元空間においては、図より自明に成り立つ。<br>


<a id="ID_B-2"></a>

### ◎ ヒルベルト空間における線形多様体への直交射影と正規方程式
ヒルベルト空間では、有限次元の部分集合は、”常に”閉集合となる（先のノルム空間における閉部分空間に関する定理より）が、以下の定理で示すように、**この有界線形部分空間への直交射影の計算は、次元の数だけ未知数を求める線形連立方程式の問題に帰着される。**<br>
（※ このことは、有限次元部分空間への直交射影が、線形代数におけるガウスの消去法を用いて有限回の四則演算で計算できることを意味している。）<br>

従って、有限次元部分空間への直交射影の計算原理を把握しておくことにより、応用上の諸問題（凸最適化問題、最小２乗推定、一般逆写像等）に、直交射影定理をうまく活用することが可能となる。<br>

- 【参考】<br>
    - [ノルム空間における閉部分空間、線形多様体、閉凸集合](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E9%96%89%E9%83%A8%E5%88%86%E7%A9%BA%E9%96%93%E7%B7%9A%E5%BD%A2%E5%A4%9A%E6%A7%98%E4%BD%93%E9%96%89%E5%87%B8%E9%9B%86%E5%90%88)<br>


<a id="ID_B-2-1"></a>

#### ☆ ヒルベルト空間における直交射影と正規方程式・グラム行列
![image](https://user-images.githubusercontent.com/25688193/45376136-08611400-b632-11e8-8380-1dd597e92828.png)<br>
- （証明）<br>
    - まず、「![image](https://user-images.githubusercontent.com/25688193/45364307-c4abe180-b614-11e8-88e4-6d97e5535639.png)」⇔「![image](https://user-images.githubusercontent.com/25688193/45364357-e5743700-b614-11e8-8b66-95b424382006.png) が正規方程式の解」の関係を示す。<br>
        図より、![image](https://user-images.githubusercontent.com/25688193/45364392-fcb32480-b614-11e8-9a80-f5ef14900697.png) となるので、直交射影定理より、<br>
        部分空間中のベクトル ![image](https://user-images.githubusercontent.com/25688193/45364456-25d3b500-b615-11e8-8a02-c3439113e59a.png) に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45364518-51569f80-b615-11e8-916b-2b570ab17634.png)<br>
        の関係が成り立つが、この式を変形すると、正規方程式なる。<br>
        従って、![image](https://user-images.githubusercontent.com/25688193/45364590-7d722080-b615-11e8-9a8b-fdbbbb89e91a.png) となるための必要十分条件が、正規方程式の解の存在となる。<br>
    - 次に、「グラム行列 G が正則行列で解が存在する（＝逆行列が存在する）」 ⇔ 「![image](https://user-images.githubusercontent.com/25688193/45364976-70a1fc80-b616-11e8-8619-d362b0469cc2.png) が一次独立」 の関係を示すために、<br>
        その対偶である 「グラム行列 G の行ベクトルが一次従属」 ⇔ 「![image](https://user-images.githubusercontent.com/25688193/45364976-70a1fc80-b616-11e8-8619-d362b0469cc2.png) が一次従属」の関係を示す。<br>
        - 「![image](https://user-images.githubusercontent.com/25688193/45364976-70a1fc80-b616-11e8-8619-d362b0469cc2.png) が一次従属」 ⇒ 「グラム行列 G の行ベクトルが一次従属」の証明<br>
            ![image](https://user-images.githubusercontent.com/25688193/45364976-70a1fc80-b616-11e8-8619-d362b0469cc2.png) が一次従属である場合には、![image](https://user-images.githubusercontent.com/25688193/45366263-63d2d800-b619-11e8-8fb7-9fc199fc2a65.png) となる非ゼロな係数ベクトル ![image](https://user-images.githubusercontent.com/25688193/45366299-7b11c580-b619-11e8-9230-b3cac8b13065.png) が存在する。<br>
            このとき、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45366344-9aa8ee00-b619-11e8-893c-17c431fa8ae2.png)<br>
            となるので、グラム行列 G の行ベクトルが一次従属となる。<br>
        - 「![image](https://user-images.githubusercontent.com/25688193/45364976-70a1fc80-b616-11e8-8619-d362b0469cc2.png) が、一次従属」 ⇐ 「グラム行列 G の行ベクトルが一次従属」の証明<br>
            グラム行列 G の行ベクトルが一次従属である場合には、![image](https://user-images.githubusercontent.com/25688193/45366964-15bed400-b61b-11e8-81d1-4d2a230ede83.png) となる非ゼロな係数ベクトル ![image](https://user-images.githubusercontent.com/25688193/45366992-28d1a400-b61b-11e8-91d7-ee7920178ce3.png) が存在する。<br>
            このとき、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45367050-4dc61700-b61b-11e8-870c-e55aec572539.png)<br>
            となるので、![image](https://user-images.githubusercontent.com/25688193/45367098-6b937c00-b61b-11e8-8fe9-43674d82f619.png) となり、![image](https://user-images.githubusercontent.com/25688193/45367145-86fe8700-b61b-11e8-9fd7-eef9233813f2.png) が、一次従属となる。<br>

- 【参考】<br>
    - [ヒルベルト空間における凸射影定理と直交射影定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%92%E3%83%AB%E3%83%99%E3%83%AB%E3%83%88%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E5%87%B8%E5%B0%84%E5%BD%B1%E5%AE%9A%E7%90%86%E3%81%A8%E7%9B%B4%E4%BA%A4%E5%B0%84%E5%BD%B1%E5%AE%9A%E7%90%86)<br>


<a id="ID_B-2-2"></a>

#### ☆ ヒルベルト空間における線形多様体への直交写像と最小ノルム点
![image](https://user-images.githubusercontent.com/25688193/45379505-3b5bd580-b63b-11e8-981e-b9fdbf4769a3.png)<br>
- （証明略）３次元空間においては、図より自明に成り立つ。<br>


<a id="ID_B-2-3"></a>

#### ☆ ヒルベルト空間における等式線形制約条件下での線形方程式の解集合と線形多様体への射影
![image](https://user-images.githubusercontent.com/25688193/45438925-77eb0800-b6f3-11e8-98f6-22c5d8b19905.png)<br>
- （証明略）３次元空間においては、図より自明に、線形方程式の解集合が線形多様体になる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45439004-ab2d9700-b6f3-11e8-809c-ae2b83562c3d.png)<br>
- （証明略）３次元空間においては、図より自明に、V∩M が最小ノルム点になる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45439668-699deb80-b6f5-11e8-9ab5-e5661cf1b4a8.png)<br>
- （証明略）３次元空間においては、図より自明に、![image](https://user-images.githubusercontent.com/25688193/45439923-05c7f280-b6f6-11e8-9e05-90e85025bff7.png) が、線形方程式 ![image](https://user-images.githubusercontent.com/25688193/45439958-1aa48600-b6f6-11e8-8efa-bd1a8e6e14ee.png) の解となる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45441056-07df8080-b6f9-11e8-85b7-1b06c49b6fd7.png)<br>
- （証明略）<br>
	３次元空間においては、図より自明に、正規方程式 ![image](https://user-images.githubusercontent.com/25688193/45441241-85a38c00-b6f9-11e8-93ec-f33c46761031.png) の解は、![image](https://user-images.githubusercontent.com/25688193/45441297-a23fc400-b6f9-11e8-87a0-421ba3b745e4.png) であるので、成り立つ。<br>

<br>

- （例）最小分散不偏推定法、カルマンフィルター<br>
    大雑把には、平均的に真の値を予想できる量（＝不偏推定量）を扱う系のうち、<br>
    特に未知変数 ![image](https://user-images.githubusercontent.com/25688193/45505548-cd90e480-b7c7-11e8-862d-64ce816f3970.png) の線形結合で表すような不偏推定量 ![image](https://user-images.githubusercontent.com/25688193/45505592-eef1d080-b7c7-11e8-9657-41bef7312bfc.png) を考える。<br>
    > 記載中...


<a id="ID_A"></a>

## ■ 作用素

<a id="ID_A-2"></a>

### ◎ ノルム空間における有界線形作用素
![image](https://user-images.githubusercontent.com/25688193/44972011-a863d100-af92-11e8-9332-52bb2669683d.png)<br>

<a id="ID_A-2-1"></a>

#### ☆ ノルム空間における作用素ノルム
![image](https://user-images.githubusercontent.com/25688193/45227558-c49da000-b2fb-11e8-9003-4721609b9ce1.png)<br>

- 【参考】
    - [関数解析メモ](https://www.yasuhisay.info/entry/20110517/1305608183)


<a id="ID_A-2-2"></a>

#### ☆ ノルム空間における有界線形汎関数
![image](https://user-images.githubusercontent.com/25688193/44958868-e4f6e480-af20-11e8-9551-935618e2ba45.png)<br>

- 【参考】[汎関数微分](http://eman-physics.net/analytic/functional.html)


<a id="ID_A-2-3"></a>

#### ☆ 線形写像の連続性
ノルム空間のような位相構造を持つ空間においては、先に記載したように線形写像の連続性についての概念を構築することが出来た。（[参照](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#ID_5-4)）<br>

以下の定理で示すように、有限次元の（＝有界な）ノルム空間においては、線形写像は必ず連続である。<br>
（従って、非連続な不連続線形作用素の議論が意味を持つのは、無限次元の空間を扱う場合になる。）<br>

![image](https://user-images.githubusercontent.com/25688193/44960837-7a09d580-af41-11e8-8de6-f331919bb09a.png)<br>
- （証明略）２次元空間においては、図より自明に成り立つ。


<a id="ID_A-2-4"></a>

#### ☆ 【補足】逆写像の存在性
![image](https://user-images.githubusercontent.com/25688193/44971756-bebd5d00-af91-11e8-9b5f-5607602c7254.png)<br>
- （証明略）<br>

![image](https://user-images.githubusercontent.com/25688193/44981112-9d1d9f00-afac-11e8-81d4-f82361cbdef7.png)<br>
- （証明略）<br>

- Wikipedia より引用<br>
    ![image](https://user-images.githubusercontent.com/25688193/44972310-ae0de680-af93-11e8-831c-7c31ee3434f6.png)<br>


<a id="ID_A-2-5"></a>

#### ☆ 有界線形写像全体が作るノルム空間
有界線形作用素としては様々なもの（行列、微分、積分、フーリエ変換など）が考えられるが、これらの有界線形作用素をかき集めて空間とみなすと、(内積空間やノルム空間を考えたときと同様に）この空間内でのノルム（＝有界線形作用素ノルム）が考えられる。<br>
そして、以下の定理で示すように、**有界線形写像全体はベクトル空間となるが、この作用素ノルムによってノルム空間になる。**<br>

![image](https://user-images.githubusercontent.com/25688193/44988250-06111100-afc5-11e8-9051-5895510cda84.png)<br>
- （証明略）<br>


<a id="ID_A-2-6"></a>

### ☆ 行列の作用素ノルム
２つの有限次元のノルム空間の間で定義される ”任意の” 線形写像は、各々のノルム空間の基底ベクトルで展開（表現）した係数ベクトル間の変換行列によって完全に表現出来る。（＝線形写像の表現行列）<br>

今、議論の対象空間として、<br>
m×n 行列の全てからなる集合 ![image](https://user-images.githubusercontent.com/25688193/44988328-3ce72700-afc5-11e8-86fb-f371d503e7cd.png) 及び、その要素である m×n の有限次元ベクトル ![image](https://user-images.githubusercontent.com/25688193/44988480-bda62300-afc5-11e8-84f1-0bb0a9ab61bb.png) を考え、このベクトル空間に定義される代表的なノルムとその性質をみていく。<br>

![image](https://user-images.githubusercontent.com/25688193/44997602-9f9ee980-afea-11e8-9b19-1ece6630b047.png)<br>
- （証明略）<br>

##### 行列の作用素ノルムの例

- （例）行列の作用素ノルムの例１<br>
	n 次元ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/44997691-379cd300-afeb-11e8-85ad-d3d7fcbef37a.png) から、別の m 次元ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/44997701-497e7600-afeb-11e8-978e-54de63e813bc.png) への線形写像 T:X→Y を、<br>
	実行列 ![image](https://user-images.githubusercontent.com/25688193/44997719-5ef3a000-afeb-11e8-81b3-3cc77e111148.png) を用いて、![image](https://user-images.githubusercontent.com/25688193/44997730-6fa41600-afeb-11e8-89e2-5acf249e961f.png) のように表現したとする。<br>
    このとき、![image](https://user-images.githubusercontent.com/25688193/44997740-85194000-afeb-11e8-9cd4-b8ade41457c1.png) のノルムを<br>
    ![image](https://user-images.githubusercontent.com/25688193/45008929-54afc100-b040-11e8-8811-32f27fc25cf8.png)<br>
    のように定義した場合に、T の作用素ノルム ‖T‖ は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45017110-aa489580-b061-11e8-8be8-58085cbbd691.png)<br>
    と表現できることを示す。<br>
    - ![image](https://user-images.githubusercontent.com/25688193/44997809-f78a2000-afeb-11e8-97aa-225033bf3c0f.png) （＝max 条件に対応）を満たす任意の ![image](https://user-images.githubusercontent.com/25688193/44997816-07a1ff80-afec-11e8-8cb2-e65d727e3e89.png) に対して、<br>
	T の作用素ノルムは、定義より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45011817-74021a80-b04f-11e8-8096-f99788356ee1.png)<br>
    と書けるが、この式の ![image](https://user-images.githubusercontent.com/25688193/45011915-f7bc0700-b04f-11e8-82c4-fc8ce4bfa5ba.png) の部分を変形すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45018271-a4a07f00-b064-11e8-9880-5b9e00ff8f91.png)<br>
    従って、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44998107-f954e300-afed-11e8-8994-c19e9c2feb98.png)<br>
    の関係が成り立つことがわかる。<br>
	ここで、この式の最右辺 ![image](https://user-images.githubusercontent.com/25688193/45011530-e96ceb80-b04d-11e8-9317-01b602379fa2.png) の式との等号は、最大値の達成時に成り立つが、<br>
	k=p で最大値が達成されるとすると、ノルムが１の単位ベクトル<br>
    ![image](https://user-images.githubusercontent.com/25688193/45011639-92b3e180-b04e-11e8-8c99-edbb77848e1d.png)<br>
    で式を表現し直すと、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45011676-baa34500-b04e-11e8-9d1c-155a1a3b33e6.png)<br>
    となり、反対方向の不等号も成立するので、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45011692-cb53bb00-b04e-11e8-9f80-b2f1a4c6d9f5.png)<br>


- （例）行列の作用素ノルムの例２<br>
    先の例と同じ状況下で、ベクトル空間（ノルム空間になる）![image](https://user-images.githubusercontent.com/25688193/45009161-84ab9400-b041-11e8-9a73-37052f67a60b.png) のノルムを、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45009101-31d1dc80-b041-11e8-8b68-efbc7411d997.png)<br>
    のように定義した場合に、T の作用素ノルム ‖T‖ は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45017583-e6302a80-b062-11e8-9520-a55f7d3fc85e.png)<br>
    と表現できることを示す。<br>
    - 先の例と同様にして、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45012002-4ff30900-b050-11e8-994b-1e50d5b23fc6.png)（＝max 条件に対応）を満たす任意の ![image](https://user-images.githubusercontent.com/25688193/45012025-6a2ce700-b050-11e8-9887-e2a3b2f6f058.png) に対して、<br>
    T の作用素ノルムは、定義より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45012120-b6782700-b050-11e8-96e1-197dbccbe0df.png)<br>
    と書けるが、この式の ![image](https://user-images.githubusercontent.com/25688193/45012187-e7f0f280-b050-11e8-86b9-16823dcc3bd7.png) の部分を変形すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45018522-4758fd80-b065-11e8-8e95-7826d234bda7.png)<br>
    従って、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45018634-68215300-b065-11e8-8b80-d573fb332d20.png)<br>
    の関係が成り立つことがわかる。<br>
	ここで、この式の最右辺 ![image](https://user-images.githubusercontent.com/25688193/45019580-aa4b9400-b067-11e8-85c4-86c3e465cdeb.png) の式との等号は、最大値 max の達成時に成り立つが、<br>
	j=p で最大値が達成されるとすると、ノルムが１の単位ベクトル<br>
    ![image](https://user-images.githubusercontent.com/25688193/45019618-c51e0880-b067-11e8-94df-6e66c9b84c6a.png)<br>
    で式を表現し直すと、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45019680-e848b800-b067-11e8-9715-4ae2554a9c37.png)<br>
    となり、反対方向の不等号も成立するので、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45019711-fa2a5b00-b067-11e8-8477-bd6f4156615c.png)<br>


<a id="ID_A-3"></a>

### ◎ ムーア・ペンローズの一般化逆写像
![image](https://user-images.githubusercontent.com/25688193/45507532-52323180-b7cd-11e8-910b-1898876cf70d.png)<br>
- （証明）<br>
    > 記載中...

- 【参考】<br>
    - [【解説】 一般逆行列](https://www.slideshare.net/wosugi/ss-79624897)<br>
    - [ヒルベルト空間における凸射影定理と直交射影定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%92%E3%83%AB%E3%83%99%E3%83%AB%E3%83%88%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E5%87%B8%E5%B0%84%E5%BD%B1%E5%AE%9A%E7%90%86%E3%81%A8%E7%9B%B4%E4%BA%A4%E5%B0%84%E5%BD%B1%E5%AE%9A%E7%90%86)<br>
    - [ヒルベルト空間における線形多様体への直交射影と正規方程式](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%92%E3%83%AB%E3%83%99%E3%83%AB%E3%83%88%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E7%B7%9A%E5%BD%A2%E5%A4%9A%E6%A7%98%E4%BD%93%E3%81%B8%E3%81%AE%E7%9B%B4%E4%BA%A4%E5%B0%84%E5%BD%B1%E3%81%A8%E6%AD%A3%E8%A6%8F%E6%96%B9%E7%A8%8B%E5%BC%8F)<br>


<a id="ID_A-3-1"></a>

#### ☆ ムーア・ペンローズの一般化逆写像の特異値分解表現
> 記載中...


##### 【補足】特異値分解
> 記載中...


<a id="ID_A-4"></a>

### ◎ リースの表現定理
ここでは、ヒルベルト空間上に定義された有界線形汎関数は、内積を使って一意に表現できるというリースの表現定理について見ていく。<br>

<br>

まずリースの表現定理を見ていくために、以下のようなことを考える。<br>

先に述べたように、ノルム空間 X から実数空間 R への有界線形写像を、有界線形汎関数というが、このノルム空間 X 上の有界線形汎関数全体からなる集合を ![image](https://user-images.githubusercontent.com/25688193/45669085-d718a480-bb59-11e8-995a-86638aa464e9.png) と書く。<br>
（※ 有界線形写像には、行列、微分、積分など様々なものが考えられるが、これらをかき集めて１つの空間したものが B(X,Y) ）<br>
ここで、![image](https://user-images.githubusercontent.com/25688193/45669085-d718a480-bb59-11e8-995a-86638aa464e9.png) は、写像先の実数空間 R の完備性と有界線形写像全体からなる集合であることにより、この ![image](https://user-images.githubusercontent.com/25688193/45669085-d718a480-bb59-11e8-995a-86638aa464e9.png) 自身も、作用素ノルム<br>
![image](https://user-images.githubusercontent.com/25688193/45669400-f5cb6b00-bb5a-11e8-9c71-3f0a3fbe6caf.png)<br>
が定義されたバナッハ空間となる。（[有界線形写像の全体集合が作るバナッハ空間の定理より](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E6%9C%89%E7%95%8C%E7%B7%9A%E5%BD%A2%E5%86%99%E5%83%8F%E5%85%A8%E4%BD%93%E3%81%AE%E9%9B%86%E5%90%88%E3%81%8C%E4%BD%9C%E3%82%8B%E3%83%90%E3%83%8A%E3%83%83%E3%83%8F%E7%A9%BA%E9%96%93%E3%81%A8%E5%85%B1%E5%BD%B9%E7%A9%BA%E9%96%93)）<br>

更に、ノルム空間の共役空間の定義（＝ノルム空間 ![image](https://user-images.githubusercontent.com/25688193/45669330-b1d86600-bb5a-11e8-9b92-30084b14b90c.png) 上に定義された有界線形汎関数全体からなるバナッハ空間 B(X,R) が X の共役空間）より、
このバナッハ空間 ![image](https://user-images.githubusercontent.com/25688193/45669085-d718a480-bb59-11e8-995a-86638aa464e9.png) は、X の共役空間となる。<br>

<br>

ここで、リースの表現定理を導入するための前段階として、ノルム空間の有界線形汎関数全体が作る共役空間に関しての以下のような補題を導く。<br>

![image](https://user-images.githubusercontent.com/25688193/45756714-86d63b00-bc5c-11e8-99eb-760b03da9836.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45713160-4083cc00-bbc9-11e8-8120-0e49f8af69bf.png)<br>
- （証明略）３次元空間においては、図より自明<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45737382-a05d8f80-bc28-11e8-8e4d-fcc7fe93f3cf.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45734425-781d6300-bc1f-11e8-8202-603d2e2e08de.png)<br>

<!--
> 【メモ】<br>
> 簡単言えば、このリースの表現定理は、射影定理によって直交補空間から非零元を取ってきて、それをグラムシュミットの方法で正規直交化している流れになっている？<br>
-->

- （証明）<br>
    - (a) は、![image](https://user-images.githubusercontent.com/25688193/45713261-8771c180-bbc9-11e8-9052-bd957c745fff.png) の存在性と一意性を示しているが、まず、![image](https://user-images.githubusercontent.com/25688193/45713261-8771c180-bbc9-11e8-9052-bd957c745fff.png) の存在性について示す。<br>
        - 写像が零写像で ![image](https://user-images.githubusercontent.com/25688193/45716095-de2ec980-bbd0-11e8-833f-b6bb318604ef.png) の場合<br>
            ![image](https://user-images.githubusercontent.com/25688193/45713294-9fe1dc00-bbc9-11e8-90fe-a466d0819800.png) の関係より、![image](https://user-images.githubusercontent.com/25688193/45713399-e59ea480-bbc9-11e8-8d58-1de29d8eafd9.png) が自明に存在する。<br>
        - 写像 ![image](https://user-images.githubusercontent.com/25688193/45716121-f1419980-bbd0-11e8-8f58-5e61423d3101.png) の場合、<br>
            先の補題（ノルム空間の線形汎関数全体が作る共役空間）より、![image](https://user-images.githubusercontent.com/25688193/45716202-2cdc6380-bbd1-11e8-816a-c59aad931835.png) となる単位ベクトルが存在し、<br>
            ヒルベルト空間中の任意のベクトル ![image](https://user-images.githubusercontent.com/25688193/45716562-3f0ad180-bbd2-11e8-85a8-4c1bef19e62d.png) は、カーネルへの直交射影 ![image](https://user-images.githubusercontent.com/25688193/45716584-55b12880-bbd2-11e8-8bca-b1165dad1e6d.png) を用いて、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45716717-b04a8480-bbd2-11e8-9291-d8635fceec97.png)<br>
            と表すことが出来る。<br>
            ![image](https://user-images.githubusercontent.com/25688193/45733196-cd0aaa80-bc1a-11e8-8612-405ee5608a34.png)<br>
            と表すことが出来る。<br>
			従って、このベクトル ![image](https://user-images.githubusercontent.com/25688193/45734444-97b48b80-bc1f-11e8-833e-b8e13f51d944.png) の有界線形汎関数 f:H→R による写像先は、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45735508-10691700-bc23-11e8-8407-ee130a193751.png)<br>
            となり、![image](https://user-images.githubusercontent.com/25688193/45735543-2bd42200-bc23-11e8-8484-9134b7f9cf24.png) の項が、この定理の条件 ![image](https://user-images.githubusercontent.com/25688193/45735559-3c849800-bc23-11e8-85c1-080b0d0b8265.png) を満たしていることが分かる。<br>
        - 又、コーシー・シュワルツの不等式より、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45735966-99348280-bc24-11e8-9862-9424d15f1eba.png)<br>
            従って、有界線形汎関数の作用素ノルムに対して、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45736003-a94c6200-bc24-11e8-82a9-1dde5d3d5957.png)<br>
            の関係が保証される。<br>
            更に、自明な関係<br>
            ![image](https://user-images.githubusercontent.com/25688193/45736396-bd449380-bc25-11e8-9adf-537daa1a029b.png)<br>
            より、作用素ノルムは、![image](https://user-images.githubusercontent.com/25688193/45736065-d862d380-bc24-11e8-9665-8cf25744a5df.png) となる。<br>
        <br>
    - 次に、![image](https://user-images.githubusercontent.com/25688193/45736777-ec0f3980-bc26-11e8-9cb2-9ac137de29c2.png) の一意性について示す。<br>
        ヒルベルト空間中の２つのベクトル ![image](https://user-images.githubusercontent.com/25688193/45736801-fe897300-bc26-11e8-9ea6-99823fb38d9f.png) に関して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45736835-1cef6e80-bc27-11e8-841a-9ee09cd82c09.png)<br>
        が成り立つとすれば、<br>
        任意の ![image](https://user-images.githubusercontent.com/25688193/45736907-532cee00-bc27-11e8-8b8e-ab54642aeae7.png) に対して、![image](https://user-images.githubusercontent.com/25688193/45736957-7788ca80-bc27-11e8-929d-3c0e3023af62.png) となるので、<br>
        任意の ![image](https://user-images.githubusercontent.com/25688193/45736907-532cee00-bc27-11e8-8b8e-ab54642aeae7.png) のうち、![image](https://user-images.githubusercontent.com/25688193/45736979-8e2f2180-bc27-11e8-83ea-f07e18f3157d.png) を選ぶと、![image](https://user-images.githubusercontent.com/25688193/45737027-b880df00-bc27-11e8-993f-f21b9338f726.png)<br>
        従って、![image](https://user-images.githubusercontent.com/25688193/45737084-d3535380-bc27-11e8-802b-611595def008.png) でなくてはならず、ただ１つのベクトルが存在することになる。<br>
        <br>
    - (b) に関しての証明<br>
        ヒルベルト空間の共役空間中の任意の有界線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45737757-a738d200-bc29-11e8-8aa4-13c56413f373.png) と ![image](https://user-images.githubusercontent.com/25688193/45737921-0c8cc300-bc2a-11e8-8141-9075023e85c1.png) に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45738010-45c53300-bc2a-11e8-889e-cd0be3247047.png)<br>
        とおくと、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45738355-25e23f00-bc2b-11e8-80c8-ab8844beba5a.png)<br>
        の関係より、![image](https://user-images.githubusercontent.com/25688193/45738416-54601a00-bc2b-11e8-9d48-e3e6cc2850aa.png) となるので、<br>
        この写像 Φ は、線形写像になる。<br>
        <br>
        更に、(a) より、この線形写像 Φ は同長写像でもある。<br>

<br>

- 【参考】<br>
    - [ノルム空間における有界線形汎関数](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E6%9C%89%E7%95%8C%E7%B7%9A%E5%BD%A2%E6%B1%8E%E9%96%A2%E6%95%B0)<br>
    - [ノルム空間における作用素ノルム](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%8E%E3%83%AB%E3%83%A0%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E4%BD%9C%E7%94%A8%E7%B4%A0%E3%83%8E%E3%83%AB%E3%83%A0)<br>
    - [有界線形写像全体の集合が作るバナッハ空間と共役空間](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E6%9C%89%E7%95%8C%E7%B7%9A%E5%BD%A2%E5%86%99%E5%83%8F%E5%85%A8%E4%BD%93%E3%81%AE%E9%9B%86%E5%90%88%E3%81%8C%E4%BD%9C%E3%82%8B%E3%83%90%E3%83%8A%E3%83%83%E3%83%8F%E7%A9%BA%E9%96%93%E3%81%A8%E5%85%B1%E5%BD%B9%E7%A9%BA%E9%96%93)<br>


<a id="ID_A-5"></a>

### ◎ 内積空間上の線形汎関数の表現
リースの表現定理で、ヒルベルト空間とその共役空間の関係性は明らかになったが、次に、ヒルベルト空間ではないノルム空間の共役空間の場合にはどのようになるのかを考える。<br>

より詳細には、簡単のためノルム空間を内積空間に限定した上で、<br>
必ずしも完備ではない内積空間上に定義された有界線形汎関数は、コーシー列と内積を用いて具体的に表現できることを見ていく。<br>
そして、この内積空間の共役空間を構築するプロセスは、先の述べた空間の完備化のプロセスの具体的になっている。<br>

<br>

以下、内積空間 X は、<br>
内積として ![image](https://user-images.githubusercontent.com/25688193/45741982-df451280-bc33-11e8-87ab-04cf6b29e0f5.png) が定義されており、<br>
ノルムとして、内積から誘導されたノルム ![image](https://user-images.githubusercontent.com/25688193/45742016-f257e280-bc33-11e8-8f98-2af0e772bd16.png) が定義されているとする。<br>

任意に選ばれたベクトル ![image](https://user-images.githubusercontent.com/25688193/45749785-c0e91200-bc47-11e8-8c20-a2ed804302ff.png) を用いて、<br>
ノルム空間 X 上の線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45749806-d3fbe200-bc47-11e8-81e2-fe8fc1bb866b.png) を、![image](https://user-images.githubusercontent.com/25688193/45749845-efff8380-bc47-11e8-987f-7320c470aca9.png) のように定義すると、<br>
この線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45749874-060d4400-bc48-11e8-8cc7-ba9c2913239f.png) 全体が作る集合は、この内積空間 X の共役空間 ![image](https://user-images.githubusercontent.com/25688193/45749947-3e148700-bc48-11e8-9b25-c3861d662b41.png) となり、![image](https://user-images.githubusercontent.com/25688193/45749974-51bfed80-bc48-11e8-9797-44407ee47f98.png) となる。<br>
又、作用素ノルムは、<br>
![image](https://user-images.githubusercontent.com/25688193/45750229-2e497280-bc49-11e8-98ff-a23ed9573da6.png)<br>
となる。<br>
更に、内積空間からその共役空間への写像 ![image](https://user-images.githubusercontent.com/25688193/45750625-98aee280-bc4a-11e8-9f7e-d24a57723a58.png) は、![image](https://user-images.githubusercontent.com/25688193/45750656-ad8b7600-bc4a-11e8-8cf2-ce550f34e459.png) を線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45750736-ec213080-bc4a-11e8-95b8-3dde698941fb.png) に対応づける１対１の写像（ ![image](https://user-images.githubusercontent.com/25688193/45750856-4ae6aa00-bc4b-11e8-99ea-669060f24cea.png) ）となっており、<br>
![image](https://user-images.githubusercontent.com/25688193/45751199-a36a7700-bc4c-11e8-92b4-4aafb5ce41af.png)<br>
となる。<br>

ここで、ノルム空間 X 上の線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45751960-f47b6a80-bc4e-11e8-947f-04eddfe52005.png) は、![image](https://user-images.githubusercontent.com/25688193/45752000-0e1cb200-bc4f-11e8-83ba-d3f6bb16ee5b.png) のように定義されているので、<br>
「内積の形で表現可能な有界線形汎関数」となっているが、<br>
逆に、”任意の” 有界線形汎関数は、ノルム空間 X 上の内積で表現できないか？ということを考える。<br>

先のリースの表現定理で述べたように、<br>
ヒルベルト空間 H の場合には、任意の線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45755350-24c80680-bc59-11e8-9f22-c4c9a9d384d7.png) に対して、![image](https://user-images.githubusercontent.com/25688193/45755652-f7c82380-bc59-11e8-93d7-6fa2787ac03f.png) を満たすベクトル ![image](https://user-images.githubusercontent.com/25688193/45755706-10383e00-bc5a-11e8-9cc2-bb2702c0a49c.png) が存在していた。<br>
一方、内積空間 X の場合は、内積空間 X 上の全ての有界線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45755769-35c54780-bc5a-11e8-9851-e77923344393.png) が、![image](https://user-images.githubusercontent.com/25688193/45755805-4d043500-bc5a-11e8-89b1-5a214989bf10.png) の形で内積表現できるためには、内積空間が完備（＝即ち、ヒルベルト空間）であることが必要になる。（後述）<br>

このことを示すために、まず以下の補題で、必ずしも完備ではない内積空間 X が与えられているときに、内積で表現される有界線形汎関数の全体の集合 ![image](https://user-images.githubusercontent.com/25688193/45756177-31e5f500-bc5b-11e8-8a7c-7c492355f872.png) が、内積空間の共役空間 ![image](https://user-images.githubusercontent.com/25688193/45749947-3e148700-bc48-11e8-9b25-c3861d662b41.png) で稠密になり、内積空間 X 上に定義された任意の有界線形汎関数（の作用素ノルム）が、「内積で表現される有界線形汎関数（の作用素ノルム）」によって、いくらでも精度よく近似可能になることを示す。<br>

![image](https://user-images.githubusercontent.com/25688193/45804003-eb91a400-bcf5-11e8-90d1-a10f356ec846.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45799647-30630e00-bce9-11e8-911a-b422c9d7c710.png)<br>
- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45804177-5a6efd00-bcf6-11e8-8613-020a4e041674.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45800043-90a67f80-bcea-11e8-8a57-dfd11b88c7ad.png)<br>
- （証明）<br>
    - (a) の証明<br>
        有界線形汎関数 f の作用素ノルムは、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45803363-68238300-bcf4-11e8-89af-ad5818bcea75.png)<br>
        のように上限 sup の形で書けるので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45803548-da946300-bcf4-11e8-8d5b-c9777e230c3e.png)<br>
        となる点列 ![image](https://user-images.githubusercontent.com/25688193/45803584-f13aba00-bcf4-11e8-83e9-2596a8458d73.png) が存在する。<br>
        <br>
    - (b) の証明<br>
        (a) の ![image](https://user-images.githubusercontent.com/25688193/45804722-d584e300-bcf7-11e8-9748-87fe7049b6c0.png) の関係より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45804770-f9e0bf80-bcf7-11e8-99ae-62ba72ce1398.png)<br>
        従って、任意の ε>0 に対して、十分大きな正数 N が存在して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45804836-2a285e00-bcf8-11e8-9b53-e74e4156b582.png)<br>
        となるので、先の補題（内積で表現される有界線形汎関数の作用素ノルムの誤差評価）より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45804885-55ab4880-bcf8-11e8-9bcc-7e118192c013.png)<br>
        即ち、定理にある<br>
        ![image](https://user-images.githubusercontent.com/25688193/45804905-66f45500-bcf8-11e8-8774-1715ae2e189c.png)<br>
        の関係が成り立つことが分かる。<br>
        このことは、内積で表現される有界線形汎関数全体の集合 J(X) が稠密であることを示している。<br>
        <br>
        ここで、内積で表現される有界線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45813681-37504780-bd0e-11e8-8026-5fe571d14182.png) の作用素ノルムは、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45813704-4a631780-bd0e-11e8-890c-1484c9eae5cf.png)<br>
        となるので、このときの場合は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45813724-5c44ba80-bd0e-11e8-8687-802cc4209342.png)<br>
        となるので、点列 ![image](https://user-images.githubusercontent.com/25688193/45813787-839b8780-bd0e-11e8-896f-c8814229b964.png) はコーシー列である。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45816442-9ade7300-bd16-11e8-9cec-b1fcfea4935d.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45816517-ccefd500-bd16-11e8-8377-c0e942c869fe.png)<br>
- （証明略）<br>

> 【メモ】有界線形汎関数の内積表現によるヒルベルト空間の特徴づけ<br>
> 内積空間 X から実数 R への有界線形汎関数 f:X→R において、この有界線形汎関数全体が作る集合 X^∗=B(X,R) は、この内積空間の共役空間となるが、<br>
> 「この内積空間 X が完備でない」⇒「内積表現可能でない有界線形汎関数が存在する。」 となるので、内積空間 X 上の全ての有界線形汎関数 ∀f∈X^∗  が、内積の形で表現できるためには、X がヒルベルト空間でなくてはならない。<br>
> この要件によりヒルベルト空間を特徴づけることも出来る。<br>
> そしてこのことは、リースの表現定理への帰結とみなすこともできる。<br>


<a id="ID_A-6"></a>

### ◎ ハーン・バナッハの定理
関数解析における４つの corner stoens （一様有界性の定理、開写像定理、閉グラフ定理、ハーン・バナッハの定理）の１つであるハーン・バナッハの定理は、他の３つの定理をとは異なり。空間の完備性を必要としない。<br>

この定理は、一般的には。、ツォルンの補題を用いてノルム空間で議論されるが、ここでは簡単のため、内積空間に限定して議論する。<br>

![image](https://user-images.githubusercontent.com/25688193/45823961-d8003080-bd29-11e8-8fbf-1912a19c6055.png)<br>
- （証明）<br>
    先の定理（内積空間上の線形汎関数の表現と構成）の (a) より、<br>
    有界線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45832236-4ea62980-bd3c-11e8-8d18-38458aca30b4.png) に対して、内積空間の部分空間 M のコーシー列 ![image](https://user-images.githubusercontent.com/25688193/45832291-77c6ba00-bd3c-11e8-9c5a-4203b1b97c3e.png) が存在し、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45832327-8f05a780-bd3c-11e8-84c0-e18db60316f0.png)<br>
    のように有界線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45832236-4ea62980-bd3c-11e8-8d18-38458aca30b4.png) が表現出来る。<br>
    <br>
    逆に、部分空間 M のコーシー列 ![image](https://user-images.githubusercontent.com/25688193/45832291-77c6ba00-bd3c-11e8-9c5a-4203b1b97c3e.png) は、元の内積空間 X のコーシー列でもあるので、<br>
    先の定理（内積空間上の線形汎関数の表現と構成）の (b) より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45832499-02a7b480-bd3d-11e8-9d62-53900c365301.png)<br>
    によって、有界線形汎関数 ![image](https://user-images.githubusercontent.com/25688193/45832474-ef94e480-bd3c-11e8-9ea5-905e6a1e3974.png) を定義することが出来る。<br>
    <br>
    従って、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45832573-371b7080-bd3d-11e8-9614-c568eeeed236.png)<br>
    となり、この定理の１つ目の式 ![image](https://user-images.githubusercontent.com/25688193/45832588-47335000-bd3d-11e8-9bcc-69fb29a2bfa4.png) は満たされることが分かる。<br>
    <br>
    更に、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45832786-d3457780-bd3d-11e8-885f-f16520538f41.png)<br>
    の関係より、この定理の２つ目の式（＝作用素ノルムが等しい）も満たされることが分かる。<br>


<a id="ID_A-7"></a>

### ◎ 有界線形作用素の共役作用素
![image](https://user-images.githubusercontent.com/25688193/45932346-8a97f380-bfb5-11e8-84f4-860a62a5806d.png)<br>

※ リースの表現定理は、ヒルベルト空間に対しての定理なので、厳密には、この内積空間上での共役作用素の定義に対しては、一意性を示せない。（ヒルベルト空間上の共役作用素に対しては、リースの表現定理で共役作用素の一意性を示せる）<br>

この内積空間での一意性を示すための証明は以下の通り。<br>

共役作用素 B の他に、<br>
![image](https://user-images.githubusercontent.com/25688193/45835341-c5dfbb80-bd44-11e8-800d-bf8211af9a68.png)<br>
を満たすような写像 C が存在したとすると、<br>
![image](https://user-images.githubusercontent.com/25688193/45835363-dabc4f00-bd44-11e8-9088-4620d5286316.png)<br>
従って、共役作用素 B はただ１つのみ存在することが分かる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45932149-fb89dc00-bfb2-11e8-84a9-1a2eb5a4b13a.png)<br>
- （証明略）(a) における、共役作用素が有界線形作用素であることのみ示す。<br>
    - (a) の証明<br>
        - まず、共役作用素 ![image](https://user-images.githubusercontent.com/25688193/45864005-7c7a8500-bdb3-11e8-88da-3b368c765ac8.png) が、線形作用素であることを示す。<br>
            有界線形作用素の共役作用素 ![image](https://user-images.githubusercontent.com/25688193/45863705-50123900-bdb2-11e8-8820-3f7dee678c2d.png) が存在するならば、<br>
            共役作用素の定義 ![image](https://user-images.githubusercontent.com/25688193/45864692-c82e2e00-bdb5-11e8-99e2-922a9184b400.png) より、<br>
            任意の ![image](https://user-images.githubusercontent.com/25688193/45863736-7932c980-bdb2-11e8-9276-bb8f6b1249c2.png) と任意の係数 ![image](https://user-images.githubusercontent.com/25688193/45863746-8b146c80-bdb2-11e8-9a7d-20504cce4f43.png) に対して、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45863817-d0d13500-bdb2-11e8-8e8a-e1a59169edbd.png)<br>
            となるので、<br>
            ![image](https://user-images.githubusercontent.com/25688193/45864708-db40fe00-bdb5-11e8-96a3-0c8fa5c36015.png)<br>
            の関係より、共役作用素 ![image](https://user-images.githubusercontent.com/25688193/45864005-7c7a8500-bdb3-11e8-88da-3b368c765ac8.png) は、線形作用素であることが分かる。<br>
        - 次に、共役作用素 ![image](https://user-images.githubusercontent.com/25688193/45864005-7c7a8500-bdb3-11e8-88da-3b368c765ac8.png) が、有界であることを示す。<br>
        ![image](https://user-images.githubusercontent.com/25688193/45864968-eea09900-bdb6-11e8-80eb-e3525d25541b.png) とおけば、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45865019-155ecf80-bdb7-11e8-9ed7-a47a3a8d2fc9.png)<br>
        従って、共役作用素 ![image](https://user-images.githubusercontent.com/25688193/45864005-7c7a8500-bdb3-11e8-88da-3b368c765ac8.png) は、有界線形作用素であり、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45865172-94540800-bdb7-11e8-9c90-86bc7c21f8e1.png)<br>
        の関係が成り立つことが分かる。<br>


<a id="ID_A-7-1"></a>

#### ☆ 共役作用素の行列表現（表現行列）
![image](https://user-images.githubusercontent.com/25688193/45894398-29332180-be09-11e8-9841-d2a9cdedea9a.png)<br>


<a id="ID_A-8"></a>

### ◎ 自己共役作用素（エルミート作用素）
![image](https://user-images.githubusercontent.com/25688193/45932235-56700300-bfb4-11e8-8040-6bc6e7d31e29.png)<br>

- （例）自己共役作用素の例（直交射影）<br>
    ヒルベルト空間 H からその部分空間 M⊂H への直交射影 ![image](https://user-images.githubusercontent.com/25688193/45880813-2d007d00-bde4-11e8-928b-706b6f3dd666.png) は、<br>
    先の定理（ヒルベルト空間の閉部分空間への直交射影の線形性・冪等性・自己共役性）における自己共役性より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45880917-794bbd00-bde4-11e8-9314-2f390a82e37e.png)<br>
    の関係を満たすので、自己共役作用素である。<br>

- 【参考】<br>
    - [自己共役作用素（エルミート作用素）と有界性＜閉グラフ定理の応用＞](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E8%87%AA%E5%B7%B1%E5%85%B1%E5%BD%B9%E4%BD%9C%E7%94%A8%E7%B4%A0%E3%82%A8%E3%83%AB%E3%83%9F%E3%83%BC%E3%83%88%E4%BD%9C%E7%94%A8%E7%B4%A0%E3%81%A8%E6%9C%89%E7%95%8C%E6%80%A7%E9%96%89%E3%82%B0%E3%83%A9%E3%83%95%E5%AE%9A%E7%90%86%E3%81%AE%E5%BF%9C%E7%94%A8)
    - [ヒルベルト空間の閉部分空間への直交射影の線形性・冪等性・自己共役性](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%92%E3%83%AB%E3%83%99%E3%83%AB%E3%83%88%E7%A9%BA%E9%96%93%E3%81%AE%E9%96%89%E9%83%A8%E5%88%86%E7%A9%BA%E9%96%93%E3%81%B8%E3%81%AE%E7%9B%B4%E4%BA%A4%E5%B0%84%E5%BD%B1%E3%81%AE%E7%B7%9A%E5%BD%A2%E6%80%A7%E5%86%AA%E7%AD%89%E6%80%A7%E8%87%AA%E5%B7%B1%E5%85%B1%E5%BD%B9%E6%80%A7)


<a id="ID_C"></a>

## ■ 凸最適化問題への応用
先に見てきた、ヒルベルト空間における射影定理は、無限次元の空間における幾何学的性質を与えてくれた。この射影定理とこれから導入される幾何学的性質は、凸最適化問題にも応用出来る。<br>
ここでは、一般化された議論を行うために、「有限次元であるユークリッド空間での凸最適化問題」ではなく、「無限次元であるヒルベルト空間で定義された凸最適化問題」を考えた上で、<br>
以下のようなトピックを取り上げる。<br>
- 「凸最適化問題が、変分不等式問題に帰着できること」<br>
- 「変分不等式問題は、非線形写像の不動点を求める問題に帰着できること」<br>
- 「凸関数がいくつかの条件を満たすとき、不動点の逐次近似アルゴリズムを用いて、<br>
    　凸最適化問題の解がいくらでも精度良く近似出来ること」<br>

そのための前段階として、まず、無限次元であるヒルベルト空間における凸集合や凸関数に関連する性質が、有限次元であるユークリッド空間と同様に成り立つのかを見ていく。<br>


<a id="ID_C-1"></a>

### ◎ ヒルベルト空間における弱点列コンパクト性と凸集合
先に、ヒルベルト空間における弱収束と強収束の違いを見てきたが、ヒルベルト空間の弱収束点列の弱極限と凸集合との非自明な関係性を見ていく。<br>

![image](https://user-images.githubusercontent.com/25688193/45899373-9f3e8500-be17-11e8-8457-239c3ac06bf4.png)<br>

![image](https://user-images.githubusercontent.com/25688193/45899549-1aa03680-be18-11e8-999a-20a8267fac78.png)<br>

- （証明略）step 1：部分列のある実数への収束性の証明のみ記載<br>
    - step 1：部分列のある実数への収束性の証明<br>
        ヒルベルト空間 H の有界な点列 ![image](https://user-images.githubusercontent.com/25688193/45902097-56d79500-be20-11e8-85fc-423cfd1e069a.png) に対しては、その有界性より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45902413-5095e880-be21-11e8-9d4d-ca998ac83b01.png)<br>
        の関係が成り立つ。<br>
        このとき、有界な点列 ![image](https://user-images.githubusercontent.com/25688193/45902097-56d79500-be20-11e8-85fc-423cfd1e069a.png) との内積の値からなる点列 ![image](https://user-images.githubusercontent.com/25688193/45902438-699e9980-be21-11e8-8841-dcbf951a85e5.png) もまた、有界な実数列となるので、（ ![image](https://user-images.githubusercontent.com/25688193/45902479-88049500-be21-11e8-987a-a369e2349fa6.png) ）<br>
        ここで、ハイネ・ボネルの被覆定理より、点列コンパクトなので、<br>
        有界な点列 ![image](https://user-images.githubusercontent.com/25688193/45902947-10d00080-be23-11e8-8de1-5b683aba0b9b.png) に、少なくとも１つの部分列 ![image](https://user-images.githubusercontent.com/25688193/45902972-234a3a00-be23-11e8-95f0-0c01ab0823e0.png) とある ![image](https://user-images.githubusercontent.com/25688193/45902995-378e3700-be23-11e8-84f1-96afe3da7517.png) が存在して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45903295-21cd4180-be24-11e8-8a43-56ae14f9d630.png)<br>
        の関係が成り立つ。<br>
        同様の手続きで、部分列 ![image](https://user-images.githubusercontent.com/25688193/45902972-234a3a00-be23-11e8-95f0-0c01ab0823e0.png) の中に、さらなる部分列 ![image](https://user-images.githubusercontent.com/25688193/45903333-4a553b80-be24-11e8-8455-75237b223cf1.png) とある ![image](https://user-images.githubusercontent.com/25688193/45903348-5ccf7500-be24-11e8-8b27-04d674ac7fce.png) が存在して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45903415-9f914d00-be24-11e8-9b3d-efbf267570fb.png)<br>
        の関係が成り立つ。<br>
        同様の議論を繰り返すことにより、部分列 ![image](https://user-images.githubusercontent.com/25688193/45903714-9654b000-be25-11e8-82ca-75a4e54ef47b.png) に対して、ある ![image](https://user-images.githubusercontent.com/25688193/45903731-aa98ad00-be25-11e8-94a7-ad392c14bc80.png) が存在して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/45903758-be441380-be25-11e8-947b-36718f031f69.png)<br>
        の関係が成り立つことが分かる。<br>
        <br>
	- step 2：ヒルベルト空間の部分空間となる線形空間の存在性と、その空間上の有界線形作用素の証明<br>
	- step 3：ヒルベルト空間の部分空間となる線形空間が閉部分集合になることの証明<br>
    - step 4：部分列がヒルベルト空間の１点に収束することの証明<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45915138-f6ca0880-be8a-11e8-8b2f-1d752e2ae81f.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45915149-09dcd880-be8b-11e8-850a-9efa964ccb5b.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45915157-224cf300-be8b-11e8-82d6-d2eef2bc69be.png)<br>
![image](https://user-images.githubusercontent.com/25688193/45914336-a9479e80-be7e-11e8-9515-7450d63b5fdc.png)<br>
- （証明）<br>
    > 記載中...

- 【参考】<br>
    - [ヒルベルト空間における強収束と弱収束](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%92%E3%83%AB%E3%83%99%E3%83%AB%E3%83%88%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E5%BC%B7%E5%8F%8E%E6%9D%9F%E3%81%A8%E5%BC%B1%E5%8F%8E%E6%9D%9F)<br>
    - [コンパクト集合](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%82%B3%E3%83%B3%E3%83%91%E3%82%AF%E3%83%88%E9%9B%86%E5%90%88)<br>


<a id="ID_C-2"></a>

### ◎ ヒルベルト空間における凸関数と基本性質
![image](https://user-images.githubusercontent.com/25688193/45928487-63beca80-bf7f-11e8-91b4-f91b7f6b81c3.png)<br>

>【Memo】<br>
> 位相空間における下半連続性の定義との違いは？<br>
> ![image](https://user-images.githubusercontent.com/25688193/45928503-b8624580-bf7f-11e8-9df9-a80ef90db214.png)<br>

- 【参考】<br>
    - [半連続 - Wikipedia](https://ja.wikipedia.org/wiki/%E5%8D%8A%E9%80%A3%E7%B6%9A)<br>

![image](https://user-images.githubusercontent.com/25688193/45928672-78e92880-bf82-11e8-88c9-824308a1c80a.png)<br>

- （例）凸関数の例（自己共役作用素を用いて定義された関数）<br>
    ヒルベルト空間 H 上に定義された自己共役作用素 A:H→H とヒルベルト空間中のベクトル ![image](https://user-images.githubusercontent.com/25688193/45932375-13af2a80-bfb6-11e8-84aa-124f5cdbb75b.png) を用いた関数<br>
    ![image](https://user-images.githubusercontent.com/25688193/45932504-f5e2c500-bfb7-11e8-8966-6d4685864d93.png)<br>
    を定義する。<br>
    このとき、この関数 ![image](https://user-images.githubusercontent.com/25688193/45932509-0a26c200-bfb8-11e8-80f2-4bcd8f477a79.png) が凸関数となることと、<br>
    任意の ![image](https://user-images.githubusercontent.com/25688193/45932183-9682b600-bfb3-11e8-9eaf-3d6912fc27a5.png) に対して、![image](https://user-images.githubusercontent.com/25688193/45932595-60483500-bfb9-11e8-85fd-a8e2f30fbfdc.png) が成り立つことが等価であることを示す。<br>
    <br>
    任意の ![image](https://user-images.githubusercontent.com/25688193/45932519-24f93680-bfb8-11e8-8ab8-3f5e158f4177.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45932538-75709400-bfb8-11e8-9321-757561f44d93.png)<br>
    となるので、f:H→R が凸関数であれば、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45932573-30009680-bfb9-11e8-80ff-c01ebe232a00.png)<br>
    従って、以下のような関係が成り立つ。<br>
    ![image](https://user-images.githubusercontent.com/25688193/45932601-7e159a00-bfb9-11e8-8abb-bfeb071699d9.png)<br>


<a id="ID_C-3"></a>

### ◎ ヒルベルト空間における凸関数と最小値の存在性
ヒルベルト空間における凸集合と凸関数は、以下の定理で示すように、（有限次元のユークリッド空間のときと同様にして）エピグラフという概念によって、関連付けることが可能である。<br>

![image](https://user-images.githubusercontent.com/25688193/45942511-b0f17980-c01d-11e8-994d-8ddafbd361a8.png)<br>
- （証明略）<br>
    - (a) の証明<br>
        図より、エピグラフが凸集合であることと、元の関数 f が凸関数であることが同値なことは自明。<br>
        又、エピグラフは閉集合であるととと、元の関数 f が下半連続であることが同値なことは自明。<br>

- 【参照】<br>
    - [凸解析 - 初級Mathマニアの寝言](http://ogyahogya.hatenablog.com/entry/2016/05/19/%E5%87%B8%E8%A7%A3%E6%9E%90)<br>
    - [エピグラフ (数学) - Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%A8%E3%83%94%E3%82%B0%E3%83%A9%E3%83%95_(%E6%95%B0%E5%AD%A6))<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45953135-2708d700-c044-11e8-9268-2e709415d1a6.png)<br>
- （証明）<br>
    関数 f は下半連続な真凸関数なので、先の定理（エピグラフとその性質）より、点列 ![image](https://user-images.githubusercontent.com/25688193/45956965-d8ad0580-c04e-11e8-87fa-a40e2f0c3b96.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45958403-532b5480-c052-11e8-8e9a-7d7965cfceca.png)<br>
    ここで、内積部分の項は、![image](https://user-images.githubusercontent.com/25688193/45958439-68a07e80-c052-11e8-8598-0e4d191d3a07.png) の条件より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45958511-92f23c00-c052-11e8-85f7-7b799ee25d92.png)<br>
    となる。<br>
    従って、この内積からなる点列 ![image](https://user-images.githubusercontent.com/25688193/45958555-aef5dd80-c052-11e8-80d8-d189c419461d.png) は、有界であり、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45958579-c59c3480-c052-11e8-9a87-ee8723c5c282.png)<br>
    下極限の定義より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/45958622-e4023000-c052-11e8-8a8c-7dd6798c4ce1.png)<br>
    > 記載中...


- 【参照】<br>
    - [【補足】弱点列コンパクト性と凸集合](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#%E8%A3%9C%E8%B6%B3%E5%BC%B1%E7%82%B9%E5%88%97%E3%82%B3%E3%83%B3%E3%83%91%E3%82%AF%E3%83%88%E6%80%A7%E3%81%A8%E5%87%B8%E9%9B%86%E5%90%88)<br>
    - [上極限と下極限](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E4%B8%8A%E6%A5%B5%E9%99%90%E3%81%A8%E4%B8%8B%E6%A5%B5%E9%99%90)<br>
    - [半連続 - Wikipedia](https://ja.wikipedia.org/wiki/%E5%8D%8A%E9%80%A3%E7%B6%9A)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/45967816-0f444980-c06a-11e8-8666-78011e2ba1b6.png)<br>
- （証明略）２次元空間においては、図より自明<br>


<a id="ID_C-4"></a>

### ◎ ヒルベルト空間における凸関数の微分の単調性
![image](https://user-images.githubusercontent.com/25688193/46001535-7b649300-c0e6-11e8-8493-8f2584dfc0e4.png)<br>
- （証明）<br>
    - (a) ⇒ (b) の証明<br>
        ガトー微分の定義式<br>
        ![image](https://user-images.githubusercontent.com/25688193/46002801-f7aca580-c0e9-11e8-9240-695c03f91d03.png)<br>
        は、α∈R に関しての単調減少関数となっているので（計算略）、<br>
        任意の ∀λ∈R に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46002877-275bad80-c0ea-11e8-929c-376f312877e4.png)<br>
        の関係が成り立つ。<br>
        更に、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46003089-a650e600-c0ea-11e8-9c30-9ceaa6c38a82.png)<br>
        の関係より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46003123-b799f280-c0ea-11e8-95c8-92237b24c98e.png)<br>
        この式は、任意の ![image](https://user-images.githubusercontent.com/25688193/46003157-cda7b300-c0ea-11e8-8e2c-d7485daa95b6.png) に対して成り立っているので、<br>
        ヒルベルト空間中の任意の２点 ![image](https://user-images.githubusercontent.com/25688193/46003253-06e02300-c0eb-11e8-8cae-cfed24d6155a.png) に対しては、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46003280-195a5c80-c0eb-11e8-9551-07eed51c31b7.png)<br>
        が成り立つことが分かる。<br>
        この２つの式の両辺を足し合わせると、定理の (b) の単調写像の条件<br>
        ![image](https://user-images.githubusercontent.com/25688193/46003305-2a0ad280-c0eb-11e8-9b97-abaa1c4e5816.png)<br>
        が導かれる。<br>
        <br>
    - (b) ⇒ (a) の証明<br>
        ヒルベルト空間上の任意の固定されたベクトル ![image](https://user-images.githubusercontent.com/25688193/46012906-92ff4400-c105-11e8-91c8-e4ba304ebb7a.png) に対しての線形結合 ![image](https://user-images.githubusercontent.com/25688193/46012937-a7434100-c105-11e8-99cf-082e6e68c338.png) を、<br>
        ガトー微分関係な写像 f で写像した ![image](https://user-images.githubusercontent.com/25688193/46012981-c17d1f00-c105-11e8-8f16-552b1094f0c1.png) を写像先とする写像、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46013007-df4a8400-c105-11e8-815f-0166b7f1f741.png)<br>
        は、λ=0 or 1 で変数 λ に対して微分可能であり、その微分（導関数）は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46013068-0e60f580-c106-11e8-867b-46704355c1fa.png)<br>
        となる。<br>
        又、ガトー微分での導関数 f′ が定理 (b) の単調写像の条件<br>
        ![image](https://user-images.githubusercontent.com/25688193/46013098-2a649700-c106-11e8-874d-3f7e2763b3d2.png)<br>
        を満たすので、<br>
        任意の ![image](https://user-images.githubusercontent.com/25688193/46013744-17eb5d00-c108-11e8-86ad-c0d8e0dcc8cf.png) に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46013783-2d608700-c108-11e8-87f2-076714c47fe1.png)<br>
        となるので、この関数 ψ は凸関数であることが保証され（途中計算略）、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46013838-5e40bc00-c108-11e8-95c0-94607ac8e5f9.png)<br>
        が関係が成り立つ。<br>
        従って、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46014071-15d5ce00-c109-11e8-8531-b5a484102a44.png)<br>
        となり、ガトー微分可能な写像 f は凸関数であることが分かる。<br>

- 【参照】<br>
    - [ガトー微分](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%82%AC%E3%83%88%E3%83%BC%E5%BE%AE%E5%88%86)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/46018785-a6b2a680-c115-11e8-8690-380233113a66.png)<br>
- （証明）<br>
    - (a) の証明<br>
        任意の ∀t∈(0,1) とある２つのベクトル ![image](https://user-images.githubusercontent.com/25688193/46035856-0ec9b280-c13f-11e8-8ff4-e4dcfd6f72a4.png) に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46035905-2a34bd80-c13f-11e8-94df-efafdd5c6783.png)<br>
        の関係が成り立つので、この距離関数 ![image](https://user-images.githubusercontent.com/25688193/46036037-839cec80-c13f-11e8-8ecf-77090cdbc0de.png) は、凸関数である。<br>
        更に任意の ![image](https://user-images.githubusercontent.com/25688193/46036112-ae874080-c13f-11e8-824f-9edf5cc66db2.png) に対して、![image](https://user-images.githubusercontent.com/25688193/46036084-9d3e3400-c13f-11e8-823a-bffbaff8cc12.png) となるので、この距離関数 ![image](https://user-images.githubusercontent.com/25688193/46036037-839cec80-c13f-11e8-8ecf-77090cdbc0de.png) は、真凸関数となる。<br>
        <br>
    - (b) の２乗距離関数 ![image](https://user-images.githubusercontent.com/25688193/46037542-623dff80-c143-11e8-8ffb-1bbfbf310671.png) の凸性証明<br>
        任意の ∀t∈(0,1) とある２つのベクトル ![image](https://user-images.githubusercontent.com/25688193/46035856-0ec9b280-c13f-11e8-8ff4-e4dcfd6f72a4.png) に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46037626-a0d3ba00-c143-11e8-86e7-5c6d195119aa.png)<br>
        の関係が成り立つので、この２乗距離関数 ![image](https://user-images.githubusercontent.com/25688193/46037542-623dff80-c143-11e8-8ffb-1bbfbf310671.png) は、凸関数である。<br>
        <br>
    - (b) の２乗距離関数 ![image](https://user-images.githubusercontent.com/25688193/46037542-623dff80-c143-11e8-8ffb-1bbfbf310671.png) のフレッシェ微分可能性の証明<br>
        任意の ![image](https://user-images.githubusercontent.com/25688193/46067886-d4016200-c1b2-11e8-87f4-be990403df7a.png) に対して、２乗距離関数の変化量は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46067922-e7143200-c1b2-11e8-80d1-ff7b2b70059d.png)<br>
        ここで、直交射影 ![image](https://user-images.githubusercontent.com/25688193/46067966-ff844c80-c1b2-11e8-8960-90a91445897c.png) の定義より、この式から以下の２つの不等式が成り立つ。<br>
        ![image](https://user-images.githubusercontent.com/25688193/46067998-19259400-c1b3-11e8-97b2-2c527d6a1e37.png)<br>
        従って、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46068039-35c1cc00-c1b3-11e8-9fcf-9f7dfb279ec6.png)<br>
        更に、直交射影 ![image](https://user-images.githubusercontent.com/25688193/46067966-ff844c80-c1b2-11e8-8960-90a91445897c.png) の非拡大性より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46068114-66a20100-c1b3-11e8-9822-a12cf2b982b2.png)<br>
        従って、先の不等式<br>
        ![image](https://user-images.githubusercontent.com/25688193/46068141-76b9e080-c1b3-11e8-9260-bf1fbb33a2e8.png)<br>
        で ![image](https://user-images.githubusercontent.com/25688193/46068435-1aa38c00-c1b4-11e8-8d50-27e76c14703d.png) とすると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46068297-d912e100-c1b3-11e8-87fd-99f2bb989b54.png)<br>

- 【参照】<br>
    - [フレッシェ微分](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%95%E3%83%AC%E3%83%83%E3%82%B7%E3%82%A7%E5%BE%AE%E5%88%86)<br>


<a id="ID_C-5"></a>

### ◎ 凸最適化問題と変分不等式問題と不動点問題
![image](https://user-images.githubusercontent.com/25688193/46080379-c230b680-c1d4-11e8-95f0-573ab9553df4.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46082708-a9c39a80-c1da-11e8-9da5-b39cddf06282.png)<br>

<!--
![image](https://user-images.githubusercontent.com/25688193/46083243-f6f43c00-c1db-11e8-9dd4-48795244325c.png)<br>
-->

<br>

以下の定理は、「凸最適化問題」 と 「変分不等式問題」 と 「不動点問題」 とを結びつける定理であり、特に重要な定理となってる。<br>
※ ヒルベルト空間における凸射影、直交射影の概念を使っていることに注目<br>

![image](https://user-images.githubusercontent.com/25688193/46089954-9e786b00-c1ea-11e8-9e8e-e8e1cc9ca657.png)<br>
- （証明）<br>
    - (a) ⇒ (b) の証明<br>
        ![image](https://user-images.githubusercontent.com/25688193/46100940-a691d400-c205-11e8-8884-b58f0de474cd.png)<br>
        ならば、![image](https://user-images.githubusercontent.com/25688193/46101005-cc1edd80-c205-11e8-9fb0-4f34870f5263.png) の間の点 ![image](https://user-images.githubusercontent.com/25688193/46101040-e1940780-c205-11e8-817a-2be94334cba7.png) に対して、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46101107-0daf8880-c206-11e8-9956-29169d2c26b1.png)<br>
		が成り立つ。この式を変形して ![image](https://user-images.githubusercontent.com/25688193/46101293-84e51c80-c206-11e8-8237-749ddefe3ddc.png) とすると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46101438-d8f00100-c206-11e8-8c95-e938511b6ca6.png)<br>
    - (b) ⇒ (a) の証明<br>
        ガトー微分可能な真凸関数 f の凸性より、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46101723-a1ce1f80-c207-11e8-8fab-6b476fc35ef0.png)<br>
        変形して、![image](https://user-images.githubusercontent.com/25688193/46101293-84e51c80-c206-11e8-8237-749ddefe3ddc.png) とすると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46101751-b14d6880-c207-11e8-8c58-04437bf64fa6.png)<br>
    - (b) ⇔ (c) の証明<br>
        簡単な式変形となってる。<br>
    - (c) ⇔ (d) の証明<br>
        凸射影定理にある「凸射影の幾何学特徴付け」の関係<br>
        ![image](https://user-images.githubusercontent.com/25688193/46100414-49495300-c204-11e8-975b-96b9eaf57e10.png) より<br>
        (c) の条件と (d) の条件を比較すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46100694-f3c17600-c204-11e8-9c07-625ba066f0a7.png)<br>
        で対応しているので、(c) ⇔ (d) が成り立つ。<br>

<br>

- 【参照】<br>
    - [ヒルベルト空間における凸射影定理と直交射影定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E3%83%92%E3%83%AB%E3%83%99%E3%83%AB%E3%83%88%E7%A9%BA%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E5%87%B8%E5%B0%84%E5%BD%B1%E5%AE%9A%E7%90%86%E3%81%A8%E7%9B%B4%E4%BA%A4%E5%B0%84%E5%BD%B1%E5%AE%9A%E7%90%86)<br>


<a id="ID_C-6"></a>

### ◎ ヒルベルト空間における射影勾配法
ここで、以下の定理で示すように、<br>
特別な単調作用素 ![image](https://user-images.githubusercontent.com/25688193/46083283-13907400-c1dc-11e8-92ac-ee4f56fe4158.png) に対しては、非線形である直交射影の合成写像 ![image](https://user-images.githubusercontent.com/25688193/46083311-24d98080-c1dc-11e8-9a07-c66ec90e34fe.png) における μ の設定を工夫することにより、この非線形である直交射影の合成写像 ![image](https://user-images.githubusercontent.com/25688193/46083521-99acba80-c1dc-11e8-9932-98a8e0daff72.png) を縮小写像や非拡大写像にすることが出来る。(＝非線形である直交射影の合成写像の非拡大性）<br>
このことと、先の定理にあった、<br>
「凸最適化問題 」⇔ 「変分不等式問題」⇔ 「（非線形である直交射影の合成写像に対する）不動点問題」の結論を組み合わせると、<br>
種々の不動点定理（例えば、縮小写像の不動点定理など）から、変分不等式問題や不動点に関しての逐次近似アルゴリズム（例えば、射影勾配法など）を構築出来ることが分かる。<br>

![image](https://user-images.githubusercontent.com/25688193/46098791-1ef59680-c200-11e8-8099-ae57a9168ab2.png)<br>
- （証明）<br>
    - (a) の証明<br>
        直交射影の合成写像（＝非線形写像）![image](https://user-images.githubusercontent.com/25688193/46099558-0ab29900-c202-11e8-9024-5dbca36db754.png) の拡大性に関する式は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/46099508-ec4c9d80-c201-11e8-91b4-fdf91d20f8f2.png)<br>
        となる。<br>
		従って、非線形な直交射影の合成写像 ![image](https://user-images.githubusercontent.com/25688193/46099558-0ab29900-c202-11e8-9024-5dbca36db754.png) は、縮小写像になっていることが分かる。<br>
        <br>
    - (b) の証明<br>
        定理にも示しているように、<br>
        非線形な直交射影の合成写像 ![image](https://user-images.githubusercontent.com/25688193/46099558-0ab29900-c202-11e8-9024-5dbca36db754.png) が、縮小写像になるので、<br>
        縮小写像の不動点定理より、唯一の不動点 ![image](https://user-images.githubusercontent.com/25688193/46098163-b5c15380-c1fe-11e8-96a4-dc3b2ef34e82.png) に強収束する点列 ![image](https://user-images.githubusercontent.com/25688193/46098178-c40f6f80-c1fe-11e8-8067-1bcaa5c072cd.png) が存在する。<br>

<br>

> 【Memo】凸最適化問題に対する関数解析（主にヒルベルト空間と凸射影、縮小写像の不動点定理）の適用<br>
> １．ヒルベルト空間における凸射影（直交射影）の非拡大性 → 縮小写像の不動点定理 → 不動点の逐次近似アルゴリズムの議論が可能になる。<br>
> ２．凸最適化問題 → ヒルベルト空間における凸射影（直交射影）と単調写像やガトー微分の合成写像（非線形写像になる）に対する不動点問題に置き換え→この非線形写像の非拡大性 → 種々の不動点定理（縮小写像の不動点定理など） → 不動点の逐次近似アルゴリズムの議論（射影勾配法など）が可能になる。<br>

- 【参照】<br>
    - [縮小写像の不動点定理](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90_Note.md#-%E7%B8%AE%E5%B0%8F%E5%86%99%E5%83%8F%E3%81%AE%E4%B8%8D%E5%8B%95%E7%82%B9%E5%AE%9A%E7%90%86)<br>


<a id="ID_C-7"></a>

### ◎ 射影勾配法の一般化
先に見たように、凸最適化問題の古典的なアルゴリズム（射影勾配法）を、関数解析の視点（ヒルベルト空間、凸射影、直交射影、非拡大写像、縮小写像の不動点定理など）や不動点理論の視点から捉え直すことにより、凸最適化問題の古典的なアルゴリズム（射影勾配法）の非自明な一般化が可能となる。<br>

- 【参照】<br>
    - [最適化と信号処理（前編）～射影勾配法の２つの一般化～](https://www.jstage.jst.go.jp/article/itej/63/8/63_8_1088/_pdf)<br>
    - [非拡大写像の不動点表現が拓いた凸最適化の進化と信号処理への応用 (ウェーブレット解析とサンプリング理論)](https://repository.kulib.kyoto-u.ac.jp/dspace/bitstream/2433/224328/1/1972-01.pdf)<br>


<a id="ID_C-7-1"></a>

#### ☆ Mann の不動点近似定理と射影勾配法の弱収束定理
![image](https://user-images.githubusercontent.com/25688193/46137727-33c83d80-c285-11e8-907a-37b9aaef036f.png)<br>
- （証明略）<br>

<br>

以下の定理（Mann の不動点近似定理）は、非拡大写像の逐次近似を可能にする重要なアルゴリズムになっている。<br>

![image](https://user-images.githubusercontent.com/25688193/46140709-ccae8700-c28c-11e8-89c0-af3d0c90c9aa.png)<br>
- （証明略）<br>

<br>

以下の定理（射影勾配法の弱収束定理）は、この定理（Mann の不動点近似定理）を凸最適化問題に適用することにより得られる定理である。<br>

![image](https://user-images.githubusercontent.com/25688193/46156124-c1228680-c2b3-11e8-9ee8-872dea752451.png)<br>
- （証明略）<br>


<a id="ID_C-7-2"></a>

#### ☆ 射影 Landweber 法
射影 Landweber 法は、逐次近似アルゴリズムの１つであるが、射影勾配法の特別なケースでの一例となっている。<br>

![image](https://user-images.githubusercontent.com/25688193/46169205-5c782380-c2d5-11e8-820b-738ca79c118c.png)<br>
- （証明）<br>
    有界線形作用素 A の共役作用素 ![image](https://user-images.githubusercontent.com/25688193/46164727-b541bf00-c2c9-11e8-8e14-4b51bf57e70d.png) を用いて、関数 Φ を表現し直すことを考える。<br>
    ![image](https://user-images.githubusercontent.com/25688193/46166890-3f405680-c2cf-11e8-90dc-23487d269153.png)<br>
    ここで、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46164967-5597e380-c2ca-11e8-905f-c5b4268fccf1.png)<br>
    従って、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46166917-52ebbd00-c2cf-11e8-9c9c-adfe7fad70d2.png)<br>
    <br>
    ここで、先の例題（凸関数の例：自己共役作用素を用いて定義された関数）でみたように、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46165720-4b76e480-c2cc-11e8-8aa7-562ad8b0f3f5.png) に対して、<br>
    関数 f:H→R が凸関数となることと、<br>
    任意の ![image](https://user-images.githubusercontent.com/25688193/46165780-6ba6a380-c2cc-11e8-96ed-162577b7ba18.png) に対して、![image](https://user-images.githubusercontent.com/25688193/46165811-8416be00-c2cc-11e8-9645-328212f45a58.png) が成り立つことが等価であるので、<br>
    今の ![image](https://user-images.githubusercontent.com/25688193/46165880-b1636c00-c2cc-11e8-8a9d-0c19d219a698.png) の関係より、この関数 Φ は凸関数であることが分かる。<br>
    <br>
    更に、この関数 Φ のフレッシェ微分（ガトー微分でもある）は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46168449-7add1f80-c2d3-11e8-9637-6d9ee20ac9fc.png)<br>
    となるので（計算略）、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46168473-8e888600-c2d3-11e8-81be-6c841932ff75.png)<br>
    となり、フレッシェ微分（ガトー微分でもある）![image](https://user-images.githubusercontent.com/25688193/46169254-84678700-c2d5-11e8-8a3f-8aa101de82b7.png) は非拡大写像であることが分かる。<br>
    <br>
    そして、この結論（![image](https://user-images.githubusercontent.com/25688193/46169254-84678700-c2d5-11e8-8a3f-8aa101de82b7.png) は非拡大写像）に対して、射影勾配法を適用することが出来て、このアルゴリズム（射影 Landweber 法）が導かれる。<br>


<a id="ID_C-7-3"></a>

#### ☆ 並列射影法
並列射影法もまた、逐次近似アルゴリズムの１つであるが、射影勾配法の特別なケースでの一例となっている。<br>

> 記載中...



---


<a id="参考文献"></a>

## ■ 参考文献

- 工学のための関数解析 (工学のための数学) <br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E5%B7%A5%E5%AD%A6%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90-%E5%B7%A5%E5%AD%A6%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E6%95%B0%E5%AD%A6-%E5%B1%B1%E7%94%B0-%E5%8A%9F/dp/4901683624/ref=sr_1_1?ie=UTF8&qid=1535919962&sr=8-1&keywords=%E5%B7%A5%E5%AD%A6%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90)<br>

- 関数解析 共立数学講座 (15)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90-%E5%85%B1%E7%AB%8B%E6%95%B0%E5%AD%A6%E8%AC%9B%E5%BA%A7-15-%E9%BB%92%E7%94%B0-%E6%88%90%E4%BF%8A/dp/4320011066?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320011066)<br>

- 新版 応用のための関数解析―その考え方と技法 (SGC BOOKS)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E6%96%B0%E7%89%88-%E5%BF%9C%E7%94%A8%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90%E2%80%95%E3%81%9D%E3%81%AE%E8%80%83%E3%81%88%E6%96%B9%E3%81%A8%E6%8A%80%E6%B3%95-SGC-BOOKS-%E5%90%89%E7%94%B0/dp/4781911463?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4781911463)<br>

- カーネル法入門―正定値カーネルによるデータ解析 (シリーズ 多変量データの統計科学)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95%E5%85%A5%E9%96%80%E2%80%95%E6%AD%A3%E5%AE%9A%E5%80%A4%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E5%A4%9A%E5%A4%89%E9%87%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%B5%B1%E8%A8%88%E7%A7%91%E5%AD%A6-%E7%A6%8F%E6%B0%B4-%E5%81%A5%E6%AC%A1/dp/4254128088?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4254128088)<br>
