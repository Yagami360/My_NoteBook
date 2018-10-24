# 測度論 [measure theory] / ルベーグ積分
測度論とルベーグ積分の基本事項を記載したマイノートです。随時追記中。<br>

## 目次 [Contents]

1. [概要](#ID_1)
1. [測度に基づく積分の定義](#ID_2)
    1. [σ-加法族（完全加法族）](#ID_2-1)
    1. [測度、測度空間](#ID_2-2)
    1. [可測性（可測関数、可測集合）](#ID_2-3)
    1. [単関数](#ID_2-4)
    1. [可測関数の積分（ルベーグ積分）](#ID_2-5)
        1. ディリクレ関数を用いた積分
1. [測度に基づく積分の性質](#ID_3)
    1. [σ-加法族の性質と可測性](#ID_3-1)
    1. [単関数の積分とその性質](#ID_3-2)
    1. [可測関数の積分の性質](#ID_3-3)
    1. [エゴロフの定理](#ID_3-4)
    1. [ファトゥの補題](#ID_3-5)
    1. [単調収束定理](#ID_3-6)
    1. [ルベーグの収束定理](#ID_3-7)
1. [測度０の集合](#ID_4)
    1. [ほとんどいたるところ [almost everyewhere]](#ID_4-1)
    1. [積分の定義のほとんどいたるところを用いた表現](#ID_4-2)
    1. [各種収束定理のほとんどいたるところを用いた表現](#ID_4-3)
    1. [Lp 空間の完備性と測度の σ-加法性](#ID_4-4)
1. [ルベーグ積分の具体的な計算（一次元ルベーグ積分）](#ID_5)
1. [有限加法的測度（ジョルダン測度）とそれが誘導する外測度](#ID_6)
    1. [面積の過大評価と過小評価（内面積、外面積）](#ID_6-1)
    1. [有限加法的測度（ジョルダン測度）](#ID_6-2)
        1. [非減少関数が誘導する有限加法的測度](#ID_6-2-1)
    1. [集合の分割](#ID_6-3)
    1. [半加法族](#ID_6-4)
    1. [有限加法的測度（ジョルダン測度）が誘導する外測度](#ID_6-5)
        1. [劣加法性と σ-加法性](#ID_6-5-1)
        1. [有限加法的測度が誘導する外測度の性質](#ID_6-5-2)
        1. [非減少関数の誘導するルベーグ-スティルチェル外測度、１次元ルベーグ外測度](#ID_6-5-3)
1. [カラテオドリ外測度からの測度の構成](#ID_7)
    1. [カラテオドリ外測度](#ID_7-1)
    1. [カラテオドリ外測度に関しての可測性（可測集合、可測集合族）](#ID_7-2)
    1. [カラテオドリ外測度に関しての可測集合族の σ-加法性](#ID_7-3)
    1. 零集合
    1. 完備測度空間
    1. ホップ [Hopf] の拡張定理
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## ■ 概要
ここでは、測度論、及び、ルベーグ積分の概要と全体像を、以下のトピックの観点から見ていく。<br>

1. 複雑な関数の積分で生じる問題（リーマン積分の問題点）<br>

2. ルベーグ積分の視点（縦割り分割 → 横割り分割）<br>

3. 測度に基づく積分<br>

    > 【メモ】
    > 測度に基づく積分の定義の流れ<br>
    > - 積分を計算する際に、図形をより細かい図形で分割して和をとる。<br>
    > - その分割した図形のリストは、面積の分割に関する加法性（＝複雑な形でも分割すれば面積を求められる）を満たす。<br>
    > - この分割図形のリストにおける加法性の性質が、σ-加法族を構成する各集合に対応できる。<br>
    > - この σ-加法族（＝分割した図形のリストに対応）の集合の大きさ（＝面積など）を測る写像として測度を定義する。<br>

4. ルベーグ積分を導入することのメリット<br>

<br>

1. 複雑な関数の積分<br>
    > 記載中...<br>

<br>

2. ルベーグ積分の視点<br>
    > 記載中...<br>

    積分では、様々な形でのある種の単調性がポイントとなる。<br>
    （例えば、リーマン積分における分割和の極限など）<br>
    このことは、面積の分割に対する加法性（＝複雑な形状のものでも、分割すればその加法で面積が求められる性質）に起因している。<br>
    <br>
    ルベーグ積分では、可算無限個までの面積の分割を許可した上で、その面積の分割に対する加法性を考える。
    その結果として、測度という概念が必要になってくる。<br>
    言い換えれば、測度という概念を使って、加重和で表現した面積を定めると、大変うまく機能する。<br>
    <br>
    ![image](https://user-images.githubusercontent.com/25688193/46857755-a4a25480-ce44-11e8-93b2-c6f8a9219c92.png)<br>
    <br>
    ルベーグ積分では、可算無限個までの面積の分割を許可した上で、その面積の分割に対する加法性を考える。その結果として、測度という概念が必要になってくる。<br>
    言い換えれば、測度という概念を使って、加重和で表現した面積を定めると、大変うまく機能する。<br>

<br>

3. 測度に基づく積分<br>
    以下、この測度に基づく積分がどうのようなものなのか？の概要を見ていく。<br>
    <br>
    面積を測る操作（＝測度）を、「図形のリストに対して、ある実数値を対応させること」 と考える。<br>
    即ち、図形のリスト B に対し、面積を測る操作（一種の写像）を、![image](https://user-images.githubusercontent.com/25688193/46858662-bf75c880-ce46-11e8-8904-3170ed8908a9.png) で表記することにする。<br>
    （※この図形のリスト B とは、言い換えれば、ユークリッド空間 ![image](https://user-images.githubusercontent.com/25688193/46858829-298e6d80-ce47-11e8-8994-3d595dd28649.png) の部分集合を要素とする集合族のことである。）<br>
    <br>
    その上で、この操作（写像）μ の加法性を定義するのであるが、この加法性を定めるには、予め図形のリストの形状（大きさ）に関する構造が定まっている必要がある。<br>
    そのためにまずは、以下のように定義される完全加法族なるものを導入する。<br>
    <br>
    ![image](https://user-images.githubusercontent.com/25688193/46900327-30ff5680-cedb-11e8-96b1-13ed1aae92f7.png)<br>
    <br>
    その上で、この図形のリスト B を測る操作（＝写像） μ に対しての加法性を導入し、以下のように測度として定義する。<br>
    <br>
    ![image](https://user-images.githubusercontent.com/25688193/46900335-44aabd00-cedb-11e8-80d0-bea74fc8fda1.png)<br>
    <br>
    この測度の中で、特に面積に関する測度が、ルベーグ積分となる。<br>
    即ち、２次元ルベーグ測度は、以下のように定義される。<br>
    ![image](https://user-images.githubusercontent.com/25688193/46859095-c5b87480-ce47-11e8-8990-e5559cfbb703.png)<br>
    > 記載中...<br>

<br>

4. ルベーグ積分を導入することでのメリット<br>
    > 記載中...<br>


<a id="ID_2"></a>

## ■ 測度に基づく積分の定義
ここでは、先の概要で述べたことを、改めて、より一般的な形式で厳密に定義する。<br>

<a id="ID_2-1"></a>

### ◎ σ-加法族（完全加法族）
![image](https://user-images.githubusercontent.com/25688193/47439662-bf32e100-d7e7-11e8-87fc-f2fb8958aa14.png)<br>


<a id="ID_2-2"></a>

### ◎ 測度、測度空間
σ-加法族を定義した上で、この σ-加法族 B（＝図形のリストに対応）を測る操作（＝写像） μ に対しての加法性を導入し、以下のように測度として定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/46900508-38742f00-cede-11e8-92eb-fb785c9f4a86.png)<br>

![image](https://user-images.githubusercontent.com/25688193/46904837-94ae7180-cf25-11e8-9e44-375dcfcf9aa2.png)<br>

以下、<br>
![image](https://user-images.githubusercontent.com/25688193/46926806-4efcc080-d06d-11e8-8d58-79ed5486d0ee.png)<br>
という文言を、この測度空間の言葉を用いて<br>
![image](https://user-images.githubusercontent.com/25688193/46926820-5d4adc80-d06d-11e8-837e-1f21a5d15572.png)<br>
と記述する。<br>


<a id="ID_2-3"></a>

### ◎ 可測性（可測関数、可測集合）
先に見た積分対象関数の横方向へのスライスから生じる集合（＝図形の分割）は、以下の定義で定義される可測関数に対して、σ-加法族に属することになる。<br>
逆に言えば、横方向スライスから生じる集合が、σ-加法族に属するように、可測関数、可測集合なるものを定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/47376518-c1d10000-d72d-11e8-9f5c-b9312d3a8649.png)<br>


<a id="ID_2-4"></a>

### ◎ 単関数
![image](https://user-images.githubusercontent.com/25688193/46926868-95eab600-d06d-11e8-8ddb-742681bb219f.png)<br>


<a id="ID_2-5"></a>

### ◎ 可測関数の積分（ルベーグ積分）
この σ-加法族、測度、及び、可測関数、単関数を元に、可測関数に対しての積分、即ち、ルベーグ積分が定義できる。<br>

![image](https://user-images.githubusercontent.com/25688193/47377212-97804200-d72f-11e8-9640-9a45d64332af.png)<br>

> 【Memo】ルベーグ積分の柔軟性と σ-加法族<br>
> リーマン積分では、最初から定義域を画一的に分割しているが、その故に、あまり融通が利かなかった。<br>
> 一方、ルベーグ積分では、値域の分割の逆像を考えるので、定義域の分割は区間とは限らず、もっと広く、σ-加法族に属していればよい。<br>
> そのため、定義域を柔軟に分割することが出来る。<br>
> それ故に、ルベーグ積分では、リーマン積分より広い関数を扱うことが出来るのである。<br>

<br>

次に、このように定義した積分に対しての積分可能性（＝可積分、可積分関数）を議論するのであるが、<br>
更に、可積分関数 f に対しての ![image](https://user-images.githubusercontent.com/25688193/46903224-08905000-cf0d-11e8-8220-83357a6f9cb6.png) 条件を利用することで、この可積分性（＝可積分関数）から積分を再定義することも出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/46926929-e2ce8c80-d06d-11e8-9fef-2df2a8cdd641.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/46934244-f986da80-d091-11e8-93b7-5ba3034e6ae1.png)<br>



<a id="ID_3"></a>

## ■ 測度に基づく積分の性質

- 【参考】<br>
    - [ときわ台学/ルベーグ積分/収束定理](http://www.f-denshi.com/000TokiwaJPN/16lebeg/100lbg.html)<br>


<a id="ID_3-1"></a>

### ◎ σ-加法族の性質と可測性
ここでは、先に見てきた関数の可測性の観点から、σ-加法族を再度見直してみる。<br>

まずは、σ-加法族の定義を、可測関数の視点で捉え直す。<br>

![image](https://user-images.githubusercontent.com/25688193/46904861-ea831980-cf25-11e8-850e-6108707db2da.png)<br>

- （証明）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/46934305-3b178580-d092-11e8-8438-4621a26119e6.png)<br>

- （証明）<br>


<a id="ID_3-2"></a>

### ◎ 単関数の積分とその性質
積分に関する一般的な性質（線形性など）を、先の積分の定義から直接導出するのは、困難である。
そこでまずは、単関数の場合に限定し、更に、積分の性質を確かめるための補助的な量を別途定義した上で、先の積分の定義と関連付けて議論することにする。<br>

![image](https://user-images.githubusercontent.com/25688193/46926699-c9791080-d06c-11e8-801c-2c5fe5329b3b.png)<br>

積分の性質（線形性など）との関連付けて議論するために、このように定義した補助的な量に対して、いくつかの性質を見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/46926967-232e0a80-d06e-11e8-8a1a-e0b6df299317.png)<br>

- （証明）<br>
    合成関数 h の値域 range(h) に関して、以下のような関係が成り立つ。<br>
    ![image](https://user-images.githubusercontent.com/25688193/46912850-a8a4b280-cfbb-11e8-991f-4947b47c7fe4.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/46912861-e570a980-cfbb-11e8-8ac7-c03cca11e1ee.png)<br>
    更に、関数 ϕ の値域の有限値を定める定数 ![image](https://user-images.githubusercontent.com/25688193/46912854-b78b6500-cfbb-11e8-94fc-02608e52092a.png) に対して、以下のような関係が成り立つ。<br>
    ![image](https://user-images.githubusercontent.com/25688193/46912874-36809d80-cfbc-11e8-8009-eff374e1d646.png)<br>
    この式は、例えば、![image](https://user-images.githubusercontent.com/25688193/46912879-5a43e380-cfbc-11e8-85c3-355ee1a788d5.png) のときは、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46912885-6f207700-cfbc-11e8-8482-5f6be6865250.png)<br>
    となり、下図のように、２つの単関数 f,g の組み合わせによって、![image](https://user-images.githubusercontent.com/25688193/46912890-9d05bb80-cfbc-11e8-96c4-f9b18bf374ab.png) 領域の分割が生じる様子を示している。<br>
    ![image](https://user-images.githubusercontent.com/25688193/46912933-c70bad80-cfbd-11e8-85a7-53d1d779f1ed.png)<br>
    ここで、<br>
	「値域 range(h) が、可算集合ならば、関数 h の可測性は、y∈range(h) に対して、![image](https://user-images.githubusercontent.com/25688193/46912990-3f26a300-cfbf-11e8-93fc-21eab7f257b5.png) が成り立つことと同値である」<br>
	という関係（証明略）より、<br>
	上式の右辺（＝上図に示した分割領域の和集合）が、有限集合であり、σ-加法族 B に属することは、
	合成関数 h が、B-可測関数であることを意味している。<br>
	従って、合成関数 h は、単関数である。<br>

<br>

この単関数の合成関数の性質を、<br>
先に定義した積分の性質を確かめるための補助的な量<br>
![image](https://user-images.githubusercontent.com/25688193/46913036-69c52b80-cfc0-11e8-8065-40b027c2a7b2.png)<br>
に適用すると、以下のような定理が導かれる。<br>

![image](https://user-images.githubusercontent.com/25688193/46926991-422c9c80-d06e-11e8-8020-02c22ec184b8.png)<br>

- （証明略）<br>

<br>

この定理から、ここでの主目的であった、<br>
積分の性質を確かめるための補助的な量 ![image](https://user-images.githubusercontent.com/25688193/46913070-17d0d580-cfc1-11e8-90d0-502dde717076.png) に対する、積分演算で一般的に成り立つ性質（線形性など）の導出と、<br>
この補助的な量 ![image](https://user-images.githubusercontent.com/25688193/46913070-17d0d580-cfc1-11e8-90d0-502dde717076.png) が、積分の定義に一致する、即ち、![image](https://user-images.githubusercontent.com/25688193/46913072-2c14d280-cfc1-11e8-8c2d-0cbf93264e4b.png) の関係を示すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/46927017-65574c00-d06e-11e8-94d7-ddd0390f6082.png)<br>

- （証明略）<br>


<a id="ID_3-3"></a>

### ◎ 可測関数の積分の性質
以下、可測関数の積分に関しての、基本的な性質を見ていく。<br>
まずは、測度 μ の有限加法性に起因する性質を見ていく。<br>

![image](https://user-images.githubusercontent.com/25688193/46934377-7ca83080-d092-11e8-929b-8ac45931a885.png)<br>

- （証明略）

<br>

次に、σ-加法性に起因する性質を見ていく。<br>

> 記載中...


<a id="ID_3-4"></a>

### ◎ エゴロフの定理
<!--
可測関数の積分は、単関数の点列で可測関数を近似した上で定義する方法と、単関数の積分の上限で定義する方法の２通り考えられるが、<br>
以下に示すエゴロフの定理を用いれば、これらの２つの値が一致することを示すことが出来る。<br>
-->

![image](https://user-images.githubusercontent.com/25688193/46936622-e11abe00-d099-11e8-87b5-ef46812714a3.png)<br>

- （証明略）図より自明<br>

<br>

このエゴロフの定理を用いれば、<br>
積分の基本性質である、「（単関数における）極限と積分の順序の交換可能性」を示すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/46938746-7c626200-d09f-11e8-994d-a91dcc2c36ef.png)<br>

- （証明）<br>
    > 記載中...


<a id="ID_3-5"></a>

### ◎ ファトゥの補題
単調収束定理やルベーグ収束定理を示すための前段階として、以下のファトゥの補題を示す。<br>
このファトゥの補題は、このファトゥの補題は、先の単関数に対する極限と積分の交換可能性の性質を、可測関数に拡張したものになっている。<br>

![image](https://user-images.githubusercontent.com/25688193/46940028-b8e38d00-d0a2-11e8-867b-31b463666293.png)<br>

- （証明略）<br>


<a id="ID_3-6"></a>

### ◎ 単調収束定理
ファトゥの補題を用いれば、以下の単調収束定理を示すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/47134171-c6895480-d2e6-11e8-9283-80bc4d7c4a1b.png)<br>

- （証明）<br>
    定理の参考図にも示しているように、<br>
    可測集合 A∈B 上で、可測関数の単調増加の点列 ![image](https://user-images.githubusercontent.com/25688193/46940732-64d9a800-d0a4-11e8-93cc-a42a39f3f0c0.png) に対しては、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46940770-78850e80-d0a4-11e8-8054-f292ee538398.png)<br>
    の関係が成り立つので、これを、ファトゥの補題の関係式<br>
    ![image](https://user-images.githubusercontent.com/25688193/46941100-4a53fe80-d0a5-11e8-9619-12dc0c841223.png)<br>
    に代入すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46941157-6fe10800-d0a5-11e8-834a-015288ce09a0.png)<br>
    <br>
    また、積分の単調性の性質 ![image](https://user-images.githubusercontent.com/25688193/46941739-cb5fc580-d0a6-11e8-8c09-c4ce1ea909b1.png) より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/46941801-e3374980-d0a6-11e8-9ad5-af7cb7797e4a.png)<br>


<a id="ID_3-7"></a>

### ◎ ルベーグ収束定理
ファトゥの補題から導かれるルベーグ-ファトゥの補題（＝ファトゥの不等式）を用いれば、
以下のルベーグの収束定理も示すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/46996226-da05b580-d156-11e8-8bbc-e87a861740b2.png)<br>
![image](https://user-images.githubusercontent.com/25688193/46996194-be9aaa80-d156-11e8-882f-cd39213942a0.png)<br>

- （証明略）<br>


<a id="ID_4"></a>

## ■ 測度０の集合
> 記載中...

<a id="ID_4-1"></a>

### ◎ ほとんどいたるところ [almost eyerywhere]
![image](https://user-images.githubusercontent.com/25688193/47011447-f4eb2080-d17c-11e8-97d0-32930af5b06f.png)<br>

この零集合は、その定義より、測度０の集合となるが、測度０の集合上での違いは、積分に影響せず無視できるという事実がある。（証明略）<br>
そこで、積分に影響しない例外（今の場合、測度０の零集合）に関しては、無視する。<br>
ということを表す概念を導入することを考える。<br>
この概念こそが、以下のほとんどいたるところの概念になる。<br>

![image](https://user-images.githubusercontent.com/25688193/47012296-ef8ed580-d17e-11e8-89fe-8c187e02989d.png)<br>

以下、例を用いて、このほとんどいたるところの概念が、「積分上無視できる部分を除いて」の意味になっていることを示す。<br>

- （例）積分上無視できる部分が存在する積分<br>
    ![image](https://user-images.githubusercontent.com/25688193/47013471-37632c00-d182-11e8-8e1a-e2914809f6ab.png)<br>
    という関数を 0~1 の範囲で積分 ![image](https://user-images.githubusercontent.com/25688193/47013491-4ea21980-d182-11e8-890d-9a40e6f3dc40.png) することを考える。<br>
    <br>
    この関数は x=0.5 以外では、通常の f(x)=x と変わらない関数であり、積分時の分割図形と共に表示すると、以下の図のようになる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/47013849-7f368300-d183-11e8-97b5-4f8a49ee46cb.png)<br>
	上図から分かるように、不連続点が寄与する分割長方形の面積は、リーマン積分時の幅を無限に細く取る操作で、無限に小さく出来るので、無視できる。<br>
	（※このことは、リーマン積分においては、非連続点が測度０で零集合であることを意味している。）<br>
	即ち、この関数の積分は、![image](https://user-images.githubusercontent.com/25688193/47013981-e05e5680-d183-11e8-9d18-0aad35411043.png) となるのであるが、この f(x) の、積分する上では、x と変わらないという事実を、<br>
	「ほとんどいたるところ f(x)=x」或いは「f(x)=x a.e」のように、ほとんどいたるところの概念を用いて表現する。<br>

<br>

> 【Memo】 測度論における、ほとんどいたるところ [almost everywhere]<br>
> 零集合はその定義より、測度０の集合となるが、測度０の集合上での違いは、積分に影響せず無視できるという事実がある。（例えば、リーマン積分では、非連続点は測度０で零集合になり、積分上無視出来る。）<br>
> そこで、「積分に影響しない例外（今の場合、測度０の零集合）に関しては、無視して取り除く」 ということを表す概念を導入することを考える。この概念こそが、ほとんどいたるところの概念になる。<br>
> このほとんどいたるところの概念を用いれば、例えば、リーマン積分を<br>
> 「ほとんどいたるところで連続⇔リーマン積分可能」と表現できる。<br>
> （※この必要十分条件は、リーマン積分では、非連続点は測度０で零集合になり、積分上無視出来るという性質に起因する。）<br>

<br>

- 【参考】<br>
    - [ほとんどいたるところ - すもう](http://end01nojo.hatenablog.com/entry/2014/12/06/174314)<br>


<a id="ID_4-2"></a>

### ◎ 積分の定義のほとんどいたるところを用いた表現
> 記載中

- 【参考】<br>
    - [「リーマン積分＜ルベーグ積分」という感覚を味わう - ペンギンは空を飛ぶ](http://peng225.hatenablog.com/entry/2017/11/03/104617)<br>


<a id="ID_4-3"></a>

### ◎ 各種収束定理のほとんどいたるところを用いた表現
ほとんどいたるところで定義された関数を用いると、全ての点で収束するとは言えないような関数列に対しても、
先の各種収束定理（単調収束定理、ルベーグの収束定理）を適用できるようになる。<br>

![image](https://user-images.githubusercontent.com/25688193/47142691-71593d00-d2fe-11e8-9f23-f6d3f916d00b.png)<br>

- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47136083-8aa5bd80-d2ed-11e8-9f3c-bd1c0ce89fb7.png)<br>

- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47142809-b9785f80-d2fe-11e8-9ecb-ceb0bcb7dc05.png)<br>

- （証明略）<br>


<a id="ID_4-4"></a>

### ◎ Lp 空間の完備性と測度の σ-加法性
![image](https://user-images.githubusercontent.com/25688193/47145929-e714d700-d305-11e8-9de5-13555d9b75b4.png)<br>

<br>

以下の定理で示すように、L1ノルムは、μ-可積分な関数全体の集合に、距離に対する完備性を持つ（＝コーシー列が収束する）距離を導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/47149793-9ace9480-d30f-11e8-8a26-bce5829e7fe6.png)<br>

- （証明）<br>
    > 記載中...

<br>

>【Memo】<br>
> ここで、以下の２つの事実を総括すると、このLp空間の完備性は、測度が σ-加法性をもつことに起因していると言える。<br>
> - 測度空間（今の場合、L1空間）が、完備であることの条件は、「任意の零集合の部分集合が、また零集合である」（※零集合は、測度０の集合）<br>
> - σ-加法族の公理の１つである、零集合自身も σ-加法族に含まれる。<br>

<br>

>【Memo】<br>
> 上記の ”L1ノルムは、μ-可積分な関数全体の集合に、完備性を持つ（＝コーシー列が収束）距離を導入する。これをL1空間の完備化という。”<br>
> の意味での完備の条件は、距離に対する完備の意味である。<br>
> 一方、測度空間が、完備であることの条件は、「任意の零集合の部分集合が、また零集合である」であるが、これは、測度に対する完備の意味となり、両者は同じ完備の名前でも別の意味となる。<br>

<br>

>【Memo】<br>
> - 完備測度空間？<br>


<a id="ID_5"></a>

## ■ ルベーグ積分の具体的な計算（一次元ルベーグ積分）
ルベーグ積分の具体的な計算として、まずは、１次元区間上の積分を見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/47201715-d2901780-d3b5-11e8-9461-e0341f0f1e06.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47201776-f7848a80-d3b5-11e8-8240-8183781a2857.png)<br>

この原始関数は、以下の定理で示すように、１次元ルベーグ積分では、与えられた可積分関数に対して、原始関数が必ず存在し、積分操作は、原始関数を求めることに一致する。<br>
（※リーマン積分のときは、連続関数に対して同様の関係が成り立つ。）<br>

![image](https://user-images.githubusercontent.com/25688193/47203516-92cc2e80-d3bb-11e8-916a-9ace98a92f84.png)<br>

- （証明）<br>
    - (a) の証明<br>
        - 積分区間の変数 x∈R に対して、c≤x<b とすると、<br>
            ルベーグ測度は、![image](https://user-images.githubusercontent.com/25688193/47252071-5232ea80-d479-11e8-82ad-1a9c80980694.png)<br>
        - 積分区間は、細かく分割した積分区間の和の形、即ち、<br>
            積分区間 ![image](https://user-images.githubusercontent.com/25688193/47252082-8dcdb480-d479-11e8-8156-08b8d53c308c.png) に対して、<br>
            の形で表現できるので、積分区間 a<c≤x に対しては、<br>
            ![image](https://user-images.githubusercontent.com/25688193/47252092-bce42600-d479-11e8-9bb0-d19dc940ca7d.png)<br>
            積分に影響しない項 ![image](https://user-images.githubusercontent.com/25688193/47252101-cec5c900-d479-11e8-9ac8-b00ad54539a9.png) を両辺に追加すると、<br>
            ![image](https://user-images.githubusercontent.com/25688193/47252120-3f6ce580-d47a-11e8-81b0-2050efe7adf2.png)<br>
            ![image](https://user-images.githubusercontent.com/25688193/47253724-3b4cc200-d492-11e8-987f-91f4dbbd886e.png)<br>
        - 被積分関数 f は連続関数なので、
            c∈(a,b) に対して、ε-δ 論法で、<br>
            ![image](https://user-images.githubusercontent.com/25688193/47252061-2adc1d80-d479-11e8-8f13-eb2f459c103a.png) が成り立つ。<br>
            従って、先の式は、<br>
            ![image](https://user-images.githubusercontent.com/25688193/47253745-9bdbff00-d492-11e8-8deb-0210ad04d7f4.png) に対して、<br>
            ![image](https://user-images.githubusercontent.com/25688193/47253752-b01ffc00-d492-11e8-8b51-a57edaddf730.png)<br>
            従って、関数 ![image](https://user-images.githubusercontent.com/25688193/47253838-1a856c00-d494-11e8-9f6c-97edcfd09293.png) は、c において微分可能であり、微分係数は f(c) に等しい。<br>
            従って、![image](https://user-images.githubusercontent.com/25688193/47253849-4c96ce00-d494-11e8-884c-10645fdf7cf3.png) の関係（＝原始関数 F の微分が、被積分関数 f）を満たすような原始関数 ![image](https://user-images.githubusercontent.com/25688193/47253838-1a856c00-d494-11e8-9f6c-97edcfd09293.png) が存在する。<br>
        <br>
    - (b) の証明<br>
        積分区間上での原始関数 F は、定数の違いを除いて一意なので、<br>
        ![image](https://user-images.githubusercontent.com/25688193/47254068-6be32a80-d497-11e8-8ef5-ead5f28e1cb3.png)<br>
        の関係が成り立つ。<br>
        ![image](https://user-images.githubusercontent.com/25688193/47254074-7f8e9100-d497-11e8-8e71-a9c507c0ed03.png)<br>

        > 記載中...


この定理の (b) の微積分の基本定理により、一次元ルベーグ積分の具体的な計算が与えられる。<br>
以下、いくつかの例で、一次元ルベーグ積分の具体的な計算を見ていく。<br>

> 記載中...

<!--
<a id="ID_6"></a>

## ■ ルベーグ測度の構成
ここでは、測度の構成をより一般的な枠組みで展開する。<br>
-->

<a id="ID_6"></a>

## ■ 有限加法的測度（ジョルダン測度）とそれが誘導する外測度
先の測度の構成では、σ-加法族をもとに測度、及びルベーグ積分を構成してきたが、ここでは、より一般的な測度の構成を見ていく。（具体的には、σ-加法族ではなく、より制限の弱いより抽象的な半加法族での測度の構成）


<a id="ID_6-1"></a>

### ◎ 面積の過大評価と過小評価（内面積、外面積）
そのためにまず、図形の面積を測るということがどのようなことなのかを再考する。<br>

![image](https://user-images.githubusercontent.com/25688193/47374830-d8755800-d729-11e8-83f7-c16d48c4a50e.png)<br>

今、上図のように、平面上の図形にタイル状の網目をかけて、図形の内部からはみ出さない部分を数えると、図形の面積を過小評価していることになるが、この過小評価の上限を内面積という。<br>
一方、図形に少しでも重なる部分（＝図形を覆う部分）を数えると、図形の面積を過大評価していることになるが、この過大評価の下限を外面積という。<br>

そして、この内面積と外面積が一致するとき、この図形の面積が確定し、その共通の値が面積であると定義出来る。<br>
このことは、言い換えると、測度が、以下で定義するような有限加法性をもつことを意味している。<br>


<a id="ID_6-2"></a>

### ◎ 有限加法的測度（ジョルダン測度）
![image](https://user-images.githubusercontent.com/25688193/47373878-aa8f1400-d727-11e8-8e3f-2b5b9d1970c4.png)<br>

<a id="ID_6-2-1"></a>

#### ☆ 非減少関数が誘導する有限加法的測度
この有限加法的測度の例として、以下のようなものが存在する。<br>

![image](https://user-images.githubusercontent.com/25688193/47263245-83262480-d538-11e8-9746-83764069bcea.png)<br>


<a id="ID_6-3"></a>

### ◎ 集合の分割
次に、図形の面積の分割を考える前段階として、以下のような集合の分割の概念を導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/47359076-ba4a3080-d706-11e8-8740-31d41b843648.png)<br>


<a id="ID_6-4"></a>

### ◎ 半加法族
より抽象的な定義での測度は、以下で定義する半加法族 Θ に対して、先に定義した有限加法的測度 m:Θ→R を構成したもの（＝半加法族上に定義された有限加法的測度）となる。<br>
そして、このような測度を (Θ,m) と表記することにする。<br>

![image](https://user-images.githubusercontent.com/25688193/47362593-b078fb00-d70f-11e8-925d-b7a832abf557.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47363162-0dc17c00-d711-11e8-804b-70a52a7f8718.png)<br>

- （証明略）<br>


<a id="ID_6-5"></a>

### ◎ 有限加法的測度が誘導する外測度
先の外面積の例では、図形を覆うように配置した有限個の長方形で、図形の面積を評価（＝図形の面積の過大評価の下限）したが、これを有限個→可算無限個の長方形で覆うようした上で、面積を評価するように拡張したのが、以下で定義する外測度である。<br>

![image](https://user-images.githubusercontent.com/25688193/47406495-8cf69480-d791-11e8-9617-fd59702eafeb.png)<br>

<a id="ID_6-5-1"></a>

#### ☆ 劣加法性と σ-加法性
![image](https://user-images.githubusercontent.com/25688193/47408856-e4016700-d79b-11e8-9c74-b0a06be76910.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47407163-d4325480-d794-11e8-8162-48170d58c752.png)<br>

<a id="ID_6-5-2"></a>

#### ☆ 有限加法的測度が誘導する外測度の性質
![image](https://user-images.githubusercontent.com/25688193/47406515-abf52680-d791-11e8-9b24-ddfc06bf4e14.png)<br>

- （証明略）<br>

> 記載中...

<a id="ID_6-5-3"></a>

#### ☆ 非減少関数の誘導するルベーグ-スティルチェル外測度、１次元ルベーグ外測度
![image](https://user-images.githubusercontent.com/25688193/47408543-cbdd1800-d79a-11e8-95e6-aa91d73366db.png)<br>


<a id="ID_7"></a>

## ■ カラテオドリ外測度からの測度の構成
先に見たように、σ-加法族を元にした測度の構成を、より一般化、抽象化した測度の構成方法として、半加法族を元にした有限加法的測度（＝ジョルダン測度）から誘導される外測度から再構築してきた。<br>
一方、この構築方法とは別の方法として、カラテオドリの外測度からの測度の構成方法も考えられる。<br>


<a id="ID_7-1"></a>

### ◎ カラテオドリ外測度
カラテオドリ外測度は、先の有限加法的測度から誘導される外測度を、更に抽象化したものになっている。<br>

![image](https://user-images.githubusercontent.com/25688193/47410794-e070de80-d7a1-11e8-9350-52b977409b7e.png)<br>


<a id="ID_7-2"></a>

### ◎ カラテオドリ外測度に関しての可測性（可測集合、可測集合族）
![image](https://user-images.githubusercontent.com/25688193/47429220-a4a13d80-d7d0-11e8-9db0-56e25d35d090.png)<br>

- 【参考】
    - [集合の分割](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E6%B8%AC%E5%BA%A6%E8%AB%96_%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86_Note.md#ID_6-3)

<br>

![image](https://user-images.githubusercontent.com/25688193/47428405-16c45300-d7ce-11e8-8b46-ee70c1831090.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47429299-edf18d00-d7d0-11e8-8fb1-9b16fbe346df.png)<br>

- （証明略）図より自明に成り立つ。<br>


<a id="ID_7-3"></a>

### ◎ カラテオドリ外測度に関しての可測集合族の σ-加法性
![image](https://user-images.githubusercontent.com/25688193/47440405-0e2d4600-d7e9-11e8-9056-6e4f766917d9.png)<br>

- 【参考】<br>
    - [ユークリッド空間上の σ-加法族（完全加法族）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E6%B8%AC%E5%BA%A6%E8%AB%96_%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86_Note.md#-%CF%83-%E5%8A%A0%E6%B3%95%E6%97%8F%E5%AE%8C%E5%85%A8%E5%8A%A0%E6%B3%95%E6%97%8F)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47442182-e5a74b00-d7ec-11e8-9487-1f6ed39c0129.png)<br>

- （証明）<br>
    > 記載中...



---

<a id="参考文献"></a>

## ■ 参考文献

- ルベーグ積分 理論と計算手法<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86-%E7%90%86%E8%AB%96%E3%81%A8%E8%A8%88%E7%AE%97%E6%89%8B%E6%B3%95-%E5%B2%A9%E7%94%B0-%E8%80%95%E4%B8%80%E9%83%8E/dp/4627054319?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627054319)<br>

- 測度・確率・ルベーグ積分 応用への最短コース (KS理工学専門書)<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E6%B8%AC%E5%BA%A6%E3%83%BB%E7%A2%BA%E7%8E%87%E3%83%BB%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86-%E5%BF%9C%E7%94%A8%E3%81%B8%E3%81%AE%E6%9C%80%E7%9F%AD%E3%82%B3%E3%83%BC%E3%82%B9-KS%E7%90%86%E5%B7%A5%E5%AD%A6%E5%B0%82%E9%96%80%E6%9B%B8-%E5%8E%9F-%E5%95%93%E4%BB%8B/dp/4061565710/ref=sr_1_1?ie=UTF8&qid=1540384467&sr=8-1&keywords=%E6%B8%AC%E5%BA%A6+%E7%A2%BA%E7%8E%87+%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86)<br>

- ルベーグ積分超入門―関数解析や数理ファイナンス理解のために<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86%E8%B6%85%E5%85%A5%E9%96%80%E2%80%95%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90%E3%82%84%E6%95%B0%E7%90%86%E3%83%95%E3%82%A1%E3%82%A4%E3%83%8A%E3%83%B3%E3%82%B9%E7%90%86%E8%A7%A3%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AB-%E6%A3%AE-%E7%9C%9F/dp/4320017781?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320017781)<br>


### ◎ 参考サイト

- [理系インデックス / 対談（ルベーグ積分）](http://rikei-index.blue.coocan.jp/taidan/taidanrube.html)<br>
    - リーマン積分とルベーグ積分での重要な定理、性質の対応関係
    - カラテオドリ外測度からの測度の定義
    - 面積の過大評価からの測度（＝半加法族上で定義された有限加法的測度が誘導する外測度のこと）の概要
    - σ-加法族での測度の定義（面積の過大評価からの測度の定義との比較を交えながら）
    - ルベーグ積分の柔軟性とσ-加法族
    - ルベーグの収束定理が示されるまでの流れ（単調収束定理→ファトゥの補題→ルベーグの収束定理）
    などの話が短くまとまっていてわかりやすい。<br>

