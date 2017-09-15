# 機械学習 [Machine Learning] / パターン認識 [Pattern recognition]

機械学習、パターン認識に関してのマイノートです。今後も随時追加予定です。

This is my notebook that summarizes about "Machine Learning" and "Pattern recognition". I will add contents as needed.

![s_](https://user-images.githubusercontent.com/25688193/29311672-d5cb20c2-81ed-11e7-9c44-002fe0eb0873.png)


> 外部リンク
>> Twitter モーメント：</br>
>> 機械学習 : https://twitter.com/i/moments/781970648385978368</br>
>> SVM : https://twitter.com/i/moments/785417932629168129</br>
>> 情報理論 : https://twitter.com/i/moments/796112497388335105</br>

>> My GitHub
>>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き :
>>> https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn

>>> 主に、「はじパタ」R実行例のサンプルRコード :</br>
>>> https://github.com/Yagami360/PRML_RCode


## 目次 [Contents]
1. [機械学習の概要 [Overview]](#ID_1)
    1. [全体 MAP 図](#ID_1-1)
    1. [機械学習の基本的なタスク処理](#ID_1-2)
        1. [回帰のための機械学習](#ID_1-2-1)
        1. [分類のための機械学習](#ID_1-2-2)
    1. [学習の方法、種類](#ID_1-3)
        1. [教師あり学習 [supervised learning] と教師なし学習 [Unsupervised learning]](#ID_1-3-1)
        1. [バッチ学習 [batch learning] とオンライン学習 [online learning]](#ID_1-3-2)
        1. [強化学習 [reinforcement learning]](#ID_1-3-3)
        1. [アンサンブル学習 [ensemble learning]](#ID_1-3-4)
1. [機械学習の前処理 [pre processing]](#ID_2)
    1. [欠損値への対応](#ID_2-1)
    1. [カテゴリデータ（名義 [nominal] 特徴量、順序 [ordinal] 特徴量）の処理](ID_2-2)
    1. [データの分割](#ID_2-3)
    1. [特徴データの変換、特徴量のスケーリング](#ID_2-4)
        1. [特徴ベクトル空間 [feature vector space]](#ID_2-4-1)
        1. [特徴ベクトルの変換](#ID_2-4-2)
        1. [特徴ベクトルの正規化（標準化） [normalization/standardization]](#ID_2-4-3)
        1. [特徴ベクトルの無相関化 [decorrelation]](#ID_2-4-4)
        1. [特徴ベクトルの白色化 [whitening]](#ID_2-4-5)
    1. [特徴データの次元圧縮、特徴抽出](#ID_2-5)
        1. [主成分分析 [PCA : Principal Component Analysis]](#ID_2-5-1)
            1. [主成分分析（PCA）の分散最大化による定式化](#ID_2-5-1-1)
            1. [主成分分析（PCA）の誤差最小化による定式化](#ID_2-5-1-2)
        1. [カーネル主成分分析 [kernel PCA : kernel Principal Component Analysis]](#ID_2-5-2)
        1. [部分空間法 [subspace methods]](#ID_2-5-3)
            1. [部分空間 [sub space]](#ID_2-5-3-1)
        1. [カーネル部分空間法 [kernel subspace methods]](#ID_2-5-4)
2. [モデルの評価 [evaluate model]](#ID_3)
    1. [汎化能力 [generalizing capability]](#ID_3-1)
        1. [モデルの選択 [model selection]](#ID_3-1-1)
            1. [多項式の関数近似での例](#ID_3-1-1-1)
            1. [【補足】より広義な意味でのモデル選択](#ID_3-1-1-2)
        1. [バイアス・バリアントトレードオフ [bias-variance trade-off]](#ID_3-1-2) 
            1. [多項式の関数近似での例](#ID_3-1-2-1)
        1. [過学習 [overfitting]](#ID_3-1-3)
            1. [多項式の関数近似での例](#ID_3-1-2-1)
        1. [正則化 [Regularization] による過学習への対応](#ID_3-1-4)
            1. [L2 正則化 [L2 reguraration]（正則化最小２乗法）](#ID_3-1-4-1)
            1. [L1正則化による疎な解  [Sparse solution]（ほとんどの特徴量の重みが０になるような解）](#ID_3-1-4-2)
        1. [損失関数 [loss functions]（コスト関数、誤差関数）](#ID_3-1-5)
            1. [回帰問題の為の、損失関数（L2正則化、L1正則化）](#ID_3-1-5-1)
            1. [分類問題の為の、損失関数](#ID_3-1-5-2)
    1. [データの分割手法とモデルの評価](#ID_3-2)
        1. [ホールド・アウト法 [holdout method]](#ID_3-2-1)
        1. [交差確認法 [cross validation method] （＝交差検証法、交差妥当化法）](#ID_3-2-2)
        1. [１つ抜き法 [leave-one-out method] （＝ジャックナイフ法）](#ID_3-2-3)
        1. [ブートストラップ法 [bootstrap method]](#ID_3-2-4)
    1. [学習曲線 [Learning Curve]と検証曲線 [Validation Curve]](#ID_3-3)
    1. [陽性 [positive]、陰性 [negative] から導かれる各種評価指数（２クラスの識別問題）](#ID_3-4)
        1. [混同行列、適合率、再現率、F1スコア](#ID_3-4-1)
        1. [ROC曲線（受信者動作特性曲線）[receiver operator characteristics curve]](#ID_3-4-2)
    1. [グリッドサーチに [grid search] よるモデルのハイパーパラメータのチューニング](#ID_3-7)
    1. [情報量基準[Information Criterion]](#ID_3-8)
        1. [AIC（赤池の情報量基準）[Akaike's Information Criterion]](#ID_3-8-1)
1. [確率モデルと識別関数 [discriminant function]](#ID_4)
    1. [確率モデル（パラメトリックモデル [parametric models]と、ノンパラメトリックモデル [non-parametric models]）](#ID_4-1)
    1. [識別規則 [idification rule]](#ID_4-2)
    1. [正規分布関数と正規分布から導かれる識別関数](#ID_4-3)
    1. [最大尤度法 [MLE：maximum likelihood estimation]による確率モデルのパラメータの推定](#4-4)
1. [ベイズ識別](#ID_5)
    1. [ベイスの識別規則 [Bayes's idification rule]](#ID_5-1)
    1. [](#ID_5-x)
    1. [](#ID_5-x)
    1. [](#ID_5-x)
1. [線形判別分析 [LDA : liner discrinant analysis]](#ID_6)
    1. [線形識別関数 [liner discriminant function] でのクラス識別＜識別規則＞](#ID_6-1)
    1. [線形判別分析 [LDA : liner discrinant analysis] によるパラメータ推定](#ID_6-2)
       1. [判別分析法](#ID_6-2-1)
1. [ロジスティクス回帰 [Logistic Regression]](#ID_7)
1. [最近接法, k-NN 法 [k-nearest neighbor algorithm]](#ID_8)
1. [サポートベクターマシン [SVM : Support Vector Machine]](#ID_9)
1. [決定木 [Decision Tree]](#ID_10)
1. [アンサンブル学習 [ensemble learning]](#ID_11)
    1. [混合モデル [mixed model]](#ID_11-1)
        1. [混合モデルによるモデル多様体の拡張（混合モデルの幾何学的解釈）](#ID_11-1-1)
        1. [混合正規分布モデル [GMM : Gaussian Mixture Model]](#ID_11-1-2)
        1. [混合正規分布モデルの幾何学的観点](#ID_11-1-3)
    1. [EM アルゴリズム [expectation–maximization algorithm]](#ID_11-2)
        1. [EM アルゴリズムの適用例](#ID_11-2-1)
        1. [EM アルゴリズムの幾何学解釈](#ID_11-2-2)
    1. [ブースティング [Boosting]、アダブースト [AdaBoost]](#ID_11-3)
        1. [アダブースト [AdaBoost]](#ID_11-3-1)
            1. [AdaBoost の学習アルゴリズムの導出](#ID_11-3-1-1)
            1. [AdaBoost の幾何学的解釈](#ID_11-3-1-2)        
    1. [バギング [Bagging]](#ID_11-4)
        1. [バギングの幾何学解釈](#ID_11-4-1)
1. [クラスタリング [clustering]](#ID_12)
1. [パターン認識 [pattern recognition]](#ID_x)
    1. [パターン認識における前処理](#ID_x-x-x)
1. [](#ID_x)
1. [](#ID_x)
1. [参考文献](#参考文献)
---
旧目次（後で削除予定）
1. [識別規則 [Idification rule (Overview)]](#識別規則)
1. [ベイスの識別規則 [Bayes's idification rule]](#ベイスの識別規則)
1. [ROC 曲線 [receiver operator characteristics curve]](#ROC曲線)
1. [最近接法, k-NN 法 [k-nearest neighbor algorithm]](#最近接法、kNN法)
1. [線形識別関数 [liner discriminant function]](#線形識別関数)
1. [線形判別分析 [LDA : liner discrinant analysis]](#線形判別分析)
1. [ロジスティクス回帰 [Logistic Regression]](#ロジスティクス回帰)
1. [サポートベクターマシン [SVM : Support Vector Machine] ](#サポートベクターマシン)
1. [決定木 [Decision Tree]](#決定木)
1. [混合モデルとアンサンブル学習](#混合モデルとアンサンブル学習)
1. [EMアルゴリズム](#EMアルゴリズム)
1. [AdaBoost](#AdaBoost)
1. [バギング [Bagging]](#バギング)
1. [ランダムフォレスト [Random Forests]](#ランダムフォレスト)
---



<a id="ID_1"></a>

## 機械学習の概要 [Overview]

<a id="ID_1-1"></a>

### 全体 MAP 図
> 記載中...

<a id="ID_1-2"></a>

### 機械学習の基本的なタスク処理
機械学習は、大きく分けて以下の２つの問題設定＆解決のための手法に分けることが出来る。
- ① 回帰問題の為の手法。（単回帰分析、重回帰分析、等）
- ② （クラスの）分類問題の為の手法（SVM、k-NN、ロジスティクス回帰、等）

<a id="ID_1-2-1"></a>

#### 回帰のための機械学習
> 記載中...

<a id="ID_1-2-2"></a>

#### 分類のための機械学習
> 記載中...


<a id="ID_1-3"></a>

### 学習の方法、種類

<a id="ID_1-3-1"></a>

#### 教師あり学習 [supervised learning] と教師なし学習 [Unsupervised learning]
> 記載中...

<a id="ID_1-3-2"></a>

#### バッチ学習 [batch learning] とオンライン学習 [online learning]
![image](https://user-images.githubusercontent.com/25688193/30470771-09669b7c-9a31-11e7-8985-74fc6ed9c903.png)

<a id="ID_1-3-3"></a>

#### 強化学習 [reinforcement learning]
![image](https://user-images.githubusercontent.com/25688193/30470943-bb9e0eb0-9a31-11e7-95d1-681b16a7272e.png)

<a id="ID_1-3-4"></a>

#### アンサンブル学習 [ensemble learning]
各識別器を組み合わせて使用し、それらの識別器（弱識別器という）の投票結果（単純な多数決 or 重み付け後の多数決等）で最終的な判断を下す学習方法。</br>
様々な識別器を組み合わせて **多様性のある学習** を行うため、汎化性能が高く、又過学習 [overfitting] を起こしにくい。

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> 機械学習における、アンサンブル学習のサンプルコード集。（練習プログラム）</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/EnsembleLearning_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/EnsembleLearning_scikit-learn)</br>



<a id="ID_2"></a>

## 機械学習の前処理 [pre processing]

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> 機械学習における、データの前処理のサンプルコード集。（練習プログラム）</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/DataPreProcess_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/DataPreProcess_scikit-learn)</br>

<a id="ID_2-1"></a>

### 欠損値への対応
![image](https://user-images.githubusercontent.com/25688193/30471608-531bc1ea-9a34-11e7-91c2-addd81f5961e.png)
> 記載中...

<a id="ID_2-2"></a>

### カテゴリデータ（名義 [nominal] 特徴量、順序 [ordinal] 特徴量）の処理
![image](https://user-images.githubusercontent.com/25688193/30471754-df5feea6-9a34-11e7-87a1-f556e6d94829.png)
![image](https://user-images.githubusercontent.com/25688193/30471665-859ece0a-9a34-11e7-91c1-44c0ce6eae1e.png)
> 記載中...


<a id="ID_2-3"></a>

### データの分割
![image](https://user-images.githubusercontent.com/25688193/30472734-a8bc90a8-9a38-11e7-9f7b-95b8086f9c87.png)
![image](https://user-images.githubusercontent.com/25688193/30472774-c973f412-9a38-11e7-8570-49a8b4d36eed.png)


<a id="ID_2-4"></a>

### 特徴データの変換、特徴量のスケーリング

<a id="ID_2-4-1"></a>

#### 特徴ベクトル空間 [feature vector space]
![image](https://user-images.githubusercontent.com/25688193/30472026-eccf1052-9a35-11e7-82ad-3d0427854066.png)

<a id="ID_2-4-2"></a>

#### 特徴ベクトルの変換
![image](https://user-images.githubusercontent.com/25688193/30471869-44436b54-9a35-11e7-861f-1d4a495f9720.png)
![image](https://user-images.githubusercontent.com/25688193/30471905-6939bc92-9a35-11e7-93dc-b57e2fb5d80b.png)
![image](https://user-images.githubusercontent.com/25688193/30472182-6883ff0a-9a36-11e7-847a-50a03ec100f6.png)
![image](https://user-images.githubusercontent.com/25688193/30472221-8270e950-9a36-11e7-845f-cb572d00eeb5.png)

<a id="ID_2-4-3"></a>

#### 特徴ベクトルの正規化（標準化） [normalization/standardization]
![image](https://user-images.githubusercontent.com/25688193/30472418-3e9a9ffe-9a37-11e7-9377-dc43109d73c7.png)
![image](https://user-images.githubusercontent.com/25688193/30472452-66fe0986-9a37-11e7-8848-0acb11fdaba2.png)

<a id="ID_2-4-4"></a>

#### 特徴ベクトルの無相関化 [decorrelation]
![image](https://user-images.githubusercontent.com/25688193/30472530-d7244c02-9a37-11e7-9875-9eaf85293d03.png)
![image](https://user-images.githubusercontent.com/25688193/30472631-3ea0a9de-9a38-11e7-9d40-9c446b939362.png)
![image](https://user-images.githubusercontent.com/25688193/30472658-659a7b1e-9a38-11e7-854f-fe00f0a39994.png)

<a id="ID_2-4-5"></a>

#### 特徴ベクトルの白色化 [whitening]
> 記載中...

<a id="ID_2-5"></a>

### 特徴データの次元圧縮
![image](https://user-images.githubusercontent.com/25688193/30472927-61d09922-9a39-11e7-9c9c-95fe52eb7228.png)

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> 主成分分析 [PCA : Principal Component Analysis] による教師なしデータの次元削除、特徴抽出</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/PCA_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/PCA_scikit-learn)</br>
>>> カーネル主成分分析 [kernelPCA : kernel Principal Component Analysis] による非線形写像と教師なしデータの次元削除、特徴抽出</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/kernelPCA_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/kernelPCA_scikit-learn)</br>

<a id="ID_2-5-1"></a>

#### 主成分分析 [PCA : Principal Component Analysis]
![image](https://user-images.githubusercontent.com/25688193/30473228-a2600c56-9a3a-11e7-9aa6-30c7823ea225.png)

<a id="ID_2-5-1-1"></a>

##### 主成分分析（PCA）の分散最大化による定式化
![image](https://user-images.githubusercontent.com/25688193/30473864-bdb8520e-9a3c-11e7-8569-e41289908793.png)
![image](https://user-images.githubusercontent.com/25688193/30473991-25d766ae-9a3d-11e7-9d19-9412ace0ddd5.png)

<a id="ID_2-5-1-2"></a>

##### 主成分分析（PCA）の誤差最小化による定式化
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

PCAによる次元の削除
![image](https://user-images.githubusercontent.com/25688193/30474027-3cd29d24-9a3d-11e7-943e-4511c27bd74a.png)

> PCA による次元の削除の使用例
>> 13×178 次元のワインデータ → 2×124 次元のデータに次元削除（特徴抽出）（※124は分割したトレーニングデータ数）
>>> ワインデータをPCAによる次元削除を行なったデータの散布図。
寄与率と累積寄与率の図より、第１主成分と第２主成分だけで、全体のデータの６０％近くを説明できることから、2×124 次元のデータで散布図を図示。この後、この次元削除したデータでクラス識別用のデータに使用する。
![pca_scikit-learn_3](https://user-images.githubusercontent.com/25688193/29248635-f33244ac-8057-11e7-9de8-89b925f16560.png)

>> 固有値
![pca_scikit-learn_1](https://user-images.githubusercontent.com/25688193/29246419-1b9440ae-8034-11e7-979c-566d42c37b5f.png)

|λ_1|λ_2|λ_3|λ_4|λ_5|λ_6|λ_7|λ_8|λ_9|λ_10|λ_11|λ_12|λ_13|
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|4.56|2.65|1.33|1.13|0.80|0.55|0.43|0.25|0.22|0.18|0.16|0.12|0.11|

>> 寄与率（分散の比）[proportion of the variance] / 累積寄与率 [Cumulative contribution rate]
![pca_scikit-learn_2](https://user-images.githubusercontent.com/25688193/29246420-1ecbdf3e-8034-11e7-9732-1979c1d9c597.png)

|principal component|1|2|3|4|5|6|7|8|9|10|11|12|13|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|寄与率|0.366|0.213|0.107|0.090|0.064|0.044|0.035|0.020|0.017|0.014|0.0125|0.009|0.0086|
|累積寄与率|0.366|0.578|0.685|0.775|0.839|0.883|0.918|0.938|0.955|0.970|0.982|0.991|1.000|


<a id="ID_2-5-2"></a>

### カーネル主成分分析 [kernel PCA : kernel Principal Component Analysis]
![image](https://user-images.githubusercontent.com/25688193/30474295-2bcd4b90-9a3e-11e7-852a-2e9ffab3c1cc.png)
![image](https://user-images.githubusercontent.com/25688193/30474341-53c99a36-9a3e-11e7-81ec-9e50e9a445e8.png)
![image](https://user-images.githubusercontent.com/25688193/30474362-68a2529a-9a3e-11e7-9b27-a4ff4fcf48de.png)
![image](https://user-images.githubusercontent.com/25688193/30474393-8360553c-9a3e-11e7-815c-a04929df7088.png)
![image](https://user-images.githubusercontent.com/25688193/30474426-9ea0b7ce-9a3e-11e7-84c5-5c314ae8814e.png)

- kernelPCA による次元の削除の使用例
> `sklearn.datasets.make_moons( n_samples = 100 )` で生成した半月状のデータ（サンプル数：１００個）に対し、通常の PCA を適用した結果。</br>
>>上段の図より、通常の PCA では、うまく線形分離可能なテータに変換できていないことが分かる。（※下段の図は、各主成分に対する固有値と寄与率、累積率寄与率の図）尚、第１主成分 PC1 のみに次元削除（特徴抽出）した図は、各クラス（0 or 1）の識別を見やすくするため、上下に少し移動させている。
![kernelpca_scikit-learn_1](https://user-images.githubusercontent.com/25688193/29363412-e2cbf200-82ca-11e7-97b9-7ac3edce6383.png)

>`sklearn.datasets.make_moons( n_samples = 100 )` で生成した半月状のデータ（サンプル数：１００個）に対し、RBF カーネルをカーネル関数とする、カーネル PCA を適用した結果。</br>
>>上段の図より、RBFカーネルをカーネルとするkernelPCA では、この半月状のデータをうまく線形分離可能な特徴空間に写像出来ていることが分かる。（尚、第１主成分 PC1 のみに次元削除（特徴抽出）した図は、各クラス（0 or 1）の識別を見やすくするため、上下に少し移動させている。）</br>
>> 下段の図は、RBFカーネル関数のカーネル行列（グラム行列）の固有値を、大きい順に 40 個表示した図。カーネル行列の固有値は固有値分解を近似的な数値解析的手法で解いており、0 に近い値の固有値がこれに続いている。
![kernelpca_scikit-learn_2](https://user-images.githubusercontent.com/25688193/29363414-e47126c0-82ca-11e7-8931-10472ac76627.png)

>`sklearn.datasets.make_circles( n_samples = 1000 )` で生成した同心円状のデータ（サンプル数：１０００個）に対し、通常の PCA を適用した結果。</br>
>> 上段の図より、通常の PCA では、うまく線形分離可能なテータに変換できていないことが分かる。（※下段の図は、各主成分に対する固有値と寄与率、累積率寄与率の図）尚、第１主成分 PC1 のみに次元削除（特徴抽出）した図は、各クラス（0 or 1）の識別を見やすくするため、上下に少し移動させている。
![kernelpca_scikit-learn_4](https://user-images.githubusercontent.com/25688193/29364831-bc25d8dc-82cf-11e7-84b2-9842d5e96a1c.png)

> `sklearn.datasets.make_circles( n_samples = 1000 )` で生成した同心円状のデータ（サンプル数：１０００個）に対し、RBF カーネルをカーネル関数とする、カーネル PCA を適用した結果。
>> 上段の図より、RBFカーネルをカーネルとするkernelPCA では、この半月状のデータをうまく線形分離可能な特徴空間に写像出来ていることが分かる。（尚、第１主成分 PC1 のみに次元削除（特徴抽出）した図は、各クラス（0 or 1）の識別を見やすくするため、上下に少し移動させている。）
![kernelpca_scikit-learn_5](https://user-images.githubusercontent.com/25688193/29364832-bc48a862-82cf-11e7-9e59-25991406e03c.png)


<a id="ID_2-5-3"></a>

### 部分空間法 [subspace methods]
> 記載中...

<a id="ID_2-5-3-1"></a>

#### 部分空間 [sub space]
![image](https://user-images.githubusercontent.com/25688193/30475298-5114e6f8-9a41-11e7-80e2-6213b9400490.png)

<a id="ID_2-5-4"></a>

### カーネル部分空間法 [kernel subspace methods]
> 記載中...



<a id="ID_3"></a>

## モデルの評価 [evaluate model]

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> scikit-learn パイプライン（Pipeline クラス）による機械学習処理フローの効率化、
及び、モデルの汎化性能の各種評価方法（２クラスの識別問題を対象）</br>
>>>[Yagami360/MachineLearning_Exercises_Python_scikit-learn/MachineLearningPipeline_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/MachineLearningPipeline_scikit-learn)</br>

<a id="ID_3-1"></a>

### 汎化能力 [generalizing capability]
![image](https://user-images.githubusercontent.com/25688193/30475576-3f59061e-9a42-11e7-82cb-6e273bce5cd3.png)

<a id="ID_3-1-1"></a>

#### モデル選択 [model selection]
「モデル選択」という用語は、チューニングパラメータの”最適な”値を選択する分類問題を指す。
![image](https://user-images.githubusercontent.com/25688193/30476139-0af0e52a-9a44-11e7-9013-299ba54be39d.png)

<a id="ID_3-1-1-1"></a>

#### 多項式の関数近似での例
![image](https://user-images.githubusercontent.com/25688193/30476384-ccf2689c-9a44-11e7-83cf-d9fd32436c1e.png)

<a id="ID_3-1-1-2"></a>

#### 【補足】より広義な意味でのモデル選択
![image](https://user-images.githubusercontent.com/25688193/30476420-f0f18264-9a44-11e7-9139-7e5b6a985cd5.png)
![image](https://user-images.githubusercontent.com/25688193/30476447-06db4222-9a45-11e7-9c85-260f746c8400.png)

<a id="ID_3-1-2"></a>

#### バイアス・バリアントトレードオフ [bias-variance trade-off]

<a id="ID_3-1-2-1"></a>

##### 多項式の関数近似での例
![image](https://user-images.githubusercontent.com/25688193/30477235-6353ccde-9a47-11e7-8d85-5069ac18d68f.png)
![image](https://user-images.githubusercontent.com/25688193/30477396-f55f5df0-9a47-11e7-8361-460f41247683.png)

<a id="ID_3-1-3"></a>

#### 過学習 [overfitting]

<a id="ID_3-1-3-1"></a>

##### 多項式の関数近似での例
![image](https://user-images.githubusercontent.com/25688193/30477056-eeb521e8-9a46-11e7-8f54-d5985e350287.png)

![image](https://user-images.githubusercontent.com/25688193/30477158-2d2122ce-9a47-11e7-8c86-1ab11cd21485.png)

<a id="ID_3-1-4"></a>

#### 正則化 [Regularization] による過学習への対応
![image](https://user-images.githubusercontent.com/25688193/30478077-74ae8b10-9a4a-11e7-8d92-52cc4d969fb8.png)

<a id="ID_3-1-4-1"></a>

##### L2 正則化 [L2 reguraration]（正則化最小２乗法）
![image](https://user-images.githubusercontent.com/25688193/30478173-ecf0f9d2-9a4a-11e7-90d0-a1ac73bfc340.png)
![image](https://user-images.githubusercontent.com/25688193/30478194-03c31da2-9a4b-11e7-8804-37f3410b79ce.png)

<a id="ID_3-1-4-2"></a>

#### L1 正則化による疎な解  [Sparse solution]（ほとんどの特徴量の重みが０になるような解）
![image](https://user-images.githubusercontent.com/25688193/30478307-818fd216-9a4b-11e7-9724-ce2ad09ea1b0.png)
![image](https://user-images.githubusercontent.com/25688193/30478346-a5637f6c-9a4b-11e7-90cd-2a3e35048a87.png)


<a id="ID_3-1-5"></a>

### 損失関数 [loss funtions]（コスト関数、誤差関数）
損失関数（評価関数、誤差関数）は、モデルの出力と目的値（真の値、教師データ）との差（いいえ変えれば、誤差、距離）を計測する関数であり、モデルの学習に適用されるものである。

ここで、機械学習は、大きく分けて以下の２つの問題設定＆解決のための手法に分けることが出来た。
① 回帰問題の為の手法。（単回帰分析、重回帰分析、等）
② （クラスの）分類問題の為の手法（SVM、k-NN、ロジスティクス回帰、等）

従って、損失関数も同様にして、回帰問題の為の損失関数と、分類問題の為の損失関数が存在することになる。

<a id="ID_3-1-5-1"></a>

#### 回帰問題の為の、損失関数（L2正則化、L1正則化）

> 回帰の為の、損失関数（L2正則化、L1正則化）のグラフ
![processingformachinelearning_tensorflow_2-1](https://user-images.githubusercontent.com/25688193/30248461-2ed858f4-9663-11e7-9e1e-880bd99ca0c7.png)

- L2 正則化の損失関数は、目的値への距離の２乗で表されるので、下に凸な２次関数の形状をしており、</br>
  目的値（この場合 0）の近くで急なカーブを描く。</br>
  この特性が、損失関数と扱う際に優れているのが特徴である。
- L1 正則化の損失関数は、目的値への距離の絶対値で表される損失関数である。</br>
  その為、目的値（この場合 0）からのズレが大きくなっても（ズレの大きなに関わらず）、その傾き（勾配）は一定である。</br>
  その為、L1 正則化は L2 正則化よりも、外れ値にうまく対応するケースが多いのが特徴である。</br>
  又、目的値（この場合 0）にて、関数が連続でないために、対応するアルゴリズムがうまく収束しないケースが存在することに注意が必要となる。


<a id="ID_3-1-5-2"></a>

#### 分類問題の為の、損失関数
> 記載中...

<a id="ID_3-2"></a>

### データの分割手法とモデルの評価
![image](https://user-images.githubusercontent.com/25688193/30475690-ada1e9f6-9a42-11e7-9b87-e231cb502159.png)

手元にあるデータを学習用とテスト用に分割する代表的な方法、及びモデルの評価法には、以下のような手法がある。

<a id="ID_3-2-1"></a>

#### ホールド・アウト法 [holdout method]
![image](https://user-images.githubusercontent.com/25688193/30475667-9aa6fce2-9a42-11e7-9d6a-a70fca1460d1.png)

<a id="ID_3-2-2"></a>

#### 交差確認法 [cross validation method] （＝交差検証法、交差妥当化法）
![image](https://user-images.githubusercontent.com/25688193/30475852-1eb37556-9a43-11e7-83ca-ef3bd4bf58d4.png)
![image](https://user-images.githubusercontent.com/25688193/30475909-4da96118-9a43-11e7-9050-dc9d1bdbec4c.png)

<a id="ID_3-2-3"></a>

#### １つ抜き法 [leave-one-out method] （＝ジャックナイフ法）
> 記載中...


<a id="ID_3-2-4"></a>

#### ブートストラップ法 [bootstrap method]
![image](https://user-images.githubusercontent.com/25688193/30475951-6c86eede-9a43-11e7-8661-26fdedce2b9f.png)
![image](https://user-images.githubusercontent.com/25688193/30475973-83814cc4-9a43-11e7-9261-cf30f895ff0d.png)


<a id="ID_3-3"></a>

### 学習曲線 [Learning Curve]と検証曲線 [Validation Curve]
> 記載中...

<a id="ID_3-4"></a>

### 陽性 [positive]、陰性 [negative] から導かれる各種評価指数（２クラスの識別問題）

<a id="ID_3-4-1"></a>

#### 混同行列、適合率、再現率、F1スコア

<a id="ID_3-4-2"></a>

#### ROC曲線（受信者動作特性曲線）[receiver operator characteristics curve]

![twitter_ 13-1_161227](https://user-images.githubusercontent.com/25688193/29311708-e0f24fac-81ed-11e7-8461-ea000cac9608.png)
![twitter_ 13-2_161227](https://user-images.githubusercontent.com/25688193/29311709-e0f3ae74-81ed-11e7-93aa-42632dbc8ff8.png)
![twitter_ 13-3_161229](https://user-images.githubusercontent.com/25688193/29311710-e0fc87ba-81ed-11e7-9644-49881177d910.png)
![twitter_ 13-5_170101](https://user-images.githubusercontent.com/25688193/29311712-e1098ca8-81ed-11e7-9e67-5d2c57edd75b.png)
![twitter_ 13-8_170102](https://user-images.githubusercontent.com/25688193/29311715-e116b8a6-81ed-11e7-8716-53b612126a91.png)
![twitter_ 13-9_170102](https://user-images.githubusercontent.com/25688193/29311716-e12071fc-81ed-11e7-83e7-bfb361481266.png)
![twitter_ 13-10_170102](https://user-images.githubusercontent.com/25688193/29311717-e12908e4-81ed-11e7-8d8e-d6ffac3cc539.png)

<a id="ID_3-5"></a>

### グリッドサーチ [grid search] によるハイパーパラメータのチューニング
> 記載中...


<a id="ID_4"></a>

## 確率モデルと識別関数 [discriminant function]

<a id="ID_4-1"></a>

### 確率モデル（パラメトリックモデル [parametric models]と、ノンパラメトリックモデル [non-parametric models]）
![twitter_ 20-1_170108](https://user-images.githubusercontent.com/25688193/29311795-e389900e-81ed-11e7-950d-37c22138aed4.png)

<a id="ID_4-2"></a>

### 識別規則 [idification rule]
![twitter_ 2-1_160917](https://user-images.githubusercontent.com/25688193/29311684-e0581b44-81ed-11e7-9480-7efee4e5804a.png)
![twitter_ 2-2_160917](https://user-images.githubusercontent.com/25688193/29311685-e0589862-81ed-11e7-91ac-b4fac350b558.png)


<a id="ID_4-3"></a>

### 正規分布関数と正規分布から導かれる識別関数
![twitter_ 20-2_170108](https://user-images.githubusercontent.com/25688193/29311796-e38bbff0-81ed-11e7-8035-58a67b9776c4.png)
![twitter_ 20-3_170109](https://user-images.githubusercontent.com/25688193/29311797-e38e38d4-81ed-11e7-81f6-94b34e68912a.png)

![twitter_ 20-5_170110](https://user-images.githubusercontent.com/25688193/29311799-e39b8476-81ed-11e7-962b-10f3f8d4f1a5.png)
![twitter_ 20-6_170110](https://user-images.githubusercontent.com/25688193/29311801-e3ac1ef8-81ed-11e7-992c-09bc4a17f929.png)
![twitter_ 20-7_170110](https://user-images.githubusercontent.com/25688193/29311800-e3ab980c-81ed-11e7-9bc8-f5072291d9a8.png)
![twitter_ 20-8_170116](https://user-images.githubusercontent.com/25688193/29311804-e3c1282a-81ed-11e7-87e7-0307b1562bb4.png)
![twitter_ 20-9_170116](https://user-images.githubusercontent.com/25688193/29311802-e3b24774-81ed-11e7-8274-86ad54b28f6c.png)
![twitter_ 20-10_170116](https://user-images.githubusercontent.com/25688193/29311803-e3b5aacc-81ed-11e7-846f-66cefc69bb11.png)

<a id="ID_4-3"></a>

### 最大尤度法 [MLE：maximum likelihood estimation]による確率モデルのパラメータの推定
![twitter_ 20-18_170127](https://user-images.githubusercontent.com/25688193/29311812-e3f16b0c-81ed-11e7-99ad-bc6ae4315238.png)




<a id="ID_5"></a>

## ベイスの識別

<a id="ID_5-1"></a>

### ベイスの識別規則 [Bayes's idification rule]
![twitter_ 7-1_160930](https://user-images.githubusercontent.com/25688193/29311692-e09d7e0a-81ed-11e7-926a-bd5c1f4a2ce5.png)
![twitter_ 7-2_160930](https://user-images.githubusercontent.com/25688193/29311693-e09e1fe0-81ed-11e7-9477-ffe003d53b49.png)

![twitter_ 8-1_161001](https://user-images.githubusercontent.com/25688193/29311694-e09ed4a8-81ed-11e7-9a44-0026c1ec425f.png)

![twitter_ 9-1_161003](https://user-images.githubusercontent.com/25688193/29311699-e0c1411e-81ed-11e7-8e4e-2c2a0d0d0416.png)
![twitter_ 9-1_161003](https://user-images.githubusercontent.com/25688193/29311700-e0c21c7e-81ed-11e7-929c-88fb64a79cfc.png)

![twitter_ 10-1_161005](https://user-images.githubusercontent.com/25688193/29311701-e0c33898-81ed-11e7-9611-8c5b4f8f3814.png)
![twitter_ 10-2_161005](https://user-images.githubusercontent.com/25688193/29311703-e0d18dbc-81ed-11e7-88a7-1b0153d422ef.png)
![twitter_ 10-3_161005](https://user-images.githubusercontent.com/25688193/29311702-e0d0d3b8-81ed-11e7-8b91-d142d7ed6e75.png)

![twitter_ 11-1_161005](https://user-images.githubusercontent.com/25688193/29311704-e0d85106-81ed-11e7-97fe-0ce8edb63966.png)
![twitter_ 11-3_161005](https://user-images.githubusercontent.com/25688193/29311705-e0e3ed86-81ed-11e7-9d70-c99072c0aaba.png)

![twitter_ 12-1_161004](https://user-images.githubusercontent.com/25688193/29311706-e0e44ce0-81ed-11e7-8238-3967e593dd27.png)
![twitter_ 12-2_161004](https://user-images.githubusercontent.com/25688193/29311707-e0e6588c-81ed-11e7-84c7-3635a2d8537d.png)


<a id="ID_6"></a>

## 線形判別分析 [LDA : liner discrinant analysis]

<a id="ID_6-1"></a>

### 線形識別関数 [liner discriminant function] でのクラス識別＜識別規則＞
![twitter_ 17-1_161113](https://user-images.githubusercontent.com/25688193/29311733-e188c93c-81ed-11e7-8622-5688879e3e06.png)
![twitter_ 17-2_161113](https://user-images.githubusercontent.com/25688193/29311734-e1926c08-81ed-11e7-94b1-47561b20d85e.png)
![twitter_ 17-3_161113](https://user-images.githubusercontent.com/25688193/29311735-e195289e-81ed-11e7-99a8-fa05260c9edf.png)
![twitter_ 17-4_161114](https://user-images.githubusercontent.com/25688193/29311736-e1964d96-81ed-11e7-8deb-967edb1100c6.png)
![twitter_ 17-5_161114](https://user-images.githubusercontent.com/25688193/29311738-e1a2a4f6-81ed-11e7-98a8-e354024e7cc5.png)
![twitter_ 17-6_161115](https://user-images.githubusercontent.com/25688193/29311739-e1ae8c6c-81ed-11e7-8e58-49521ca97f27.png)
![twitter_ 17-7_161115](https://user-images.githubusercontent.com/25688193/29311740-e1b50920-81ed-11e7-976b-1a3da2b5b471.png)
![twitter_ 17-8_161115](https://user-images.githubusercontent.com/25688193/29311741-e1b75784-81ed-11e7-939d-22af94e938d5.png)
![twitter_ 17-9_161116](https://user-images.githubusercontent.com/25688193/29311742-e1b9add6-81ed-11e7-8f7f-68cbfc635bc0.png)
![twitter_ 17-10_1_171029](https://user-images.githubusercontent.com/25688193/29311743-e1cff5b4-81ed-11e7-992b-c26737ead99a.png)
![twitter_ 17-10_2_171029](https://user-images.githubusercontent.com/25688193/29311747-e1d8699c-81ed-11e7-9a04-2daa68230d4b.png)

<a id="ID_6-2"></a>

### 線形判別分析 [LDA : liner discrinant analysis] によるパラメータ推定
![twitter_ 17-10_161116](https://user-images.githubusercontent.com/25688193/29311746-e1d6ec70-81ed-11e7-8b9f-b969af491912.png)
![twitter_ 17-11_161116](https://user-images.githubusercontent.com/25688193/29311748-e1da7868-81ed-11e7-98a1-db01e60a5326.png)
![twitter_ 17-12_161116](https://user-images.githubusercontent.com/25688193/29311749-e1dcc848-81ed-11e7-89b6-22664d7f91c1.png)
![twitter_ 17-13_161118](https://user-images.githubusercontent.com/25688193/29311750-e1f338a8-81ed-11e7-80b3-3e5c1388350e.png)

<a id="ID_6-2-1"></a>

####　判別分析法
![twitter_ 17-14_161123](https://user-images.githubusercontent.com/25688193/29311751-e1f55688-81ed-11e7-9a1a-4b695f9cb435.png)
![twitter_ 17-15_161123](https://user-images.githubusercontent.com/25688193/29311754-e20c28ea-81ed-11e7-8bdf-9750c373cc16.png)
![twitter_ 17-16_161123](https://user-images.githubusercontent.com/25688193/29311752-e1fae198-81ed-11e7-952b-bd56703e6c2c.png)

![twitter_ 17-20_170130](https://user-images.githubusercontent.com/25688193/29311755-e20f8198-81ed-11e7-8958-dec5c59f20e8.png)

![twitter_ 17-25_170201](https://user-images.githubusercontent.com/25688193/29311757-e281b0f6-81ed-11e7-8c1e-dde2a688c020.png)
![twitter_ 17-26_170202](https://user-images.githubusercontent.com/25688193/29311758-e2a378b2-81ed-11e7-9e85-cf8b274eb3c6.png)


<a id="ID_7"></a>

## ロジスティクス回帰 [Logistic Regression]
![twitter_ 18-1_161129](https://user-images.githubusercontent.com/25688193/29311761-e2bb0752-81ed-11e7-94fc-6a887193766f.png)
![twitter_ 18-1_161130](https://user-images.githubusercontent.com/25688193/29311762-e2bffd52-81ed-11e7-8792-460a06fd85cb.png)
![twitter_ 18-2_161130](https://user-images.githubusercontent.com/25688193/29311763-e2c3934a-81ed-11e7-96df-d6efb0d753b7.png)
![twitter_ 18-3_161130](https://user-images.githubusercontent.com/25688193/29311764-e2cb7c5e-81ed-11e7-817e-b7d8d12fe7d1.png)
![twitter_ 18-4_161130](https://user-images.githubusercontent.com/25688193/29311767-e2de1062-81ed-11e7-88a4-40c59a934d55.png)
![twitter_ 18-5_161201](https://user-images.githubusercontent.com/25688193/29311766-e2db6506-81ed-11e7-8462-d0d5054964e8.png)
![twitter_ 18-6_161201](https://user-images.githubusercontent.com/25688193/29311768-e2e062e0-81ed-11e7-99d2-00d3c802e369.png)
![twitter_ 18-6 _170204](https://user-images.githubusercontent.com/25688193/29311769-e2e22b16-81ed-11e7-93e2-9252b524a4e6.png)
![twitter_ 18-7_161201](https://user-images.githubusercontent.com/25688193/29311770-e2fa944e-81ed-11e7-8ab0-6ca5be89e421.png)
![twitter_ 18-7 _170204](https://user-images.githubusercontent.com/25688193/29311772-e300ba54-81ed-11e7-8ea6-088f6f79d61c.png)
![twitter_ 18-8_170204](https://user-images.githubusercontent.com/25688193/29311771-e2feb470-81ed-11e7-9d6a-c55321d5764b.png)
![twitter_ 18-9_170208](https://user-images.githubusercontent.com/25688193/29311773-e30114ea-81ed-11e7-9dcd-9cd99ac926ee.png)
![twitter_ 18-10_170208](https://user-images.githubusercontent.com/25688193/29311774-e30526e8-81ed-11e7-80dd-75fe8fba875b.png)
![twitter_ 18-11_170209](https://user-images.githubusercontent.com/25688193/29311775-e30bd466-81ed-11e7-983b-92047d58d118.png)
![twitter_ 18-11 _170210](https://user-images.githubusercontent.com/25688193/29311776-e31e2d14-81ed-11e7-8dc4-d3c01c7f46ba.png)
![twitter_ 18-12_170209](https://user-images.githubusercontent.com/25688193/29311777-e322d170-81ed-11e7-82dc-4d34c48dcbdd.png)
![twitter_ 18-12 _170210](https://user-images.githubusercontent.com/25688193/29311779-e3240d06-81ed-11e7-8f9e-61274ddbf738.png)
![twitter_ 18-13_170210](https://user-images.githubusercontent.com/25688193/29311778-e3239aba-81ed-11e7-9d57-2b3d620486be.png)
![twitter_ 18-14_170210](https://user-images.githubusercontent.com/25688193/29311780-e3286b9e-81ed-11e7-99d5-1dfc532da857.png)
![twitter_ 18-15_170210](https://user-images.githubusercontent.com/25688193/29311781-e32fea90-81ed-11e7-8464-c71a34d15ba3.png)
![twitter_ 18-16_170210](https://user-images.githubusercontent.com/25688193/29311782-e3411270-81ed-11e7-95f8-6e9b2798ced6.png)
![twitter_ 18-17_170726](https://user-images.githubusercontent.com/25688193/29311783-e3456b72-81ed-11e7-87ef-4fdba93cf0ea.png)
![twitter_ 18-18_170726](https://user-images.githubusercontent.com/25688193/29311784-e3461bd0-81ed-11e7-80af-6c8404d6c0c6.png)
![twitter_ 18-19_170727](https://user-images.githubusercontent.com/25688193/29311785-e34831d6-81ed-11e7-93f0-0eb9400253dd.png)

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> ロジスティクス回帰の練習コード</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/LogisticRegression_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/LogisticRegression_scikit-learn)</br>



<a id="ID_8"></a>

## 最近接法, k-NN 法 [k-nearest neighbor algorithm]

![twitter_ 14-1_161007](https://user-images.githubusercontent.com/25688193/29311718-e12caecc-81ed-11e7-84d5-bc46932892c1.png)
![twitter_ 14-2_161007](https://user-images.githubusercontent.com/25688193/29311719-e12edc7e-81ed-11e7-9ea0-8be8e1e59b1b.png)
![twitter_ 14-3_161008](https://user-images.githubusercontent.com/25688193/29311720-e1365d46-81ed-11e7-8552-f97071578c18.png)
![twitter_ 14-4_161009](https://user-images.githubusercontent.com/25688193/29311721-e1397abc-81ed-11e7-893b-8850e2002a5b.png)
![twitter_ 14-5_161010](https://user-images.githubusercontent.com/25688193/29311722-e143c60c-81ed-11e7-90ac-3baab1fd30a9.png)

![twitter_ 15-1_161216](https://user-images.githubusercontent.com/25688193/29311723-e14c2da6-81ed-11e7-99ae-e31d77c6efc3.png)
![twitter_ 15-1 _161221](https://user-images.githubusercontent.com/25688193/29311724-e14ee2bc-81ed-11e7-908b-2fa2cd4a8921.png)
![twitter_ 15-2_161216](https://user-images.githubusercontent.com/25688193/29311725-e151886e-81ed-11e7-9306-f83c341a3c22.png)
![twitter_ 15-2 _161221](https://user-images.githubusercontent.com/25688193/29311726-e158ec12-81ed-11e7-81e1-32d918b2f08e.png)

![twitter_ 16-1_161011](https://user-images.githubusercontent.com/25688193/29311727-e15eb1d8-81ed-11e7-8d5d-1308321d9d74.png)
![twitter_ 16-2_161012](https://user-images.githubusercontent.com/25688193/29311728-e166a5dc-81ed-11e7-9fd5-e24c61588dea.png)
![twitter_ 16-3_161111](https://user-images.githubusercontent.com/25688193/29311729-e16e9a4e-81ed-11e7-804b-2fbed8884257.png)
![twitter_ 16-4_161111](https://user-images.githubusercontent.com/25688193/29311730-e171a8f6-81ed-11e7-8c9c-8299c2e4ae42.png)
![twitter_ 16-5_161112](https://user-images.githubusercontent.com/25688193/29311731-e1739ecc-81ed-11e7-9feb-6c1168aab9f8.png)
![twitter_ 16-6_161112](https://user-images.githubusercontent.com/25688193/29311732-e18010ee-81ed-11e7-9d3d-47877a66f994.png)
![twitter_ 16-7_170729](https://user-images.githubusercontent.com/25688193/29311737-e199b45e-81ed-11e7-8685-98c52a6594b2.png)

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> k-NN 法の練習コード</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/kNN_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/kNN_scikit-learn)</br>



<a id="ID_9"></a>

## サポートベクターマシン [SVM : Support Vector Machine]
![twitter_svm_1-1_170211](https://user-images.githubusercontent.com/25688193/29311963-8c41480e-81ee-11e7-84a5-7ccfa0f2d724.png)
![twitter_svm_1-2_170211](https://user-images.githubusercontent.com/25688193/29311961-8c2d24e6-81ee-11e7-801a-f406b6007b04.png)
![twitter_svm_2-1_170212](https://user-images.githubusercontent.com/25688193/29311964-8c41fbe6-81ee-11e7-89ba-6bbfe11dfc55.png)
![twitter_svm_2-2_170212](https://user-images.githubusercontent.com/25688193/29311962-8c4081b2-81ee-11e7-82d5-3ad978082b95.png)
![twitter_svm_3-1_170214](https://user-images.githubusercontent.com/25688193/29311966-8c42b464-81ee-11e7-966f-9ca1ea6fbc76.png)
![twitter_svm_3-2_170214](https://user-images.githubusercontent.com/25688193/29311965-8c427a26-81ee-11e7-9c3a-ea8ddd28d510.png)
![twitter_svm_3-3_170214](https://user-images.githubusercontent.com/25688193/29311967-8c4f9bca-81ee-11e7-8e69-e8cc8d7914ff.png)
![twitter_svm_3-4_170214](https://user-images.githubusercontent.com/25688193/29311968-8c6387e8-81ee-11e7-8906-9164dfa399ef.png)
![twitter_svm_3-5_170216](https://user-images.githubusercontent.com/25688193/29311969-8c644746-81ee-11e7-9bf9-8bbf6859ac72.png)
![twitter_svm_4-1_170216](https://user-images.githubusercontent.com/25688193/29311971-8c6509d8-81ee-11e7-8488-31927efc6e3f.png)
![twitter_svm_4-2_170217](https://user-images.githubusercontent.com/25688193/29311970-8c64a7ae-81ee-11e7-868f-6ab7982ee83e.png)
![twitter_svm_4-3_170217](https://user-images.githubusercontent.com/25688193/29311972-8c661166-81ee-11e7-8361-7be24886064b.png)
![twitter_svm_4-4_170218](https://user-images.githubusercontent.com/25688193/29311973-8c716d5e-81ee-11e7-88f9-a76c020f1ae9.png)
![twitter_svm_4-5_170218](https://user-images.githubusercontent.com/25688193/29311974-8c8614e8-81ee-11e7-9f73-c08228309ecd.png)
![twitter_svm_5-1_170219](https://user-images.githubusercontent.com/25688193/29311975-8c86acf0-81ee-11e7-9439-d245702b6a18.png)
![twitter_svm_5-2_170220](https://user-images.githubusercontent.com/25688193/29311977-8c87a916-81ee-11e7-9914-9744d08557c4.png)
![twitter_svm_5-2_170225](https://user-images.githubusercontent.com/25688193/29311976-8c86e2ba-81ee-11e7-87ec-5a1508130509.png)
![twitter_svm_5-3_170222](https://user-images.githubusercontent.com/25688193/29311978-8c897980-81ee-11e7-81e0-da923729128b.png)
![twitter_svm_5-4_170225](https://user-images.githubusercontent.com/25688193/29311979-8c93a130-81ee-11e7-8631-b7a12773ab50.png)
![twitter_svm_5-5_170303](https://user-images.githubusercontent.com/25688193/29311980-8ca849e6-81ee-11e7-9871-267853a4e608.png)
![twitter_svm_5-6_170303](https://user-images.githubusercontent.com/25688193/29311981-8ca89252-81ee-11e7-9d50-f97de95c69eb.png)
![twitter_svm_5-7_170305](https://user-images.githubusercontent.com/25688193/29311982-8ca99b66-81ee-11e7-8676-3ff2a6e792ca.png)
![twitter_svm_6-1_170728](https://user-images.githubusercontent.com/25688193/29311983-8caa804e-81ee-11e7-8d7a-31112a92a58f.png)
![twitter_svm_6-2_170728](https://user-images.githubusercontent.com/25688193/29311984-8cab9e84-81ee-11e7-88c3-102147c84341.png)
![twitter_svm_6-2 _170728](https://user-images.githubusercontent.com/25688193/29311985-8cb6430c-81ee-11e7-965b-ba1421d9ceb4.png)
![twitter_svm_6-3_170729](https://user-images.githubusercontent.com/25688193/29311986-8ccc025a-81ee-11e7-8097-6f1daf9e1a49.png)



<a id="ID_10"></a>

## 決定木 [Decision Tree]
![twitter_ 21-1_170730](https://user-images.githubusercontent.com/25688193/29311813-e3f36cc2-81ed-11e7-88aa-387bd4b36715.png)
![twitter_ 21-2_170730](https://user-images.githubusercontent.com/25688193/29311815-e3fc7bdc-81ed-11e7-9af6-a2cbb9d4af64.png)
![twitter_ 21-3_170731](https://user-images.githubusercontent.com/25688193/29311814-e3fbf7ca-81ed-11e7-9837-1ab49a6c8827.png)
![twitter_ 21-5_170731](https://user-images.githubusercontent.com/25688193/29311817-e407558e-81ed-11e7-8ec3-a45393202903.png)
![twitter_ 21-6_170731](https://user-images.githubusercontent.com/25688193/29311816-e407481e-81ed-11e7-9566-4db88d64e241.png)
![twitter_ 21-7_170731](https://user-images.githubusercontent.com/25688193/29311820-e427e092-81ed-11e7-88d1-de7f469431f6.png)
![twitter_ 21-8_170801](https://user-images.githubusercontent.com/25688193/29311821-e428507c-81ed-11e7-8123-b9c4db7b12a4.png)
![twitter_ 21-9_170801](https://user-images.githubusercontent.com/25688193/29311819-e41ebb70-81ed-11e7-9bbc-8bef4683006f.png)
![twitter_ 21-10_170801](https://user-images.githubusercontent.com/25688193/29311823-e432419a-81ed-11e7-93dc-0487eaeed1bd.png)
![twitter_ 21-11_170801](https://user-images.githubusercontent.com/25688193/29311822-e42adcde-81ed-11e7-9237-39c7fcefd100.png)
![twitter_ 21-12_170802](https://user-images.githubusercontent.com/25688193/29311824-e43db656-81ed-11e7-9c1a-01f8f3554f01.png)
![twitter_ 21-13_170802](https://user-images.githubusercontent.com/25688193/29311825-e44193ac-81ed-11e7-95e2-830f102cbbf0.png)
![twitter_ 21-14_170802](https://user-images.githubusercontent.com/25688193/29311829-e45cca5a-81ed-11e7-9e16-b9a66fa68715.png)
![twitter_ 21-15_170802](https://user-images.githubusercontent.com/25688193/29311826-e44e93c2-81ed-11e7-816d-23f42aead2b2.png)



<a id="ID_11"></a>

## アンサンブル学習 [ensemble learning]

<a id="ID_11-1"></a>

### 混合モデル

<a id="ID_11-1-1"></a>

#### 混合モデルによるモデル多様体の拡張

<a id="ID_11-2"></a>

### EM アルゴリズム

<a id="ID_11-3"></a>

### 

<a id="ID_11-4"></a>

### 

<a id="ID_11-5"></a>

### 


<a name="参考文献"></a>

## 参考文献

> はじめてのパターン認識 </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)</br>

> パターン認識と機械学習 上（ベイズ理論による統計的予測）</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98%E3%81%A8%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92-%E4%B8%8A-C-M-%E3%83%93%E3%82%B7%E3%83%A7%E3%83%83%E3%83%97/dp/4621061224)</br>
> パターン認識と機械学習 下（ベイズ理論による統計的予測）</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98%E3%81%A8%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92-%E4%B8%8B-%E3%83%99%E3%82%A4%E3%82%BA%E7%90%86%E8%AB%96%E3%81%AB%E3%82%88%E3%82%8B%E7%B5%B1%E8%A8%88%E7%9A%84%E4%BA%88%E6%B8%AC-C-M-%E3%83%93%E3%82%B7%E3%83%A7%E3%83%83%E3%83%97/dp/4621061240/ref=pd_lpo_sbs_14_t_2?_encoding=UTF8&psc=1&refRID=4NVPYNHD2TGV0PZ1KQS0)</br>

> パターン認識と機械学習の学習普及版―ベイズ理論に負けないための数学</br>
[amazonで詳細を見る](https://www.amazon.co.jp/%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98%E3%81%A8%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%81%AE%E5%AD%A6%E7%BF%92%E2%80%95%E3%83%99%E3%82%A4%E3%82%BA%E7%90%86%E8%AB%96%E3%81%AB%E8%B2%A0%E3%81%91%E3%81%AA%E3%81%84%E3%81%9F%E3%82%81%E3%81%AE%E6%95%B0%E5%AD%A6-%E5%85%89%E6%88%90-%E6%BB%8B%E7%94%9F/dp/4873100933?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4873100933)

> 情報理論の基礎―情報と学習の直観的理解のために (SGC Books) </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%83%85%E5%A0%B1%E7%90%86%E8%AB%96%E3%81%AE%E5%9F%BA%E7%A4%8E%E2%80%95%E6%83%85%E5%A0%B1%E3%81%A8%E5%AD%A6%E7%BF%92%E3%81%AE%E7%9B%B4%E8%A6%B3%E7%9A%84%E7%90%86%E8%A7%A3%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AB-SGC-Books-%E6%9D%91%E7%94%B0-%E6%98%87/dp/4781912125?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4781912125)</br>

> 言語処理のための機械学習入門 (自然言語処理シリーズ)</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E8%A8%80%E8%AA%9E%E5%87%A6%E7%90%86%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E5%85%A5%E9%96%80-%E8%87%AA%E7%84%B6%E8%A8%80%E8%AA%9E%E5%87%A6%E7%90%86%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E9%AB%98%E6%9D%91-%E5%A4%A7%E4%B9%9F/dp/4339027510?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4339027510)

> 深層学習: Deep Learning</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%B7%B1%E5%B1%A4%E5%AD%A6%E7%BF%92-Deep-Learning-%E7%9B%A3%E4%BF%AE-%E4%BA%BA%E5%B7%A5%E7%9F%A5%E8%83%BD%E5%AD%A6%E4%BC%9A/dp/476490487X)

> 情報数理の基礎と応用 (ライブラリ情報学コア・テキスト) </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%83%85%E5%A0%B1%E6%95%B0%E7%90%86%E3%81%AE%E5%9F%BA%E7%A4%8E%E3%81%A8%E5%BF%9C%E7%94%A8-%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA%E6%83%85%E5%A0%B1%E5%AD%A6%E3%82%B3%E3%82%A2%E3%83%BB%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88-%E5%B0%BE%E7%95%91-%E4%BC%B8%E6%98%8E/dp/4781912109?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4781912109)</br>

> Excelで学ぶ多変量解析―資料に隠れた大切な関係は多変量解析を駆使してあぶり出す!</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/Excel%E3%81%A7%E5%AD%A6%E3%81%B6%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90%E2%80%95%E8%B3%87%E6%96%99%E3%81%AB%E9%9A%A0%E3%82%8C%E3%81%9F%E5%A4%A7%E5%88%87%E3%81%AA%E9%96%A2%E4%BF%82%E3%81%AF%E5%A4%9A%E5%A4%89%E9%87%8F%E8%A7%A3%E6%9E%90%E3%82%92%E9%A7%86%E4%BD%BF%E3%81%97%E3%81%A6%E3%81%82%E3%81%B6%E3%82%8A%E5%87%BA%E3%81%99-%E6%B6%8C%E4%BA%95-%E8%89%AF%E5%B9%B8/dp/481633968X)

> 複素ニューラルネットワーク(第2版) 2016年 06 月号 [雑誌]: 数理科学 別冊</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E8%A4%87%E7%B4%A0%E3%83%8B%E3%83%A5%E3%83%BC%E3%83%A9%E3%83%AB%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF-%E7%AC%AC2%E7%89%88-2016%E5%B9%B4-06-%E6%9C%88%E5%8F%B7/dp/B01GU5F48Q?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=B01GU5F48Q)

> Python機械学習プログラミング 達人データサイエンティストによる理論と実践 (impress top gear)</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/Python%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0-%E9%81%94%E4%BA%BA%E3%83%87%E3%83%BC%E3%82%BF%E3%82%B5%E3%82%A4%E3%82%A8%E3%83%B3%E3%83%86%E3%82%A3%E3%82%B9%E3%83%88%E3%81%AB%E3%82%88%E3%82%8B%E7%90%86%E8%AB%96%E3%81%A8%E5%AE%9F%E8%B7%B5-impress-top-gear/dp/4844380605)

> TensorFlow機械学習クックブック Pythonベースの活用レシピ60+</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/TensorFlow%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%82%AF%E3%83%83%E3%82%AF%E3%83%96%E3%83%83%E3%82%AF-Python%E3%83%99%E3%83%BC%E3%82%B9%E3%81%AE%E6%B4%BB%E7%94%A8%E3%83%AC%E3%82%B7%E3%83%9460-impress-top-gear/dp/4295002003?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4295002003)

---
# 以下、旧内容（後で削除予定）








<a name="決定木"></a>

## 決定木 [Decision Tree]




<a name="混合モデルとアンサンブル学習"></a>

## 混合モデルとアンサンブル学習
![twitter_ _ _11-1_170626](https://user-images.githubusercontent.com/25688193/29312250-795757fa-81ef-11e7-8185-87d3127f6973.png)

### 混合モデルによるモデル多様体の拡張

![twitter_ _ _11-2_170630](https://user-images.githubusercontent.com/25688193/29312252-7957c64a-81ef-11e7-8e0b-f373dcdd8d55.png)
![twitter_ _ _11-3_170630](https://user-images.githubusercontent.com/25688193/29312251-7957822a-81ef-11e7-9f05-f1d331dc26a1.png)
![twitter_ _ _11-4_170630](https://user-images.githubusercontent.com/25688193/29312255-795c36f8-81ef-11e7-98d8-2464f129048e.png)
![twitter_ _ _11-5_170630](https://user-images.githubusercontent.com/25688193/29312253-795813e8-81ef-11e7-9f61-3bdb0d56b93e.png)


<a name="EMアルゴリズム"></a>

## EMアルゴリズム

![twitter_ _ _11-6_170701](https://user-images.githubusercontent.com/25688193/29312254-7958c342-81ef-11e7-9e7e-34f261d6ad14.png)
![twitter_ _ _11-7_170701](https://user-images.githubusercontent.com/25688193/29312256-797abca4-81ef-11e7-9f2f-9d8de6ec4fc8.png)
![twitter_ _ _11-7 _170701](https://user-images.githubusercontent.com/25688193/29312257-797b4912-81ef-11e7-8da1-1135c8ff87f5.png)
![twitter_ _ _11-8_170701](https://user-images.githubusercontent.com/25688193/29312258-797bb37a-81ef-11e7-8898-cef3dc5020de.png)
![twitter_ _ _11-9_170701](https://user-images.githubusercontent.com/25688193/29312259-797c3c0a-81ef-11e7-9bd1-a3bd369a78e9.png)
![twitter_ _ _11-10_170701](https://user-images.githubusercontent.com/25688193/29312260-797df95a-81ef-11e7-98a7-f5c22dc9e4ce.png)
![twitter_ _ _11-11_170702](https://user-images.githubusercontent.com/25688193/29312261-797fd37e-81ef-11e7-83e2-f773db4fd494.png)


<a name="AdaBoost"></a>

## AdaBoost

![twitter_ _ _11-12_170703](https://user-images.githubusercontent.com/25688193/29312262-799d8018-81ef-11e7-8afe-a172cae63a6a.png)
![twitter_ _ _11-13_170703](https://user-images.githubusercontent.com/25688193/29312263-799eb1ea-81ef-11e7-8fc6-de627e6765f6.png)
![twitter_ _ _11-14_170704](https://user-images.githubusercontent.com/25688193/29312264-799ec8b0-81ef-11e7-94c0-3f08b73f6f16.png)
![twitter_ _ _11-15_170704](https://user-images.githubusercontent.com/25688193/29312267-79b2ac7c-81ef-11e7-9a4c-9073ca9835cf.png)
![twitter_ _ _11-16_170705](https://user-images.githubusercontent.com/25688193/29312266-79a33e72-81ef-11e7-9ab6-b82a0805f846.png)
![twitter_ _ _11-17_170705](https://user-images.githubusercontent.com/25688193/29312265-79a28d4c-81ef-11e7-803d-16d725fdba36.png)


<a name="バギング"></a>

## バギング [Bagging]

![twitter_ _ _11-18_170705](https://user-images.githubusercontent.com/25688193/29312269-79d30102-81ef-11e7-85a1-431e9a19fb61.png)
![twitter_ _ _11-19_170707](https://user-images.githubusercontent.com/25688193/29312268-79c1f1e6-81ef-11e7-941c-3f20fbdf74d9.png)


<a name="ランダムフォレスト"></a>

## ランダムフォレスト [Random Forests]

![twitter_ 22-1_170802](https://user-images.githubusercontent.com/25688193/29311827-e44f4970-81ed-11e7-9e51-b6acc9187b77.png)
![twitter_ 22-2_170802](https://user-images.githubusercontent.com/25688193/29311828-e454f2e4-81ed-11e7-8571-21ae4bb9e86c.png)
![twitter_ 22-3_170802](https://user-images.githubusercontent.com/25688193/29311830-e46150de-81ed-11e7-95c2-6748c43ce6a4.png)
![twitter_ 22-4_170803](https://user-images.githubusercontent.com/25688193/29311831-e46479c6-81ed-11e7-8a8c-81644dd09049.png)
![twitter_ 22-5_170803](https://user-images.githubusercontent.com/25688193/29311832-e4716686-81ed-11e7-9155-292b1f4ce17a.png)
![twitter_ 22-6_170804](https://user-images.githubusercontent.com/25688193/29311833-e473a6d0-81ed-11e7-8f89-2a07870dbd16.png)
![twitter_ 22-7_170804](https://user-images.githubusercontent.com/25688193/29311834-e477f2b2-81ed-11e7-9e69-5ccb947e2189.png)
![twitter_ 22-8_170804](https://user-images.githubusercontent.com/25688193/29311835-e48033be-81ed-11e7-8158-fda1df1da929.png)

