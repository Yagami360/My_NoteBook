# 関数解析

## 目次 [Contents]

1. [概要](#ID_1)
1. [線形空間（ベクトル空間）](#ID_2)
    1. [張る（生成する）](#ID_2-1)
    1. [線形独立（一次独立）と線形従属（一次従属）](#ID_2-2)
        1. [線形独立（一次独立）と線形従属（一次従属）の幾何学的イメージ](#ID_2-2-1)    
    1. [基底ベクトル](#ID_2-3)
    1. [ベクトルの次元](#ID_2-4)
1. [関数空間](#ID_3)
    1. [ノルムとノルム空間](#ID_3-1)
    1. [収束と極限](#ID_3-2)
    1. [Cauchy 列（基本列）と完備性](#ID_3-3)
    1. [バナッハ空間 [Banach space]](#ID_3-4)
    1. ヒルベルト空間 [Hilbert space]
        1. ヒルベルト空間の完全正規直交基底
    1. フーリエ級数展開
    1. フーリエ変換
    1. ルジャンドル多項式、ルジャンドル級数展開
1. 作用素
    1. 線形作用素
    1. コンパクト作用素
1. [xxx](#ID_x)
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## ■ 概要
> 記載中...


---

<a id="ID_2"></a>

## ■ 線形空間（ベクトル空間）
![image](https://user-images.githubusercontent.com/25688193/44356650-e40a8f80-a4ea-11e8-8401-40d46d43542a.png)<br>

<!--
![image](https://user-images.githubusercontent.com/25688193/44353953-7a3ab780-a4e3-11e8-9e0f-2579f21944cf.png)<br>
> 集合 X の任意の２つの要素 u,v に対して、<br>
u と v の和 ![image](https://user-images.githubusercontent.com/25688193/44354106-e87f7a00-a4e3-11e8-8772-f94af35b3da4.png) 及び、α と u の積 αu∈X が定義されていて、<br>
それらが、以下の８つの条件を満たす時、この集合 X は、複素線形空間（又は実線形空間）であるという。（但し、α,β は任意の複素数又は実数、u,v,w∈X）<br>
そして、この線形空間の要素のことをベクトルという。<br>
> 1. 加法の結合律：![image](https://user-images.githubusercontent.com/25688193/44354146-faf9b380-a4e3-11e8-8f49-be3f2b015a9c.png)<br>
>2. 加法の可換律：![image](https://user-images.githubusercontent.com/25688193/44354928-22518000-a4e6-11e8-90ad-77cd1536c210.png)<br>
>3. 加法単位元の存在：ゼロベクトル ![image](https://user-images.githubusercontent.com/25688193/44354956-34cbb980-a4e6-11e8-8f96-4805890bfc8b.png) が存在して、任意の u∈X に対して、![image](https://user-images.githubusercontent.com/25688193/44354973-43b26c00-a4e6-11e8-9ef2-1076500371ad.png) が成り立つ<br>
>4. 加法逆元の存在：任意の u∈X に対して、加法逆元 −u∈X が存在して、![image](https://user-images.githubusercontent.com/25688193/44355162-cdfad000-a4e6-11e8-9567-1cd45f156057.png)<br>
>5. 加法に対するスカラー乗法の分配律：α(u+v)=αu+αv<br>
>6. 体の加法に対するスカラー乗法の分配律：(α+β)u=αu+βu<br> 
>7. 体の乗法とスカラー乗法の両方条件：(αβ)u=α(βu)  <br>
>8. スカラー乗法の単位元の存在：1u=u<br>
-->

![image](https://user-images.githubusercontent.com/25688193/44385151-7ba6c700-a559-11e8-8b16-b6ec0ee1130f.png)<br>

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


---

<a id="ID_3"></a>

## ■ 関数空間
関数解析で扱う関数空間は、収束の概念などの位相的な性質をもつベクトル空間である。<br>
ここで、この収束の概念とは、
有次元ベクトル空間において、ベクトルの列 ![image](https://user-images.githubusercontent.com/25688193/44466778-1c7dab00-a65c-11e8-89d8-4f7f0ee1b465.png) とあるベクトル ![image](https://user-images.githubusercontent.com/25688193/44467081-ee4c9b00-a65c-11e8-9a34-44426b74fa69.png) の距離 ![image](https://user-images.githubusercontent.com/25688193/44467213-3ff52580-a65d-11e8-92f7-09f40d909d8c.png) が０に収束することである。
（このとき、ベクトルの列 ![image](https://user-images.githubusercontent.com/25688193/44466778-1c7dab00-a65c-11e8-89d8-4f7f0ee1b465.png) あるベクトル ![image](https://user-images.githubusercontent.com/25688193/44467081-ee4c9b00-a65c-11e8-9a34-44426b74fa69.png) に収束するという。）<br>


<a id="ID_3-1"></a>

### ◎ ノルムとノルム空間
ベクトルの長さに相当するいくつかの基本的性質のみ抽出すれば、より抽象的な概念として、より一般的な空間にも、ベクトルの長さに相当する概念を導入することが出来る。<br>
そしてその概念こそがノルムとなる。<br>

![image](https://user-images.githubusercontent.com/25688193/44467877-f6a5d580-a65e-11e8-8c5b-a6b1180245e6.png)<br>

- （例）<br>
    n 次元の複素ベクトル空間 ![image](https://user-images.githubusercontent.com/25688193/44469680-ff000f80-a662-11e8-9b4b-d78dddceadbb.png) において、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44469744-2060fb80-a663-11e8-8631-6e7cff12570a.png)<br>
    を定義すれば、ノルムの４つの条件式が成り立つので（計算略）、この ![image](https://user-images.githubusercontent.com/25688193/44469772-2d7dea80-a663-11e8-83c1-6eab48dc62ac.png) はノルムである。<br>
    <br>
    又、<br>
    ![image](https://user-images.githubusercontent.com/25688193/44470057-c9a7f180-a663-11e8-8d28-3b68b64d6d41.png)<br>
	もノルムの４つの条件式が成り立つので（計算略）、ノルムとなる。<br>
	
	このように１つの空間に導入し得るノルムは１つとは限らない。<br>


<a id="ID_3-3"></a>

### ◎ 収束と極限
![image](https://user-images.githubusercontent.com/25688193/44505648-85593780-a6dd-11e8-9b15-d0dcfbfd5533.png)<br>


<a id="ID_3-4"></a>

### ◎ Cauchy 列（基本列）と完備性
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


<a id="ID_3-5"></a>

### ◎ バナッハ空間 [Banach space]
![image](https://user-images.githubusercontent.com/25688193/44508109-0f0e0280-a6e8-11e8-9db4-61e32552669a.png)<br>

- （例）<br>
    閉区間 [a,b] 内の複数空間 C[a,b] は、ノルム<br>
    ![image](https://user-images.githubusercontent.com/25688193/44508696-2b12a380-a6ea-11e8-8b80-66ec7343808d.png)<br>
    に関して、完備であるか調べる。<br>
    <br>
    > 記載中...




---


<a id="参考文献"></a>

## ■ 参考文献

- 関数解析 共立数学講座 (15)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90-%E5%85%B1%E7%AB%8B%E6%95%B0%E5%AD%A6%E8%AC%9B%E5%BA%A7-15-%E9%BB%92%E7%94%B0-%E6%88%90%E4%BF%8A/dp/4320011066?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320011066)<br>

- カーネル法入門―正定値カーネルによるデータ解析 (シリーズ 多変量データの統計科学)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95%E5%85%A5%E9%96%80%E2%80%95%E6%AD%A3%E5%AE%9A%E5%80%A4%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E5%A4%9A%E5%A4%89%E9%87%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%B5%B1%E8%A8%88%E7%A7%91%E5%AD%A6-%E7%A6%8F%E6%B0%B4-%E5%81%A5%E6%AC%A1/dp/4254128088?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4254128088)
