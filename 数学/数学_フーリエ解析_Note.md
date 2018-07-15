# フーリエ解析

## 目次 [Contents]

1. [概要](#ID_1)
1. [フーリエ級数展開](#ID_2)
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



