# 多変数解析 [multivariate analysis]

多変数解析に関してまとめたマイノートです。今後も随時追加予定です。

This is my notebook that summarizes about "multivariate analysis". I will add contents as needed.

> Twitterモーメント：https://twitter.com/i/moments/781977273268174849
>> ![twitter_ _ _161001](https://user-images.githubusercontent.com/25688193/29314888-0d233a34-81fb-11e7-8168-7810725fee78.png)

## 項目 [Contents]
1. [概要 [Overview]、全体 MAP](#ID_1)
1. [回帰分析 [regression analysis]](#ID_2)
    1. [相関係数 [correlation coefficient] について](#ID_2-1)
    1. [単回帰分析 [simple regression analysis]](#ID_2-2)
        1. [最小２乗法](#ID_2-2-1)
        1. [決定係数（寄与率）](#ID_2-2-2)
            1. [なぜ２乗か？](#ID_2-2-2-1)
    1. [重回帰分析 [multiple regression analysis]](#ID_2-3)
        1. [最小２乗法](#ID_2-3-1)
        1. [偏回帰係数](#ID_2-3-2)
        1. [重相間係数](#ID_2-3-3)
        1. [決定変数（寄与率）](#ID_2-3-4)
    1. [数量化理論I類](#ID_2-4)
1. [主成分分析 [principal component analysis（PCA）]](#ID_3)
    1. [固有方程式](#ID_3-x)
    1. [固有値、固有ベクトルと主成分](#ID_3-x)    
    1. [寄与率](#ID_3-x)
    1. [累積蓄積率](#ID_3-x)
1. [因子分析](#ID_4)
    1. [因子負荷行列Aの推定](#ID_4-1)
    1. [主因子法（PFA：Principal Factor Analysis）](#ID_4-2)
1. [判別分析](#ID_5)
    1. [Mahalanobisの距離による判別](#ID_5-1)
        1. [２変数の場合](#ID_5-1-1)
        1. [一般のの場合](#ID_5-1-2)    
    1. [判別関数による判別](#ID_5-2)
    1. [数量化理論Ⅱ類（数量化 II 類）](#ID_5-3)
1. [クラスター分析（階層）](#ID_6)
    1. [近さを測る量、つまり距離の定義とその性質](#ID_6-1)
        1. [ユークリッド距離](#ID_6-1-x)
        1. [ユークリッド距離の２乗](#ID_6-1-x)
        1. [マハラノビスの距離](#ID_6-1-x)
        1. [ミンコフスキー距離](#ID_6-1-x)
    1. [クラスター間の距離のとり方](#ID_6-2)
        1. [最短距離法](#ID_6-2-x)
        1. [最長距離法](#ID_6-2-x)
        1. [重心法](#ID_6-2-x)
        1. [メディアン法](#ID_6-2-x)
        1. [群平均法](#ID_6-2-x)
        1. [ウォード法](#ID_6-2-x)
    1. [クラスター分析の手段](#ID_6-3)
1. [](#ID_x)
1. [](#ID_x)
1. [](#ID_x)
1. [](#ID_x)
1. [参考文献](#参考文献)

- 追記予定項目
    - ポートフォリオ分析


<a id="ID_1"></a>

## 概要 [Overview]、全体 MAP
![image](https://user-images.githubusercontent.com/25688193/30424070-b91cadfc-997f-11e7-9d7a-6b4edb562731.png)

<a id="ID_2"></a>

## 回帰分析 [regression analysis]
![twitter_ _ _1-1_160711](https://user-images.githubusercontent.com/25688193/29316760-1ca0f07e-8204-11e7-8aad-b328c6d7e649.jpg)

<a id="ID_2-1"></a>

### 相関係数 [correlation coefficient] について
![twitter_ _ _1-1_170815](https://user-images.githubusercontent.com/25688193/29317049-46e2511a-8205-11e7-84f9-74e0a36300db.png)
![twitter_ _ _1-2_170815](https://user-images.githubusercontent.com/25688193/29317050-46e29f4e-8205-11e7-834d-3506bbd6fe57.png)

<a id="ID_2-2"></a>

### 単回帰分析 [simple regression analysis]
![twitter_ _ _1-1_170815](https://user-images.githubusercontent.com/25688193/29317069-55e460c2-8205-11e7-8e12-28778ac2a166.png)
![twitter_ _ _1-2_170815](https://user-images.githubusercontent.com/25688193/29317067-55e0d402-8205-11e7-86f4-ef4405c360e5.png)
![twitter_ _ _1-3_170815](https://user-images.githubusercontent.com/25688193/29317071-55e8f894-8205-11e7-8c58-86e683231e98.png)
![twitter_ _ _1-4_170815](https://user-images.githubusercontent.com/25688193/29317070-55e746b6-8205-11e7-9b9f-0b8517cbb754.jpg)
![twitter_ _ _1-5_170815](https://user-images.githubusercontent.com/25688193/29317066-55df1f72-8205-11e7-8140-23273439886f.jpg)

<a id="ID_2-3"></a>

### 重回帰分析 [multiple regression analysis]
![twitter_ _ _1-1_170815](https://user-images.githubusercontent.com/25688193/29317097-76220484-8205-11e7-91ee-90a8871f9347.png)
![twitter_ _ _1-2_170815](https://user-images.githubusercontent.com/25688193/29317099-7625b3ea-8205-11e7-9d66-0291bff4ba8a.png)
![twitter_ _ _1-3_170815](https://user-images.githubusercontent.com/25688193/29317098-76236e00-8205-11e7-9802-a784786d3e8d.png)
![twitter_ _ _1-4_170815](https://user-images.githubusercontent.com/25688193/29317100-76274430-8205-11e7-95e9-1909250b1940.png)
![twitter_ _ _1-5_170815](https://user-images.githubusercontent.com/25688193/29317096-7621b84e-8205-11e7-918c-084cf43e292c.jpg)

<a id="ID_2-4"></a>

### 数量化理論Ⅰ類
![twitter_ _ _1-1_160703](https://user-images.githubusercontent.com/25688193/29316694-e93505fe-8203-11e7-8366-8f4beed1f575.jpg)


<a id=ID_3></a>

## 主成分分析（PCA）

![twitter_ _ 1-1_161209](https://user-images.githubusercontent.com/25688193/29316377-cbf8a6ae-8202-11e7-8e71-e91ccfb1f9c1.png)
![twitter_ _ 1-2_161209](https://user-images.githubusercontent.com/25688193/29316375-cbf7d06c-8202-11e7-88c8-3e3c141152c6.png)
![twitter_ _ 1-3_161209](https://user-images.githubusercontent.com/25688193/29316379-cc0365bc-8202-11e7-853b-3d0fd770090c.png)
![twitter_ _ 1-4_161209](https://user-images.githubusercontent.com/25688193/29316376-cbf80a28-8202-11e7-8fa4-c3b20104f900.png)
![twitter_ _ 1-5_161209](https://user-images.githubusercontent.com/25688193/29316378-cbf91e18-8202-11e7-9b8a-17a4fcf7b084.png)
![twitter_ _ 1-6_161209](https://user-images.githubusercontent.com/25688193/29316380-cc18fe4a-8202-11e7-9af5-a407a60d95ae.png)
![twitter_ _ 1-7_161209](https://user-images.githubusercontent.com/25688193/29316384-cc2d3662-8202-11e7-802f-e381df1a15be.png)
![twitter_ _ 1-8_161209](https://user-images.githubusercontent.com/25688193/29316381-cc1a6c3a-8202-11e7-97ec-5a03a6e8225a.png)
![twitter_ _ 1-9_161209](https://user-images.githubusercontent.com/25688193/29316383-cc1cb81e-8202-11e7-8817-b1c8836e1b90.png)
![twitter_ _ 1-10_161209](https://user-images.githubusercontent.com/25688193/29316382-cc1c6a4e-8202-11e7-88d0-8f90f5e1c13e.png)


<a id=ID_4></a>

## 因子分析

![twitter_](https://user-images.githubusercontent.com/25688193/29316431-0781f2e8-8203-11e7-95bd-b6f49bca448b.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316430-077c29da-8203-11e7-8457-4e5cfee00644.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316432-078d52e6-8203-11e7-81d8-6f47b1d1c0f0.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316433-07901710-8203-11e7-8de5-e8941491a026.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316434-0792adae-8203-11e7-99e1-b5ad8c38801c.png)


<a id=ID_5></a>

## 判別分析

![twitter_ 1](https://user-images.githubusercontent.com/25688193/29316461-28fca83c-8203-11e7-8f09-15005f352a42.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316460-28f4086c-8203-11e7-8a85-960629f04e38.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316463-290caebc-8203-11e7-87eb-dbd412ab7da4.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316464-290cae44-8203-11e7-9a75-3f96ced90568.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316462-2906a4fe-8203-11e7-92a4-afe49ecb9014.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316465-290d20c2-8203-11e7-98ee-898e66774a19.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316466-291e5874-8203-11e7-9c41-2dd50cde5f94.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316467-292f4332-8203-11e7-95ab-384038a74769.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316469-2936c4c2-8203-11e7-9531-c890ccc3c3fc.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316470-293a9b7e-8203-11e7-87ac-60cb07f53a98.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316468-293173b4-8203-11e7-8f60-0a9bd12417ea.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316471-293e2dc0-8203-11e7-9dd1-eebcbf5dc8f7.png)
![twitter_](https://user-images.githubusercontent.com/25688193/29316472-294a35ac-8203-11e7-9611-304b68d97cc1.png)

![twitter_ _](https://user-images.githubusercontent.com/25688193/29316491-355398ca-8203-11e7-9668-821ba897b5aa.png)
![twitter_ _](https://user-images.githubusercontent.com/25688193/29316498-39396474-8203-11e7-91f4-d3c1c2c7cb39.png)

<a id=ID_5-3></a>

### 数量化理論Ⅱ類
![twitter_ _160825](https://user-images.githubusercontent.com/25688193/29316554-719610b0-8203-11e7-9d35-a2845071b5c7.png)



<a id=ID_6></a>

## クラスター分析
![twitter_ _160825](https://user-images.githubusercontent.com/25688193/29316564-7d1eddcc-8203-11e7-8bf4-d1a7127b2845.png)
![twitter_ _160825](https://user-images.githubusercontent.com/25688193/29316562-7d1c1efc-8203-11e7-9ec0-5fb9a8944805.png)
![twitter_ _160825](https://user-images.githubusercontent.com/25688193/29316563-7d1ddfb2-8203-11e7-9924-331bb273b271.png)
![twitter_ _160825](https://user-images.githubusercontent.com/25688193/29316565-7d1f4136-8203-11e7-9328-7f0fbb5ebaaa.png)
![twitter_ _160825](https://user-images.githubusercontent.com/25688193/29316566-7d212e92-8203-11e7-86a2-18b35fd33b06.png)





<a name="参考文献"></a>

## 参考文献

> Excelで学ぶ多変量解析―資料に隠れた大切な関係は多変量解析を駆使してあぶり出す! 
>> [amazonで探す](https://www.amazon.co.jp/Excel%E3%81%A7%E5%AD%A6%E3%81%B6%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90%E2%80%95%E8%B3%87%E6%96%99%E3%81%AB%E9%9A%A0%E3%82%8C%E3%81%9F%E5%A4%A7%E5%88%87%E3%81%AA%E9%96%A2%E4%BF%82%E3%81%AF%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90%E3%82%92%E9%A7%86%E4%BD%BF%E3%81%97%E3%81%A6%E3%81%82%E3%81%B6%E3%82%8A%E5%87%BA%E3%81%99-%E6%B6%8C%E4%BA%95-%E8%89%AF%E5%B9%B8/dp/481633968X)

> 統計基礎用語集（和英編）
>> http://www.qmss.jp/qmss/glossary/stat-glossary-je.htm
