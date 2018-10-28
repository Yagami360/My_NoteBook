# 測度論 [measure theory] / ルベーグ積分 [Lebesgue integral]
測度論とルベーグ積分の基本事項を記載したマイノートです。随時追記中。<br>

## 目次 [Contents]

1. [概要](#ID_1)
1. [σ-加法族を定義域とする測度](#ID_2)
    1. [σ-加法族（完全加法族）](#ID_2-1)
    1. [測度、測度空間](#ID_2-2)
    1. [可測性（可測関数、可測集合、可測空間）](#ID_2-3)
    1. [単関数](#ID_2-4)
    1. [ルベーグ積分（可測関数の積分）](#ID_2-5)
        1. ディリクレ関数を用いた積分
    1. [可積分、可積分関数](#ID_2-6)
1. [有限加法的測度（ジョルダン測度）とそれが誘導する外測度](#ID_6)
    1. [面積の過大評価と過小評価（内面積、外面積）](#ID_6-1)
    1. [有限加法的測度（ジョルダン測度）](#ID_6-2)
    1. [集合の分割](#ID_6-3)
    1. [半加法族](#ID_6-4)
    1. [有限加法的測度（ジョルダン測度）が誘導する外測度](#ID_6-5)
        1. [劣加法性と σ-加法性](#ID_6-5-1)
        1. [有限加法的測度が誘導する外測度の性質](#ID_6-5-2)
1. [カラテオドリ外測度からの測度の構成](#ID_7)
    1. [カラテオドリ外測度](#ID_7-1)
    1. [（カラテオドリ外測度に関しての）可測集合](#ID_7-2)
        1. [（有限加法的測度が誘導する外測度に関しての）可測集合](#ID_7-2-1)
        1. [（カラテオドリ外測度に関しての）可測集合族の σ-加法性](#ID_7-2-2)
    1. [（カラテオドリ外測度に関しての）零集合](#ID_7-4)
        1. [（有限加法的測度が誘導する外測度に関しての）零集合](#ID_7-4-1)
    1. [完備測度、完備測度空間](#ID_7-5)
        1. [（カラテオドリ外測度に関しての）完備測度](#ID_7-5-1)
        1. [（有限加法的測度が誘導する外測度に関しての）完備測度](#ID_7-5-2)
1. [ルベーグ測度の構成](#ID_8)
    1. [非減少関数が誘導する有限加法的測度](#ID_8-1)
    1. [ルベーグ-スティルチェス外測度、１次元ルベーグ外測度](#ID_8-2)
    1. [ルベーグ可測集合（ルベーグ外測度に関しての可測集合）](#ID_8-3)
    1. [ルベーグ-スティルチェス測度、１次元ルベーグ測度](#ID_8-4)
    1. [ルベーグ積分（より一般化した定義）](#ID_8-5)
1. [測度の拡張と一意性](#ID_9)
    1. [集合族から生成される σ-加法族](#ID_9-0)
    1. [測度の拡張とホップ [Hopf] の拡張定理](#ID_9-1)
    1. [拡張の一意性とその応用](#ID_9-2)
    1. [ボレル集合族、ボレル測度](#ID_9-x)
1. [ルベーグ積分の性質](#ID_3)
    1. [σ-加法族の性質と可測性](#ID_3-1)
    1. [単関数の積分とその性質](#ID_3-2)
    1. [ルベーグ積分の性質（可測関数の積分の性質）](#ID_3-3)
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
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## ■ 概要
ここでは、測度論、及び、ルベーグ積分の概要と全体像を、以下のトピックの観点から見ていく。<br>

1. 複雑な関数の積分で生じる問題（リーマン積分の問題点）<br>

2. ルベーグ積分の視点（縦割り分割 → 横割り分割）<br>

3. 測度に基づく積分<br>

    > 【Memo】
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
    即ち、図形のリスト ![image](https://user-images.githubusercontent.com/25688193/47611932-03a5d180-dab3-11e8-8e19-ec65315f2b88.png) に対し、面積を測る操作（一種の写像）を、![image](https://user-images.githubusercontent.com/25688193/47491178-45513500-d885-11e8-8568-cc7716251563.png)（![image](https://user-images.githubusercontent.com/25688193/47491230-5f8b1300-d885-11e8-96ba-3a93bdee2608.png) は非負値の実数集合）で表記することにする。<br>
    （※この図形のリスト ![image](https://user-images.githubusercontent.com/25688193/47611932-03a5d180-dab3-11e8-8e19-ec65315f2b88.png) とは、言い換えれば、ユークリッド空間 ![image](https://user-images.githubusercontent.com/25688193/46858829-298e6d80-ce47-11e8-8994-3d595dd28649.png) の部分集合を要素とする集合族のことである。）<br>
    <br>
    その上で、この操作（写像）μ の加法性を定義するのであるが、この加法性を定めるには、予め図形のリストの形状（大きさ）に関する構造が定まっている必要がある。<br>
    そのためにまずは、以下のように定義される完全加法族なるものを導入する。<br>
    <br>
    ![image](https://user-images.githubusercontent.com/25688193/47491262-7893c400-d885-11e8-9038-3a77fa461408.png)<br>
    <br>
    その上で、この図形のリスト ![image](https://user-images.githubusercontent.com/25688193/47611932-03a5d180-dab3-11e8-8e19-ec65315f2b88.png) を測る操作（＝写像） μ に対しての加法性を導入し、以下のように測度として定義する。<br>
    <br>
    ![image](https://user-images.githubusercontent.com/25688193/47491319-96612900-d885-11e8-963a-0ea879f822de.png)<br>
    <br>
    この測度の中で、特に面積に関する測度が、ルベーグ積分となる。<br>
    即ち、２次元ルベーグ測度は、以下のように定義される。<br>
    ![image](https://user-images.githubusercontent.com/25688193/47491384-b42e8e00-d885-11e8-946e-bd7012ceabbf.png)<br>

<br>

4. ルベーグ積分を導入することでのメリット<br>
    > 記載中...<br>

<br>

- 測度の構成方法<br>

    > 【Memo】 測度の構成<br>
    > 測度論で扱われる測度の構成には、以下のような方法がある。<br>
	> ① σ-加法族を定義域とする測度の構成<br>
	> ② 有限加法的測度が誘導する外測度からの測度の構成<br>
	> ③ カラテオドリ外測度からの測度の構成<br>
	> より抽象的、一般的な測度の構成から並び替えると、③→②→①の順。<br>
        
    > ① σ-加法族を定義域とする測度の構成<br>
    > - σ加法族を定義域とする測度は、面積の分割に関しての、σ加法性を持つ。<br>
    > - この σ加法性は、図形（＝集合）の面積の分割前と分割後の面積が一致することを意味しており、これは図形の面積が測れる要件になっている。<br>
    > ※ 逆に言えば、図形の面積を測れるためには（＝測度であるためには）、集合の面積の分割前と分割後の面積が一致しなくてはならない。<br>
    > ※ 式で書くと、集合 A,B 測度 μ に対して、μ(B)=μ(A∩B)+μ(A\B)<br>
    > - 従って、σ加法族を定義域とする測度は、面積を測れるという意味で、測度になりえる。<br>
     
    > ② 有限加法的測度が誘導する外測度からの測度の構成<br>
    > - 外測度は、図形をタイル状に均等に分割した際に、それらで被覆する外面積の極限として定義される。<br>
    > → ここでいう外測度とは、カラテオドリ外測度のこと？或いは、有限加法的測度が誘導する外測度のこと？<br>
    > - 有限加法的測度は、有限加法性を持つ。<br>
    > → このことが、測度の構成とどうつながる？
    > - 半加法族を定義域とする有限加法的測度は、劣加法性と、σ-加法性をもつ？<br>
    > → このことが、測度の構成とどうつながる？
    > - 半加法族を定義域とする有限加法的測度が誘導する外測度は、劣加法性を持つが、σ-加法性をもたない。<br>
    > ※ 式で書くと、集合 A,B 有限加法的測度 m、m が誘導する外測度 γ(m;・) に対して、<br>
    > γ(m;B)≦γ(m;A∩B)+γ(m;A\B)<br>
    > - 従って、図形（＝集合）の面積の分割前と分割後の面積が一致しないので、そのままでは、測度になりえない。<br>
    > ※ σ加法性を持たないが、劣加法性をもつような、測度より弱い概念になっている。
    > - 従って、半加法族を定義域とする有限加法的測度が誘導する外測度は、カラテオドリ外測度でもある。<br>
    > - 従って、カラテオドリ外測度と同様にして、有限加法的測度が誘導する外測度の定義域を半加法族から、（有限加法的測度が誘導する外測度に関しての）可測集合族に制限した関数は、完備測度になる。<br>
    > - 完備測度になれば、測度になる？（＝σ加法性を持つ？）<br>
    
    > ③ カラテオドリ外測度からの測度の構成<br>
    > - カラテオドリ外測度は、有限加法的測度が誘導する外測度を、より抽象化した概念になっている。<br>
    > - カラテオドリ外測度は、劣加法性をもつが、σ加法性を持たない。<br>
    > ※ 式で書くと、集合 A,B 外測度 γ に対して、γ(B)≦γ(A∩B)+γ(A\B)<br>
    > - 従って、図形（＝集合）の面積の分割前と分割後の面積が一致しないので、そのままでは、測度になりえない。<br>
    > ※ σ加法性を持たないが、劣加法性をもつような、測度より弱い概念になっている。<br>
    > - カラテオドリ外測度の定義域は、抽象集合のべき集合（＝最も要素数の多いσ加法族）で定義されているが、定義域を（カラテオドリ外測度に関しての）可測集合族に制限した関数は、完備測度になる。<br>
    > - 完備測度になれば、測度になる？（＝σ加法性を持つ？）


- 一次元ルベーグ積分の構成

    > 【Memo】 一次元ルベーグ積分の構成<br>
    > １次元ルベーグ測度は、以下のような手順で構成出来る。<br>
    > ① 非減少関数が誘導する有限加法性測度<br>
    > ② ルベーグ-スティルチェス外測度<br>
    > ③ １次元ルベーグ外測度<br>
    > ④ ルベーグ-スティルチェス外測度に関しての可測集合、ルベーグ可測集合<br>
    > ⑤ ルベーグ-スティルチェス測度<br>
    > ⑥ １次元ルベーグ測度<br>

    > ① 非減少関数が誘導する有限加法性測度<br>
    > R 上で定義された非減少関数 v:R→R+ に対して、<br>
    > 定義域を左半開区間 (a,b] 全体と空集合、値域を２つの点 a,b∈R の区間幅 v(b)-v(a) とした
    > 関数 dv:(a,b]↦{v(b)−v(a)}∈R+ は、有限加法性を持つので、有限加法性測度になる。<br>

    > ② ルベーグ-スティルチェス外測度<br>
    > 開区間 I を定義域とする右連続な非減少関数 v:I→R が誘導する有限加法性測度 dv:L(I)→R+ に対して、<br>
    > 集合 X のべき集合 2^X を定義域とする関数 γ(dv;∙) を<br>
    > 非減少関数 v が誘導するルベーグ-スティルチェル外測度という。<br>
    > - この非減少関数が誘導する有限加法的測度から構成した、ルベーグ-スティルチェス外測度は、劣加法性を持つが、σ-加法性をもたない。<br>
    > - 従って、集合の面積の分割前と分割後の面積が一致しないので、そのままでは、測度になりえない。<br>

    > ③ １次元ルベーグ外測度<br>
    > ルベーグ-スティルチェス外測度において、<br>
    > 特に、非減少関数 v ではなく恒等写像 I が誘導するルベーグ-スティルチェル外測度を、１次元ルベーグ外測度 γ(λ,∙) という。<br>
    > - この非減少関数が誘導する有限加法的測度から構成した、ルベーグ外測度は、劣加法性を持つが、σ-加法性をもたない。<br>
    > - 従って、集合の面積の分割前と分割後の面積が一致しないので、そのままでは、測度になりえない。<br>

    > ④ ルベーグ-スティルチェス外測度に関しての可測集合、ルベーグ可測集合<br>
    > ルベーグ-スティルチェス外測度 γ(dv;∙) に対して、σ-加法性の条件<br>
    > γ(dv;B)=γ(dv;A∩B)+γ(dv;A−B)<br>
    > の関係が成り立つとき、ルベーグ-スティルチェス外測度に関しての可測集合という。<br>
    > 同様にして、一次元ルベーグ外測度に対して、σ-加法性の条件<br>
    > γ(λ;B)=γ(λ;A∩B)+γ(λ;A−B)<br>
    > の関係が成り立つとき、ルベーグ可測集合という。<br>
    > - このσ-加法性の条件は、集合の面積の分割前と分割後の面積が一致することを意味しており、測度の要件になっている。<br>

    > ⑤ ルベーグ-スティルチェス測度<br>
    > ルベーグ-スティルチェス外測度 γ(dv;∙) は、べき集合を定義域としているが、<br>
    > ルベーグ-スティルチェス可測集合族 M(dv) を定義域として制限した測度 dv:M(dv)→R+ は、完備測度となる。<br>
    > そして、この完備測度 (M(dv),dv) を、右連続な非減少関数 v:I→R が誘導するルベーグ-スティルチェス測度という。<br>
    > - このルベーグ-スティルチェス測度に対しては、σ-加法性の条件が成り立ち、集合の面積の分割前と分割後の面積が一致するので、測度になりえる。<br>

    > ⑥ １次元ルベーグ測度<br>
    > ルベーグ-スティルチェス測度において、<br>
    > 特に、非減少関数 v ではなく恒等写像 I が誘導するルベーグ-スティルチェル外測度を、１次元ルベーグ測度 λ という。<br>
    > - このルベーグ測度に対しては、σ-加法性の条件が成り立ち、集合の面積の分割前と分割後の面積が一致するので、測度になりえる。<br>



<a id="ID_2"></a>

## ■ σ-加法族を定義域とする測度
ここでは、先の概要で述べたことを、改めて、より一般的な形式で厳密に定義する。<br>

尚、以下の議論では、σ加法族 ![image](https://user-images.githubusercontent.com/25688193/47611932-03a5d180-dab3-11e8-8e19-ec65315f2b88.png) の対象空間として、d 次元ユークリッド空間 ![image](https://user-images.githubusercontent.com/25688193/47611941-21733680-dab3-11e8-9731-dc66ce51d79c.png) ではなく、より抽象的・一般的な抽象集合 X で定義する。<br>
こうすることで、ルベーグ積分をより、一般的で広範囲た対象のものとして扱える。<br>
そして、この抽象集合 X の最も典型的なものが、ユークリッド空間 ![image](https://user-images.githubusercontent.com/25688193/47611941-21733680-dab3-11e8-9731-dc66ce51d79c.png) であるという位置づけになる。<br>

<a id="ID_2-1"></a>

### ◎ σ-加法族（完全加法族）
![image](https://user-images.githubusercontent.com/25688193/47612010-baef1800-dab4-11e8-9b13-4ca3a6e3257f.png)<br>


<a id="ID_2-2"></a>

### ◎ 測度、測度空間
σ-加法族を定義した上で、この σ-加法族 ![image](https://user-images.githubusercontent.com/25688193/47611932-03a5d180-dab3-11e8-8e19-ec65315f2b88.png)（＝図形のリストに対応）を測る操作（＝写像） μ に対しての加法性を導入し、以下のように測度として定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/47612223-921d5180-dab9-11e8-8f73-dddc562d7a21.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47612027-276a1700-dab5-11e8-975c-e7059174cfb4.png)<br>

以下、<br>
![image](https://user-images.githubusercontent.com/25688193/47612031-4072c800-dab5-11e8-8748-0054d257b0de.png)<br>
という文言を、この測度空間の言葉を用いて<br>
![image](https://user-images.githubusercontent.com/25688193/47491814-96155d80-d886-11e8-8617-ccff76fb3993.png)<br>
と記述する。<br>


<a id="ID_2-3"></a>

### ◎ 可測性（可測関数、可測集合、可測空間）
先に見た積分対象関数の横方向へのスライスから生じる集合（＝図形の分割）は、以下の定義で定義される可測関数に対して、σ-加法族に属することになる。<br>
逆に言えば、横方向スライスから生じる集合が、σ-加法族に属するように、可測関数、可測集合なるものを定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/47612192-e83dc500-dab8-11e8-9faf-7965fdc3ac3a.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47612161-f50de900-dab7-11e8-9279-c6b2af4ed004.png)<br>


<a id="ID_2-4"></a>

### ◎ 単関数
![image](https://user-images.githubusercontent.com/25688193/47491965-eb516f00-d886-11e8-8950-654002feea1b.png)<br>


<a id="ID_2-5"></a>

### ◎ ルベーグ積分（可測関数の積分）
この σ-加法族、測度、及び、可測関数、単関数を元に、可測関数に対しての積分、即ち、ルベーグ積分が定義できる。<br>

![image](https://user-images.githubusercontent.com/25688193/47612239-c729a400-dab9-11e8-94a8-0d8de16b1464.png)<br>

> 【Memo】ルベーグ積分の柔軟性と σ-加法族<br>
> リーマン積分では、最初から定義域を画一的に分割しているが、その故に、あまり融通が利かなかった。<br>
> 一方、ルベーグ積分では、値域の分割の逆像を考えるので、定義域の分割は区間とは限らず、もっと広く、σ-加法族に属していればよい。<br>
> そのため、定義域を柔軟に分割することが出来る。<br>
> それ故に、ルベーグ積分では、リーマン積分より広い関数を扱うことが出来るのである。<br>


<a id="ID_2-6"></a>

### ◎ 可積分、可積分関数
次に、このように定義したルベーグ積分に対しての積分可能性（＝可積分、可積分関数）を議論するのであるが、<br>
更に、可積分関数 f に対しての ![image](https://user-images.githubusercontent.com/25688193/46903224-08905000-cf0d-11e8-8220-83357a6f9cb6.png) 条件を利用することで、この可積分性（＝可積分関数）から積分を再定義することも出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/47612257-72d2f400-daba-11e8-95eb-103c6f7b9115.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47612260-8716f100-daba-11e8-9fd7-6d471f10bbe2.png)<br>


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
![image](https://user-images.githubusercontent.com/25688193/47494439-957fc580-d88c-11e8-8d5b-68a8bfa06476.png)<br>


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

![image](https://user-images.githubusercontent.com/25688193/47503695-b274c280-d8a5-11e8-9218-990f0262890f.png)<br>

> 【Memo】<br>
> カラテオドリ外測度や有限加法的測度が誘導する外測度の定義域が、べき集合なのはなんでや？と思ったけど、べき集合が最も要素数の多い σ-加法族であることと、測度が σ加法族を定義域とすることが理由<br>


<a id="ID_6-5-1"></a>

#### ☆ 劣加法性と σ-加法性
![image](https://user-images.githubusercontent.com/25688193/47495359-e42e5f00-d88e-11e8-810a-a3d44f89a4f6.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47495384-f90af280-d88e-11e8-8d27-054ad0f582ec.png)<br>

<a id="ID_6-5-2"></a>

#### ☆ 有限加法的測度が誘導する外測度の性質
![image](https://user-images.githubusercontent.com/25688193/47495415-10e27680-d88f-11e8-9bef-36c78e0b0495.png)<br>

- （証明略）<br>

> 記載中...


<a id="ID_7"></a>

## ■ カラテオドリ外測度からの測度の構成
先に見たように、σ-加法族を元にした測度の構成を、より一般化、抽象化した測度の構成方法として、半加法族を元にした有限加法的測度（＝ジョルダン測度）から誘導される外測度から再構築してきた。<br>
一方、この構築方法とは別の方法として、カラテオドリの外測度からの測度の構成方法も考えられる。<br>


<a id="ID_7-1"></a>

### ◎ カラテオドリ外測度
カラテオドリ外測度は、先の有限加法的測度から誘導される外測度を、更に抽象化したものになっている。<br>

![image](https://user-images.githubusercontent.com/25688193/47503822-f7005e00-d8a5-11e8-9a12-da18c0807f31.png)<br>


<a id="ID_7-2"></a>

### ◎ （カラテオドリ外測度に関しての）可測集合
![image](https://user-images.githubusercontent.com/25688193/47545926-c5c97180-d929-11e8-8727-aacb7001c3a9.png)<br>

- 【参考】
    - [集合の分割](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E6%B8%AC%E5%BA%A6%E8%AB%96_%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86_Note.md#ID_6-3)

<br>

![image](https://user-images.githubusercontent.com/25688193/47545952-e98cb780-d929-11e8-9f66-939bee08ec02.png)<br>

- （証明略）図より自明に成り立つ。<br>


<a id="ID_7-2-1"></a>

#### ☆ （有限加法的測度が誘導する外測度に関しての）可測集合
半加法族 Θ を定義域とする有限加法的測度 ![image](https://user-images.githubusercontent.com/25688193/47495628-8fd7af00-d88f-11e8-8a35-db5f3bdec584.png) が誘導する外測度 ![image](https://user-images.githubusercontent.com/25688193/47495705-c281a780-d88f-11e8-87ea-d0119195e496.png) は、先に見たように、カラテオドリの外測度でもあるので、カラテオドリの外測度のときと同様にして、可測集合なるものが導入できる。<br>

![image](https://user-images.githubusercontent.com/25688193/47546041-4daf7b80-d92a-11e8-9f1a-41cc3d3aebe7.png)<br>


<a id="ID_7-2-2"></a>

#### ☆ （カラテオドリ外測度に関しての）可測集合族の σ-加法性
![image](https://user-images.githubusercontent.com/25688193/47546164-ec3bdc80-d92a-11e8-8a4c-291de39925e4.png)<br>

- 【参考】<br>
    - [ユークリッド空間上の σ-加法族（完全加法族）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E6%B8%AC%E5%BA%A6%E8%AB%96_%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86_Note.md#-%CF%83-%E5%8A%A0%E6%B3%95%E6%97%8F%E5%AE%8C%E5%85%A8%E5%8A%A0%E6%B3%95%E6%97%8F)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47546181-feb61600-d92a-11e8-9a38-cb8b6467e516.png)<br>

- （証明）<br>
    > 記載中...


<a id="ID_7-4"></a>

### ◎ （カラテオドリ外測度に関しての）零集合
![image](https://user-images.githubusercontent.com/25688193/47546203-1d1c1180-d92b-11e8-80ba-eb663c02c68d.png)<br>

<a id="ID_7-4-1"></a>

#### ☆ （有限加法的測度が誘導する外測度に関しての）零集合
半加法族 Θ を定義域とする有限加法的測度 ![image](https://user-images.githubusercontent.com/25688193/47495628-8fd7af00-d88f-11e8-8a35-db5f3bdec584.png) が誘導する外測度 ![image](https://user-images.githubusercontent.com/25688193/47495705-c281a780-d88f-11e8-87ea-d0119195e496.png) は、先に見たように、カラテオドリの外測度でもあるので、カラテオドリの外測度のときと同様にして、零集合なるものが導入できる。<br>

![image](https://user-images.githubusercontent.com/25688193/47546220-32913b80-d92b-11e8-9685-d913ca4d55db.png)<br>


<a id="ID_7-5"></a>

### ◎ 完備測度、完備測度空間
![image](https://user-images.githubusercontent.com/25688193/47543720-995c2800-d91e-11e8-81ce-856e7f7d0379.png)<br>


<a id="ID_7-5-1"></a>

### ◎ （カラテオドリ外測度に関しての）完備測度、完備測度空間
![image](https://user-images.githubusercontent.com/25688193/47565076-31c7cc00-d962-11e8-8c62-5155348a69de.png)<br>

- （証明）
    > 記載中...


<a id="ID_7-5-2"></a>

#### ☆ （有限加法的測度が誘導する外測度に関しての）完備測度
半加法族 Θ を定義域とする有限加法的測度 ![image](https://user-images.githubusercontent.com/25688193/47495628-8fd7af00-d88f-11e8-8a35-db5f3bdec584.png) が誘導する外測度 ![image](https://user-images.githubusercontent.com/25688193/47495705-c281a780-d88f-11e8-87ea-d0119195e496.png) は、先に見たように、カラテオドリの外測度でもあるので、カラテオドリの外測度のときと同様にして、完備測度なるものが導入できる。<br>

![image](https://user-images.githubusercontent.com/25688193/47565200-ac90e700-d962-11e8-8d5b-db4276b9ed8d.png)<br>

- （証明）
    有限加法的測度が誘導する外測度は、カラテオドリ外測度でもあるので、<br>
    定理（カラテオドリ外測度の可測集合族への制限と完備測度）より成り立つ。<br>


<a id="ID_8"></a>

## ■ ルベーグ測度の構成
ここでは、先のカラテオドリ外測度、有限加法的測度が誘導する外測度での議論を、ルベーグ外測度に適用して、ルベーグ測度の存在を示すことを考える。<br>

<a id="ID_8-1"></a>

#### ◎ 非減少関数が誘導する有限加法的測度
先に見たの有限加法的測度の例として、以下のようなものが存在する。<br>

![image](https://user-images.githubusercontent.com/25688193/47545665-64ed6980-d928-11e8-8c28-9cb2f3d91c2b.png)<br>


<a id="ID_8-2"></a>

### ◎ ルベーグ-スティルチェス外測度、１次元ルベーグ外測度
非減少関数が誘導する有限加法的測度に対して、１次元ルベーグ外測度なるものが構築できる。<br>

![image](https://user-images.githubusercontent.com/25688193/47546559-ca435980-d92c-11e8-930f-88515dd74840.png)<br>


<a id="ID_8-3"></a>

### ◎ ルベーグ可測集合（ルベーグ外測度に関しての可測集合）
ルベーグ-スティルチェル外測度、即ち、非減少関数 v が誘導する有限加法的測度 ![image](https://user-images.githubusercontent.com/25688193/47547060-e1834680-d92e-11e8-96cf-616c6a9c29e9.png) に対する外測度 ![image](https://user-images.githubusercontent.com/25688193/47547073-f364e980-d92e-11e8-9d13-3c268364f786.png) は、カラテオドリの外測度でもあるので、カラテオドリの外測度のときと同様にして、可測集合なるものが導入できる。<br>

![image](https://user-images.githubusercontent.com/25688193/47603708-e88f7f00-da2a-11e8-9daa-8cacc84753f4.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47547122-2909d280-d92f-11e8-975e-e1ee2702d686.png)<br>


<a id="ID_8-4"></a>

### ◎ ルベーグ-スティルチェス測度、１次元ルベーグ測度
![image](https://user-images.githubusercontent.com/25688193/47560987-f1158600-d954-11e8-8b88-678b87e3b88f.png)<br>


<a id="ID_8-5"></a>

### ◎ ルベーグ積分（より一般化した定義）
このルベーグ可測集合の考えを用いれば、先の σ-加法族に基づくルベーグ積分の定義を、より一般化したルベーグ積分の定義として構築できる。<br>

![image](https://user-images.githubusercontent.com/25688193/47561034-199d8000-d955-11e8-93b7-12efc2f945ac.png)<br>
![image](https://user-images.githubusercontent.com/25688193/47561329-f9ba8c00-d955-11e8-901f-f63055c831c1.png)<br>


- 【参考】<br>
    - [σ-加法族に基づくルベーグ積分](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%95%B0%E5%AD%A6/%E6%95%B0%E5%AD%A6_%E6%B8%AC%E5%BA%A6%E8%AB%96_%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86_Note.md#-%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B0%E7%A9%8D%E5%88%86)<br>


<a id="ID_9"></a>

## ■ 測度の拡張と一意性
> 記載中...

<a id="ID_9-0"></a>

### ◎ 集合族から生成される σ-加法族
![image](https://user-images.githubusercontent.com/25688193/47604649-6c4f6880-da37-11e8-8d4a-0320f65d4323.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47604866-00baca80-da3a-11e8-88aa-bc79451212a5.png)<br>

- （証明）<br>
    m-可測集合族 ![image](https://user-images.githubusercontent.com/25688193/47604808-796d5700-da39-11e8-8142-75ebb1ee4702.png) は、その定義（＝σ-加法性）より、σ-加法族である。<br>
    従って、一方、半加法族 Θ は、σ-加法族より弱い条件になっているので、![image](https://user-images.githubusercontent.com/25688193/47604811-8b4efa00-da39-11e8-8e8f-17e11d6fa463.png) の関係が成り立つ。<br>
    又、半加法族 Θ から生成される σ-加法族 ![image](https://user-images.githubusercontent.com/25688193/47604843-d6690d00-da39-11e8-90fb-ed399bf112d8.png) は、半加法族 Θ を含む ”最小の” σ-加法族なので、<br>
    ![image](https://user-images.githubusercontent.com/25688193/47604811-8b4efa00-da39-11e8-8e8f-17e11d6fa463.png) の関係より、![image](https://user-images.githubusercontent.com/25688193/47604836-bb969880-da39-11e8-8c09-5e005d435eb9.png) の関係が成り立つ。<br>


<a id="ID_9-1"></a>

### ◎ 測度の拡張とホップの拡張定理
![image](https://user-images.githubusercontent.com/25688193/47566075-80c33080-d965-11e8-86c3-9ad717c4d746.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47510918-156d5600-d8b4-11e8-90e8-809e5bfe174e.png)<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47566385-8b31fa00-d966-11e8-8616-a41cff780a9a.png)<br>


<a id="ID_9-2"></a>

### ◎ 拡張の一意性とその応用
抽象集合 X 上の σ-加法族 ![image](https://user-images.githubusercontent.com/25688193/47611932-03a5d180-dab3-11e8-8e19-ec65315f2b88.png) が、![image](https://user-images.githubusercontent.com/25688193/47566796-c123ae00-d967-11e8-8aa0-82d38a9df4c1.png) の関係を満たし、<br>
σ-加法族 ![image](https://user-images.githubusercontent.com/25688193/47566753-99344a80-d967-11e8-9b90-e44183bc300e.png) を定義域とする抽象集合 X 上の２つの測度 ![image](https://user-images.githubusercontent.com/25688193/47566831-d6004180-d967-11e8-84ae-b1ab000df360.png) が、
半加法族 Θ を定義域とする抽象集合 X 上の有限加法的測度 ![image](https://user-images.githubusercontent.com/25688193/47566876-eca69880-d967-11e8-87e0-33b9ede1cb80.png) を拡張する場合において、<br>
どのような場合に μ_1=μ_2  の関係、即ち、測度の一意性が成り立つであろうか？ということを考える。<br>

この一意性の条件は、以下で見るように、有限加法的測度 ![image](https://user-images.githubusercontent.com/25688193/47566876-eca69880-d967-11e8-87e0-33b9ede1cb80.png) とσ-加法族 ![image](https://user-images.githubusercontent.com/25688193/47611932-03a5d180-dab3-11e8-8e19-ec65315f2b88.png) の両方が関わってくる。<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47567552-d4d01400-d969-11e8-9e95-e6ecaab79d16.png)<br>

![image](https://user-images.githubusercontent.com/25688193/47567579-e4e7f380-d969-11e8-8596-f8bcc0ab509f.png)<br>

- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47603724-1eccfe80-da2b-11e8-9d23-af628d324fe6.png)<br>

- （証明略）<br>

<br>

> 記載中...


<a id="ID_9-x"></a>

### ◎ ボレル集合族、ボレル測度
![image](https://user-images.githubusercontent.com/25688193/47543271-50a36f80-d91c-11e8-80dd-46c09d4bff8a.png)<br>

このボレル集合族を定義域とする測度は、ボレル測度と呼ばれ、一意に定まる測度となる。<br>

![image](https://user-images.githubusercontent.com/25688193/47543411-14244380-d91d-11e8-9cc5-e9940bc91008.png)<br>


> 記載中...

---

<a id="ID_3"></a>

## ■ ルベーグ積分の性質

> 【Memo】 リーマン積分 ↔ ルベーグ積分の定理の対応関係<br>
> ![image](https://user-images.githubusercontent.com/25688193/47612480-8b450d80-dabe-11e8-9381-1f9d0561bbb5.png)<br>

<br>

- 【参考】<br>
    - [ときわ台学/ルベーグ積分/収束定理](http://www.f-denshi.com/000TokiwaJPN/16lebeg/100lbg.html)<br>


<a id="ID_3-1"></a>

### ◎ σ-加法族の性質と可測性
ここでは、先に見てきた関数の可測性の観点から、σ-加法族を再度見直してみる。<br>

まずは、σ-加法族の定義を、可測関数の視点で捉え直す。<br>

![image](https://user-images.githubusercontent.com/25688193/47612327-c85bd080-dabb-11e8-8a39-ee9cfa2ba306.png)<br>

- （証明）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47612403-11605480-dabd-11e8-8d72-880d84b451ab.png)<br>

- （証明）<br>


<a id="ID_3-2"></a>

### ◎ 単関数の積分とその性質
積分に関する一般的な性質（線形性など）を、先の積分の定義から直接導出するのは、困難である。
そこでまずは、単関数の場合に限定し、更に、積分の性質を確かめるための補助的な量を別途定義した上で、先の積分の定義と関連付けて議論することにする。<br>

![image](https://user-images.githubusercontent.com/25688193/47612428-99def500-dabd-11e8-99ed-eaea5df0d195.png)<br>

積分の性質（線形性など）との関連付けて議論するために、このように定義した補助的な量に対して、いくつかの性質を見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/47492963-248ade80-d889-11e8-8358-96dc965b1fa2.png)<br>

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
	上式の右辺（＝上図に示した分割領域の和集合）が、有限集合であり、σ-加法族 ![image](https://user-images.githubusercontent.com/25688193/47611932-03a5d180-dab3-11e8-8e19-ec65315f2b88.png) に属することは、
	合成関数 h が、B-可測関数であることを意味している。<br>
	従って、合成関数 h は、単関数である。<br>

<br>

この単関数の合成関数の性質を、<br>
先に定義した積分の性質を確かめるための補助的な量<br>
![image](https://user-images.githubusercontent.com/25688193/46913036-69c52b80-cfc0-11e8-8065-40b027c2a7b2.png)<br>
に適用すると、以下のような定理が導かれる。<br>

![image](https://user-images.githubusercontent.com/25688193/47493081-6c116a80-d889-11e8-9953-899041fc4b03.png)<br>

- （証明略）<br>

<br>

この定理から、ここでの主目的であった、<br>
積分の性質を確かめるための補助的な量 ![image](https://user-images.githubusercontent.com/25688193/46913070-17d0d580-cfc1-11e8-90d0-502dde717076.png) に対する、積分演算で一般的に成り立つ性質（線形性など）の導出と、<br>
この補助的な量 ![image](https://user-images.githubusercontent.com/25688193/46913070-17d0d580-cfc1-11e8-90d0-502dde717076.png) が、積分の定義に一致する、即ち、![image](https://user-images.githubusercontent.com/25688193/46913072-2c14d280-cfc1-11e8-8c2d-0cbf93264e4b.png) の関係を示すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/47493208-b09d0600-d889-11e8-98fa-e461efeff5d4.png)<br>

- （証明略）<br>


<a id="ID_3-3"></a>

### ◎ ルベーグ積分の性質
以下、可測関数の積分に関しての、基本的な性質を見ていく。<br>
まずは、測度 μ の有限加法性に起因する性質を見ていく。<br>

![image](https://user-images.githubusercontent.com/25688193/47612434-bc710e00-dabd-11e8-80ae-6e44e2d820ae.png)<br>

- （証明略）

<br>

次に、σ-加法性に起因する性質を見ていく。<br>

> 記載中...


<a id="ID_3-4"></a>

### ◎ エゴロフの定理
<!--
ルベーグ積分は、単関数の点列で可測関数を近似した上で定義する方法と、単関数の積分の上限で定義する方法の２通り考えられるが、<br>
以下に示すエゴロフの定理を用いれば、これらの２つの値が一致することを示すことが出来る。<br>
-->

![image](https://user-images.githubusercontent.com/25688193/47612451-0a861180-dabe-11e8-9883-6b11c8c9297b.png)<br>

- （証明略）図より自明<br>

<br>

このエゴロフの定理を用いれば、<br>
積分の基本性質である、「（単関数における）極限と積分の順序の交換可能性」を示すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/47493479-53ee1b00-d88a-11e8-9f35-f68851995e69.png)<br>

- （証明）<br>
    > 記載中...


<a id="ID_3-5"></a>

### ◎ ファトゥの補題
単調収束定理やルベーグ収束定理を示すための前段階として、以下のファトゥの補題を示す。<br>
このファトゥの補題は、先の単関数に対する極限と積分の交換可能性の性質を、可測関数、即ちルベーグ積分に拡張したものになっている。<br>

![image](https://user-images.githubusercontent.com/25688193/47612487-b16aad80-dabe-11e8-9702-56434a64fb35.png)<br>

- （証明略）<br>


<a id="ID_3-6"></a>

### ◎ 単調収束定理
ファトゥの補題を用いれば、以下の単調収束定理を示すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/47612505-158d7180-dabf-11e8-87a4-115f9fad2459.png)<br>

- （証明）<br>
    定理の参考図にも示しているように、<br>
    可測集合 ![image](https://user-images.githubusercontent.com/25688193/47612510-2807ab00-dabf-11e8-8527-a48de0e63b2e.png) 上で、可測関数の単調増加の点列 ![image](https://user-images.githubusercontent.com/25688193/46940732-64d9a800-d0a4-11e8-93cc-a42a39f3f0c0.png) に対しては、<br>
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

![image](https://user-images.githubusercontent.com/25688193/47612521-64d3a200-dabf-11e8-9e4a-6fe8ced159bd.png)<br>

- （証明略）<br>

---

<a id="ID_4"></a>

## ■ 測度０の集合
> 記載中...

<a id="ID_4-1"></a>

### ◎ ほとんどいたるところ [almost eyerywhere]
![image](https://user-images.githubusercontent.com/25688193/47612556-4fab4300-dac0-11e8-9947-4cd2788788bb.png)<br>

この零集合は、その定義より、測度０の集合となるが、測度０の集合上での違いは、積分に影響せず無視できるという事実がある。（証明略）<br>
そこで、積分に影響しない例外（今の場合、測度０の零集合）に関しては、無視する。<br>
ということを表す概念を導入することを考える。<br>
この概念こそが、以下のほとんどいたるところの概念になる。<br>

![image](https://user-images.githubusercontent.com/25688193/47612559-65b90380-dac0-11e8-86c9-e39b623fe213.png)<br>

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

![image](https://user-images.githubusercontent.com/25688193/47612572-db24d400-dac0-11e8-8219-3807a0e8f827.png)<br>

- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47612588-44a4e280-dac1-11e8-81dd-b61826256c8f.png)<br>

- （証明略）<br>

<br>

![image](https://user-images.githubusercontent.com/25688193/47612611-af561e00-dac1-11e8-8b55-9e3eecbdab2a.png)<br>

- （証明略）<br>


<a id="ID_4-4"></a>

### ◎ Lp 空間の完備性と測度の σ-加法性
![image](https://user-images.githubusercontent.com/25688193/47612632-225f9480-dac2-11e8-837f-7aed0bb8ff52.png)<br>

<br>

以下の定理で示すように、L1ノルムは、μ-可積分な関数全体の集合に、距離に対する完備性を持つ（＝コーシー列が収束する）距離を導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/47494247-2b672080-d88c-11e8-8f0f-1e9fc4e24e7d.png)<br>

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

---

<a id="ID_5"></a>

## ■ ルベーグ積分の具体的な計算（一次元ルベーグ積分）
ルベーグ積分の具体的な計算として、まずは、１次元区間上の積分を見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/47494305-50f42a00-d88c-11e8-84a7-ca7ad0e151d3.png)<br>

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
    以下のトピックなどの話が短くまとまっていてわかりやすい。<br>
    - リーマン積分とルベーグ積分での重要な定理、性質の対応関係
    - カラテオドリ外測度からの測度の定義
    - 面積の過大評価からの測度（＝半加法族上で定義された有限加法的測度が誘導する外測度のこと）の概要
    - σ-加法族での測度の定義（面積の過大評価からの測度の定義との比較を交えながら）
    - ルベーグ積分の柔軟性とσ-加法族
    - ルベーグの収束定理が示されるまでの流れ（単調収束定理→ファトゥの補題→ルベーグの収束定理）

