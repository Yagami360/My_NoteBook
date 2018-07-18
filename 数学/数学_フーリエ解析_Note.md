# フーリエ解析

## 目次 [Contents]

1. [概要](#ID_1)
1. [フーリエ級数展開](#ID_2)
    1. [フーリエ係数の意味](#ID_2-1)
    1. [フーリエ級数の収束性](#ID_2-2)
    1. [xxx](#ID_2-x)
1. xxx

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

- （性質）<br>
	周期 T の周期関数 ![image](https://user-images.githubusercontent.com/25688193/42734575-553295f8-8881-11e8-8ec4-84713313acaf.png) は、必ず、同じ周期 T をもつ偶関数 ![image](https://user-images.githubusercontent.com/25688193/42734587-7d9675d2-8881-11e8-86d9-87607425a184.png) と奇関数 ![image](https://user-images.githubusercontent.com/25688193/42734591-901b46ba-8881-11e8-95db-419d5e078ca8.png) の和、<br>
	即ち、![image](https://user-images.githubusercontent.com/25688193/42734599-ab9aff70-8881-11e8-8426-aa2055cd246d.png) で記述できる。<br>
    <br>
    （証明）<br>
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
![image](https://user-images.githubusercontent.com/25688193/42897453-080f597e-8afb-11e8-8146-caddd32dbd66.png)<br>

- t>0 で t=0 付近の拡大図（N=2,5,20,40,70,100）<br>
![image](https://user-images.githubusercontent.com/25688193/42897496-25de0cb6-8afb-11e8-8d49-717c430f4823.png)<br>

図からわかるように、不連続点である t=0 での ![image](https://user-images.githubusercontent.com/25688193/42906446-1eb0965a-8b16-11e8-9069-0ab0c860672e.png) の値が、N の増加と共に、1/2(=0.5) の値に近づいていることが分かる。<br>
ここで、この 1/2(=0.5) という値は、t の値が正→0 に近づいていく極限での f(t) の値を意味する f(0+0)=0 と、t の値が負→0 に近づいていく極限での f(t) の値を意味する f(0−0)=0 との平均値となっている。<br>

このような性質は、この例に限らず一般的にも成り立ち、以下のように表すことが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/42906841-2604059e-8b17-11e8-8a2b-7e0a93b2fc67.png)<br>