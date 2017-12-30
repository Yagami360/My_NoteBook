# 自然言語処理 [NLP : natural language processing]

自然言語処理（NLP）に関してのマイノートです。<br>
特に、ニューラルネットワーク、ディープラーニングによる自然言語処理（NLP）を重点的に取り扱っています。<br>
今後も随時追加予定です。<br>

尚、ニューラルネットワークに関しては、以下の記事に記載しています。

- [星の本棚（ニューラルネットワーク）](http://yagami12.hatenablog.com/entry/2017/09/17/111935#ID_10-4-3)

又、より一般的な機械学習に関しては、以下の記事に記載しています。

- [星の本棚（機械学習）](hhttp://yagami12.hatenablog.com/entry/2017/09/17/111400)

## 目次 [Contents]
1. [自然言語処理（NLP）](#ID_10)
    1. one-hot encode と one-hot ベクトル    
    1. [埋め込みベクトル [embedding vector] と埋め込み行列 [embedding matrix]](#ID_10-2)
    1. [言語モデル [LM : Language model]](#ID_10-3)
        1. N グラム言語モデル
        1. [ニューラル言語モデル [NLM : Neural Language Model]](#ID_10-3-2)
            1. [順伝播型ニューラル言語モデル（FFNN-LM）](#ID_10-3-2-1)
            1. [再帰ニューラル（RNN）言語モデル [RNN-LM]](#ID_10-3-2-2)
        1. 言語モデルの評価
            1. パープレキシティ [PPL : Perplexity]
    1. [分散表現 [distributional / distributed]](#ID_10-4)
        1. [単語の分散表現、Word 単語埋め込み [Word Embeddings]](#ID_10-4-1)
        1. [単語の分散表現、Word 単語埋め込み [Word Embeddings] の具体的な獲得方法](#ID_10-4-2)
            1. [ニューラル言語モデルを用いた分散表現の獲得方法](#ID_10-4-2-1)
            1. [対数双線形モデルを用いた分散表現の獲得方法](#ID_10-4-2-2)
            1. [負例サンプリングを用いた分散表現の獲得方法](#ID_10-4-2-3)
        1. [word2vec ツール](#ID_10-4-3)
            1. [CBOW [Countinuous Bag-of-Words] モデル](#ID_10-4-3-1)
            1. [skip-gram モデル](#ID_10-4-3-2)

<a id="ID_10"></a>

## ニューラルネットワーク、ディープラーニングによる自然言語処理（NLP）

<a id="ID_10-1"></a>

<!--
### one-hot encode と one-hot ベクトル
> 記載中...
-->

<a id="ID_10-2"></a>

### 埋め込みベクトル [embedding vector] と埋め込み行列 [embedding matrix]
![image](https://user-images.githubusercontent.com/25688193/34094596-26e24d16-e411-11e7-95d3-1971133297c1.png)


<a id="ID_10-3"></a>

### 言語モデル [LM : Language model]
![image](https://user-images.githubusercontent.com/25688193/34341685-05559ffc-e9e0-11e7-8380-3a905352754c.png)
![image](https://user-images.githubusercontent.com/25688193/34341696-37917a36-e9e0-11e7-9281-efb5294dd58a.png)
![image](https://user-images.githubusercontent.com/25688193/34341814-cd99e62e-e9e2-11e7-8de5-a94fe5a6d2d2.png)
![image](https://user-images.githubusercontent.com/25688193/34342794-a5966640-e9fe-11e7-93dc-b9245c1a611e.png)
![image](https://user-images.githubusercontent.com/25688193/34342701-3cbea040-e9fb-11e7-9680-03e146549cc4.png)
![image](https://user-images.githubusercontent.com/25688193/34342734-b8146f80-e9fc-11e7-8fe4-ee99fd46cb87.png)


<a id="ID_10-3-1"></a>

<!--
### N グラム言語モデル
記載中...
-->

<a id="ID_10-3-2"></a>

### ニューラル言語モデル [NNLM : Neural network Language model ]

<a id="ID_10-3-2-1"></a>

#### 順伝播型ニューラル言語モデル（FFNN-LM）
![image](https://user-images.githubusercontent.com/25688193/34349562-19147962-ea55-11e7-9487-96780bed2a74.png)
![image](https://user-images.githubusercontent.com/25688193/34351744-e686df00-ea61-11e7-85dd-d32f73e1d589.png)
![image](https://user-images.githubusercontent.com/25688193/34355192-d80a567c-ea76-11e7-83c7-2b68388608dd.png)
![image](https://user-images.githubusercontent.com/25688193/34361963-788001ca-eab2-11e7-8985-1c24d2b1beb3.png)


<a id="ID_10-3-2-2"></a>

#### 再帰ニューラル言語モデル（RNN-LM）
![image](https://user-images.githubusercontent.com/25688193/34355245-34a868c4-ea77-11e7-95a4-4bf84dd09ae6.png)
![image](https://user-images.githubusercontent.com/25688193/34359181-1bb80866-ea99-11e7-9241-6e346425b392.png)
![image](https://user-images.githubusercontent.com/25688193/34355272-62e4239a-ea77-11e7-9ae0-62210d7509fc.png)
![image](https://user-images.githubusercontent.com/25688193/34362048-60889040-eab3-11e7-9996-f639a6bf5ead.png)


<a id="ID_10-4"></a>

### 分散表現 [distributional / distributed]
![image](https://user-images.githubusercontent.com/25688193/34366909-eee0f68e-eae5-11e7-8fe8-bd36d46f00f1.png)
![image](https://user-images.githubusercontent.com/25688193/34368672-000af334-eaf9-11e7-8425-c5acd7036701.png)
![image](https://user-images.githubusercontent.com/25688193/34368876-c70ae9c0-eafa-11e7-882d-bbf5b65b7352.png)
![image](https://user-images.githubusercontent.com/25688193/34369022-fa7eee86-eafb-11e7-94ae-8be2fe02f0b1.png)


<a id="ID_10-4-1"></a>

#### 単語の分散表現 [disturibute representation]、単語埋め込み [Word Embeddings]
![image](https://user-images.githubusercontent.com/25688193/34368756-ad274428-eaf9-11e7-8bc4-d68876b8027d.png)
![image](https://user-images.githubusercontent.com/25688193/34102231-ad432a1e-e42b-11e7-8aa2-12920b882ebd.png)
![image](https://user-images.githubusercontent.com/25688193/34108443-66e29466-e443-11e7-9145-bc1921e90498.png)

<a id="ID_10-4-2"></a>

#### 単語の分散表現、単語埋め込み [Word Embeddings] の具体的な獲得方法
![image](https://user-images.githubusercontent.com/25688193/34370735-ed89bd24-eb09-11e7-9732-bf39e23985c0.png)

<a id="ID_10-4-2-1"></a>

#### ニューラル言語モデルを用いた分散表現の獲得方法
![image](https://user-images.githubusercontent.com/25688193/34377024-6ab57900-eb32-11e7-993b-4b8a636a6c3c.png)
![image](https://user-images.githubusercontent.com/25688193/34377036-78a46562-eb32-11e7-8420-8c3e8967b3f8.png)
![image](https://user-images.githubusercontent.com/25688193/34377396-31308cfe-eb34-11e7-85b2-4d0cc615ce18.png)


<a id="ID_10-4-2-2"></a>

#### 対数双線形モデルを用いた分散表現の獲得方法
> 記載中...


<a id="ID_10-4-2-3"></a>

#### 負例サンプリングを用いた分散表現の獲得方法
> 記載中...


<a id="ID_10-4-3"></a>

### word2vec ツール
![image](https://user-images.githubusercontent.com/25688193/34443712-51ea6814-ed0c-11e7-9324-87056689bee8.png)

<a id="ID_10-4-3-1"></a>

#### CBOW [Countinuous Bag-of-Words] モデル
![image](https://user-images.githubusercontent.com/25688193/34443731-6cf88154-ed0c-11e7-9b94-75e065a4026d.png)
![image](https://user-images.githubusercontent.com/25688193/34443022-955317d4-ed09-11e7-8c2b-ceb4ebb0669e.png)
![image](https://user-images.githubusercontent.com/25688193/34441364-aaa8d606-ecfe-11e7-9909-34028aabc0ca.png)
![image](https://user-images.githubusercontent.com/25688193/34436963-c1059824-ecdd-11e7-8230-884cfb87113a.png)
![image](https://user-images.githubusercontent.com/25688193/34436979-cf35ab00-ecdd-11e7-9fc6-e1aab309fd57.png)
![image](https://user-images.githubusercontent.com/25688193/34441458-340083b8-ecff-11e7-8034-862f4cb58912.png)

<a id="ID_10-4-3-2"></a>

#### skip-gram モデル
- 参考サイト : http://tkengo.github.io/blog/2016/05/09/understand-how-to-learn-word2vec/

> 記載＆修正中...<br>
![image](https://user-images.githubusercontent.com/25688193/34443558-5b664f62-ed0b-11e7-85c5-95788e8cdd5f.png)
![image](https://user-images.githubusercontent.com/25688193/34444167-88e435c2-ed0f-11e7-82ee-ae6e6c7831f5.png)
![image](https://user-images.githubusercontent.com/25688193/34444399-4782fe36-ed11-11e7-918e-816c2f1ba9cd.png)
![image](https://user-images.githubusercontent.com/25688193/34444193-adb38092-ed0f-11e7-8ccd-c1fd1bbf41b4.png)



<br>

---

<a name="参考文献"></a>

## 参考文献

> 深層学習: Deep Learning</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%B7%B1%E5%B1%A4%E5%AD%A6%E7%BF%92-Deep-Learning-%E7%9B%A3%E4%BF%AE-%E4%BA%BA%E5%B7%A5%E7%9F%A5%E8%83%BD%E5%AD%A6%E4%BC%9A/dp/476490487X)

> 詳解 ディープラーニング ~ TensorFlow・Keras による時系列データ処理</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/exec/obidos/ASIN/4839962510/hikarus0sem0y-22/)<br>
>> 本書のレビュー記事 :<br> 
>> [【書籍紹介】詳解ディープラーニング TensorFlow・Kerasによる時系列データ処理](http://s0sem0y.hatenablog.com/entry/2017/06/25/025725)

> 深層学習による自然言語処理 (機械学習プロフェッショナルシリーズ) <br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%B7%B1%E5%B1%A4%E5%AD%A6%E7%BF%92%E3%81%AB%E3%82%88%E3%82%8B%E8%87%AA%E7%84%B6%E8%A8%80%E8%AA%9E%E5%87%A6%E7%90%86-%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%83%97%E3%83%AD%E3%83%95%E3%82%A7%E3%83%83%E3%82%B7%E3%83%A7%E3%83%8A%E3%83%AB%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E5%9D%AA%E4%BA%95-%E7%A5%90%E5%A4%AA/dp/4061529242)

> TensorFlow機械学習クックブック Pythonベースの活用レシピ60+</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/TensorFlow%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%82%AF%E3%83%83%E3%82%AF%E3%83%96%E3%83%83%E3%82%AF-Python%E3%83%99%E3%83%BC%E3%82%B9%E3%81%AE%E6%B4%BB%E7%94%A8%E3%83%AC%E3%82%B7%E3%83%9460-impress-top-gear/dp/4295002003?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4295002003)
>> 本書のレビュー記事 :<br> 
>> [【書籍紹介】TensorFlow機械学習クックブック](http://s0sem0y.hatenablog.com/entry/2017/09/08/005322)


---

以下、同様の文献（はてなブログ形式）

<!-- 深層学習: Deep Learning -->
[asin:476490487X:detail]

<!-- 詳解 ディープラーニング ~ TensorFlow・Keras による時系列データ処理 ~-->
[asin:4839962510:detail]

<!-- 深層学習による自然言語処理 (機械学習プロフェッショナルシリーズ) -->
[asin:4061529242:detail]

<!-- TensorFlow機械学習クックブック Pythonベースの活用レシピ60+ -->
[asin:4295002003:detail]
