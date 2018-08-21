# 関数解析

## 目次 [Contents]

1. [概要](#ID_1)
1. [線形空間（ベクトル空間）](#ID_2)
    1. [張る（生成する）](#ID_2-1)
    1. [線形独立（一次独立）と線形従属（一次従属）](#ID_2-2)
        1. [線形独立（一次独立）と線形従属（一次従属）のイメージ](#ID_2-2-1)    
    1. [](#ID_2-3)
    1. [xxx](#ID_2-x)
1. 関数空間
    1. バナッハ空間 [Banach space]
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

#### ☆ 線形独立（一次独立）と線形従属（一次従属）のイメージ


---

<a id="参考文献"></a>

## ■ 参考文献

- 関数解析 共立数学講座 (15)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90-%E5%85%B1%E7%AB%8B%E6%95%B0%E5%AD%A6%E8%AC%9B%E5%BA%A7-15-%E9%BB%92%E7%94%B0-%E6%88%90%E4%BF%8A/dp/4320011066?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320011066)<br>

- カーネル法入門―正定値カーネルによるデータ解析 (シリーズ 多変量データの統計科学)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E6%B3%95%E5%85%A5%E9%96%80%E2%80%95%E6%AD%A3%E5%AE%9A%E5%80%A4%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E8%A7%A3%E6%9E%90-%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E5%A4%9A%E5%A4%89%E9%87%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%B5%B1%E8%A8%88%E7%A7%91%E5%AD%A6-%E7%A6%8F%E6%B0%B4-%E5%81%A5%E6%AC%A1/dp/4254128088?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4254128088)
