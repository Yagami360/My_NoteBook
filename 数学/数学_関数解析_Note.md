# 関数解析
関数解析の基本事項を記載したマイノートです。随時追記中。<br>

## 目次 [Contents]

1. [概要](#ID_1)
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
        1. [開集合、閉集合](#ID_4-3-2)
        1. [写像の連続性](#ID_4-3-3)
        1. [コンパクト集合](#ID_4-3-4)
        1. [縮小写像の不動点定理](#ID_4-3-5)
        1. ベールの定理
        1. 可分性
1. [ノルムとノルム空間](#ID_5)
    1. [ノルム空間の例](#ID_5-1)
    1. [ノルム空間における Cauchy 列（基本列）と完備性](#ID_5-x)
    1. ノルムの位相構造
1. [内積空間](#ID_6)
1. [バナッハ空間 [Banach space]](#ID_7)
    1. [バナッハ空間の例](#ID_7-1)
1. [ヒルベルト空間 [Hilbert space]](#ID_8)
    1. [三平方の定理、中線定理](#ID_8-1)
    1. [ヒルベルト空間の例](#ID_8-2)
    1. ヒルベルト空間の完全正規直交基底
1. フーリエ級数展開とフーリエ変換
1. ルジャンドル級数展開
1. 作用素
    1. 線形作用素
    1. コンパクト作用素
1. [xxx](#ID_x)
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## ■ 概要
![image](https://user-images.githubusercontent.com/25688193/44618657-2221fd80-a8b5-11e8-85dd-caaa4b8d2c9e.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44618903-c3ab4e00-a8b9-11e8-8426-59eda8f1af4a.png)<br>

---

<a id="ID_2"></a>

## ■ 線形空間（ベクトル空間）
![image](https://user-images.githubusercontent.com/25688193/44356650-e40a8f80-a4ea-11e8-8401-40d46d43542a.png)<br>

![image](https://user-images.githubusercontent.com/25688193/44618648-13d3e180-a8b5-11e8-9160-c5b5544aa5e0.png)<br>

- （例）<br>
    １階の線形微分方程式<br>
    ![image](https://user-images.githubusercontent.com/25688193/44380172-d124a900-a544-11e8-93d9-0f34dac15bec.png)<br>
    において、方程式の解（ベクトル）<br>
    ![image](https://user-images.githubusercontent.com/25688193/44380222-03cea180-a545-11e8-8ef5-f24a5abc5996.png)<br>
    のすべてからなる集合 V はベクトル空間であることを示す。<br>
    <br>
	１階の線形微分方程式の解 ![image](https://user-images.githubusercontent.com/25688193/44384028-b7d82880-a555-11e8-9d88-7d0f64fc95a6.png) に対して、公理 (1),(2),(5),(6) は自明に成り立つ。<br>
	また、【定理１】より (7),(8) も成り立つ。<br>
    公理 (3) は、![image](https://user-images.githubusercontent.com/25688193/44384118-084f8600-a556-11e8-9dcd-cde4884ed788.png) に対して、![image](https://user-images.githubusercontent.com/25688193/44384210-61b7b500-a556-11e8-8c6f-65f5c606f41c.png)<br>
    公理 (4) は、![image](https://user-images.githubusercontent.com/25688193/44384499-5a44db80-a557-11e8-964a-d60c4c174b52.png) とすると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44384542-7fd1e500-a557-11e8-8bf2-358cd892d0f5.png)<br>
    つまり、![image](https://user-images.githubusercontent.com/25688193/44384499-5a44db80-a557-11e8-964a-d60c4c174b52.png) は、この微分方程式の解であり、集合 V に含まれるので成り立つ。（公理(4)を満たす）<br>
    よって、１階の線形微分方程式の解全体の集合はベクトル空間となる！<br>

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
    <br>
    ベクトルの組 ![image](https://user-images.githubusercontent.com/25688193/44393768-8456c780-a570-11e8-9695-43aad8df20d0.png) が線形従属か線形独立かを調べるために、<br>
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

![image](https://user-images.githubusercontent.com/25688193/44616618-07885e00-a88e-11e8-84c8-d465f53a53af.png)<br>


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
	ここで、距離空間において、点列がある点に収束するならば、その点列はコーシー列になるので（コーシー列の基本性質）、<br>
	この実数列 ![image](https://user-images.githubusercontent.com/25688193/44628126-4218f600-a975-11e8-8a7d-b09460299143.png) は、距離空間 ![image](https://user-images.githubusercontent.com/25688193/44624893-f8f58180-a935-11e8-94da-3e66b3aab318.png) のコーシー列になる。<br>
    そして、有理数の距離空間 ![image](https://user-images.githubusercontent.com/25688193/44628393-e00ebf80-a979-11e8-89a8-c7235400f083.png) のコーシー列でもある。<br>
    <br>
	従って、この有理数の距離空間 ![image](https://user-images.githubusercontent.com/25688193/44628393-e00ebf80-a979-11e8-89a8-c7235400f083.png) は、完備”でない”距離空間になる。<br>
	（一方、実数の距離空間 ![image](https://user-images.githubusercontent.com/25688193/44628399-f61c8000-a979-11e8-9d00-97e43453a8d2.png) は、完備な距離空間である。）<br>

- （例）距離空間 ![image](https://user-images.githubusercontent.com/25688193/44646962-b1472680-aa17-11e8-9714-156772648b3b.png)<br>
    距離空間 ![image](https://user-images.githubusercontent.com/25688193/44646962-b1472680-aa17-11e8-9714-156772648b3b.png) が完備であるかを調べる。<br>
    <br>
	コーシー列と完備性の関係（＝任意のコーシー列が収束するなら、その距離空間は完備）より、<br>
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
    <br>
	次に、![image](https://user-images.githubusercontent.com/25688193/44706125-8c1bec00-aadb-11e8-89b0-8098ca2878d9.png) は、点列 ![image](https://user-images.githubusercontent.com/25688193/44706144-9ccc6200-aadb-11e8-8903-9fee78b58ce4.png) の有力な収束先の候補であるが、<br>
	実際に、![image](https://user-images.githubusercontent.com/25688193/44706403-6fcc7f00-aadc-11e8-81ab-41b553dbf8bc.png) となり ![image](https://user-images.githubusercontent.com/25688193/44706436-870b6c80-aadc-11e8-9777-e2bf8eaa7821.png) となることを示す。<br>
    先の<br>
    ![image](https://user-images.githubusercontent.com/25688193/44706612-23357380-aadd-11e8-90df-a38964ed9fd9.png)<br>
    の関係より、任意の ![image](https://user-images.githubusercontent.com/25688193/44706659-4d873100-aadd-11e8-9e0d-cb982747ab0b.png) に対して、n,m>N ならば、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44706677-61cb2e00-aadd-11e8-8dd6-5a0fd65f6aff.png)<br>
    > 記載中...<br>


<a id="ID_4-3-2"></a>

#### ☆ 開集合、閉集合
> 記載中...


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

![image](https://user-images.githubusercontent.com/25688193/44764472-d27c5400-ab8a-11e8-8950-3afaeb718750.png)<br>
    ※ この定義の条件（ ![image](https://user-images.githubusercontent.com/25688193/44724450-b38bac80-ab0d-11e8-95ea-535fa99872bf.png) ）は、<br>
    　 距離空間 X,Y の開球 ![image](https://user-images.githubusercontent.com/25688193/44724481-c7371300-ab0d-11e8-99df-03d73a5cbb91.png) の言葉を用いると、以下のように表現できる。<br>
    　 ![image](https://user-images.githubusercontent.com/25688193/44724516-df0e9700-ab0d-11e8-8536-bcb83b5b82ac.png)<br>


<a id="ID_4-3-4"></a>

#### ☆ コンパクト集合
コンパクト性は、距離空間の部分集合に関する性質である。<br>

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



<a id="ID_5"></a>

## ■ ノルムとノルム空間
ベクトルの長さに相当するいくつかの基本的性質のみ抽出すれば、より抽象的な概念として、より一般的な空間にも、ベクトルの長さに相当する概念を導入することが出来る。<br>
そしてその概念こそがノルムとなる。<br>

![image](https://user-images.githubusercontent.com/25688193/44467877-f6a5d580-a65e-11e8-8c5b-a6b1180245e6.png)<br>

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

<a id="ID_6"></a>

## ■ 内積空間
> 記載中...



<a id="ID_7"></a>

## ■ バナッハ空間 [Banach space]
![image](https://user-images.githubusercontent.com/25688193/44508109-0f0e0280-a6e8-11e8-9db4-61e32552669a.png)<br>

<a id="ID_7-1"></a>

### ◎ バナッハ空間の例
- （例）<br>
    閉区間 [a,b] 内の複数空間 C[a,b] は、ノルム<br>
    ![image](https://user-images.githubusercontent.com/25688193/44508696-2b12a380-a6ea-11e8-8b80-66ec7343808d.png)<br>
    に関して、完備であるか調べる。<br>
    <br>
    > 記載中...


<a id="ID_8"></a>

## ■ ヒルベルト空間 [Hilbert space]
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


<a id="ID_8-1"></a>

### ◎ ３平方の定理や中線定理
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


<a id="ID_8-2"></a>

### ◎ ヒルベルト空間の例
> 記載中...

- （例）　ヒルベルト空間の例<br>
    <br>



---


<a id="参考文献"></a>

## ■ 参考文献

- 関数解析 共立数学講座 (15)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90-%E5%85%B1%E7%AB%8B%E6%95%B0%E5%AD%A6%E8%AC%9B%E5%BA%A7-15-%E9%BB%92%E7%94%B0-%E6%88%90%E4%BF%8A/dp/4320011066?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320011066)<br>

- カーネル法入門―正定値カーネルによるデータ解析 (シリーズ 多変量データの統計科学)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95%E5%85%A5%E9%96%80%E2%80%95%E6%AD%A3%E5%AE%9A%E5%80%A4%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E5%A4%9A%E5%A4%89%E9%87%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%B5%B1%E8%A8%88%E7%A7%91%E5%AD%A6-%E7%A6%8F%E6%B0%B4-%E5%81%A5%E6%AC%A1/dp/4254128088?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4254128088)
