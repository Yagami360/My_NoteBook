# 統計学 [statistics] / 統計解析 [statistical analysis]

統計解析に関してのまとめた⚡マイノートです。今後も随時追加予定。

This is my notebook that summarizes about "statistical analysis". I will add contents as needed.

> Twitterモーメント：https://twitter.com/i/moments/781976867125420033
>> ![twitter_ _ _161001](https://user-images.githubusercontent.com/25688193/29314888-0d233a34-81fb-11e7-8168-7810725fee78.png)

## 項目 [Contents]
1. [概要 [Overview]、全体 MAP](#ID_1)
1. [統計量](#ID_2)
    1. [データ分布の中心的傾向を表す統計量](#ID_2-1)
        1. [平均値 [mean]](#ID_2-1-1)
    1. [データ分布の広がり具合（バラツキ）を表す量](#ID_2-2)
        1. [分散値 [variance]](#ID_2-2-1)
        1. [標準偏差 [standard deviation]](#ID_2-2-2)
        1. [不偏分散（母分散の不偏な推定量）[unbiased estimate of population variance]](#ID_2-2-3)
        1. [共分散 [covariance]](#ID_2-2-4)
    1. [その他の統計量](#ID_2-3)
        1. [自由度 [degree of freedom]](#ID_2-3-1)
        1. [相関係数 [correlation coefficient]](#ID_2-3-2)
            1. [相関係数の式の意味](#ID_2-3-2-1)
        1. [重相関係数 [multiple correlation coefficient]](#ID_2-3-3)
        1. [偏相関係数 [partial correlation coefficient]](#ID_2-3-4)
        1. [決定係数 [coefficient of determination]（寄与率 [contribution]）](#ID_2-3-5)
        1. [モーメント](#ID_2-3-6)
1. [確率 [probability]](#ID_3)
1. [確率分布 [probability distribution]](#ID_4)
    1. [離散化](#ID_4-1)
    1. [連続型](#ID_4-2)
    1. [変数変換した変数の確率分布](#ID_4-3)
    1. [多変量の確率分布](#ID_4-4)
    1. [正規分布](#ID_4-5)
        1. [正規分布に関しての重要な命題](#ID_4-5-1)
        1. [正規分布の再生性](#ID_4-5-2)
    1. [Χ（カイ）２乗分布](#ID_4-6)
        1. [Χ（カイ）２乗分布に関しての重要な命題](#ID_4-6-1)
    1. [F 分布](#ID_4-7)
        1. [F 分布に関しての重要な命題（その１）](#ID_4-7-1)
        1. [F 分布に関しての重要な命題（その２）](#ID_4-7-2)
    1. [t（タウ）分布](#ID_4-8)
        1. [t（タウ）分布に関しての重要な命題（その２）](#ID_4-8-1)
1. [区間推定 [interval estimation]](#ID_5)
    1. [母集団が既値のときの母平均の推定（※但し、母平均は正規分布しているとする。）](#ID_5-1)
    1. [母集団が未知のときの母平均の推定（※但し、母平均は正規分布しているとする。）](#ID_5-2)
        1. [F 分布の命題を使う方法](#ID_5-2-1)
        1. [t 分布の命題を使う方法](#ID_5-2-2)
    1. [母分散の推定（※但し、母平均は正規分布しているとする。）](#ID_5-3)
1. [仮説検定](#ID_6)
    1. [帰無仮説と対立仮説](#ID_6-1)
    1. [母数の検定](#ID_6-2)
        1. [母分散が既知のときの母平均の検定（但し、母集団は正規分布しているとする。）](#ID_6-2-1)
        1. [母分散が未知のときの母平均の検定【t検定】（但し、母集団は正規分布しているとする。）](#ID_6-2-2)
1. [参考文献](#参考文献)

- 追記予定項目
    - 各種統計量
    - 各種離散分布関数（２項分布、ポアソン分布等）

<a id="ID_1"></a>

## 概要 [Overview]、全体 MAP
![1_160701](https://user-images.githubusercontent.com/25688193/29314896-169f1182-81fb-11e7-90d6-0eec4478b0cf.jpg)


<a id="ID_2"></a>

## 統計量

<a id="ID_2-1"></a>

### データ分布の中心的傾向を表す統計量

<a id="ID_2-1-1"></a>

#### 平均値 [mean]
![image](https://user-images.githubusercontent.com/25688193/30419800-a1fd870c-9972-11e7-8afc-4b2ba7b44e10.png)

<a id="ID_2-2"></a>

### データ分布の広がり具合（バラツキ）を表す量

<a id="ID_2-2-1"></a>

#### 分散値 [variance]
![image](https://user-images.githubusercontent.com/25688193/30420695-5c61a0ae-9975-11e7-9a37-eea792e732bd.png)

<a id="ID_2-2-2"></a>

#### 標準偏差 [standard deviation]
![image](https://user-images.githubusercontent.com/25688193/30420779-a3b89dae-9975-11e7-9665-02e66c0c4e4e.png)

<a id="ID_2-2-3"></a>

#### 不偏分散（母分散の不偏な推定量）[unbiased estimate of population variance]
![image](https://user-images.githubusercontent.com/25688193/30420841-d6cf03fe-9975-11e7-8d0d-5743bf01dd12.png)

<a id="ID_2-2-4"></a>

#### 共分散 [covariance]
![image](https://user-images.githubusercontent.com/25688193/30420920-10332b70-9976-11e7-98aa-f87d68f4849e.png)

<a id="ID_2-3"></a>

### その他の統計量

<a id="ID_2-3-1"></a>

#### 自由度 [degree of freedom]
![image](https://user-images.githubusercontent.com/25688193/30421061-93c76cb2-9976-11e7-8d95-2a0987f63d4f.png)

<a id="ID_2-3-2"></a>

#### 相関係数 [correlation coefficient]
![image](https://user-images.githubusercontent.com/25688193/30421120-bf1c45d6-9976-11e7-9052-e9d04dc4a0ab.png)

<a id="ID_2-3-2-1"></a>

##### 相関関係の式の意味
![image](https://user-images.githubusercontent.com/25688193/30421403-a0d7853a-9977-11e7-86ea-3f952a5711b4.png)
![image](https://user-images.githubusercontent.com/25688193/30421464-cacf54b2-9977-11e7-8256-f183ec06829b.png)


<a id="ID_2-3-3"></a>

#### 重相関係数 [multiple correlation coefficient]
> 記載中...
重回帰式によって求まる、予想値と実際のデータのとの間の相関係数


<a id="ID_2-3-4"></a>

#### 偏相関係数 [partial correlation coefficient]
> 記載中...

<a id="ID_2-3-5"></a>

#### 決定係数 [coefficient of determination]（寄与率 [contribution]）
回帰式がどのくらいデータを要約しているかの指標

<a id="ID_2-3-6"></a>

#### モーメント
![image](https://user-images.githubusercontent.com/25688193/30421538-0a09188e-9978-11e7-8639-40381f3a5312.png)



<a id="ID_3"></a>

## 確率 [probability]
![3_160703](https://user-images.githubusercontent.com/25688193/29314975-98ba100e-81fb-11e7-8db8-932f38c57e6e.jpg)

<a id="ID_4"></a>

## 確率分布 [probability distribution]

<a id="ID_4-1"></a>

### 離散型
![image](https://user-images.githubusercontent.com/25688193/30421578-310a7d06-9978-11e7-95ab-1ee8203f0308.png)

<a id="ID_4-2"></a>

### 連続型
![image](https://user-images.githubusercontent.com/25688193/30421606-450ef926-9978-11e7-8749-ee2e5a103dc7.png)

<a id="ID_4-3"></a>

### 変数変換した変数の確率分布
![image](https://user-images.githubusercontent.com/25688193/30422143-04e68f88-997a-11e7-9152-ab0121590634.png)


<a id="ID_4-4"></a>

### 多変量の確率分布
![twitter_ _10_160708](https://user-images.githubusercontent.com/25688193/29317405-c5164ca2-8206-11e7-8581-6aaeb21acf2b.jpg)
![twitter_ _11_160708](https://user-images.githubusercontent.com/25688193/29317406-c518f394-8206-11e7-8e1a-ffa341dca2d6.jpg)

<a id="ID_4-5"></a>

#### 正規分布
![image](https://user-images.githubusercontent.com/25688193/30422226-4b070ae2-997a-11e7-9b26-75761c09d117.png)
![image](https://user-images.githubusercontent.com/25688193/30422264-6408023a-997a-11e7-8226-1c863cf2ca04.png)

<a id="ID_4-5-1"></a>

##### 正規分布に関しての重要な命題
![image](https://user-images.githubusercontent.com/25688193/30422300-81a7102e-997a-11e7-8a23-7099528d7506.png)

<a id="ID_4-5-2"></a>

##### 正規分布の再生性
> 記載中....



<a id="ID_4-6"></a>

#### Χ（カイ）２乗分布
![image](https://user-images.githubusercontent.com/25688193/30422690-a90b1934-997b-11e7-845d-6cb1d4c5a94c.png)
![image](https://user-images.githubusercontent.com/25688193/30422738-cd1fd396-997b-11e7-89d8-17c57cac7a2e.png)
![image](https://user-images.githubusercontent.com/25688193/30422773-e3775934-997b-11e7-8559-85dcf87e7676.png)

<a id="ID_4-6-1"></a>

#### Χ（カイ）２乗分布に関しての重要な命題
![image](https://user-images.githubusercontent.com/25688193/30422817-05ecc774-997c-11e7-8007-28f9f5b4a2ec.png)
![image](https://user-images.githubusercontent.com/25688193/30422984-726c0fc2-997c-11e7-86d4-efc7c2ff05aa.png)
![image](https://user-images.githubusercontent.com/25688193/30423037-9f4b0610-997c-11e7-91fa-ff9cdd99dcd1.png)
![image](https://user-images.githubusercontent.com/25688193/30423067-b57dcabc-997c-11e7-86cd-af2127ac1075.png)
![image](https://user-images.githubusercontent.com/25688193/30423143-f03b7f78-997c-11e7-80fd-bc7ec12a72d6.png)


<a id="ID_4-7"></a>

#### F 分布
![twitter_ _12_160708](https://user-images.githubusercontent.com/25688193/29317462-042d4db4-8207-11e7-8658-2e20b3838c49.jpg)

<a id="ID_4-7-1"></a>

#### F 分布に関しての重要な命題（その１）
![image](https://user-images.githubusercontent.com/25688193/30423317-761a3c74-997d-11e7-80ba-f381c2fd2171.png)
![image](https://user-images.githubusercontent.com/25688193/30423379-9d3317fe-997d-11e7-9cab-c1bf2778e72c.png)

<a id="ID_4-7-2"></a>

#### F 分布に関しての重要な命題（その２）
![twitter_ _14_160708](https://user-images.githubusercontent.com/25688193/29317464-0453695e-8207-11e7-8aae-7ed322a7a0cd.jpg)


<a id="ID_4-8"></a>

#### t（タウ）分布
![twitter_ _t _1-1_170815](https://user-images.githubusercontent.com/25688193/29317935-1d67232a-8209-11e7-8cd2-ddea3dd60a00.png)

<a id="ID_4-8-1"></a>

#### t（タウ）分布に関しての重要な命題
![twitter_ _t _1-2_170815](https://user-images.githubusercontent.com/25688193/29317934-1d60a928-8209-11e7-94db-3cbd9ce32bfc.png)



<a id="ID_5"></a>

## 区間推定
![twitter_ _ _1-1_170815](https://user-images.githubusercontent.com/25688193/29317950-25d9907e-8209-11e7-9218-e23be97788db.png)
![twitter_ _ _1-2_170815](https://user-images.githubusercontent.com/25688193/29317949-25d814e2-8209-11e7-96a5-67b0d41b0048.png)
![twitter_ _ _1-3_170815](https://user-images.githubusercontent.com/25688193/29317952-25dc0fac-8209-11e7-859e-b105accf4175.png)
![twitter_ _ _1-4_170815](https://user-images.githubusercontent.com/25688193/29317948-25d51396-8209-11e7-96cc-9a73c1c9fd9b.png)
![twitter_ _ _1-5_170815](https://user-images.githubusercontent.com/25688193/29317951-25daa4f0-8209-11e7-95e3-f14a4a512574.png)



<a id="ID_6"></a>

## 仮説検定
![twitter_ _ _1-1_170815](https://user-images.githubusercontent.com/25688193/29318007-5a1e9852-8209-11e7-93b1-89dac30beeb3.png)
![twitter_ _ _1-2_170815](https://user-images.githubusercontent.com/25688193/29318006-5a1b5b38-8209-11e7-8e91-1cf299d37e32.png)
![twitter_ _ _1-3_170815](https://user-images.githubusercontent.com/25688193/29318008-5a22489e-8209-11e7-92d5-3479efc066fe.png)




<a name="参考文献"></a>

## 参考文献

> Excelで学ぶ多変量解析―資料に隠れた大切な関係は多変量解析を駆使してあぶり出す! 
>> [amazonで探す](https://www.amazon.co.jp/Excel%E3%81%A7%E5%AD%A6%E3%81%B6%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90%E2%80%95%E8%B3%87%E6%96%99%E3%81%AB%E9%9A%A0%E3%82%8C%E3%81%9F%E5%A4%A7%E5%88%87%E3%81%AA%E9%96%A2%E4%BF%82%E3%81%AF%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90%E3%82%92%E9%A7%86%E4%BD%BF%E3%81%97%E3%81%A6%E3%81%82%E3%81%B6%E3%82%8A%E5%87%BA%E3%81%99-%E6%B6%8C%E4%BA%95-%E8%89%AF%E5%B9%B8/dp/481633968X)

> 統計基礎用語集（和英編）
>> http://www.qmss.jp/qmss/glossary/stat-glossary-je.htm
