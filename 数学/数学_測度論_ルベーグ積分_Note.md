# 測度論 [measure theory] / ルベーグ積分
測度論とルベーグ積分の基本事項を記載したマイノートです。随時追記中。<br>

## 目次 [Contents]

1. [概要](#ID_1)
1. [測度に基づく積分の定義](#ID_2)
    1. [σ-加法族（完全加法族）](#ID_2-1)
    1. [測度](#ID_2-2)
    1. [可測性（可測関数、可測集合）](#ID_2-3)
    1. [単関数](#ID_2-4)
    1. [積分](#ID_2-5)
    1. [単関数の積分](#ID_2-6)
    1. [可測関数の積分](#ID_2-7)
1. [測度に基づく積分の性質](#ID_3)
    1. [σ-加法族の性質と可測性](#ID_3-1)
    1. 単調収束定理
    1. ルベーグの収束定理
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
![image](https://user-images.githubusercontent.com/25688193/46900339-5e4c0480-cedb-11e8-86de-0659a3a0be3f.png)<br>


<a id="ID_2-2"></a>

### ◎ 測度
σ-加法族を定義した上で、この σ-加法族 B（＝図形のリストに対応）を測る操作（＝写像） μ に対しての加法性を導入し、以下のように測度として定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/46900508-38742f00-cede-11e8-92eb-fb785c9f4a86.png)<br>

![image](https://user-images.githubusercontent.com/25688193/46904837-94ae7180-cf25-11e8-9e44-375dcfcf9aa2.png)<br>


<a id="ID_2-3"></a>

### ◎ 可測性（可測関数、可測集合）
先に見た積分対象関数の横方向へのスライスから生じる集合（＝図形の分割）は、以下の定義で定義される可測関数に対して、σ-加法族に属することになる。<br>
逆に言えば、横方向スライスから生じる集合が、σ-加法族に属するように、可測関数、可測集合なるものを定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/46900905-f7334d80-cee4-11e8-8a8e-fc69c4612f0e.png)<br>


<a id="ID_2-4"></a>

### ◎ 単関数
![image](https://user-images.githubusercontent.com/25688193/46903202-c2d38780-cf0c-11e8-8382-8233d6571899.png)<br>


<a id="ID_2-5"></a>

### ◎ 積分
この σ-加法族、測度、及び、可測関数、単関数を元に、（可測関数に対して）積分が定義できる。<br>

![image](https://user-images.githubusercontent.com/25688193/46903213-f0b8cc00-cf0c-11e8-9a28-c44c0c7b535c.png)<br>

次に、このように定義した積分に対しての積分可能性（＝可積分、可積分関数）を議論するのであるが、<br>
更に、可積分関数 f に対しての ![image](https://user-images.githubusercontent.com/25688193/46903224-08905000-cf0d-11e8-8220-83357a6f9cb6.png) 条件を利用することで、この可積分性（＝可積分関数）から積分を再定義することも出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/46903242-2eb5f000-cf0d-11e8-8a81-e6b723b35a8f.png)<br>


<a id="ID_2-6"></a>

### ◎ 単関数の積分
積分に関する一般的な性質（線形性など）を、先の積分の定義から直接導出するのは、困難である。
そこでまずは、単関数の場合に限定し、更に、積分の性質を確かめるための補助的な量を別途定義した上で、先の積分の定義と関連付けて議論することにする。<br>

![image](https://user-images.githubusercontent.com/25688193/46906241-69cf1800-cf3b-11e8-88f7-1cff454bc25c.png)<br>

積分の性質（線形性など）との関連付けて議論するために、このように定義した補助的な量に対して、いくつかの性質を見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/46906264-badf0c00-cf3b-11e8-9130-7448cb61c704.png)<br>

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

![image](https://user-images.githubusercontent.com/25688193/46913017-1226c000-cfc0-11e8-86db-a70781122730.png)<br>

- （証明略）<br>

<br>

この定理から、ここでの主目的であった、<br>
積分の性質を確かめるための補助的な量 ![image](https://user-images.githubusercontent.com/25688193/46913070-17d0d580-cfc1-11e8-90d0-502dde717076.png) に対する、積分演算で一般的に成り立つ性質（線形性など）の導出と、<br>
この補助的な量 ![image](https://user-images.githubusercontent.com/25688193/46913070-17d0d580-cfc1-11e8-90d0-502dde717076.png) が、積分の定義に一致する、即ち、![image](https://user-images.githubusercontent.com/25688193/46913072-2c14d280-cfc1-11e8-8c2d-0cbf93264e4b.png) の関係を示すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/46913146-d3ded000-cfc2-11e8-9b74-72b73a7eefd6.png)<br>

- （証明略）<br>


<a id="ID_3"></a>

## ■ 測度に基づく積分の性質

<a id="ID_3-1"></a>

### ◎ σ-加法族の性質と可測性
ここでは、先に見てきた関数の可測性の観点から、σ-加法族を再度見直してみる。<br>

まずは、σ-加法族の定義を、可測関数の視点で捉え直す。<br>

![image](https://user-images.githubusercontent.com/25688193/46904861-ea831980-cf25-11e8-850e-6108707db2da.png)<br>

- （証明）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/46906249-7f444200-cf3b-11e8-8722-f7342862308b.png)<br>

- （証明）<br>


---

<a id="参考文献"></a>

## ■ 参考文献

- ルベーグ積分超入門―関数解析や数理ファイナンス理解のために<br>
    - [amazon で詳細を見る](https://www.amazon.co.jp/%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86%E8%B6%85%E5%85%A5%E9%96%80%E2%80%95%E9%96%A2%E6%95%B0%E8%A7%A3%E6%9E%90%E3%82%84%E6%95%B0%E7%90%86%E3%83%95%E3%82%A1%E3%82%A4%E3%83%8A%E3%83%B3%E3%82%B9%E7%90%86%E8%A7%A3%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AB-%E6%A3%AE-%E7%9C%9F/dp/4320017781?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp&tag=cloudstudy09-22&amp&linkCode=xm2&amp&camp=2025&amp&creative=165953&amp&creativeASIN=4320017781)
