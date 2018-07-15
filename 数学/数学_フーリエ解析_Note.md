# フーリエ解析

## 目次 [Contents]

1. [概要](#ID_1)
1. [フーリエ級数展開](#ID_2)
1. xxx

---

<a id="ID_2"></a>

## ■ フーリエ級数展開 [Fourier series]
フーリエ級数展開 ![image](https://user-images.githubusercontent.com/25688193/42722784-4ed96e1a-878d-11e8-889e-2832b4435f68.png) の式<br>
![image](https://user-images.githubusercontent.com/25688193/42722854-72e0913e-878e-11e8-8bec-efc04726ed1d.png)<br>
の係数 ![image](https://user-images.githubusercontent.com/25688193/42722787-5ff7fe00-878d-11e8-9933-88c9692916a4.png) を求める。<br>

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

- （例）![image](https://user-images.githubusercontent.com/25688193/42732080-437672d4-8855-11e8-9d45-722e499e0bcd.png) をフーリエ級数展開の式で表す。<br>

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