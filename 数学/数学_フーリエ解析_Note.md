# フーリエ解析

## 目次 [Contents]

1. [概要](#ID_1)
1. [フーリエ級数展開](#ID_2)
    1. [フーリエ係数の意味](#ID_2-1)
    1. [フーリエ級数の収束性](#ID_2-2)
1. [複素フーリエ級数](#ID_3)
1. [直交級数としてのフーリエ級数（関数解析視点でのフーリエ級数）](#ID_4)
    1. [関数同士の直交（直交関数系）](#ID_4-1)
    1. [直交級数（一般化フーリエ級数）](#ID_4-2)
    1. [完全な直交関数系](#ID_4-3)
    1. [ルジャンドル多項式](#ID_4-4)
    1. [最適な直交級数の選択](#ID_4-5)
1. [フーリエ変換](#ID_5)
    1. [フーリエ変換は何を表しているか](#ID_5-1)
    1. [フーリエ変換出来る関数と出来ない関数](#ID_5-2)
    1. [フーリエ変換の計算](#ID_5-3)
        1. [微分・積分した関数のフーリエ変換](#ID_5-3-1)
        1. [合成積（畳み込み）、積のフーリエ変換とパーシバルの等式](#ID_5-3-2)
        1. [ガウス関数のフーリエ変換](#ID_5-3-3)
1. [偏微分方程式への応用](#ID_6)
    1. [一定の長さのリング状の棒での熱伝導方程式](#ID_6-1)
    1. [無限に長い棒での熱伝導方程式](#ID_6-2)
    1. [xxx](#ID_6-x)
1. [xxx](#ID_x)

---

<a id="ID_2"></a>

## ■ フーリエ級数展開 [Fourier series]
以下のような、sin,cos の和からなる級数（フーリエ級数）![image](https://user-images.githubusercontent.com/25688193/42722784-4ed96e1a-878d-11e8-889e-2832b4435f68.png) の式<br>
![image](https://user-images.githubusercontent.com/25688193/42722854-72e0913e-878e-11e8-8bec-efc04726ed1d.png)<br>
に対して、各項の係数（フーリエ係数）![image](https://user-images.githubusercontent.com/25688193/42722787-5ff7fe00-878d-11e8-9933-88c9692916a4.png) を求めることを考える。<br>

まず、係数を ![image](https://user-images.githubusercontent.com/25688193/42722790-7a834d2e-878d-11e8-86b6-a78d540a7914.png) 求める。<br>
上式の左から ![image](https://user-images.githubusercontent.com/25688193/42722795-8b87764a-878d-11e8-963e-8ea81df3411c.png) を掛けて ![image](https://user-images.githubusercontent.com/25688193/42722803-9d15bc5a-878d-11e8-8b53-fcbf86fe3c18.png) の範囲で積分すると、<br>
![image](https://user-images.githubusercontent.com/25688193/42722809-b18610fe-878d-11e8-9472-41bed8d26e36.png)<br>

ここで、<br>
![image](https://user-images.githubusercontent.com/25688193/42722823-e976e38a-878d-11e8-871f-9c3e1c4414ce.png)<br>
![image](https://user-images.githubusercontent.com/25688193/42722833-16e8e958-878e-11e8-97c7-72a0d89080bc.png)<br>
の関係より、<br>

![image](https://user-images.githubusercontent.com/25688193/42722845-321c318a-878e-11e8-9ed0-b92472ccd5dd.png)<br>
![image](https://user-images.githubusercontent.com/25688193/42722861-8eed5e2a-878e-11e8-96dd-34edf0aae3b1.png)<br>

次に、係数 ![image](https://user-images.githubusercontent.com/25688193/42722870-bda27976-878e-11e8-8a93-e803b979da44.png) を求める。<br>
フーリエ級数展開の式に、![image](https://user-images.githubusercontent.com/25688193/42722876-ce174d68-878e-11e8-8e7e-4c85059a40b0.png) をかけて ![image](https://user-images.githubusercontent.com/25688193/42722887-e10a519a-878e-11e8-97f0-8270f772ef0c.png) の範囲で積分すると、<br>
![image](https://user-images.githubusercontent.com/25688193/42722895-f372f68e-878e-11e8-95fe-40fbe29be541.png)<br>
ここで、<br>
![image](https://user-images.githubusercontent.com/25688193/42722970-0a15cbcc-8790-11e8-85b2-d99885804a70.png)<br>
![image](https://user-images.githubusercontent.com/25688193/42722978-1ad22bfe-8790-11e8-9e6b-a0fbaece09d6.png)<br>
の関係より、<br>
![image](https://user-images.githubusercontent.com/25688193/42722983-30f98eea-8790-11e8-82c7-48daf5d1185e.png)<br>
![image](https://user-images.githubusercontent.com/25688193/42722991-46d4f736-8790-11e8-8379-af200115d8a8.png)<br>

最後に、係数 ![image](https://user-images.githubusercontent.com/25688193/42722996-6eadad8e-8790-11e8-8328-e4ff4ab9b936.png) を求める。<br>
フーリエ級数展開の式を ![image](https://user-images.githubusercontent.com/25688193/42722887-e10a519a-878e-11e8-97f0-8270f772ef0c.png) の範囲で積分すると、<br>
![image](https://user-images.githubusercontent.com/25688193/42723141-4d52cfb8-8793-11e8-8eba-1e770da10fc4.png)<br>

まとめると、<br>
![image](https://user-images.githubusercontent.com/25688193/42723147-6f8134c6-8793-11e8-9c4c-b71b19884887.png)<br>

<br>

**このフーリエ級数は、周期 2π の周期関数であるが、**<br>
**次に、以下の例で（周期 2π の）周期関数が、フーリエ級数の形で記述できることを示す。**<br>

- （例）周期 2π の周期関数 ![image](https://user-images.githubusercontent.com/25688193/42732080-437672d4-8855-11e8-9d45-722e499e0bcd.png) をフーリエ級数展開の式で表す。<br>

    ![image](https://user-images.githubusercontent.com/25688193/42732085-572a99e0-8855-11e8-82b5-e41bf9c0ca64.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/42732091-84224d94-8855-11e8-9ead-43b4fddf6a3c.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/42732098-a0797a6c-8855-11e8-9373-616b19b61053.png)<br>
    定積分を実行すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42732118-de4983c8-8855-11e8-91a7-377ffede1acf.png)<br>
    
    同様にして、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42732126-fad2ec78-8855-11e8-834d-e4793c8656d1.png)<br>
    定積分を実行すると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42732141-52ccc020-8856-11e8-84c6-acb35df45d4b.png)<br>
    最後に、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42732147-6d95e904-8856-11e8-8ed8-d18a2700c22b.png)<br>
    よって、周期関数 ![image](https://user-images.githubusercontent.com/25688193/42732152-8c29450a-8856-11e8-9d76-d1bf98f73028.png) は、フーリエ級数展開の式、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42732159-b1ce5002-8856-11e8-83ad-5d8009868454.png)<br>
    で記述できる。<br>


この例のように、**周期関数を sin.cos の和の重ね合わせで表すことをフーリエ級数展開とよび、得られた級数をフーリエ級数という。**<br>
**逆に言えば、このフーリエ級数展開は、全ての周期関数はsin.cos の和の重ね合わせで表せることを示している！**<br>

フーリエ級数の一般的な形（周期 2π→T に一般化）は、<br>
![image](https://user-images.githubusercontent.com/25688193/42732560-d83c284c-885e-11e8-91f5-6cf128ac6c3c.png)<br>

フーリエ係数は、<br>
![image](https://user-images.githubusercontent.com/25688193/42732569-f207aa12-885e-11e8-8861-6b19ff5d8d65.png)<br>

※ 係数 ![image](https://user-images.githubusercontent.com/25688193/42732587-2253433e-885f-11e8-8137-36b9cb2c8aee.png) は、![image](https://user-images.githubusercontent.com/25688193/42732593-3f7e0cfa-885f-11e8-9502-518d1debf8e7.png) より、![image](https://user-images.githubusercontent.com/25688193/42732598-55766408-885f-11e8-9b88-25a1e7aa8a77.png)<br>
※ ![image](https://user-images.githubusercontent.com/25688193/42732603-785a383c-885f-11e8-9764-4e49493e1e00.png) の形状は、周期 T の周期関数 ![image](https://user-images.githubusercontent.com/25688193/42732607-89ca5796-885f-11e8-820a-1a6efcba25d0.png) であることによる。<br>


<a id="ID_2-1"></a>

### ◎ フーリエ係数の意味
周期 T のフーリエ級数展開<br>
![image](https://user-images.githubusercontent.com/25688193/42733401-c3073216-886b-11e8-99f2-10edeeb337ec.png)<br>
において、<br>
正の整数 n に対する関数（＝基底ベクトルとなる）![image](https://user-images.githubusercontent.com/25688193/42733414-fb16cb62-886b-11e8-87c1-6fc285a2c56f.png) は、周期 T/n の周期関数である。<br>
従って、これらの関数の係数であるフーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/42733427-243673a8-886c-11e8-9582-7d27e674cb1c.png) は、周期関数 f(t) の中に、周期 T/n で変動する成分がどの程度含まれているのか（＝振幅の大きさ）を示している。<br>

例えば、先の周期関数 ![image](https://user-images.githubusercontent.com/25688193/42733435-498672f2-886c-11e8-91df-f6fe74d3cd9c.png) の例では、<br>
そのフーリエ級数 ![image](https://user-images.githubusercontent.com/25688193/42733447-89a9dea0-886c-11e8-844c-41b7b735677b.png) の各項は以下の図のようになり、元の周期関数はこれらの重ね合わせで表現できるが、各フーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/42733427-243673a8-886c-11e8-9582-7d27e674cb1c.png) は、各項の振幅の大きさに対応していることが分かる。<br>
![image](https://user-images.githubusercontent.com/25688193/42733454-9fd0676c-886c-11e8-8b4d-89cdc9b28cdf.png)<br>

<br>

次に、フーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/42734566-41c85746-8881-11e8-9357-37a1d16e7db5.png) が、偶関数・奇関数の観点から、周期関数 ![image](https://user-images.githubusercontent.com/25688193/42734575-553295f8-8881-11e8-8ec4-84713313acaf.png) のどのような性質を表しているのか見てみる。<br>
そのためにまず、以下の性質が成り立つことを示す。<br>

![image](https://user-images.githubusercontent.com/25688193/42907000-9032b76c-8b17-11e8-9f46-cf933a18537d.png)<br>
- （証明）<br>
    まず、周期関数 ![image](https://user-images.githubusercontent.com/25688193/42734575-553295f8-8881-11e8-8ec4-84713313acaf.png) から、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42734610-e6259772-8881-11e8-8a61-54e6f2911e85.png)<br>
    が成り立つような関数 ![image](https://user-images.githubusercontent.com/25688193/42734612-fca4b9b0-8881-11e8-91d1-92e442b5980b.png) を作ると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42734622-23ac716a-8882-11e8-9a52-0e7bdb6ba12d.png)<br>
    より、![image](https://user-images.githubusercontent.com/25688193/42734599-ab9aff70-8881-11e8-8426-aa2055cd246d.png) の関係は成り立つ。<br>
    <br>
    次に、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42734646-8d4e00ca-8882-11e8-95ee-16203d8d4561.png)<br>
    の関係より、この ![image](https://user-images.githubusercontent.com/25688193/42734587-7d9675d2-8881-11e8-86d9-87607425a184.png) は偶関数であることが分かる。<br>
    <br>
	更に、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42734669-ecfbcd86-8882-11e8-957b-87525ce9941a.png)<br>
    の関係より、この ![image](https://user-images.githubusercontent.com/25688193/42734591-901b46ba-8881-11e8-95db-419d5e078ca8.png) は奇関数であることが分かる。<br>
    <br>
	従って、<br>
	周期関数 ![image](https://user-images.githubusercontent.com/25688193/42734575-553295f8-8881-11e8-8ec4-84713313acaf.png) は、（同じ周期を持つ）偶関数 ![image](https://user-images.githubusercontent.com/25688193/42734587-7d9675d2-8881-11e8-86d9-87607425a184.png) と奇関数 ![image](https://user-images.githubusercontent.com/25688193/42734591-901b46ba-8881-11e8-95db-419d5e078ca8.png) の和で記述できる。<br>

<br>

ここで、周期関数 ![image](https://user-images.githubusercontent.com/25688193/42734575-553295f8-8881-11e8-8ec4-84713313acaf.png) のフーリエ級数展開の式<br>
![image](https://user-images.githubusercontent.com/25688193/42734811-f8e47678-8884-11e8-929c-ffcd841d71f2.png)<br>
と、先の性質<br>
![image](https://user-images.githubusercontent.com/25688193/42734825-3cca3242-8885-11e8-91b2-aeb3977ec266.png)<br>
を見比べると、<br>
偶関数 ![image](https://user-images.githubusercontent.com/25688193/42734587-7d9675d2-8881-11e8-86d9-87607425a184.png) と奇関数 ![image](https://user-images.githubusercontent.com/25688193/42734591-901b46ba-8881-11e8-95db-419d5e078ca8.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/42734846-965c574a-8885-11e8-82f1-565af80cf65a.png)<br>

従って、同じ周期の変動成分（＝振幅の大きさ）に対応しているフーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/42734856-c084ea3c-8885-11e8-9a6c-ec04cdb03099.png) の内、<br>
![image](https://user-images.githubusercontent.com/25688193/42734861-dd64b52e-8885-11e8-848c-e5ae219f72f0.png)
 は偶関数の成分（＝cos 成分）、![image](https://user-images.githubusercontent.com/25688193/42734873-03f0c886-8886-11e8-815e-a013dc60a2e3.png) は奇関数の成分（＝sin 成分）を表している。<br>
言い換えると、<br>
**周期関数は、一般的に偶関数成分と奇関数成分を含んでいるが、**<br>
**これら２つの成分を表現するのに、２つの係数 ![image](https://user-images.githubusercontent.com/25688193/42734856-c084ea3c-8885-11e8-9a6c-ec04cdb03099.png) が必要であることを示している。**

<br>

次にフーリエ級数展開の式において、正の整数 n に対して、フーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/42734856-c084ea3c-8885-11e8-9a6c-ec04cdb03099.png) に関係する部分を取り出してまとめた式に変形すると、<br>
![image](https://user-images.githubusercontent.com/25688193/42749897-480e70a0-8920-11e8-9d01-2eb4b47c0b7c.png)<br>
この式は、cos , sin からなる同じ周期 T/n の２つの変動成分 ![image](https://user-images.githubusercontent.com/25688193/42734856-c084ea3c-8885-11e8-9a6c-ec04cdb03099.png) の和が、
振幅 ![image](https://user-images.githubusercontent.com/25688193/42748767-55aa337e-891c-11e8-9184-4d2a16aa3657.png) をもつ周期 T/n の１つの変動成分の形で表現できることを示している。<br>
従って、この振幅 ![image](https://user-images.githubusercontent.com/25688193/42748767-55aa337e-891c-11e8-9184-4d2a16aa3657.png) は、周期関数 f(t) に含まれる周期 T/n の変動成分の大きさに対応しているといえる。<br>

一般的に、ある周期関数が与えれた時に、そのフーリエ級数展開でのどの周期の変動成分が大きいのかを見分けるのは容易ではない。<br>
このような場合に、与えれた周期関数のフーリエ級数展開を行い、![image](https://user-images.githubusercontent.com/25688193/42748767-55aa337e-891c-11e8-9184-4d2a16aa3657.png) を計算すれば、どの周期成分が大きいのかを即座に知ることが出来る。<br>

- （例）周期関数 ![image](https://user-images.githubusercontent.com/25688193/42749965-853b9232-8920-11e8-9bd3-635414e029a6.png) の ![image](https://user-images.githubusercontent.com/25688193/42748767-55aa337e-891c-11e8-9184-4d2a16aa3657.png) を計算し、どの周期の変動成分が大きのかを判断<br>

    この周期関数のフーリエ係数は<br>
    ![image](https://user-images.githubusercontent.com/25688193/42750002-a3b295f8-8920-11e8-9b5a-220a19e7e715.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/42750043-b7ee2712-8920-11e8-894f-663c52663032.png)<br>
    従って、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42750062-cf794d6c-8920-11e8-9233-1607f49aed63.png) となり、<br>
    ![image](https://user-images.githubusercontent.com/25688193/42750099-e7ea8550-8920-11e8-86d2-18ce88054bef.png) が成り立つので、<br>
    n=1 となる周期 2π(=2π/1)  の変動成分が最も大きく、続いて n=2 となる周期 π(=2π/2)  の変動成分が大きい・・・ということが分かる。<br>

<br>

最後に、フーリエ級数展開における定数 ![image](https://user-images.githubusercontent.com/25688193/42750487-5d2ffc2c-8922-11e8-9d97-fb080133302b.png) は、周期関数 f(t) の t に依存せず変動しない成分を表しているが、**この ![image](https://user-images.githubusercontent.com/25688193/42750487-5d2ffc2c-8922-11e8-9d97-fb080133302b.png) は、周期関数 f(t)  の（１周期 0 ~ T での）平均値となっている。**<br>
![image](https://user-images.githubusercontent.com/25688193/42750533-82d43402-8922-11e8-9799-0976921d5662.png)<br>

<br>

<a id="ID_2-2"></a>

### ◎ フーリエ級数の収束性
周期関数をフーリエ級数の形で表すと、一般的に、無限個の cos,sin の和になるが、このような場合に、この級数和が、ある点や関数に収束するのか否かの収束性に関する議論は重要な問題である。<br>

先に見たように、周期 T の周期関数 f(t) が与えれたときに、そのフーリエ級数展開は、<br>
![image](https://user-images.githubusercontent.com/25688193/42757352-a75f2cc4-893a-11e8-8fef-f34160b6094e.png)<br>
![image](https://user-images.githubusercontent.com/25688193/42757402-e5f19094-893a-11e8-8e0e-d1fe0edc51a7.png)<br>

多くの場合、この展開式は無限個の sin,cos の和になる。<br>
しかしならが実際上では、無限個の和を足し合わせることは無可能であるので、適当な大きな整数 N を決めて、n=N の後まで足し合わせて途中で打ち切ることになる。<br>
この途中で打ち切って作った関数を ![image](https://user-images.githubusercontent.com/25688193/42757423-01b207be-893b-11e8-9f91-55a9d4506bbb.png) と書くことにすると、<br>
![image](https://user-images.githubusercontent.com/25688193/42757439-133ffc02-893b-11e8-8b44-214ff31b7f05.png)<br>
となる。<br>

今、フーリエ級数展開の収束性について考えるために、無限個の級数和である右辺が、元の周期関数 f(t) に等しいといえるための条件を ![image](https://user-images.githubusercontent.com/25688193/42757423-01b207be-893b-11e8-9f91-55a9d4506bbb.png) で表現すること考えると、<br>
これは、「どの t に対しても N を大きくしていったときに、![image](https://user-images.githubusercontent.com/25688193/42757423-01b207be-893b-11e8-9f91-55a9d4506bbb.png) が元の周期関数 f(t) に際限なく近づく」ことを考えていることになる。<br>
これを式で書くと、<br>
![image](https://user-images.githubusercontent.com/25688193/42757522-600844c2-893b-11e8-9344-ec7c007af9a0.png)<br>
と記述できる。<br>

次の課題は、どんな周期関数 f(t) に対して上式の収束性が成り立つのか？ということである。<br>


#### ☆ 滑らかな関数なら収束する
一般的に、滑らかな周期関数のフーリエ級数の収束性に関しては、以下の性質が成り立つ。<br>

![image](https://user-images.githubusercontent.com/25688193/42906355-dfba91c6-8b15-11e8-9a19-906bcb95602a.png)<br>

<br>

次に、必ずしも（任意の点で）滑らかではないが、区分的には連続な関数に関しての収束性を考える。<br>
区分的に連続な関数とは、例えば、以下のような関数である。<br>

![image](https://user-images.githubusercontent.com/25688193/42810121-256f413c-89f2-11e8-9f6d-8a698957f3c0.png) を周期 2π で周期的に拡張した関数（下図）<br>
![image](https://user-images.githubusercontent.com/25688193/42810191-4abee1ae-89f2-11e8-8aaf-2e92d1d571ef.png)<br>

このような区分的に連続な関数であっても、そのフーリエ級数展開は、関数が滑らかな区間ごとに部分積分して、その和をとれば計算できる。<br>
一方で、このフーリエ級数は元の周期関数に収束するのかの問題は自明ではない。<br>

この収束性に関する問題を考える際には、<br>
まず、「sin,cos 関数や定数関数は、いずれも連続関数なので、それらに定数（フーリエ係数）をかけて有限項足し合わせた関数である ![image](https://user-images.githubusercontent.com/25688193/42876125-ac006180-8ac0-11e8-8564-b331b8cf9bca.png) も連続関数になる。」<br>
という性質に注意が必要となる。この性質は、N をいくら大きくしていっても成り立つ。<br>
従って、N を大きくしていったときの連続関数 ![image](https://user-images.githubusercontent.com/25688193/42876125-ac006180-8ac0-11e8-8564-b331b8cf9bca.png) が、元の周期関数 f(t)  の不連続点付近でどのように振る舞うのかが焦点となる。<br>

このような問題を扱うための、具体的として、先の ![image](https://user-images.githubusercontent.com/25688193/42810121-256f413c-89f2-11e8-9f6d-8a698957f3c0.png) を周期 2π で周期的に拡張した関数を、n=N までの有限項で打ち切ったフーリエ級数 ![image](https://user-images.githubusercontent.com/25688193/42876125-ac006180-8ac0-11e8-8564-b331b8cf9bca.png) を考える。<br>

![image](https://user-images.githubusercontent.com/25688193/42883576-e942009c-8ad6-11e8-8005-7a8ad8618434.png)<br>
n≥2 の場合は、部分積分を利用して計算すると、<br>
![image](https://user-images.githubusercontent.com/25688193/42883607-04cb8874-8ad7-11e8-8f9b-c13115453569.png)<br>
![image](https://user-images.githubusercontent.com/25688193/42883626-141328be-8ad7-11e8-9905-87dc1f49f1d6.png)<br>
![image](https://user-images.githubusercontent.com/25688193/42883701-4a41d6b0-8ad7-11e8-81da-4e35f0102c23.png)<br>
従って、フーリエ級数は、<br>
![image](https://user-images.githubusercontent.com/25688193/42883739-6d0c0d50-8ad7-11e8-9876-2b9e20fd6482.png)<br>
n=N までの有限項で打ち切ったフーリエ級数は、<br>
![image](https://user-images.githubusercontent.com/25688193/42883768-86f0fdd4-8ad7-11e8-9079-7607cece8add.png)<br>

ここで、各 N 値 に対する ![image](https://user-images.githubusercontent.com/25688193/42883817-9fae20d6-8ad7-11e8-9be7-b312a273d4b6.png) のグラフは以下の図のようになる。<br>

- 全体図（N=2,5,20）<br>
![image](https://user-images.githubusercontent.com/25688193/42897397-dc418060-8afa-11e8-9830-519bcf5ee6bc.png)<br>

- t=0 付近の拡大図（N=2,5,20,40,70,100）<br>
![image](https://user-images.githubusercontent.com/25688193/42897427-f7ee3c36-8afa-11e8-9a77-6e9d77f80397.png)<br>

- t<0 で t=0 付近の領域の拡大図（N=2,5,20,40,70,100）<br>
![image](https://user-images.githubusercontent.com/25688193/42931346-6d4886ba-8b7a-11e8-8529-90514f7bee4a.png)<br>

- t>0 で t=0 付近の拡大図（N=2,5,20,40,70,100）<br>
![image](https://user-images.githubusercontent.com/25688193/42931434-9bc4b7c0-8b7a-11e8-92ac-ac288ca01754.png)<br>

図からわかるように、不連続点である t=0 での ![image](https://user-images.githubusercontent.com/25688193/42906446-1eb0965a-8b16-11e8-9069-0ab0c860672e.png) の値が、N の増加と共に、1/2(=0.5) の値に近づいていることが分かる。<br>
ここで、この 1/2(=0.5) という値は、t の値が正→0 に近づいていく極限での f(t) の値を意味する f(0+0)=0 と、t の値が負→0 に近づいていく極限での f(t) の値を意味する f(0−0)=0 との平均値となっている。<br>

このような性質は、この例に限らず一般的にも成り立ち、以下のようなことが言える。<br>
![image](https://user-images.githubusercontent.com/25688193/42906841-2604059e-8b17-11e8-8a2b-7e0a93b2fc67.png)<br>

一方、不連続点以外の t に対しては、（任意の点で）滑らかな関数のときと同じように、以下の性質が成り立つ。<br>
![image](https://user-images.githubusercontent.com/25688193/42928607-bc3d9e8e-8b72-11e8-9d2f-a9cfe4e2a916.png)<br>

しかしながら、不連続点 t=0 からわずかに離れた正領域や負領域の拡大図を見てみると（上図）、<br>
不連続点のすぐ近くに、小さな膨らみが見られる。（負領域では上に凸な膨らみ、正領域では下に凸な膨らみ）
そして、この膨らみの高さとへこみの深さは、N の値が大きくなっても 0 に近づかず、むしろ大きくなっていっていることが分かる。<br>
又、膨らみの位置は、N の増加とともに不連続点に近づいていることが分かる。<br>

不連続点付近で発生するこのような現象は、**ギブスの現象**と呼ぶ。<br>
**このギブスの現象は、区分的に滑らかな関数が不連続点を持てば必ず発生する現象である。**<br>

因みに、このギブスの現象に関して、詳しい計算より、<br>
大きい N に対しては、大体 ![image](https://user-images.githubusercontent.com/25688193/42932261-ce4abb5c-8b7c-11e8-96b9-e2ec728dfd8d.png) がへこみの位置であり、その反対方向の ![image](https://user-images.githubusercontent.com/25688193/42932338-fb79ce38-8b7c-11e8-9114-bcfe6ecd6997.png) が膨らみの位置であることがわかっている（詳細計算略）<br>
そして、不連続点の両側での膨らみの高さ、へこみの深さは、不連続点での値 {f(t_0+0)−f(t_0−0)}  の約９％になることがわかっている。<br>

このギブスの現象は、一見すると、区分的に滑らかな関数の不連続点以外の収束性（元の周期関数 f(t) への収束）と矛盾するように思える。<br>
しかし実際には、大きな N の値に対しては矛盾は生じない。<br>
<br>

このように、ギブスの現象と不連続点以外での t に関するフーリエ級数の収束性の間には矛盾が存在しないが、![image](https://user-images.githubusercontent.com/25688193/42947814-1f2d00c6-8ba9-11e8-94f6-55c733b68054.png) の膨らみやへこみ自体は N をいくら大きくしても残っているので、直感的には、収束するということに違和感がある。そこで、この収束の定義を厳密に考えてみる。<br>

先に定義したフーリエ級数の収束の定義は、以下のようなものであった。<br>
![image](https://user-images.githubusercontent.com/25688193/42988844-1fdd3cf8-8c39-11e8-8714-013b4ef5f75c.png)<br>

これまで、収束すると扱ってきた問題は、この各点収束の意味での収束するという意味であるが、<br>
この各点収束より、厳しい狭義収束の定義として、以下のような一様収束が定義できる。<br>
![image](https://user-images.githubusercontent.com/25688193/42988892-38ff02f2-8c39-11e8-8096-c5456452b033.png)<br>

この各点収束と一様収束の言葉を使えば、<br>
フーリエ級数が、ある与えられた区間内の全ての t に対して f(t) に各点収束しても、その区間で f(t) に一様収束するとは限らないことが言える。<br>

>　例えば、xxx（記載中）<br>

このことは、一般の不連続点をもつ周期関数についても成り立ち、以下の性質が成り立つ。<br>
![image](https://user-images.githubusercontent.com/25688193/42998039-c6dcc022-8c53-11e8-85f6-9b4a140dbf30.png)<br>

尚、先に述べていた滑らかな関数におけるフーリエ級数の収束は、一様収束の意味での収束であり、
以下の性質に言い換えられる。<br>
![image](https://user-images.githubusercontent.com/25688193/42998225-6383803c-8c54-11e8-9f0c-0a9f0e79790b.png)<br>

<br>

ここまで、各点収束や一様収束の議論をしてきたが、もう１つ重要な収束性に関する概念として、平均収束というものが挙げられる。<br>
![image](https://user-images.githubusercontent.com/25688193/43009309-47c03484-8c78-11e8-9b59-3e9d986ebb49.png)<br>

より一般的に定義すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43009660-3645d622-8c79-11e8-8df4-e68ffdcadb13.png)<br>

前述のように、周期関数 f(t) が滑らかな場合は、そのフーリエ級数が f(t) に一様収束する。<br>
このとき、一様収束の定義にある ε の代わりに、正の数 ![image](https://user-images.githubusercontent.com/25688193/43018258-0cf22940-8c94-11e8-93b0-98e1f2dc7923.png) を用いると、<br>
一様収束の定義より、![image](https://user-images.githubusercontent.com/25688193/43018274-1dae4a5c-8c94-11e8-87a8-ea4777ac8162.png) のような N に対して、<br>
![image](https://user-images.githubusercontent.com/25688193/43018311-3798553e-8c94-11e8-9be4-718421a99816.png)<br>
の関係が成り立つ。<br>

従って、平均収束の定義にある ![image](https://user-images.githubusercontent.com/25688193/43018328-4788a656-8c94-11e8-9ac7-6a86ab1c6166.png) に対して、<br>
![image](https://user-images.githubusercontent.com/25688193/43018385-7b9fee5e-8c94-11e8-83f2-709ccde07822.png)<br>
の関係が成り立つので、平均収束の定義が成り立つことが分かる。<br>
つまり、フーリエ級数が一様収束するならば、必ず平均収束することが言える。<br>

![image](https://user-images.githubusercontent.com/25688193/43018634-37fc2cfc-8c95-11e8-9a1d-94e82250efbb.png)<br>

次に、区分的に滑らかな周期関数のフーリエ級数を考えると、先に述べたように、各点収束はするが、一様収束はしない。<br>
そのため、滑らかな関数のときほど簡単な議論ではないが、区分的に滑らかな関数に対しても、平均収束することがわかっている。（詳細略）<br>

![image](https://user-images.githubusercontent.com/25688193/43018667-4bc77d4a-8c95-11e8-87e1-ef31ec36c403.png)<br>

<br>

最後に、この平均収束に関連した重要な式（ベッセルの不等式、パーシバルの等式）を導く。<br>

平均収束の定義にある ![image](https://user-images.githubusercontent.com/25688193/43018328-4788a656-8c94-11e8-9ac7-6a86ab1c6166.png) を、フーリエ級数展開の形で変形すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43034210-63f2f60a-8d13-11e8-8143-1f325dab7817.png)<br>
最後の項を積分すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43034216-795a8972-8d13-11e8-9578-55419156b023.png)<br>
ここで、<br>
![image](https://user-images.githubusercontent.com/25688193/43034220-8932d35e-8d13-11e8-9115-16ccdcfee84f.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43034222-a15adb8e-8d13-11e8-9a96-b94dd0906763.png)<br>
の関係式と、フーリエ係数の定義<br>
![image](https://user-images.githubusercontent.com/25688193/43034237-e393d280-8d13-11e8-88cc-7c841432e5fb.png)<br>
より、<br>
![image](https://user-images.githubusercontent.com/25688193/43034241-f76e8db8-8d13-11e8-9424-bc23a6146b6a.png)<br>
よって、<br>
![image](https://user-images.githubusercontent.com/25688193/43034271-7920337a-8d14-11e8-84aa-a3d40eb35a13.png)<br>

ここで、平均収束に定義にある ![image](https://user-images.githubusercontent.com/25688193/43037588-a55778ce-8d49-11e8-9e85-a926ea8900c9.png) の被積分関数 ![image](https://user-images.githubusercontent.com/25688193/43037595-b8474298-8d49-11e8-8fa3-87b93ef38321.png) は、<br>
任意の t に対して、0 以上となる関数なので、![image](https://user-images.githubusercontent.com/25688193/43037599-ca272a50-8d49-11e8-84cb-9002f8af78ca.png) は 0 以上である。<br>
従って、上式は、<br>
![image](https://user-images.githubusercontent.com/25688193/43037622-0de65658-8d4a-11e8-987c-8a415cb355e5.png)<br>
となり、変形すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43037605-e2ac6e32-8d49-11e8-8cda-049f81a29a43.png)<br>
N は任意の正の整数なので、N→∞ において、<br>
![image](https://user-images.githubusercontent.com/25688193/43037629-21c65b32-8d4a-11e8-92ff-b0b06aa2cc84.png)<br>
が成り立つ。
この２つの不等式を、**ベッセルの不等式**という。<br>

<br>

区分的に滑らかな周期関数に対しては、平均収束の定義にある ![image](https://user-images.githubusercontent.com/25688193/43037599-ca272a50-8d49-11e8-84cb-9002f8af78ca.png) は、N→∞ で 0 に収束するので、<br>
上記ベッセルの不等式の等式部分が成り立ち、<br>
![image](https://user-images.githubusercontent.com/25688193/43038497-9471d166-8d54-11e8-9be8-76789498834a.png)<br>
この等式を **パーシバルの等式** という。（この式の意味は後述）<br>

---

<a id="ID_3"></a>

## ■ 複素フーリエ級数
これまでのフーリエ級数は、全て実数で扱ってきたが、複素数を使ったフーリエ級数である複素フーリエ級数なるものが考えられる。<br>
この複素フーリエ級数は、これまでの実数でのフーリエ級数（実フーリエ級数）と本質的に同じものであるが、複素フーリエ級数を使用すると、フーリエ級数に関する多くの公式が簡単になり、又、計算量も軽減できるようになるメリットが存在する。<br>

実フーリエ級数の式は、<br>
![image](https://user-images.githubusercontent.com/25688193/43044696-78e576a4-8de6-11e8-8a42-2fa7dfaf11f0.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43044704-9dce5ae4-8de6-11e8-86bf-b97e2288c5b2.png)<br>
であるが、これを複素数で書き換えることを考える。<br>
複素数で書き換えるにあって、最も重要な式は、以下のオイラーの公式である。<br>
![image](https://user-images.githubusercontent.com/25688193/43044712-b92e4f2e-8de6-11e8-9a82-7c976a86744d.png)<br>
ここで、θ は任意の実数であり、フーリエ級数の式で出てくる 2nπt/T 項を使用して書き換えると、<br>
![image](https://user-images.githubusercontent.com/25688193/43044721-ebf400e8-8de6-11e8-937d-cd91cde0e651.png)<br>
フーリエ級数のときと同様にして、n に関する級数和をとると、<br>
![image](https://user-images.githubusercontent.com/25688193/43044728-0c6ccaa8-8de7-11e8-8b6e-4d007e12e083.png)<br>
ここで、![image](https://user-images.githubusercontent.com/25688193/43044731-1f5f1ec2-8de7-11e8-9b4b-9898504f95de.png) は複素数の定数であり、実部と虚部で書くと、![image](https://user-images.githubusercontent.com/25688193/43044740-40d77ab8-8de7-11e8-8dd6-2a8af9429943.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43044955-7bca84dc-8dea-11e8-9ea1-63abad3cc957.png)<br>
虚数部が０にするために、n についての和の部分を −∞ ~ ∞ の範囲に拡張すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43044962-9e91b3b4-8dea-11e8-937d-be89d6dbec64.png)<br>
この式の虚数部を０にするために、正の n に対する ![image](https://user-images.githubusercontent.com/25688193/43044967-b3341f96-8dea-11e8-8c14-32addefbd067.png) と、負の n に対する ![image](https://user-images.githubusercontent.com/25688193/43044967-b3341f96-8dea-11e8-8c14-32addefbd067.png) の関係式を調べる。<br>
k を正の整数とし、-k を負の整数として、虚数部の級数和を n=k, n=-k の項に分解すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43045498-79c039ac-8df4-11e8-95a1-9e15fe7f46ef.png)<br>
となるので、<br>
![image](https://user-images.githubusercontent.com/25688193/43045500-9dd195e8-8df4-11e8-8a99-f839cb8224cf.png)<br>
複素数で表すと、<br>
![image](https://user-images.githubusercontent.com/25688193/43045504-be64a55c-8df4-11e8-9b42-8c8c4051ddab.png)<br>
の場合に、虚数部は０になる。<br>

実際にフーリエ級数の式に代入すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43045798-3e8fa984-8dfa-11e8-955e-6c707fd18137.png)<br>
この式と実フーリエ級数の式を比較すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43045846-f8f6c212-8dfa-11e8-8813-6291ec74d9bd.png)<br>
複素係数で表記すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43045850-0991c61c-8dfb-11e8-8a0f-dcc618eff163.png)<br>

従って、複素フーリエ級数は、<br>
![image](https://user-images.githubusercontent.com/25688193/43045855-1b42255a-8dfb-11e8-9f81-641719d171dd.png)<br>

ここで、上式の複素フーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/43048781-1e4a3a76-8e28-11e8-93e3-42f9f078dcab.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/43048783-34680a72-8e28-11e8-89bb-97e0578e0e8a.png)<br>
で求まる実フーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/43048796-5003823e-8e28-11e8-9cf4-7334aaeeebad.png) から求めており、これでは計算量の削減になっていない。<br>
そこで、次に、複素フーリエ係数を直接計算することを考える。<br>
複素フーリエ級数の式の両辺に ![image](https://user-images.githubusercontent.com/25688193/43048806-6a081758-8e28-11e8-8d08-4dadfc56a29a.png) をかけて、0~T の範囲で積分すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43049119-5a154d98-8e2d-11e8-9961-3e487cbd7a36.png)<br>
ここで、右辺の積分項は、<br>
![image](https://user-images.githubusercontent.com/25688193/43111365-dd6b1ad4-8f2b-11e8-932a-de6b62e9a9cf.png)<br>
k=0 の場合は、被積分項が 1 になるので、<br>
![image](https://user-images.githubusercontent.com/25688193/43111383-f2162046-8f2b-11e8-8229-dd962b53d931.png)<br>
従って、<br>
![image](https://user-images.githubusercontent.com/25688193/43111425-2ea3d774-8f2c-11e8-96d3-6440e7d45f31.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43111436-3d054b18-8f2c-11e8-8df1-b3e6e42af9f5.png)<br>
以上の結果をまとめると、周期 T の周期関数 f(t) の複素フーリエ級数展開は、<br>
![image](https://user-images.githubusercontent.com/25688193/43111622-007a480a-8f2d-11e8-82c1-e98113c44158.png)<br>
となる。<br>

<br>

- （例）複素フーリエ係数を直接計算<br>
    ![image](https://user-images.githubusercontent.com/25688193/43142272-fea95708-8f92-11e8-80fa-a83238c93046.png)<br>
    を周期 2π 間隔で周期的に拡張した周期関数の複素フーリエ係数を、実フーリエ係数からではなく、直接計算する。<br>

    ![image](https://user-images.githubusercontent.com/25688193/43149430-5957484a-8fa2-11e8-9737-25e0b9d25a6f.png)<br>
    ここで、オイラーの公式より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43149148-b9ea07fc-8fa1-11e8-9c50-1fef809f5d30.png)<br>
    の関係が成り立つので、<br>

    - 0 以外の偶数の n に対しては、<br>
        ![image](https://user-images.githubusercontent.com/25688193/43149468-6c5c7ab4-8fa2-11e8-857e-d7ea3a2b827f.png)<br>
    
    - 奇数の n に対しては、<br>
        ![image](https://user-images.githubusercontent.com/25688193/43150453-ee492c32-8fa4-11e8-8eaf-47180ecd578a.png)<br>

    - n=0 の場合は、<br>
        ![image](https://user-images.githubusercontent.com/25688193/43150507-11e13612-8fa5-11e8-8e59-68d311705191.png)<br>

<br>

---

<a id="ID_4"></a>

## ■ 直交級数としてのフーリエ級数（関数解析視点でのフーリエ級数）
級数和としてのフーリエ級数の概念より、より広義の概念として、直交級数というものが存在する。<br>
この概念は、関数解析という分野に基づく概念であり、関数同士の直交や関数系の完全性などの概念をもたらす。<br>
ここでは、直交級数の概念でフーリエ級数を再解釈し、より広い視点でのフーリエ級数を見ていく。<br>


<a id="ID_4-1"></a>

### ◎ 関数同士の直交（直交関数系）
実フーリエ級数は、<br>
![image](https://user-images.githubusercontent.com/25688193/43206505-db87b0de-9060-11e8-8393-119b375fd68e.png)<br>
の式で表せたが、これは見方を変えると、<br>
**周期関数 f(t) を無限個の関数（関数系という）**<br>
![image](https://user-images.githubusercontent.com/25688193/43206529-eb0f0728-9060-11e8-9a3d-80bcc44feaf9.png)<br>
**の重ね合わせで表現したものであるとも言える。**<br>
**この視点に立つと、重ね合わせを行うときの係数がフーリエ係数に相当する。**<br>

このフーリエ係数は、<br>
![image](https://user-images.githubusercontent.com/25688193/43207775-c10f9430-9063-11e8-898b-0ae027514383.png)<br>
の式から計算できるが、この式の導出過程においては、以下の公式が重要な役割を果たしていた。<br>
![image](https://user-images.githubusercontent.com/25688193/43207809-d5c2af20-9063-11e8-9905-667e984b4f74.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43207835-e681c97c-9063-11e8-9f85-9e333a809bca.png)<br>
<br>
**これらの式は、**<br>
![image](https://user-images.githubusercontent.com/25688193/43206529-eb0f0728-9060-11e8-9a3d-80bcc44feaf9.png)<br>
**というの無限個の関数の集合（＝関数系）から２つの異なる関数を取り出し、それら関数の積を 0~T の範囲で積分したものが０になることを示している式となっている。**<br>
**この性質は、この関数の直交性と呼ばれ、この直交性が成り立つが故に、フーリエ係数は、上式のような比較的簡単な式で記述出来ている。**<br>

この関数系の直交性の概念は、より一般的には以下のようになる。<br>

![image](https://user-images.githubusercontent.com/25688193/43217665-2f017b16-907d-11e8-9124-f044c2c2f29e.png)<br>

一般的には、関数直交系というと、上記の被積分項に重み ρ(t) を付けた　![image](https://user-images.githubusercontent.com/25688193/43217788-8182be9a-907d-11e8-8e1a-2b022dc1bc8c.png) で扱うが、<br>
ここでは重み１のケース ρ(t)=1 を考える。<br>

この関数系の直交性は、ベクトルにおける直交性（内積が０）を一般化した概念であり、<br>
各関数が１つのベクトルに対応し、積分部分が、２つのベクトルである ![image](https://user-images.githubusercontent.com/25688193/43313589-7784ad32-91cb-11e8-873c-d9e3d44ec11b.png) の内積に対応する。<br>
従って、直交関数系は、互いに直交するベクトルの集合のようなものであるであると言える。<br>

直交関数系において、更に、大きさが１（![image](https://user-images.githubusercontent.com/25688193/43313678-c090cfb0-91cb-11e8-81a1-1ec860d2597e.png)）になるようなケース、<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/43313698-d1ad139e-91cb-11e8-9a5a-f15c4becef8c.png)<br>
が成り立つ場合、この関数系を正規直交系と呼ぶ。<br>

<br>

<a id="ID_4-2"></a>

### ◎ 直交級数（一般化フーリエ級数）
区間 p≤t≤q で定義される関数 f(t) を、直交性 ![image](https://user-images.githubusercontent.com/25688193/43352723-01815ffc-9263-11e8-9002-f588d3bc1e3f.png) を満たす直交関数系 ![image](https://user-images.githubusercontent.com/25688193/43352732-202fdc44-9263-11e8-99ec-d09295a5b9f8.png) の各関数の重ね合わせで表現すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43352738-3d8eaa22-9263-11e8-86de-760c8c9a9c7c.png)<br>
とかける。<br>
ここで、![image](https://user-images.githubusercontent.com/25688193/43352740-4e60c024-9263-11e8-9b04-cfc1a0057adf.png) は係数であり、<br>
両辺に右から ![image](https://user-images.githubusercontent.com/25688193/43352751-6650df16-9263-11e8-9afa-48053899c9e8.png) をかけて、t=p~q までの範囲で積分した式、<br>
![image](https://user-images.githubusercontent.com/25688193/43355995-158cfb74-92a3-11e8-94b9-f9318ef56397.png)<br>
よって、<br>
![image](https://user-images.githubusercontent.com/25688193/43356002-3e82c996-92a3-11e8-8727-2ba0bf9a09f1.png)<br>
このようにして求まる関数 f(t) を、**直交展開級数** といい、定数 ![image](https://user-images.githubusercontent.com/25688193/43356028-f53af88e-92a3-11e8-87ee-f5140c9ca220.png) を **展開係数** という。<br>

この観点から見ると、実フーリエ級数展開は、直交関数系 ![image](https://user-images.githubusercontent.com/25688193/43356179-e3317b06-92a6-11e8-99b8-b790d6477e50.png) による直交級数展開であり、実フーリエ級数は、この級数の展開係数である。<br>
直交級数としては、このフーリエ級数展開以外にも多くのものが存在するが（ルジャンドル多項式等）、フーリエ級数が最もよく使われるので、その意味で、直交級数を **一般化フーリエ級数** と呼ぶこともある。<br>

<br>

<a id="ID_4-3"></a>

### ◎ 完全な直交関数系
直交級数展開<br>
![image](https://user-images.githubusercontent.com/25688193/43357227-46b30d36-92b9-11e8-828a-9574fede4bd7.png)<br>
が成り立つことは、展開先の級数が、大きな n に対して、元の関数 f(t)  に収束するであるが、この収束性は、常に保証されるものではない。<br>

例えば、先の実フーリエ級数の（無限個の要素からなる）直交級数系において、１つの関数 cos⁡(2πt/T) だけを取り除いた関数系<br>
![image](https://user-images.githubusercontent.com/25688193/43357252-8b22f56c-92b9-11e8-8e81-37a51763da68.png)<br>
を考えると、これは依然として、無限個の要素から直交関数系ではあるが、この関数系は、例えば、f(t)=cos⁡(2πt/T) という関数に対しては、その直交級数（フーリエ級数）は収束しない。（＝フーリエ級数展開で表現できない）<br>
このような直交関数系では、収束していかない関数（＝級数展開で表現できない関数）が存在するという意味で、不完全である。<br>

![image](https://user-images.githubusercontent.com/25688193/43357847-a044eac8-92c2-11e8-8ba5-9439e7e3ed68.png)<br>

この完全な直交関数系の条件（![image](https://user-images.githubusercontent.com/25688193/43357429-66fd9630-92bc-11e8-8a23-02bae39890ab.png)）が成り立つ場合においては、<br>
![image](https://user-images.githubusercontent.com/25688193/43357444-a2cb1d68-92bc-11e8-889f-4f35126add4a.png) の被積分関数 ![image](https://user-images.githubusercontent.com/25688193/43357439-85f5e83a-92bc-11e8-9754-4ecd22475225.png) が、どの t に対しても 0 以上であると言えるので、不連続点のような t を除けば、直交級数は元の関数 f(t) に収束し、関数 f(t)  を直交級数で表現することが出来る。<br>
（![image](https://user-images.githubusercontent.com/25688193/43357447-b3c2bd42-92bc-11e8-9ead-3e2b9463e495.png) が成り立つ。）<br>

<br>

関数を、フーリエ級数をはじめとする直交級数で表現することの目的・ケースは、<br>
主に、以下の２点存在する。<br>

1. 関数の持つ性質について調べたい時。<br>
	例えば、ある関数 f(t)  をフーリエ級数の形で表すことにより、f(t)  の各周期の変動成分の大きさ（＝振幅の幅）を知ることが出来るなど。<br>
	
2. 微分方程式などの方程式の解を求める際に、<br>
	解の関数を直交級数で表現することにより、比較的簡単に解を求めたい時。

これらの目的により、区分的に滑らかな関数のような、実用上通常扱われる関数の中に、直交級数で表現出来ないものが含まれないと（実用上）困る。<br>
**完全直交関数系は、区分的に滑らかな関数ならば、何でも表現することが出来るので、実用上の観点から応用範囲が広い。**<br>

<br>

次に、完全直交関数系の定義で定義した ![image](https://user-images.githubusercontent.com/25688193/43357444-a2cb1d68-92bc-11e8-889f-4f35126add4a.png) を別の形（パーシバルの等式）に書き直すことを考える。<br>
![image](https://user-images.githubusercontent.com/25688193/43358491-d32aa436-92cd-11e8-9d9e-693acf92ab4f.png)<br>
ここで、![image](https://user-images.githubusercontent.com/25688193/43358503-ede64f14-92cd-11e8-8426-2faa03aa9f99.png) の関係式より、<br>
![image](https://user-images.githubusercontent.com/25688193/43358746-6d5425ac-92d1-11e8-84c3-768b8f92970b.png)<br>
従って、直交関数系 ![image](https://user-images.githubusercontent.com/25688193/43358751-878cebd4-92d1-11e8-997e-dbe087e3635c.png) が完全であるための条件 lim_(N→∞) I_N=0 は、<br>
![image](https://user-images.githubusercontent.com/25688193/43358885-e0623096-92d3-11e8-97b9-5d58bc4bba3e.png)<br>
と書き直せる。<br>

ここで、パーシバルの等式 ![image](https://user-images.githubusercontent.com/25688193/43359300-24961a46-92db-11e8-8c9e-4c6efb2343e4.png) と、この完全直交関数系であるための条件 ![image](https://user-images.githubusercontent.com/25688193/43359304-3bcf24fa-92db-11e8-8335-9f92b745149e.png) を比較すると、<br>
フーリエ展開における関数 ![image](https://user-images.githubusercontent.com/25688193/43359316-6f9a6ace-92db-11e8-8c5d-3e1eadd79cc0.png) に対応する展開係数は ![image](https://user-images.githubusercontent.com/25688193/43359329-86052254-92db-11e8-988a-28b81db65184.png) であることが分かる。<br>
又、直交性の条件 ![image](https://user-images.githubusercontent.com/25688193/43359340-b28d5788-92db-11e8-8565-6ed900e39691.png) を、フーリエ級数に対応するように p=0, q=T で n=m の場合で計算すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43359344-d69e9ae2-92db-11e8-8d31-41d2881999d8.png) のときは、![image](https://user-images.githubusercontent.com/25688193/43359351-e5e2c550-92db-11e8-862b-3efa3be35bea.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43359356-fa6af182-92db-11e8-83dd-f25e54cbc3f0.png) のときは、![image](https://user-images.githubusercontent.com/25688193/43359360-09d0217e-92dc-11e8-909c-6e2d6d111032.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43359365-1fb33792-92dc-11e8-9fda-a0af308d5168.png) のときは、![image](https://user-images.githubusercontent.com/25688193/43359360-09d0217e-92dc-11e8-909c-6e2d6d111032.png)<br>
従って、完全直交関数系であるための条件 ![image](https://user-images.githubusercontent.com/25688193/43359369-3d78a28a-92dc-11e8-87aa-6385c701e33c.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/43359374-55219112-92dc-11e8-8249-2849182fcfb6.png)<br>
となり、パーシバルの等式になっていることが分かる。<br>

従って、完全直交関数系の条件から、パーシバルの等式（フーリエ級数の場合の平均収束の定義から導かれる条件）を（等しい関係で）構築できるので、<br>
**実フーリエ級数の”もとになっている”直交関数系**<br>
![image](https://user-images.githubusercontent.com/25688193/43360230-af3e8c44-92ec-11e8-91df-a119ff599e30.png)<br>
**は完全である（＝完全直交関数系である）** と言える。<br>

又、**複素フーリエ級数の”もとになっている”直交関数系**<br>
![image](https://user-images.githubusercontent.com/25688193/43360269-ccca7ee8-92ed-11e8-895a-e9994cabd38e.png)<br>
**も完全である（＝完全直交関数系である）** と言える。<br>

<br>

<a id="ID_4-4"></a>

### ◎ ルジャンドル多項式
完全な直交関数系には、様々な種類が存在するが、完全直交関数系に基づく直交級数は、フーリエ級数の仲間になる。ここでは、このフーリエ級数の仲間の１例としてルジャンドル多項式を見てみる。<br>

今、−1≤t≤1 という区間で、区分的に滑らかな関数 f(t) を、直交関数系を用いて級数展開することを考える。

まず最初に思いつくのは、べき関数からなる関数系 ![image](https://user-images.githubusercontent.com/25688193/43360571-8673f604-92f2-11e8-8127-922ad8a137eb.png) であるが、これは直交性の条件を満たさず、残念ながら直交関数系ではない（証明略）
<br>

次に、多項式の０次・１次・２次・・・からなる関数系において、各々の要素が直交性の条件を満たすように、０次から n 次までの多項式が直交性の条件を満たす時に、次の次数 n+1 の多項式も直交性の条件を満たすように式を構築するようにすることを考える。<br>

具体的には、まず０次の多項式（定数）![image](https://user-images.githubusercontent.com/25688193/43360585-d1a594c0-92f2-11e8-8ba6-bcb4d8e60a48.png) と１次の多項式 ![image](https://user-images.githubusercontent.com/25688193/43360593-f5de2d16-92f2-11e8-9fc6-1d7577c74842.png) に対しては、<br>
直交性の条件 ![image](https://user-images.githubusercontent.com/25688193/43361401-c55db272-9308-11e8-822e-a2c107e5dd2a.png) を満たすので、![image](https://user-images.githubusercontent.com/25688193/43361406-e7fd2e3e-9308-11e8-8a6b-efac903796d7.png) は直交関数系である。<br>
次に、２次の多項式 ![image](https://user-images.githubusercontent.com/25688193/43361444-aa80f6d4-9309-11e8-9e0c-d51cc91ebc76.png) に対しては、<br>
![image](https://user-images.githubusercontent.com/25688193/43361406-e7fd2e3e-9308-11e8-8a6b-efac903796d7.png) と共に直交するという条件を満たすようにするめには、![image](https://user-images.githubusercontent.com/25688193/43361453-f0b75602-9309-11e8-9c6b-cf7a8bf3bb50.png) となるようにする（計算略）と、![image](https://user-images.githubusercontent.com/25688193/43361464-0e309108-930a-11e8-916f-a2d33f0a6302.png) は直交関数系である。<br>
これらの作業を繰り返すと、<br>
![image](https://user-images.githubusercontent.com/25688193/43361483-4fb59db2-930a-11e8-8d19-7656f6075d84.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43361486-66dd94c2-930a-11e8-82fc-cfac6200a1b5.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43361493-a2c7fb8a-930a-11e8-8189-b0908deaf6bd.png)<br>
が得られ、![image](https://user-images.githubusercontent.com/25688193/43361500-df3a160c-930a-11e8-969a-7e8adab46e14.png) は直交関数系である。といった具合である。<br>

このようにして得られた関数系 ![image](https://user-images.githubusercontent.com/25688193/43361508-172a1ce2-930b-11e8-849d-055fbba46175.png) は、**ルジャンドル多項式** と呼ばれる。<br>
そして、**このルジャンドル多項式からなる関数系は、”完全な”直交関数系である。**<br>

従って、−1≤t≤1 という区間で、区分的に滑らかな任意の関数 f(t) は、級数展開の形<br>
![image](https://user-images.githubusercontent.com/25688193/43361535-1239feb8-930c-11e8-8c9c-77c5408a4c25.png)<br>
で表現することが出来る。<br>
そして、この級数展開を、**ルジャンドル級数展開** という。<br>

このルジャンドル級数展開の展開係数は、<br>
![image](https://user-images.githubusercontent.com/25688193/43361805-a03750d6-9315-11e8-8ceb-6860f7a42c92.png)<br>
※ 級数展開の場合展開係数の式 ![image](https://user-images.githubusercontent.com/25688193/43361811-01135d32-9316-11e8-8101-10a023547a8a.png) において、![image](https://user-images.githubusercontent.com/25688193/43361813-1d180d34-9316-11e8-85c3-eb07fee7239e.png) とおいた式<br>
※ ![image](https://user-images.githubusercontent.com/25688193/43361818-465abf8e-9316-11e8-87f7-90f8d4e9290c.png) は、![image](https://user-images.githubusercontent.com/25688193/43361826-72203284-9316-11e8-9f13-f3c80cd85f12.png) において、![image](https://user-images.githubusercontent.com/25688193/43361832-92ca7d0a-9316-11e8-90ca-b3702fdf063b.png) とおいた式 ![image](https://user-images.githubusercontent.com/25688193/43361838-b2bd3e04-9316-11e8-80b7-4fae7e4bf842.png) から求まり、![image](https://user-images.githubusercontent.com/25688193/43361850-f631bcc8-9316-11e8-86ea-d6ca022e34b9.png) となる。（計算略）<br>

<br>

<a id="ID_4-5"></a>

### ◎ 最適な直交級数の選択
フーリエ級数展開は、区分的に滑らかな関数に対しては成り立つ（＝級数が収束する。）<br>
又、ルジャンドル級数展開は、−1≤t≤1 の範囲において、区分的に滑らかな関数に対しては成り立つ（＝級数が収束する。）<br>
従って、区分的に滑らかな関数は、−1≤t≤1 の範囲において、フーリエ級数でもルジャンドル級数でも表現できる。このように、完全直交関数系は複数存在するので、１つの関数を複数の直交級数の形で表現できるケースが存在する。<br>

このような場合において、複数の直交級数の内、どの直交級数を使うべきかを考える必要が出てくるが、この問題は、関数のもつある性質を調べるにあたって、その性質を最もよく表現出来るような級数を選択すればよい。<br>

例えば、関数に含まれる様々な周期の変動成分の大きさを知りたい際には、フーリエ級数展開で表現するのがベストな選択である。<br>
微分方程式などの方程式の解を比較的簡単に求めるために解の関数を直交級数展開する際には、直交関数系を構成する各関数が取り扱いやすい形（＝微分・積分の計算が楽な形）になるようにするようにする。（フーリエ級数展開は、三角関数で取り扱いやすい。又、ルジャンドル級数展開も多項式で取り扱いやすい。）<br>

もう１つ重要な要素としては、級数展開時の各級数の収束の速さである。<br>
これは、ある関数を級数和で近似するのに、たくさんの項が必要なのか、或いは少数の項で済むのかの問題であるが、解の関数を近似する数値計算では、特に重要になってくる。<br>

<!--
- （例）<br>
    以下の関数のフーリエ級数展開とルジャンドル級数展開の収束の差を調べる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/43371149-f5c913ca-93c6-11e8-98ba-9fe88db38cce.png)<br>
    <br>
    ① まず、ルジャンドル級数の展開係数を求める。<br>
    ![image](https://user-images.githubusercontent.com/25688193/43371153-0f576814-93c7-11e8-9e22-8173cfd97b09.png)<br>
	この例題の関数 f(t) は、偶関数（![image](https://user-images.githubusercontent.com/25688193/43371180-b0fe7568-93c7-11e8-883f-b1ba7dd41c47.png)）であり、<br>
	又、ルジャンドル多項式 ![image](https://user-images.githubusercontent.com/25688193/43371159-3a50590e-93c7-11e8-99e0-ddd708f1d935.png) は奇関数（![image](https://user-images.githubusercontent.com/25688193/43371199-1ce90946-93c8-11e8-8aa7-c1b271e8c9a2.png)）なので、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43371211-498523f4-93c8-11e8-875b-5cfd4cef20fa.png)<br>
-->

---

<a id="ID_5"></a>

## ■ フーリエ変換
フーリエ級数展開では、周期関数が sin,cos の和で表現できることが分かったが、同様にして、非周期関数も、様々な周期の sin,cos の和で表現できないかを考える。<br>

この問題を考えるための例として、以下のような関数を考える。<br>

![image](https://user-images.githubusercontent.com/25688193/43378907-988c7812-9404-11e8-8025-4cfe00e38c53.png)<br>
この関数は、t→±∞ としても値が０のままであるので、非周期関数である。<br>

次に、この非周期関数 ![image](https://user-images.githubusercontent.com/25688193/43379018-3c15c4f2-9405-11e8-81ab-c98423327181.png) の代わりに、以下のような周期関数 ![image](https://user-images.githubusercontent.com/25688193/43379038-5a5765ba-9405-11e8-8ce4-b063d3d69a9a.png) を考える。<br>
![image](https://user-images.githubusercontent.com/25688193/43379120-cb4c3b2e-9405-11e8-9a3a-4c450a8317b1.png)<br>

２つの関数を比較すると、M→∞ とすると、![image](https://user-images.githubusercontent.com/25688193/43383768-fadcb2fe-9416-11e8-8fec-80f2dc53fa45.png) となることが分かる。<br>
そこで、まず周期関数である ![image](https://user-images.githubusercontent.com/25688193/43379038-5a5765ba-9405-11e8-8ce4-b063d3d69a9a.png) のフーリエ級数（※周期関数はフーリエ級数展開可能）を求め、次に M→∞ としたときにどうなるのかを見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/43379038-5a5765ba-9405-11e8-8ce4-b063d3d69a9a.png) は偶関数なので、そのフーリエ級数展開は、<br>
![image](https://user-images.githubusercontent.com/25688193/43382747-c101d5c6-9413-11e8-9b58-9978a6ed231a.png)<br>
具体的に計算すると、<br>
<br>

ここで、このフーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/43382825-053c1ddc-9414-11e8-90b1-ffc462a4b4e0.png) は、正の整数 n に対する周期の三角関数の変動成分の大きさを表しているが、以降では、周期の代わりに、波数 ![image](https://user-images.githubusercontent.com/25688193/43382871-2b19ddb4-9414-11e8-9dc5-1e4eef943305.png) を用いてこれら各変動成分を区別していくことにする。<br>

次に、M→∞ とした場合に、このフーリエ係数 a_n  がどのようになるのかを調べる。<br>
そのために、![image](https://user-images.githubusercontent.com/25688193/43404733-28c716fa-9453-11e8-9bf8-41a3acc05931.png) に ![image](https://user-images.githubusercontent.com/25688193/43404790-4c1c6f42-9453-11e8-8631-f099518c01b8.png) をかけて、M を消去し、k に依存した式 ![image](https://user-images.githubusercontent.com/25688193/43408682-ec27bd80-945c-11e8-9a11-aeb0fa7c494e.png) を導くと、<br>
![image](https://user-images.githubusercontent.com/25688193/43408717-feb57b18-945c-11e8-9739-31fb84040449.png)<br>
となり、フーリエ係数は、<br>
![image](https://user-images.githubusercontent.com/25688193/43408787-24bc0192-945d-11e8-9247-97e9b71dff16.png)<br>
とかける。<br>

従って、フーリエ級数展開の式は、<br>
![image](https://user-images.githubusercontent.com/25688193/43408913-71fa7d12-945d-11e8-9155-d417b49a3268.png)<br>
ここで、この式の第２項である ![image](https://user-images.githubusercontent.com/25688193/43409204-3bd6c0c8-945e-11e8-9f60-0eb95e52a9d4.png) の部分を図示すると以下の図のようになる。<br>
<br>
この図からわかるように、長方形の幅は、k=2π/T=n/M の関係より、一番左（a_0  の部分）のもので 1/2M となり、それ以外は 1/M である。<br>
従って、この長方形の面積の和は、フーリエ級数展開の式の第２項の部分 ![image](https://user-images.githubusercontent.com/25688193/43410337-8618a7e8-9461-11e8-966c-32a862befcc2.png) になっている。<br>
そして、M→∞ とすると、この長方形の幅は０に近づき、関数 a ̂(k)  cos⁡(kt)  の面積（積分）![image](https://user-images.githubusercontent.com/25688193/43410405-b8e2c6fe-9461-11e8-82b9-0e1fc515ef36.png) に近づく。<br>
![image](https://user-images.githubusercontent.com/25688193/43422073-94891c14-9483-11e8-9417-fbb673dc41ba.png)<br>
よって、<br>
![image](https://user-images.githubusercontent.com/25688193/43410441-d5a51ce2-9461-11e8-9669-b29ae0d3e71e.png)<br>
となり、また ![image](https://user-images.githubusercontent.com/25688193/43410464-ef5a0d82-9461-11e8-9fc5-24e821c7f99b.png) の関係より、<br>
![image](https://user-images.githubusercontent.com/25688193/43423725-1e08262a-9488-11e8-95cc-e12f9383827e.png)<br>
が成り立つ。<br>

<br>

次に、一般的な周期関数 ![image](https://user-images.githubusercontent.com/25688193/43427083-13b50034-9493-11e8-827c-2765a9d6941f.png)（周期 T）の場合を考える<br>
この周期関数 ![image](https://user-images.githubusercontent.com/25688193/43427083-13b50034-9493-11e8-827c-2765a9d6941f.png) をフーリエ級数展開すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43427166-65487fc0-9493-11e8-9868-f6c76c202efa.png)<br>
波数 k で書き換えると、<br>
![image](https://user-images.githubusercontent.com/25688193/43427190-7c40b38c-9493-11e8-8361-2beb694e6de8.png)<br>

T=2Mπ より、M に依存しないフーリエ係数の形 ![image](https://user-images.githubusercontent.com/25688193/43427700-c14c58f8-9495-11e8-849f-c980b05d8aef.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/43427726-de6c344e-9495-11e8-9390-6ce722a3c4c5.png)<br>
に書き換えられるので、これを使用してフーリエ級数を書き換えると、<br>
![image](https://user-images.githubusercontent.com/25688193/43427757-004a2562-9496-11e8-8808-d54e59de3c26.png)<br>
この式に対して、周期 T→∞ とすると、先の例と同じように、<br>
{} 内の部分（赤字部分）は、![image](https://user-images.githubusercontent.com/25688193/43427781-1851f4dc-9496-11e8-89b5-d0899b016dfc.png) に近づいていく。<br>

従って、<br>
![image](https://user-images.githubusercontent.com/25688193/43427815-410b833e-9496-11e8-9733-ea27633ce9b7.png)<br>
ここで、以下のような複素数の関数を導入する。<br>
![image](https://user-images.githubusercontent.com/25688193/43428099-839a3e88-9497-11e8-9525-c61446cd275b.png)<br>
そして、この関数に、先の ![image](https://user-images.githubusercontent.com/25688193/43428992-10c3f868-949c-11e8-8406-496c3a4fa559.png) を代入すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43429047-5943f3e0-949c-11e8-8646-cf778b524d95.png)<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/43429088-86c22ea4-949c-11e8-9b48-acc59269a7f5.png)<br>
が成り立つ。<br>
この式を用いて、関数 f(t) から F(k) を求めることを、関数の **フーリエ変換** と呼ぶ。<br>
（関数 F(k) を関数 f(t) のフーリエ変換と呼んでもよい。）<br>

次に、![image](https://user-images.githubusercontent.com/25688193/43465115-a0687d10-9517-11e8-950c-db77f5ba8723.png) を k について、−∞~∞ の範囲で積分すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43467374-8a04b9e4-951c-11e8-8cc3-2fba5b975b84.png)<br>
ここで、![image](https://user-images.githubusercontent.com/25688193/43467446-aca9555e-951c-11e8-9c68-f6ab5b1c3336.png) の関係より、<br>
![image](https://user-images.githubusercontent.com/25688193/43467534-d4aa0b34-951c-11e8-97ed-ed5f58c11803.png)<br>
の関係が成り立つ。<br>
この式を用いて、関数 F(k) から f(t) を求めることを、関数のフーリエ逆変換と呼ぶ。<br>
（関数 f(t) を関数 F(k) のフーリエ変換と呼んでもよい。）<br>

- （例）関数 ![image](https://user-images.githubusercontent.com/25688193/43490179-953639c6-955a-11e8-8fab-ae9e77afa45f.png) のフーリエ変換を求める。<br>
    ![image](https://user-images.githubusercontent.com/25688193/43490194-a67120fc-955a-11e8-98b1-c7a73f3d3537.png)<br>

    ![image](https://user-images.githubusercontent.com/25688193/43490215-bfc38806-955a-11e8-848b-0b2525e37437.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/43494120-2bf31350-956c-11e8-9b00-a81679c3bb87.png)<br>

<br>

フーリエ変換の式の F(k) に、フーリエ逆変換の結果の式を代入した式<br>
![image](https://user-images.githubusercontent.com/25688193/43494136-4435d2c2-956c-11e8-9532-6d945686625c.png)<br>
が得られる。<br>
この式は、フーリエ変換を再度フーリエ逆変換すると、元に戻るという性質を記述した式であり、**フーリエの積分公式** と呼ばれる。<br>

<br>

次に、f(t) が偶関数で、f(−t)=f(t)  を満たす場合を考えると、<br>
フーリエ係数は、<br>
![image](https://user-images.githubusercontent.com/25688193/43494169-657239f8-956c-11e8-8700-ce6f1f82db55.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43494203-91030584-956c-11e8-9535-9fce978f6a5c.png)<br>
従って、![image](https://user-images.githubusercontent.com/25688193/43494217-aec2fc8c-956c-11e8-8ef5-d13b0156a70d.png) の関係より、<br>
![image](https://user-images.githubusercontent.com/25688193/43494288-0a66d77a-956d-11e8-9ae5-64f537250f3d.png)<br>
が成り立つ。<br>
この場合（＝f(t) が偶関数）の a ̂(k) は、関数 f(t) のフーリエ余弦変換と呼ばれる。<br>
（２つの目の式は、その逆変換）<br>

又、f(t) が奇関数で、f(−t)=−f(t) を満たす場合を考えると、同様にして、<br>
![image](https://user-images.githubusercontent.com/25688193/43494389-89a816fc-956d-11e8-9a79-610899f0c45c.png)<br>
が成り立つ。<br>
この場合（＝f(t) が奇関数）の b ̂(k) は、関数 f(t) の **フーリエ正弦変換** と呼ばれる。<br>
（２つの目の式は、その逆変換）<br>


<a id="ID_5-1"></a>

### ◎ フーリエ変換は何を表しているか
フーリエ級数は、周期関数 f(t) を様々な波数 k を持つ sin,cos 関数の変動成分の重ね合わせとして表現しており、各成分は、１つ・２つと数えられるものであった。（離散スペクトル）<br>
一方、フーリエ変換も、非周期関数 f(t) を様々な波数 k を持つ sin,cos 関数の変動成分の重ね合わせとして表現しるが、各変動成分の波数 k が、任意の実数の値となり、連続的な値をとり得る。（連続スペクトル）
そして、この重ね合わせの密度（＝）が、![image](https://user-images.githubusercontent.com/25688193/43539899-2fccab7c-9601-11e8-93fb-af82d7ce5f40.png) に比例する。<br>

従って、**与えられた非周期関数 f(t)  のフーリエ変換を求めることにより、この関数 f(t)  の中に、どの波数（或いは周期）の変動成分が多く含まれているか？或いは、波数や周期でみてどのような範囲の変動成分を含んでいるか？を調べることが出来る。**<br>


<a id="ID_5-2"></a>

### ◎ フーリエ変換出来る関数と出来ない関数
フーリエ変換は、全ての非周期関数について存在するわけではない。<br>
フーリエ変換が存在する条件には、以下のような条件が存在する。<br>
![image](https://user-images.githubusercontent.com/25688193/43539872-1dd0108a-9601-11e8-9b7d-1eae72ef4545.png)<br>

- （例）<br>
    ![image](https://user-images.githubusercontent.com/25688193/43543769-fdf167a4-960b-11e8-934f-f9a5bb7777a1.png)<br>
    が絶対可積分であるかを調べる。<br>
    この関数の絶対値の −∞ < t < ∞ 区間での積分は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43543851-32e2a522-960c-11e8-847e-31fb2dd8aae1.png)<br>
    となり、有限の値をとるので、この関数 ![image](https://user-images.githubusercontent.com/25688193/43543876-4484120c-960c-11e8-8af2-30f0a0245d01.png) は絶対可積分であり、フーリエ変換は存在する。<br>



<a id="ID_5-3"></a>

### ◎ フーリエ変換の計算
フーリエ変換は、以下のような作用素の記号で書き表すのが、意味が分かりやすく便利である。<br>
![image](https://user-images.githubusercontent.com/25688193/43550627-346c9b06-961f-11e8-982a-59c8865433b2.png)<br>

今、２つの関数 ![image](https://user-images.githubusercontent.com/25688193/43550654-49127bf2-961f-11e8-80d9-935cd46dda36.png) がフーリエ変換をもつとする。<br>
このとき、この２つの関数の各々に実数 ![image](https://user-images.githubusercontent.com/25688193/43550676-5c81114e-961f-11e8-8791-e8c6f741e5d3.png) をかけて足し合わせた関数 ![image](https://user-images.githubusercontent.com/25688193/43550709-70751718-961f-11e8-84d4-f2a20c48ee3c.png) のフーリエ変換がどうなるのかを見てみる。<br>
![image](https://user-images.githubusercontent.com/25688193/43691118-01752692-9952-11e8-8b32-788c709d8580.png)<br>
つまり、（![image](https://user-images.githubusercontent.com/25688193/43557077-f97f8930-963d-11e8-93bb-a193e0432d33.png) とすると分かるように）２つの関数の和のフーリエ変換は、各々の関数のフーリエ変換の和となる。<br>
又、（![image](https://user-images.githubusercontent.com/25688193/43557101-138938e4-963e-11e8-8f94-b68b7d24149a.png) とすると分かるように）ある関数の定数倍のフーリエ変換は、元の関数のフーリエ変換の定数倍となることが分かる。<br>
これらの関係は、**フーリエ変換についての重ね合わせの原理** と呼ばれる。<br>
この原理を使えば、例えば、フーリエ変換がわかっている２つの関数があって、その関数の和のフーリエ変換を求めたい場合に、これを直ちに計算することが出来る。<br>

尚、フーリエ逆変換についても重ね合わせの原理が成り立つ。<br>
![image](https://user-images.githubusercontent.com/25688193/43558481-b8883218-9644-11e8-891a-7cd5c7ec3a90.png)<br>

<br>

次に、関数 f(t/q) のフーリエ変換を考える。<br>
関数 f(t/q) は、関数 f(t) を t 軸方向に q 倍伸縮した関数であるが、<br>
そのフーリエ変換は、<br>
![image](https://user-images.githubusercontent.com/25688193/43691126-2a6319e2-9952-11e8-84ba-8dae853b0971.png)<br>
※ 左辺の (k) は、フーリエ変換の結果が、k に依存するという意味。<br>
※ 右辺の (qk) は、フーリエ変換の結果が、k → qk に置き換えたものになる意味。<br>

- （例）<br>
    ![image](https://user-images.githubusercontent.com/25688193/43645428-d2bfeb5c-976c-11e8-8611-bff05a1fe5e4.png)<br>
    のフーリエ変換の結果を用いて、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43645470-f29d2192-976c-11e8-938a-01f3f754e6a0.png)<br>
    のフーリエ変換を求める。<br>

    f(t) は、区分的に滑らかな関数で、かつ、絶対可積分なので、フーリエ変換が存在し、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43645510-15abca62-976d-11e8-8aa5-191bbf4b04f2.png)<br>
    一方、f ̂(t) は、f(t) を t 軸方向に q 倍したものであり、f ̂(t)=f(t/q) の関係が成り立つ。<br>
    ![image](https://user-images.githubusercontent.com/25688193/43645552-3d3ffe18-976d-11e8-83b4-b59849731d76.png)<br>

<br>

次に、関数 f(t) を t 軸方向に β だけずらした関数 f(t−β) のフーリエ変換を考える。<br>
![image](https://user-images.githubusercontent.com/25688193/43691132-4cb50f3c-9952-11e8-805f-00cd9f0c6a61.png)<br>
即ち、ある関数を t 軸方向に β だけずらした関数のフーリエ変換は、元の関数のフーリエ変換に e^(−ikβ)  をかけたものとなる。<br>
従って、元の関数のフーリエ変換が分かっている時は、このフーリエ変換の結果を用いて、元の関数を t 軸方向に任意の量だけずらした関数のフーリエ変換を容易に計算できる。<br>

- （例）<br>
    ![image](https://user-images.githubusercontent.com/25688193/43672206-394345f0-97e4-11e8-99be-991c63be9a88.png)<br>
    のフーリエ変換の結果を用いて、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43672212-568ef960-97e4-11e8-84ad-1a7ee81b6d6e.png)<br>
    のフーリエ変換を求める。<br>

    f(t) は、区分的に滑らかな関数で、かつ、絶対可積分なので、フーリエ変換が存在し、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43672217-75d18e8c-97e4-11e8-8acb-7af940077a02.png)<br>
    一方、f ̂(t) は、f(t) を t 軸方向に β だけずらしたものであり、f ̂(t)=f(t−β) の関係が成り立つ。<br>
	従って、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43672238-bd37a50e-97e4-11e8-8f48-f8d49f3e2987.png)<br>


<a id="ID_5-3-1"></a>

#### ☆ 微分・積分した関数のフーリエ変換
フーリエ変換を利用して偏微分方程式を解く際には、ある関数のフーリエ変換と、その関数を微分・積分した関数のフーリエ変換の間の関係性を知っておくことが必要になる。<br>
更に、時系列データなどの離散データの解析にも、この関係性についての知識がしばしば必要になる。<br>

そこでまず、区分的に滑らかで絶対可積分な関数 f(t) のフーリエ変換と、<br>
この関数を微分した関数（導関数）f′(t) のフーリエ変換の間の関係性を調べてみる。<br>
（ここで、導関数 f′(t) も区分的に滑らかな関数であるとする。）<br>
![image](https://user-images.githubusercontent.com/25688193/43691137-6d91fb98-9952-11e8-8a37-18ab48f3b122.png)<br>
即ち、ある関数の導関数のフーリエ変換は、元の関数のフーリエ変換に ik をかけたものになる。<br>

<br>

次に、区分的に滑らかで絶対可積分、かつ ![image](https://user-images.githubusercontent.com/25688193/43679241-145a4b5c-985d-11e8-92c9-06706a662d86.png) を満たす関数 f(t) のフーリエ変換と、
この関数を積分して得られる関数 ![image](https://user-images.githubusercontent.com/25688193/43679246-26df5132-985d-11e8-95dd-28f6da829611.png)（区分的に滑らかで絶対可積分であるとする）のフーリエ変換の間の関係性について調べてみる。<br>
![image](https://user-images.githubusercontent.com/25688193/43691149-904cf020-9952-11e8-8a33-113bf809b684.png)<br>

- （例）<br>
    ![image](https://user-images.githubusercontent.com/25688193/43679974-8e0850ea-986a-11e8-8baa-c03bc33d0644.png)<br>
    のフーリエ変換を、この関数の２階導関数 f′′(t) から求める。<br>

    ![image](https://user-images.githubusercontent.com/25688193/43679976-b47474f2-986a-11e8-870d-29d1a1aa4f6c.png)<br>
	ここで、f′(t),f′′(t) 共に、区分的に滑らかで絶対可積分な関数である。<br>
	次に、f′′(t) のフーリエ変換を求めると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43679987-fd0b3962-986a-11e8-88fe-0e564ccaf31a.png)<br>
	ここで、f′ (t) は t→−∞ で 0 となる関数なので、![image](https://user-images.githubusercontent.com/25688193/43679989-1d1ce228-986b-11e8-8502-d71896c0f053.png) の関係が成り立ち、<br>
	![image](https://user-images.githubusercontent.com/25688193/43679994-3ab096d6-986b-11e8-82c0-16a77c644455.png) の条件が成り立つ。<br>
	同様に、f(t) は t→−∞ で 0 となる関数なので、![image](https://user-images.githubusercontent.com/25688193/43679999-58c5dfa0-986b-11e8-894f-1bd3b0bf305f.png) の関係が成り立ち、<br>
	![image](https://user-images.githubusercontent.com/25688193/43680003-83e3efc4-986b-11e8-8a4d-8ae77f325e26.png) の条件が成り立つので、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43680013-a5ff87e4-986b-11e8-92ec-1287e9fcc271.png)<br>
    が成り立ち、結果、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43680018-b80588f8-986b-11e8-9a09-265813374cbc.png)<br>

<br>

<a id="ID_5-3-2"></a>

#### ☆ 合成積（畳み込み）、積のフーリエ変換とパーシバルの等式
区分的に滑らかで絶対可積分な２つの関数 f(t),g(t) が与えれたときに、<br>
f(t) と g(t) の畳み込み（合成積）を、<br>
![image](https://user-images.githubusercontent.com/25688193/43689986-a4186914-993d-11e8-9663-1d3ace4649d0.png)<br>
によって定義する。<br>
この畳み込みは、関数 g(t) を平行移動しながら関数 f(t) に重ね足し合わせる２項演算になっている。<br>
![image](https://user-images.githubusercontent.com/25688193/43689952-d161a648-993c-11e8-9859-d7b6c087dbba.png)<br>

ここで、積分変数を ![image](https://user-images.githubusercontent.com/25688193/43690017-50258034-993e-11e8-997b-530d889f263c.png) に変えると、<br>
![image](https://user-images.githubusercontent.com/25688193/43690029-6e5f618c-993e-11e8-814b-003e9a9bdfbb.png)<br>
となるので、畳み込み演算は、交換則が成り立つ。<br>

この畳み込み演算は、応用上の観点からしばしば利用されるが、<br>
**畳み込みのフーリエ変換は、これを構成する２つの関数 f(t) のフーリエ変換と g(t) のフーリエ変換を用いて、簡単な形で表せる。**<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/43691155-e39a568c-9952-11e8-8a12-e0a31901b13b.png)<br>
即ち、**２つの関数の畳み込み（合成積）のフーリエ変換は、それぞれの関数のフーリエ変換の積となる。**<br>

- （例）<br>
    ![image](https://user-images.githubusercontent.com/25688193/43692109-6fd012d4-995f-11e8-97a3-493c649e8b44.png)<br>
    この２つの関数の畳み込みは、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43692121-8c3a6762-995f-11e8-99b5-b88fb0e1500b.png)<br>
    となるが、２つの関数から畳み込みのフーリエ変換を求める。<br>

    f(t) を t 軸方向に β=1 だけずらした関数 ![image](https://user-images.githubusercontent.com/25688193/43692134-bdb780b8-995f-11e8-9d9c-791978779968.png) を考えると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43692140-d72a7d0c-995f-11e8-9323-ec5c1727e983.png)<br>
    すると、f ̂(t) は、区分的に滑らかな関数で、かつ、絶対可積分なので、フーリエ変換が存在し、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43692148-faf4628e-995f-11e8-9630-4b1d527e8c10.png)<br>
    平行移動した関数のフーリエ変換と元の関数フーリエ変換の間の関係 ![image](https://user-images.githubusercontent.com/25688193/43692164-23fedc7c-9960-11e8-912d-34cd4634ce08.png) より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43692169-3b3ce58c-9960-11e8-8872-7f8b6cc39748.png)<br>
    同様にして、g(t) を t 軸方向に β=−1 だけずらした関数 ![image](https://user-images.githubusercontent.com/25688193/43692179-53f7b412-9960-11e8-891a-5ea8c78697c3.png) を考えると、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43692198-7ed73c20-9960-11e8-9b1d-9982ee745ce1.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/43692207-9203aa0e-9960-11e8-9fb6-60eb017ac413.png)<br>

    従って、<br>
    ![image](https://user-images.githubusercontent.com/25688193/43692219-b0daccb4-9960-11e8-9ec2-81499bb2619f.png)<br>

<br>

次に、２つの関数 f(t),g(t) がそれぞれフーリエ変換 F(k),G(k) をもつ場合に、<br>
この２つの関数の積 f(t)×g(t) のフーリエ変換を F(k),G(k) を用いて比較的簡単に表せないかを調べてみる。<br>
![image](https://user-images.githubusercontent.com/25688193/43694766-f6384f70-996f-11e8-851c-c9233d5d237a.png)<br>

ここで、g(t)=f(t) で k=0 のときは、<br>
![image](https://user-images.githubusercontent.com/25688193/43698236-ef431c5e-9983-11e8-805a-1e4197683720.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43698294-2835d1e6-9984-11e8-9bea-3f618a6bcdff.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43698316-4055a274-9984-11e8-816c-fa103c89740f.png) の関係より、<br>
![image](https://user-images.githubusercontent.com/25688193/43698330-5bdb1cb8-9984-11e8-8bef-ed81cd7dc8bd.png)<br>
が成り立つ。<br>
この式は、フーリエ変換に対するパーシバルの等式と呼ばれており、先のフーリエ級数の収束性のところで取り上げた、パーシバルの等式と類似のものである。（この式の意味については、後述）<br>


<a id="ID_5-3-3"></a>

#### ☆ ガウス関数のフーリエ変換
最後に、応用上しばしば利用されるガウス関数 ![image](https://user-images.githubusercontent.com/25688193/43701426-1f80b4c8-9991-11e8-8721-629c2fbb0682.png) のフーリエ変換について調べてみる。<br>
![image](https://user-images.githubusercontent.com/25688193/43701475-405abe00-9991-11e8-9a12-e64a477785e3.png)<br>
両辺を k で微分すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43701621-d23a3bfc-9991-11e8-9e00-6647f3d28ce2.png)<br>
この式は、F(k)  に関しての微分方程式になっており、その解は<br>
![image](https://user-images.githubusercontent.com/25688193/43708914-7eb4582c-99a6-11e8-8d67-8721d00a49ae.png)<br>
となる。（計算略）<br>
ここで、F(0) は、k=0 のときの値で β に依存し<br>
![image](https://user-images.githubusercontent.com/25688193/43708969-9e5617ec-99a6-11e8-8ad0-4c66fdf94ea2.png)<br>
従って、両式を比較すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43709046-ce7455d8-99a6-11e8-8c26-c1757e8a9646.png)<br>
この微分方程式の解は、<br>
![image](https://user-images.githubusercontent.com/25688193/43709071-ddac5424-99a6-11e8-8a91-26b2c7fc18ef.png)<br>

次に、パーシバルの等式 ![image](https://user-images.githubusercontent.com/25688193/43747554-933cd2b8-9a25-11e8-86ef-912f0bf1c10a.png) に、ガウス関数の f(t) と先の ![image](https://user-images.githubusercontent.com/25688193/43747563-a9389e1c-9a25-11e8-81e4-8894b96ee7f4.png) を代入すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43747571-bed68630-9a25-11e8-8ce5-d933e0e5613a.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43747585-d266b472-9a25-11e8-8eba-b6c1c9a056c1.png) の関係より、上式は、<br>
![image](https://user-images.githubusercontent.com/25688193/43747603-e9289338-9a25-11e8-9f66-2d108b4498b8.png)<br>
よって、<br>
![image](https://user-images.githubusercontent.com/25688193/43747630-1adaa8c6-9a26-11e8-9257-d94680ca1502.png)<br>
となり、<br>
![image](https://user-images.githubusercontent.com/25688193/43747650-3649c10a-9a26-11e8-9da0-f42a6781341f.png)<br>
が成り立つ。<br>

---

<a id="ID_6"></a>

## ■ 偏微分方程式への応用
ここでは、偏微分方程式の例として熱伝導方程式を扱い、<br>
偏微分方程式の解法にフーリエ級数やフーリエ変換がどのように利用されるのかを見ていく。<br>


<a id="ID_6-1"></a>

### ◎ 一定の長さのリング状の棒での熱伝導方程式
熱伝導方程式は、以下のような偏微分方程式で表現される方程式である。<br>
![image](https://user-images.githubusercontent.com/25688193/43776161-f462cdfe-9a89-11e8-82ff-20a79e97ca44.png)<br>
ここで、初期状態として、t=0 における温度分布を f(x) とする。<br>
即ち、![image](https://user-images.githubusercontent.com/25688193/43776214-19ae2a0e-9a8a-11e8-975a-6b147a43ac26.png) であるとする。<br>

まず初めに、下図のように長さ L のリング状の細い棒での熱伝導現象を取り扱う。<br>
![image](https://user-images.githubusercontent.com/25688193/43776234-2d5493a4-9a8a-11e8-9d17-2e5826aa06bf.png)<br>

このとき、棒のリング状に沿った座標系を x とすると、<br>
棒の長さ L でリングを一周するので、![image](https://user-images.githubusercontent.com/25688193/43776477-fb72d048-9a8a-11e8-8b14-cacea93cddb3.png) は同じ点となり、<br>
境界条件として、<br>
![image](https://user-images.githubusercontent.com/25688193/43776654-73da9dcc-9a8b-11e8-867d-7cc7127f3757.png)<br>
が成り立つ。（周期的境界条件）<br>

この解 u(x,t) と初期分布 f(x) の周期性に着目し、フーリエ級数を利用することを考える。<br>
解 u(x,t) をフーリエ級数展開すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43776991-789c1006-9a8c-11e8-9ce4-a881d40ed431.png)<br>
※ u(x,t) が t にも依存することを反映して、フーリエ係数 ![image](https://user-images.githubusercontent.com/25688193/43777024-95200f3e-9a8c-11e8-843f-70a820e7eb30.png) も t の関数になっている。<br>

このフーリエ級数を、元の熱伝導方程式に代入し項別の偏微分を計算すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43806688-faffe128-9adf-11e8-9d8e-c7cbcd00c238.png)<br>
両辺に cos⁡(2mπx/L) をかけて、x=0~L の範囲で積分すると、<br>
![image](https://user-images.githubusercontent.com/25688193/43806709-15403060-9ae0-11e8-9276-d6383e9a3c0b.png)<br>
ここで、直交性条件<br>
![image](https://user-images.githubusercontent.com/25688193/43806739-34d394d0-9ae0-11e8-8b1f-d314e0578992.png)<br>
より、<br>
![image](https://user-images.githubusercontent.com/25688193/43806767-4e281b40-9ae0-11e8-8b91-eaaa3ad9bf00.png)<br>
この微分方程式は、微分しても解が変わらないので、指数関数となり、<br>
![image](https://user-images.githubusercontent.com/25688193/43806795-7403891c-9ae0-11e8-9a34-0a31ea4552b8.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43806823-8c812044-9ae0-11e8-9171-731a915a12e5.png) に関しても同様にして、両辺に sin⁡(2mπx/L) をかけて、x=0~L の範囲で積分し、計算すると（途中計算略）<br>
![image](https://user-images.githubusercontent.com/25688193/43806849-a3a25216-9ae0-11e8-8646-1cb26cd92649.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43807002-6f4d123e-9ae1-11e8-964f-2cb97fcd78a6.png) に関しては、両辺をそのまま x=0~L の範囲で積分し、計算すると（途中計算略）<br>
![image](https://user-images.githubusercontent.com/25688193/43807019-807dd26e-9ae1-11e8-8019-0cacc18d1a2c.png)<br>
これらの結果を代入すると、熱伝導方程式の特殊解は、<br>
![image](https://user-images.githubusercontent.com/25688193/43807183-3da0cee6-9ae2-11e8-8616-503284590ab4.png)<br>
![image](https://user-images.githubusercontent.com/25688193/43807401-377f2034-9ae3-11e8-8a13-85142f40596c.png)<br>

この特殊解は、境界条件を考慮した先の熱伝導方程式の解であるが、初期条件を考慮してないので、初期条件を満たすように係数の値を設定する。<br>
![image](https://user-images.githubusercontent.com/25688193/43807583-18cf79d0-9ae4-11e8-86ef-e504526689a2.png)<br>
この式は、周期 L の周期関数 f(x) フーリエ級数展開の式になっているので、フーリエ係数の値は、<br>
![image](https://user-images.githubusercontent.com/25688193/43807621-47293cc6-9ae4-11e8-9020-141d53a9f6b3.png)<br>
従って、初期条件の関数 f(x)  の形が具体的に与えられれば、フーリエ係数は求まり、境界条件と初期条件を満たす特殊解が求まる。<br>


<a id="ID_6-2"></a>

### ◎ 無限に長い棒での熱伝導方程式
先の熱伝導方程式では、長さ L のリング状の棒での熱伝導方程式を考えたが、この条件が周期性をもつために、フーリエ級数展開を利用できた。<br>
次に、無限に長い棒での熱伝導方程式のような **（周期性を持たない）無限領域を考える。このような場合には、フーリエ変換が利用できる。**<br>

