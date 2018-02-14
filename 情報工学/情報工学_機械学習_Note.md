# 機械学習 [Machine Learning]

機械学習に関してのマイノートです。今後も随時追加予定です。

![s_](https://user-images.githubusercontent.com/25688193/29311672-d5cb20c2-81ed-11e7-9c44-002fe0eb0873.png)

尚、本記事内容に関連した Python & scikit-learn ライブラリを用いた実装コード集は、以下の GitHub レポジトリにおいてあります。

- My GitHub
    - [Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn)


## 目次 [Contents]
1. [機械学習の概要 [Overview]](#ID_1)
    1. 全体 MAP 図
    1. [機械学習の基本的なタスク処理](#ID_1-2)
        1. 回帰のための機械学習
        1. 分類のための機械学習
        1. クラスタリングのための機械学習
    1. [学習の方法、種類](#ID_1-3)
        1. 教師あり学習 [supervised learning] と教師なし学習 [Unsupervised learning]
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
            1. [使用例 [example]](#ID_2-4-3-1)
        1. [特徴ベクトルの無相関化 [decorrelation]](#ID_2-4-4)
            1. [使用例 [example]](#ID_2-4-4-1)
        1. [特徴ベクトルの白色化 [whitening]](#ID_2-4-5)
    1. [特徴データの次元圧縮、特徴抽出](#ID_2-5)
        1. [主成分分析 [PCA : Principal Component Analysis]](#ID_2-5-1)
            1. [主成分分析（PCA）の分散最大化による定式化](#ID_2-5-1-1)
            1. [主成分分析（PCA）の誤差最小化による定式化](#ID_2-5-1-2)
            1. [使用例 [example]](#ID_2-5-1-3)
        1. [カーネル主成分分析 [kernel PCA : kernel Principal Component Analysis]](#ID_2-5-2)
            1. [使用例 [example]](#ID_2-5-2-1)
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
            1. [ROC曲線下面積 [AUC: area under ROC curve]](#ID_3-4-2-1)
            1. [ROC曲線と損失直線（最適な動作点の選択）](#ID_3-4-2-2)        
    1. [グリッドサーチに [grid search] よるモデルのハイパーパラメータのチューニング](#ID_3-7)
    1. [情報量基準[Information Criterion]](#ID_3-8)
        1. [AIC（赤池の情報量基準）[Akaike's Information Criterion]](#ID_3-8-1)
1. [確率モデルと識別関数 [discriminant function]](#ID_4)
    1. [確率モデル（パラメトリックモデル [parametric models]と、ノンパラメトリックモデル [non-parametric models]）](#ID_4-1)
    1. [識別規則 [idification rule]](#ID_4-2)
        1. [① 事後確率 [posterior probability] によるクラス分類法](#ID_4-2-1)
        1. [② 距離 [distance] によるクラス分類法](#ID_4-2-2)
        1. [③ 関数値 [function value] によるクラス分類法](#ID_4-2-3)
        1. [④ 決定木 [decision tree] によるクラス分類法](#ID_4-2-4)        
    1. [ベイスの識別規則 [Bayes's idification rule]](#ID_5-1)
        1. [ベイズの定理 [Bayes' theorem]](#ID_5-1-1)
        1. [ベイスの識別規則 [Bayes's idification rule]](#ID_5-1-2)
        1. [識別クラスの決定 [desicide identification class] と、尤度比（ゆうどひ） [likelihood ratio]](#ID_5-1-3)
        1. [ベイスの識別規則 [Bayes' identification rule] と誤り率最小化 [minimarize error rate]](#ID_5-1-4)
        1. [最小損失基準 [minimum loss standard] に基づくベイズの識別規則 [Bayes' identification rule]（損失を考慮に入れたベイズの識別規則）](#ID_5-1-5)
        1. [判断の留保（リジェクト） [decision of rejection]](#ID5-1-6)
        1. [使用例 [example]](#ID_5-1-7)    
    1. [正規分布関数と正規分布から導かれる識別関数](#ID_4-3)
        1. [使用例 [example]](#ID_4-3-1)
    1. [最大尤度法 [MLE：maximum likelihood estimation]による確率モデルのパラメータの推定](#4-4)
1. [線形判別分析 [LDA : liner discrinant analysis]](#ID_6)
    1. [線形識別関数 [liner discriminant function] でのクラス識別＜識別規則＞](#ID_6-1)
        1. [超平面 [hyper plabe] の方程式](#ID_6-1-1)
        1. [多クラスの識別問題への拡張](#ID_6-1-2)
        1. [使用例 [Examples]](#ID_6-1-3)
    1. [線形判別分析 [LDA : liner discrinant analysis] によるパラメータ推定](#ID_6-2)
        1. [判別分析法](#ID_6-2-1)
        1. [使用例 [Examples]](#ID_6-2-2)
1. [ロジスティクス回帰 [Logistic Regression]](#ID_7)
    1. [ロジスティック回帰 [logistic regression] による識別関数のパラメータ推定](#ID_7-1)
    1. [ロジスティック回帰モデル](#ID_7-2)
    1. [最尤度法によるロジスティック回帰モデル（確率モデル＜ノンパラメトリックモデル＞）のパラメータ推定 [MLE：maximum-likelihood estimation]](#ID_7-3)
        1. [L2 正則化による過学習への対応（評価関数への正則化項の追加）](#ID_7-3-1)
    1. [ロジスティック回帰 [logistic regression] による識別問題の多クラスへの拡張と、非線形変換 [no-liner transformation]、ガウス核関数 [Gaussian kernel function]](#ID_7-4)
    1. [使用例 [Examples]](#ID_7-5)
1. [最近接法, k-NN 法 [k-nearest neighbor algorithm]](#ID_8)
    1. [最近傍法 [nearest neighbor algorithm] とボロノイ境界 [Voronoi diagram]](#ID_8-1)
        1. [ボロノイ図 [Voronoi diagram]](#ID_8-1-1)
        1. [鋳型の数と識別性能](#ID_8-1-2)
        1. [使用例 [Examples]](#ID_8-1-3)
    1. [k最近傍法（k-NN法）[k-nearest neighbor algorithm]](#ID_8-2)
        1. [k-NN法 [k-nearest neighbor algorithm] での誤り発生のメカニズムとベイズ誤り率との関係](#ID_8-2-1)
        1. [k-NN法の計算量とその低減法](#ID_8-2-2)
        1. [使用例 [Examples]](#ID_8-2-3)
1. [サポートベクターマシン [SVM : Support Vector Machine]](#ID_9)
    1. [マージン [margin] とマージン最大化について](#ID_9-1)
    1. [サポートベクターマシン（SVM）[support vector machine] の導出](#ID_9-2)
        1. [線形分離可能な系における最適識別超平面とサポートベクトルによるマージン最大化 [margin maximization]](#ID_9-3)
        1. [マージン最大化 [margin maximization] と不等式制約条件凸最適化問題（数理計画法）[unconstrained convex optimization]](#ID_9-4)
            1. [KTT [Karush-Kuhn-Tucker] 条件](#ID_9-4-1)
    1. [データの分布が線形分離不可能な系への拡張（スラック変数の導入）とソフトマージン識別器（C-SVM）、その最適化問題](#ID_9-5)
        1. [サポートベクターマシンにおける非線形特徴写像</br>　＜カーネル関数、カーネル法 [kernel method] 、カーネルトリック　[kernel trick]＞](#ID_9-6)
            1. [多項式カーネル](#ID_9-6-1)
            1. [動径基底関数カーネル（RBFカーネル）[radial bases function kernel]](#ID_9-6-2)
        1. [使用例 [Examples]](#ID_9-7)
    1. [v-サポートベクターマシン（v-SVM）](#ID_9-8)
    1. [１クラスサポートベクターマシン](#ID_9-9)
1. [決定木 [Decision Tree]](#ID_10)
    1. [【補足】決定木に関しての諸定義（グラフ理論）](#ID_10-1)
    1. [【補足】決定木のノードの特徴空間のクラス分け（各種ノードの確率と識別クラス）](#ID_10-2)
    1. [ノードの分割規則と不純度 [purity]](#ID_10-3)
        1. [不純度 [purity] を表す代表的な関数](#ID_10-3-1)
    1. [木の剪定（せんてい） [pruning] アルゴリズムと過学習対策](#ID_10-4)
        1. [木の剪定アルゴリズム](#ID_10-4-1)
    1. [使用例 [Examples]](#ID_10-5)
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
    1. [ランダムフォレスト [random forests]](#ID_11-5)
        1. [ランダムフォレストの学習アルゴリズム](#ID_11-5-1)
        1. [ランダムフォレスト固有のデータ解析</br>（OBBランダムフォレスト固有のデータ解析（OOB 誤り率 [ out-of-bag error rate]、特徴の重要さ）](#ID_11-5-2)
1. [クラスター分析 [Clustering Analysis]](#ID_12)
    1. [標本化 [sapling] と量子化 [quantization]](#ID_12-1)
    1. [ベクトル量子化 [QV : quantization vector]](#ID_12-2)
        1. [k-means 法](#ID_12-2-1)
        1. [学習ベクトル量子化 [LQV : leaning quantization vector]](#ID_12-2-2)
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## 概要 [Overview]

<!--
<a id="ID_1-1"></a>

### ■ 全体 MAP 図
> 記載中...
-->

<a id="ID_1-2"></a>

### ■ 機械学習の基本的なタスク処理
機械学習は、大きく分けて以下の２つの問題設定＆解決のための手法に分けることが出来る。
1. 回帰問題の為の手法。（単回帰分析、重回帰分析、等）
2. （クラスの）分類問題の為の手法（SVM、k-NN、ロジスティクス回帰、等）
3. クラスタリング問題の為の手法（k-means法、等）

<!--
<a id="ID_1-2-1"></a>

#### ◎ 回帰のための機械学習
> 記載中...

<a id="ID_1-2-2"></a>

#### ◎ 分類のための機械学習
> 記載中...

<a id="ID_1-2-3"></a>

#### ◎ クラスタリングのための機械学習
> 記載中...

-->

<a id="ID_1-3"></a>

### ■ 学習の方法、種類

<!--
<a id="ID_1-3-1"></a>

#### ◎ 教師あり学習 [supervised learning] と教師なし学習 [Unsupervised learning]
> 記載中...
-->

<a id="ID_1-3-2"></a>

#### ◎ バッチ学習 [batch learning] とオンライン学習 [online learning]

##### ☆ バッチ学習 [batch processing]
一定量もしくは、一定期間データを集め、まとめて一括に学習を行う学習方式。<br>
より詳細には、<br>
**モデルの重みの更新を、各々のサンプルデータ毎に小刻みに行うでのはなく、トレーニングデータ・セット全てのサンプルに対して、一斉（一度）に行う。（バッチ処理）**<br>
最急降下法による学習などが、これに相当する。

![image](https://user-images.githubusercontent.com/25688193/36219334-588b8e7e-11fa-11e8-8501-7dd929942979.png)

##### ☆ オンライン学習 [batch processing]
データを一度に一斉に学習を行うバッチ学習とは異なり、<br>
新しいトレーニングデータが届いた際に、その場でモデルに対し、このサンプルでの追加の学習を随時行う学習方式。<br>
オンライン学習を用いれば、生じた変化に素早く適応させることができる。<br>
応用上において、これが特に役に立つのは、Webアプリケーションの顧客データなどの大量のデータを扱うケースである。<br>
確率的勾配法などがこれに相当する。

<a id="ID_1-3-3"></a>

#### ◎ 強化学習 [reinforcement learning]
**試行錯誤を通じて環境に適応する学習制御**の枠組である。<br>
教師有り学習とは異なり、状態入力に対する正しい行動出力を明示的に示す**教師データが存在しない。（教師なし学習）**<br>
そのかわりに、報酬というスカラーの情報を手がかりに学習するが、報酬にはノイズや遅れがある。<br>
そのため、行動を実行した直後の報酬をみるだけでは学習主体はその行動が正しかっ たかどうかを判断できないという困難を伴うヒューリスティックな手法。<br>
（※ ヒューリスティック：必ず正しい答えを導けるわけではないが、ある程度のレベルで正解に近い解を得ることができる方法。 ）<br>

![image](https://user-images.githubusercontent.com/25688193/36227166-8c318602-1213-11e8-8b3c-3f782300082f.png)

<a id="ID_1-3-4"></a>

#### ◎ アンサンブル学習 [ensemble learning]
各識別器を組み合わせて使用し、それらの識別器（弱識別器という）の投票結果（単純な多数決 or 重み付け後の多数決等）で最終的な判断を下す学習方法。</br>
様々な識別器を組み合わせて **多様性のある学習** を行うため、汎化性能が高く、又過学習 [overfitting] を起こしにくい。

- 実装コード
    - Python & scikit-learn ライブラリを用いた、機械学習における、アンサンブル学習のサンプルコード集。（練習プログラム）
        - https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/EnsembleLearning_scikit-learn)


---

<a id="ID_2"></a>

## ■ 機械学習の前処理 [pre processing]

- 実装コード
    - Python & scikit-learn ライブラリを用いた、機械学習における、データの前処理のサンプルコード集。（練習プログラム）
        - https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/DataPreProcess_scikit-learn


<a id="ID_2-1"></a>

### ■ 欠損値への対応

#### ◎ 欠損値 NaN を含むデータ
![image](https://user-images.githubusercontent.com/25688193/36221539-b672661e-1201-11e8-9502-f9493f036c95.png)

#### ◎ NaN の平均値補完
![image](https://user-images.githubusercontent.com/25688193/36221559-ccb5538c-1201-11e8-9c69-835575241de0.png)


<a id="ID_2-2"></a>

### ■ カテゴリデータ（名義 [nominal] 特徴量、順序 [ordinal] 特徴量）の処理
パターン認識は、対象を観測し、識別に有効な特徴を抽出することから始まるが、<br>
観測された特徴は、**非数値データとして抽出される定性的特徴 [qualitative feature]** と、**数値データとして抽出される定量的特徴 [quantitative feature]** に分類できる。<br>
定性的特徴と定量的特徴のデータは、更に下図のように型分類できる。<br>

![image](https://user-images.githubusercontent.com/25688193/36221978-315e9ba8-1203-11e8-9df3-d945d26f27a3.png)

尚、**定性的特徴を処理するためには、データの符号化を行う。**（例えば、２つのクラスラベルを表すために、"0と１"あるいは"-1と+1"のように符号化する。）


<a id="ID_2-3"></a>

### ■ データの分割

機械学習モデルの学習を行うためには、入力データとその該当するクラスを記述した学習データが必要になる。<br>
（※教師あり学習 [supervised learning] の場合 ）

クラスを指定したデータを教師データといい、<br>
２クラスの場合、出力 y の正負に対応した値<br>
![image](https://user-images.githubusercontent.com/25688193/36227244-cec6a272-1213-11e8-9b91-b9e2fea953b1.png) で表す。

クラス数が３つ以上の場合は、クラス数のビット幅を持ったダミー変数表現を用いて、<br>
例えば、<br>
![image](https://user-images.githubusercontent.com/25688193/36227262-defb05de-1213-11e8-92aa-2b24475ff295.png) のように表現する。（このような符号化方式をK対１符号化 [1-of-K coding] という。※尚、Kはクラス数を表している。）

そして、入力データと教師データのペアは、以下のように表す。<br>
![image](https://user-images.githubusercontent.com/25688193/36227290-f3d49be6-1213-11e8-9d44-d98e34537f91.png)

**学習に用いられるすべてのペアの集合を学習データセット [learning data set] と呼び**、
![image](https://user-images.githubusercontent.com/25688193/36227311-06da0604-1214-11e8-885e-7c66181201db.png) で表す。<br>

一方、**学習に使用しなかったデータは、テストデータセットとして、**
![image](https://user-images.githubusercontent.com/25688193/36227342-279e049e-1214-11e8-8e30-cc54489b72bd.png) **として、性能評価に使える。**


#### ◎ 学習データとテストデータの作り方とバイアス、誤り率
![image](https://user-images.githubusercontent.com/25688193/36227141-71aaf340-1213-11e8-9a32-62fb2bc62f46.png)

学習データセット ![image](https://user-images.githubusercontent.com/25688193/36227311-06da0604-1214-11e8-885e-7c66181201db.png) とテストデータセット ![image](https://user-images.githubusercontent.com/25688193/36227342-279e049e-1214-11e8-8e30-cc54489b72bd.png) は、手元にあるデータを分割して作ることになる。<br>
今、上図のように、<br>
とある識別対象（100円玉など）を、その母集団からN 個用意し、その内、L 個を学習用データに、T 個をテスト用データに使用する場合を考える。<br>
また、識別対象を識別するために d 個の特徴（１０円玉の重さ、透磁率など）が用いられているとする。<br>

すると、学習データセット ![image](https://user-images.githubusercontent.com/25688193/36227311-06da0604-1214-11e8-885e-7c66181201db.png) は、L 個の d 次元特徴ベクトルからなる集合<br>
　　　　テストデータセット ![image](https://user-images.githubusercontent.com/25688193/36227342-279e049e-1214-11e8-8e30-cc54489b72bd.png) は、T 個の d 次元特徴ベクトルからなる集合となる。<br>

それぞれの特徴ベクトルの d 次元空間内での分布関数を ![image](https://user-images.githubusercontent.com/25688193/36227441-6fb0ef9e-1214-11e8-9292-41fab46bbd0c.png) 及び ![image](https://user-images.githubusercontent.com/25688193/36227494-9121935e-1214-11e8-9a74-267f11de4970.png) で表すことにすれば、<br>
**この分布関数から、平均値、分散値などが計算できる！**<br>

しかしながら、<br>
学習データセットとテストデータセットは、**母集団からランダムに抽出されたもの**であるが、<br>
その分布関数 ![image](https://user-images.githubusercontent.com/25688193/36227441-6fb0ef9e-1214-11e8-9292-41fab46bbd0c.png) 及び ![image](https://user-images.githubusercontent.com/25688193/36227494-9121935e-1214-11e8-9a74-267f11de4970.png) の平均値や分散値が、母集団 ![image](https://user-images.githubusercontent.com/25688193/36227541-b0a2bf8c-1214-11e8-9be1-96f078702f9a.png) のそれと同じになるとは限らない。<br>
**この母集団とのズレをバイアス（偏り）[bias] という。**<br>

ここで、学習データセット ![image](https://user-images.githubusercontent.com/25688193/36227311-06da0604-1214-11e8-885e-7c66181201db.png) から算出し、テストデータセット ![image](https://user-images.githubusercontent.com/25688193/36227342-279e049e-1214-11e8-8e30-cc54489b72bd.png) を使用してテストしたときの誤り率を、![image](https://user-images.githubusercontent.com/25688193/36227588-dc2caa46-1214-11e8-8aab-0da039791a1e.png) で表すことにする。<br>
すると、**母集団の誤り率（真の誤り率）**は、![image](https://user-images.githubusercontent.com/25688193/36227622-fb819898-1214-11e8-90df-40fa50716a85.png) と表現でき、<br>
母集団の分布 ![image](https://user-images.githubusercontent.com/25688193/36227541-b0a2bf8c-1214-11e8-9be1-96f078702f9a.png) に従う学習データから算出し、母集団の分布 ![image](https://user-images.githubusercontent.com/25688193/36227541-b0a2bf8c-1214-11e8-9be1-96f078702f9a.png) に従うテスト用データを用いてテストしたときの誤り率を意味する。<br>

また、**母集団からサンプリングした学習データをテストデータとして再利用した場合の誤り率を、<br>
再代入誤り率 [resubstitution error]** といい、![image](https://user-images.githubusercontent.com/25688193/36227649-108df524-1215-11e8-8bf4-07fc36370f3a.png) で表現できる。<br>

<br>


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

<a id="ID_2-4-3-1"></a>

##### 使用例
![image](https://user-images.githubusercontent.com/25688193/30472452-66fe0986-9a37-11e7-8848-0acb11fdaba2.png)

<a id="ID_2-4-4"></a>

#### 特徴ベクトルの無相関化 [decorrelation]
![image](https://user-images.githubusercontent.com/25688193/30472530-d7244c02-9a37-11e7-9875-9eaf85293d03.png)
![image](https://user-images.githubusercontent.com/25688193/30472631-3ea0a9de-9a38-11e7-9d40-9c446b939362.png)

<a id="ID_2-4-4-1"></a>

##### 使用例
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

<a id="ID_2-5-1-3"></a>

##### 使用例 [example]
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

<a id="ID_2-5-2-1"></a>

##### 使用例 [example]
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

![image](https://user-images.githubusercontent.com/25688193/30488091-57814dcc-9a70-11e7-975d-3ee4128f04b1.png)
![image](https://user-images.githubusercontent.com/25688193/30488147-800bff9e-9a70-11e7-82cf-fd42bb07841d.png)
![image](https://user-images.githubusercontent.com/25688193/30488284-d57f28c0-9a70-11e7-977f-c1983dc9f83c.png)
![twitter_ 13-3_161229](https://user-images.githubusercontent.com/25688193/29311710-e0fc87ba-81ed-11e7-9644-49881177d910.png)

<a id="ID_3-4-2-1"></a>

##### ROC曲線下面積 [AUC: area under ROC curve]
![twitter_ 13-5_170101](https://user-images.githubusercontent.com/25688193/29311712-e1098ca8-81ed-11e7-9e67-5d2c57edd75b.png)

<a id="ID_3-4-2-2"></a>

##### ROC曲線と損失直線（最適な動作点の選択）
![twitter_ 13-8_170102](https://user-images.githubusercontent.com/25688193/29311715-e116b8a6-81ed-11e7-8716-53b612126a91.png)
![image](https://user-images.githubusercontent.com/25688193/30489579-8e703eea-9a72-11e7-9264-cc527a004d49.png)
![image](https://user-images.githubusercontent.com/25688193/30489407-1d00b668-9a72-11e7-9a16-53b0ec8044f7.png)
![image](https://user-images.githubusercontent.com/25688193/30489333-f37687aa-9a71-11e7-99b8-fb9e0c588789.png)

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
![image](https://user-images.githubusercontent.com/25688193/30489671-ce04d2a0-9a72-11e7-8fbb-b6e48a72c839.png)

<a id="ID_4-2-1"></a>

#### ① 事後確率 [posterior probability] によるクラス分類法
![image](https://user-images.githubusercontent.com/25688193/30489814-3991d27a-9a73-11e7-82f4-7e55cb1a684d.png)

<a id="ID_4-2-2"></a>

#### ② 距離 [distance] によるクラス分類法
![image](https://user-images.githubusercontent.com/25688193/30489838-4d3041d6-9a73-11e7-8312-807ed00ea38c.png)

<a id="ID_4-2-3"></a>

#### ③ 関数値 [function value] によるクラス分類法
![image](https://user-images.githubusercontent.com/25688193/30489861-61e02c4a-9a73-11e7-8274-665190c1ae7b.png)

<a id="ID_4-2-4"></a>

#### ④ 決定木 [decision tree] によるクラス分類法
![image](https://user-images.githubusercontent.com/25688193/30489783-24e8621c-9a73-11e7-9b29-d665432a09d5.png)


<a id="ID_5-1"></a>

### ベイスの識別規則 [Bayes's idification rule]

<a id="ID_5-1-1"></a>

#### ベイズの定理 [Bayes' theorem]
![image](https://user-images.githubusercontent.com/25688193/30490114-02dffbf2-9a74-11e7-9af9-67f815f580e7.png)
![image](https://user-images.githubusercontent.com/25688193/30490195-3bfc3748-9a74-11e7-9fe5-b9af826b4dc6.png)
![image](https://user-images.githubusercontent.com/25688193/30490231-53c1a71e-9a74-11e7-9db5-53c8cea412e4.png)

<a id="ID_5-1-2"></a>

#### ベイスの識別規則 [Bayes's idification rule]
![image](https://user-images.githubusercontent.com/25688193/30490276-73e7aae8-9a74-11e7-8ad7-37a37b9972c6.png)
![image](https://user-images.githubusercontent.com/25688193/30490319-90288d44-9a74-11e7-9226-5bef05457fc9.png)

<a id="ID_5-1-3"></a>

#### 識別クラスの決定 [desicide identification class] と、尤度比（ゆうどひ） [likelihood ratio]
![image](https://user-images.githubusercontent.com/25688193/30490354-a7340d88-9a74-11e7-945e-e5686128510b.png)

<a id="ID_5-1-4"></a>

#### ベイスの識別規則 [Bayes' identification rule] と誤り率最小化 [minimarize error rate]
![image](https://user-images.githubusercontent.com/25688193/30490414-d43f1160-9a74-11e7-85af-d3fb332aaa2d.png)
![image](https://user-images.githubusercontent.com/25688193/30490448-e9c2e5ca-9a74-11e7-9e6e-3a17fcef161c.png)
![image](https://user-images.githubusercontent.com/25688193/30490625-7716e66a-9a75-11e7-9d7f-af5389b29c50.png)

<a id="ID_5-1-5"></a>

#### 最小損失基準 [minimum loss standard] に基づくベイズの識別規則 [Bayes' identification rule]（損失を考慮に入れたベイズの識別規則）
![twitter_ 10-1_161005](https://user-images.githubusercontent.com/25688193/29311701-e0c33898-81ed-11e7-9611-8c5b4f8f3814.png)
![image](https://user-images.githubusercontent.com/25688193/30491167-5d998556-9a77-11e7-82bd-5ddff41662d7.png)
![image](https://user-images.githubusercontent.com/25688193/30491181-73c3f5dc-9a77-11e7-9678-a0b56495bd7a.png)
![twitter_ 10-3_161005](https://user-images.githubusercontent.com/25688193/29311702-e0d0d3b8-81ed-11e7-8b91-d142d7ed6e75.png)

<a id="ID_5-1-6"></a>

#### 判断の留保（リジェクト） [decision of rejection]
![image](https://user-images.githubusercontent.com/25688193/30490905-688c3554-9a76-11e7-809d-ae00a1910607.png)
![image](https://user-images.githubusercontent.com/25688193/30490934-874802b6-9a76-11e7-98b0-7b11bd9eabd6.png)
![twitter_ 11-3_161005](https://user-images.githubusercontent.com/25688193/29311705-e0e3ed86-81ed-11e7-9d70-c99072c0aaba.png)

<a id="ID_5-1-7"></a>

#### 使用例 [Examples]
![twitter_ 12-1_161004](https://user-images.githubusercontent.com/25688193/29311706-e0e44ce0-81ed-11e7-8238-3967e593dd27.png)
![twitter_ 12-2_161004](https://user-images.githubusercontent.com/25688193/29311707-e0e6588c-81ed-11e7-84c7-3635a2d8537d.png)


<a id="ID_4-3"></a>

### 正規分布関数と正規分布から導かれる識別関数
![twitter_ 20-2_170108](https://user-images.githubusercontent.com/25688193/29311796-e38bbff0-81ed-11e7-8035-58a67b9776c4.png)
![twitter_ 20-3_170109](https://user-images.githubusercontent.com/25688193/29311797-e38e38d4-81ed-11e7-81f6-94b34e68912a.png)

![twitter_ 20-5_170110](https://user-images.githubusercontent.com/25688193/29311799-e39b8476-81ed-11e7-962b-10f3f8d4f1a5.png)
![twitter_ 20-6_170110](https://user-images.githubusercontent.com/25688193/29311801-e3ac1ef8-81ed-11e7-992c-09bc4a17f929.png)
![twitter_ 20-7_170110](https://user-images.githubusercontent.com/25688193/29311800-e3ab980c-81ed-11e7-9bc8-f5072291d9a8.png)
![twitter_ 20-8_170116](https://user-images.githubusercontent.com/25688193/29311804-e3c1282a-81ed-11e7-87e7-0307b1562bb4.png)

<a id="ID_4-3-1"></a>

#### 使用例 [example]
![twitter_ 20-9_170116](https://user-images.githubusercontent.com/25688193/29311802-e3b24774-81ed-11e7-8274-86ad54b28f6c.png)


<a id="ID_4-3"></a>

### 最大尤度法 [MLE：maximum likelihood estimation]による確率モデルのパラメータの推定
![twitter_ 20-18_170127](https://user-images.githubusercontent.com/25688193/29311812-e3f16b0c-81ed-11e7-99ad-bc6ae4315238.png)





<a id="ID_6"></a>

## 線形判別分析 [LDA : liner discrinant analysis]

<a id="ID_6-1"></a>

### 線形識別関数 [liner discriminant function] でのクラス識別＜識別規則＞
![twitter_ 17-1_161113](https://user-images.githubusercontent.com/25688193/29311733-e188c93c-81ed-11e7-8622-5688879e3e06.png)

<a id="ID_6-1-1"></a>

#### 超平面 [hyper plane] の方程式
![twitter_ 17-2_161113](https://user-images.githubusercontent.com/25688193/29311734-e1926c08-81ed-11e7-94b1-47561b20d85e.png)
![twitter_ 17-3_161113](https://user-images.githubusercontent.com/25688193/29311735-e195289e-81ed-11e7-99a8-fa05260c9edf.png)

<a id="ID_6-1-2"></a>

#### 多クラスの識別問題への拡張
![twitter_ 17-4_161114](https://user-images.githubusercontent.com/25688193/29311736-e1964d96-81ed-11e7-8deb-967edb1100c6.png)
![twitter_ 17-5_161114](https://user-images.githubusercontent.com/25688193/29311738-e1a2a4f6-81ed-11e7-98a8-e354024e7cc5.png)
![twitter_ 17-6_161115](https://user-images.githubusercontent.com/25688193/29311739-e1ae8c6c-81ed-11e7-8e58-49521ca97f27.png)

<a id="ID_6-1-2"></a>

#### 最小２乗法によるパラメータ推定
![twitter_ 17-7_161115](https://user-images.githubusercontent.com/25688193/29311740-e1b50920-81ed-11e7-976b-1a3da2b5b471.png)
![twitter_ 17-8_161115](https://user-images.githubusercontent.com/25688193/29311741-e1b75784-81ed-11e7-939d-22af94e938d5.png)
![twitter_ 17-9_161116](https://user-images.githubusercontent.com/25688193/29311742-e1b9add6-81ed-11e7-8f7f-68cbfc635bc0.png)

<a id="ID_6-1-3"></a>

#### 使用例 [Example]
![twitter_ 17-10_1_171029](https://user-images.githubusercontent.com/25688193/29311743-e1cff5b4-81ed-11e7-992b-c26737ead99a.png)

<a id="ID_6-2"></a>

### 線形判別分析 [LDA : liner discrinant analysis] によるパラメータ推定
![twitter_ 17-10_161116](https://user-images.githubusercontent.com/25688193/29311746-e1d6ec70-81ed-11e7-8b9f-b969af491912.png)
![twitter_ 17-11_161116](https://user-images.githubusercontent.com/25688193/29311748-e1da7868-81ed-11e7-98a1-db01e60a5326.png)
![twitter_ 17-12_161116](https://user-images.githubusercontent.com/25688193/29311749-e1dcc848-81ed-11e7-89b6-22664d7f91c1.png)
![twitter_ 17-13_161118](https://user-images.githubusercontent.com/25688193/29311750-e1f338a8-81ed-11e7-80b3-3e5c1388350e.png)

<a id="ID_6-2-1"></a>

#### 判別分析法
![twitter_ 17-14_161123](https://user-images.githubusercontent.com/25688193/29311751-e1f55688-81ed-11e7-9a1a-4b695f9cb435.png)
![twitter_ 17-15_161123](https://user-images.githubusercontent.com/25688193/29311754-e20c28ea-81ed-11e7-8bdf-9750c373cc16.png)
![twitter_ 17-16_161123](https://user-images.githubusercontent.com/25688193/29311752-e1fae198-81ed-11e7-952b-bd56703e6c2c.png)

<a id="ID_6-2-2"></a>

#### 使用例 [Examples]
![twitter_ 17-20_170130](https://user-images.githubusercontent.com/25688193/29311755-e20f8198-81ed-11e7-8958-dec5c59f20e8.png)

![twitter_ 17-25_170201](https://user-images.githubusercontent.com/25688193/29311757-e281b0f6-81ed-11e7-8c1e-dde2a688c020.png)
![twitter_ 17-26_170202](https://user-images.githubusercontent.com/25688193/29311758-e2a378b2-81ed-11e7-9e85-cf8b274eb3c6.png)


<a id="ID_7"></a>

## ロジスティクス回帰 [Logistic Regression]

<a id="ID_7-1"></a>

### ロジスティック回帰 [logistic regression] による識別関数のパラメータ推定
![twitter_ 18-1_161130](https://user-images.githubusercontent.com/25688193/29311762-e2bffd52-81ed-11e7-8792-460a06fd85cb.png)
![twitter_ 18-2_161130](https://user-images.githubusercontent.com/25688193/29311763-e2c3934a-81ed-11e7-96df-d6efb0d753b7.png)

<a id="ID_7-2"></a>

### ロジスティック回帰モデル
![twitter_ 18-3_161130](https://user-images.githubusercontent.com/25688193/29311764-e2cb7c5e-81ed-11e7-817e-b7d8d12fe7d1.png)
![twitter_ 18-4_161130](https://user-images.githubusercontent.com/25688193/29311767-e2de1062-81ed-11e7-88a4-40c59a934d55.png)
![twitter_ 18-5_161201](https://user-images.githubusercontent.com/25688193/29311766-e2db6506-81ed-11e7-8462-d0d5054964e8.png)

<a id="ID_7-3"></a>

### 最尤度法によるロジスティック回帰モデル（確率モデル＜ノンパラメトリックモデル＞）のパラメータ推定 [MLE：maximum-likelihood estimation]
![twitter_ 18-6 _170204](https://user-images.githubusercontent.com/25688193/29311769-e2e22b16-81ed-11e7-93e2-9252b524a4e6.png)
![twitter_ 18-7 _170204](https://user-images.githubusercontent.com/25688193/29311772-e300ba54-81ed-11e7-8ea6-088f6f79d61c.png)
![image](https://user-images.githubusercontent.com/25688193/30485329-021346ae-9a68-11e7-81fa-88045b0a1a55.png)

<a id="ID_7-3-1"></a>

#### L2正則化による過学習への対応（評価関数への正則化項の追加）
![image](https://user-images.githubusercontent.com/25688193/30485372-2740792e-9a68-11e7-8123-1a31936bd633.png)

<a id="ID_7-4"></a>

### ロジスティック回帰 [logistic regression] による識別問題の多クラスへの拡張と、非線形変換 [no-liner transformation]、ガウス核関数 [Gaussian kernel function]
![twitter_ 18-8_170204](https://user-images.githubusercontent.com/25688193/29311771-e2feb470-81ed-11e7-9d6a-c55321d5764b.png)
![twitter_ 18-9_170208](https://user-images.githubusercontent.com/25688193/29311773-e30114ea-81ed-11e7-9dcd-9cd99ac926ee.png)
![twitter_ 18-10_170208](https://user-images.githubusercontent.com/25688193/29311774-e30526e8-81ed-11e7-80dd-75fe8fba875b.png)

<a id="ID_7-6"></a>

### 使用例 [Examples]
![twitter_ 18-11 _170210](https://user-images.githubusercontent.com/25688193/29311776-e31e2d14-81ed-11e7-8dc4-d3c01c7f46ba.png)
![twitter_ 18-12 _170210](https://user-images.githubusercontent.com/25688193/29311779-e3240d06-81ed-11e7-8f9e-61274ddbf738.png)
![twitter_ 18-13_170210](https://user-images.githubusercontent.com/25688193/29311778-e3239aba-81ed-11e7-9d57-2b3d620486be.png)
![twitter_ 18-14_170210](https://user-images.githubusercontent.com/25688193/29311780-e3286b9e-81ed-11e7-99d5-1dfc532da857.png)
![twitter_ 18-15_170210](https://user-images.githubusercontent.com/25688193/29311781-e32fea90-81ed-11e7-8464-c71a34d15ba3.png)
![twitter_ 18-16_170210](https://user-images.githubusercontent.com/25688193/29311782-e3411270-81ed-11e7-95f8-6e9b2798ced6.png)
![twitter_ 18-18_170726](https://user-images.githubusercontent.com/25688193/29311784-e3461bd0-81ed-11e7-80af-6c8404d6c0c6.png)
![twitter_ 18-19_170727](https://user-images.githubusercontent.com/25688193/29311785-e34831d6-81ed-11e7-93f0-0eb9400253dd.png)

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> ロジスティクス回帰の練習コード。scikit-learn ライブラリを使用。</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/LogisticRegression_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/LogisticRegression_scikit-learn)</br>



<a id="ID_8"></a>

## 最近接法, k-NN 法 [k-nearest neighbor algorithm]
![twitter_ 14-1_161007](https://user-images.githubusercontent.com/25688193/29311718-e12caecc-81ed-11e7-84d5-bc46932892c1.png)

<a id="ID_8-1"></a>

### 最近傍法 [nearest neighbor algorithm] とボロノイ境界 [Voronoi diagram]
![image](https://user-images.githubusercontent.com/25688193/30485865-af214a34-9a69-11e7-9a77-036e953569f9.png)

<a id="ID_8-1-1"></a>

#### ボロノイ図 [Voronoi diagram]
![image](https://user-images.githubusercontent.com/25688193/30485913-d5e9c5ce-9a69-11e7-99e3-2e67c213f381.png)
![twitter_ 14-3_161008](https://user-images.githubusercontent.com/25688193/29311720-e1365d46-81ed-11e7-8552-f97071578c18.png)
![twitter_ 14-4_161009](https://user-images.githubusercontent.com/25688193/29311721-e1397abc-81ed-11e7-893b-8850e2002a5b.png)

<a id="ID_8-1-2"></a>

#### 鋳型の数と識別性能
![twitter_ 14-5_161010](https://user-images.githubusercontent.com/25688193/29311722-e143c60c-81ed-11e7-90ac-3baab1fd30a9.png)

<a id="ID_8-1-3"></a>

#### 使用例 [Examples]
![twitter_ 15-1 _161221](https://user-images.githubusercontent.com/25688193/29311724-e14ee2bc-81ed-11e7-908b-2fa2cd4a8921.png)
![twitter_ 15-2 _161221](https://user-images.githubusercontent.com/25688193/29311726-e158ec12-81ed-11e7-81e1-32d918b2f08e.png)


<a id="ID_8-2"></a>

### k最近傍法（k-NN法）[k-nearest neighbor algorithm]
![twitter_ 16-1_161011](https://user-images.githubusercontent.com/25688193/29311727-e15eb1d8-81ed-11e7-8d5d-1308321d9d74.png)
![twitter_ 16-2_161012](https://user-images.githubusercontent.com/25688193/29311728-e166a5dc-81ed-11e7-9fd5-e24c61588dea.png)

![twitter_ 16-3_161111](https://user-images.githubusercontent.com/25688193/29311729-e16e9a4e-81ed-11e7-804b-2fbed8884257.png)
![twitter_ 16-4_161111](https://user-images.githubusercontent.com/25688193/29311730-e171a8f6-81ed-11e7-8c9c-8299c2e4ae42.png)

<a id="ID_8-2-1"></a>

#### k-NN法 [k-nearest neighbor algorithm] での誤り発生のメカニズムとベイズ誤り率との関係
![twitter_ 16-5_161112](https://user-images.githubusercontent.com/25688193/29311731-e1739ecc-81ed-11e7-9feb-6c1168aab9f8.png)
![twitter_ 16-6_161112](https://user-images.githubusercontent.com/25688193/29311732-e18010ee-81ed-11e7-9d3d-47877a66f994.png)

<a id="ID_8-2-2"></a>

#### k-NN法の計算量とその低減法
> 記載中...

<a id="ID_8-2-3"></a>

#### 使用例 [Examples]
![twitter_ 16-7_170729](https://user-images.githubusercontent.com/25688193/29311737-e199b45e-81ed-11e7-8685-98c52a6594b2.png)

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> k-NN 法の練習コード。scikit-learn ライブラリを使用。</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/kNN_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/kNN_scikit-learn)</br>



<a id="ID_9"></a>

## サポートベクターマシン [SVM : Support Vector Machine]
![twitter_svm_1-1_170211](https://user-images.githubusercontent.com/25688193/29311963-8c41480e-81ee-11e7-84a5-7ccfa0f2d724.png)

<a id="ID_9-1"></a>

### マージン [margin] とマージン最大化について
![twitter_svm_1-2_170211](https://user-images.githubusercontent.com/25688193/29311961-8c2d24e6-81ee-11e7-801a-f406b6007b04.png)

<a id="ID_9-2"></a>

### サポートベクターマシン（SVM）[support vector machine] の導出
![image](https://user-images.githubusercontent.com/25688193/30487135-7ce08e5a-9a6d-11e7-8636-0a43529094c6.png)

<a id="ID_9-3"></a>

#### 線形分離可能な系における最適識別超平面とサポートベクトルによるマージン最大化 [margin maximization]
![twitter_svm_2-1_170212](https://user-images.githubusercontent.com/25688193/29311964-8c41fbe6-81ee-11e7-89ba-6bbfe11dfc55.png)
![twitter_svm_2-2_170212](https://user-images.githubusercontent.com/25688193/29311962-8c4081b2-81ee-11e7-82d5-3ad978082b95.png)

<a id="ID_9-4"></a>

#### マージン最大化 [margin maximization] と不等式制約条件凸最適化問題（数理計画法）[unconstrained convex optimization]
![twitter_svm_3-1_170214](https://user-images.githubusercontent.com/25688193/29311966-8c42b464-81ee-11e7-966f-9ca1ea6fbc76.png)
![twitter_svm_3-2_170214](https://user-images.githubusercontent.com/25688193/29311965-8c427a26-81ee-11e7-9c3a-ea8ddd28d510.png)
![twitter_svm_3-3_170214](https://user-images.githubusercontent.com/25688193/29311967-8c4f9bca-81ee-11e7-8e69-e8cc8d7914ff.png)
![twitter_svm_3-4_170214](https://user-images.githubusercontent.com/25688193/29311968-8c6387e8-81ee-11e7-8906-9164dfa399ef.png)

<a id="ID_9-4-1"></a>

##### KTT [Karush-Kuhn-Tucker] 条件
![twitter_svm_3-5_170216](https://user-images.githubusercontent.com/25688193/29311969-8c644746-81ee-11e7-9bf9-8bbf6859ac72.png)

<a id="ID_9-5"></a>

### データの分布が線形分離不可能な系への拡張（スラック変数の導入）とソフトマージン識別器（C-SVM）、その最適化問題
![twitter_svm_4-1_170216](https://user-images.githubusercontent.com/25688193/29311971-8c6509d8-81ee-11e7-8488-31927efc6e3f.png)
![twitter_svm_4-2_170217](https://user-images.githubusercontent.com/25688193/29311970-8c64a7ae-81ee-11e7-868f-6ab7982ee83e.png)
![twitter_svm_4-3_170217](https://user-images.githubusercontent.com/25688193/29311972-8c661166-81ee-11e7-8361-7be24886064b.png)
![twitter_svm_4-4_170218](https://user-images.githubusercontent.com/25688193/29311973-8c716d5e-81ee-11e7-88f9-a76c020f1ae9.png)
![twitter_svm_4-5_170218](https://user-images.githubusercontent.com/25688193/29311974-8c8614e8-81ee-11e7-9f73-c08228309ecd.png)


<a id="ID_9-6"></a>

### サポートベクターマシンにおける非線形特徴写像</br>　＜カーネル関数、カーネル法 [kernel method] 、カーネルトリック　[kernel trick]＞
![twitter_svm_5-1_170219](https://user-images.githubusercontent.com/25688193/29311975-8c86acf0-81ee-11e7-9439-d245702b6a18.png)
![twitter_svm_5-2_170220](https://user-images.githubusercontent.com/25688193/29311977-8c87a916-81ee-11e7-9914-9744d08557c4.png)
![twitter_svm_5-2_170225](https://user-images.githubusercontent.com/25688193/29311976-8c86e2ba-81ee-11e7-87ec-5a1508130509.png)

<a id="ID_9-6-1"></a>

##### 多項式カーネル
![twitter_svm_5-3_170222](https://user-images.githubusercontent.com/25688193/29311978-8c897980-81ee-11e7-81e0-da923729128b.png)
![twitter_svm_5-4_170225](https://user-images.githubusercontent.com/25688193/29311979-8c93a130-81ee-11e7-8631-b7a12773ab50.png)

<a id="ID_9-6-2"></a>

##### 動径基底関数カーネル（RBFカーネル）[radial bases function kernel]
![twitter_svm_5-5_170303](https://user-images.githubusercontent.com/25688193/29311980-8ca849e6-81ee-11e7-9871-267853a4e608.png)
![twitter_svm_5-6_170303](https://user-images.githubusercontent.com/25688193/29311981-8ca89252-81ee-11e7-9d50-f97de95c69eb.png)

<a id="ID_9-7"></a>

#### 使用例 [Examples]
![twitter_svm_5-7_170305](https://user-images.githubusercontent.com/25688193/29311982-8ca99b66-81ee-11e7-8676-3ff2a6e792ca.png)
![twitter_svm_6-1_170728](https://user-images.githubusercontent.com/25688193/29311983-8caa804e-81ee-11e7-8d7a-31112a92a58f.png)
![twitter_svm_6-2_170728](https://user-images.githubusercontent.com/25688193/29311984-8cab9e84-81ee-11e7-88c3-102147c84341.png)
![twitter_svm_6-2 _170728](https://user-images.githubusercontent.com/25688193/29311985-8cb6430c-81ee-11e7-965b-ba1421d9ceb4.png)
![twitter_svm_6-3_170729](https://user-images.githubusercontent.com/25688193/29311986-8ccc025a-81ee-11e7-8097-6f1daf9e1a49.png)


<a id="ID_9-8"></a>

### v-サポートベクターマシン
>記載中...

</br>

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> サポートベクターマシンのサンプルコード集。（練習プログラム）scikit-learn ライブラリを使用。</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/SVM_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/SVM_scikit-learn)


<a id="ID_10"></a>

## 決定木 [Decision Tree]
![twitter_ 21-1_170730](https://user-images.githubusercontent.com/25688193/29311813-e3f36cc2-81ed-11e7-88aa-387bd4b36715.png)
![twitter_ 21-2_170730](https://user-images.githubusercontent.com/25688193/29311815-e3fc7bdc-81ed-11e7-9af6-a2cbb9d4af64.png)

<a id="ID_10-1"></a>

### 【補足】決定木に関しての諸定義（グラフ理論）
![twitter_ 21-3_170731](https://user-images.githubusercontent.com/25688193/29311814-e3fbf7ca-81ed-11e7-9837-1ab49a6c8827.png)

<a id="ID_10-2"></a>

### 【補足】決定木のノードの特徴空間のクラス分け（各種ノードの確率と識別クラス）
![twitter_ 21-5_170731](https://user-images.githubusercontent.com/25688193/29311817-e407558e-81ed-11e7-8ec3-a45393202903.png)
![twitter_ 21-6_170731](https://user-images.githubusercontent.com/25688193/29311816-e407481e-81ed-11e7-9566-4db88d64e241.png)

<a id="ID_10-3"></a>

### ノードの分割規則と不純度 [purity]
![twitter_ 21-7_170731](https://user-images.githubusercontent.com/25688193/29311820-e427e092-81ed-11e7-88d1-de7f469431f6.png)

<a id="ID_10-3-1"></a>

#### 不純度 [purity] を表す代表的な関数
![twitter_ 21-8_170801](https://user-images.githubusercontent.com/25688193/29311821-e428507c-81ed-11e7-8123-b9c4db7b12a4.png)

<a id="ID_10-4"></a>

### 木の剪定（せんてい） [pruning] アルゴリズムと過学習対策
![twitter_ 21-12_170802](https://user-images.githubusercontent.com/25688193/29311824-e43db656-81ed-11e7-9c1a-01f8f3554f01.png)

<a id="ID_10-4-1"></a>

#### 木の剪定アルゴリズム
![twitter_ 21-13_170802](https://user-images.githubusercontent.com/25688193/29311825-e44193ac-81ed-11e7-95e2-830f102cbbf0.png)
![twitter_ 21-14_170802](https://user-images.githubusercontent.com/25688193/29311829-e45cca5a-81ed-11e7-9e16-b9a66fa68715.png)
![twitter_ 21-15_170802](https://user-images.githubusercontent.com/25688193/29311826-e44e93c2-81ed-11e7-816d-23f42aead2b2.png)

### 使用例 [Examples]
![twitter_ 21-9_170801](https://user-images.githubusercontent.com/25688193/29311819-e41ebb70-81ed-11e7-9bbc-8bef4683006f.png)
![twitter_ 21-10_170801](https://user-images.githubusercontent.com/25688193/29311823-e432419a-81ed-11e7-93dc-0487eaeed1bd.png)
![twitter_ 21-11_170801](https://user-images.githubusercontent.com/25688193/29311822-e42adcde-81ed-11e7-9237-39c7fcefd100.png)

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> 決定木のサンプルコード集。（練習プログラム）scikit-learn ライブラリを使用。</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/DecisionTree_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/DecisionTree_scikit-learn)


<a id="ID_11"></a>

## アンサンブル学習 [ensemble learning]
各識別器を組み合わせて使用し、それらの識別器（弱識別器という）の投票結果（単純な多数決 or 重み付け後の多数決等）で最終的な判断を下す学習方法。</br>
様々な識別器を組み合わせて **多様性のある学習** を行うため、汎化性能が高く、又過学習 [overfitting] を起こしにくい。

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> アンサンブル学習のサンプルコード集。（練習プログラム）scikit-learn ライブラリを使用。</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/EnsembleLearning_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/EnsembleLearning_scikit-learn)</br>

<a id="ID_11-1"></a>

### 混合モデル [mixed model]
![twitter_ _ _11-1_170626](https://user-images.githubusercontent.com/25688193/30400845-382106c4-9913-11e7-8253-f11084f92847.png)

<a id="ID_11-1-1"></a>

#### 混合モデルによるモデル多様体の拡張
![image](https://user-images.githubusercontent.com/25688193/30415043-2ede325a-9961-11e7-865b-a209f11be7ec.png)

<a id="ID_11-1-1-1"></a>

##### 混合正規分布モデル [GMM : Gaussian Mixture Model]
![image](https://user-images.githubusercontent.com/25688193/30415111-846fb662-9961-11e7-80e4-abb1b1b9865f.png)

<a id="ID_11-1-1-2"></a>

##### 混合正規分布モデルの幾何学的観点
![image](https://user-images.githubusercontent.com/25688193/30415203-fcf52266-9961-11e7-979a-39f8fdf9d966.png)
![image](https://user-images.githubusercontent.com/25688193/30415230-1bee4c6a-9962-11e7-8f3c-a3357373c575.png)
![image](https://user-images.githubusercontent.com/25688193/30415375-c0b9178e-9962-11e7-8aa3-f88e7bd97a78.png)
![image](https://user-images.githubusercontent.com/25688193/30415398-d9c87a9e-9962-11e7-8244-0b5de3bcce16.png)
![twitter_ _ _11-5_170630](https://user-images.githubusercontent.com/25688193/30400846-38223ae4-9913-11e7-8ac3-d8851bc4d7ac.png)


<a id="ID_11-2"></a>

### EM アルゴリズム [expectation–maximization algorithm]
![twitter_ _ _11-6_170701](https://user-images.githubusercontent.com/25688193/30400850-3837c4fe-9913-11e7-95a6-70fec69c6a10.png)

<a id="ID_11-2-1"></a>

#### EM アルゴリズムの適用例
![image](https://user-images.githubusercontent.com/25688193/30416196-3f828700-9966-11e7-9e66-e02b69ec18ef.png)
![image](https://user-images.githubusercontent.com/25688193/30416221-5781ae8a-9966-11e7-90ba-373b4a2a3476.png)
![image](https://user-images.githubusercontent.com/25688193/30416156-102b22fa-9966-11e7-8d12-eb481dba881f.png)
![image](https://user-images.githubusercontent.com/25688193/30416174-25ed04b4-9966-11e7-9768-881625d9d656.png)

<a id="ID_11-2-2"></a>

#### EM アルゴリズムの幾何学的解釈
![image](https://user-images.githubusercontent.com/25688193/30415457-1a321702-9963-11e7-8922-1d9a10f55478.png)
![image](https://user-images.githubusercontent.com/25688193/30415473-311b90ce-9963-11e7-95a4-5eec3cc5fee0.png)
![image](https://user-images.githubusercontent.com/25688193/30415510-4f899a9c-9963-11e7-8e62-f1be5a2fb6ad.png)
![image](https://user-images.githubusercontent.com/25688193/30415534-696ec5ea-9963-11e7-8f78-00b9a2c8e9e0.png)


<a id="ID_11-3"></a>

### ブースティング [Boosting]、アダブースト [AdaBoost]
![image](https://user-images.githubusercontent.com/25688193/30401309-c15335d8-9914-11e7-990f-011187f57e63.png)

<a id="ID_11-3-1"></a>

#### アダブースト [AdaBoost]
![image](https://user-images.githubusercontent.com/25688193/30415636-d4ee38dc-9963-11e7-9090-28ffc5325dae.png)
![image](https://user-images.githubusercontent.com/25688193/30415665-0441c360-9964-11e7-8783-85cb1b27fd09.png)

<a id="ID_11-3-1-1"></a>

##### アダブーストの学習アルゴリズムの導出
![image](https://user-images.githubusercontent.com/25688193/30416003-7bf65b90-9965-11e7-9808-11de51cdb027.png)
![image](https://user-images.githubusercontent.com/25688193/30416046-962e982e-9965-11e7-88a4-d81bc4058bee.png)
![twitter_ _ _11-13_170703](https://user-images.githubusercontent.com/25688193/30400857-38676c4a-9913-11e7-9409-b5c9081c38a6.png)

<a id="ID_11-3-1-2"></a>

##### アダブーストの幾何学的解釈
![twitter_ _ _11-14_170704](https://user-images.githubusercontent.com/25688193/30400858-38686fe6-9913-11e7-85c1-e7ce2374513b.png)
![image](https://user-images.githubusercontent.com/25688193/30415807-ab48b664-9964-11e7-86de-2c300c3107ee.png)
![image](https://user-images.githubusercontent.com/25688193/30415837-d0222376-9964-11e7-8098-d53d03e3c62c.png)
![twitter_ _ _11-16_170705](https://user-images.githubusercontent.com/25688193/30400861-387c20ae-9913-11e7-8e09-ca1bd7b100fd.png)
![image](https://user-images.githubusercontent.com/25688193/30415878-fe5da328-9964-11e7-87ce-b3c66542e3d4.png)

<a id="ID_11-4"></a>

### バギング [Bagging]
![image](https://user-images.githubusercontent.com/25688193/30415910-2310251a-9965-11e7-8cb6-55434f78d045.png)
![image](https://user-images.githubusercontent.com/25688193/30415937-371b910c-9965-11e7-9171-0671ea3cfb96.png)

<a id="ID_11-4-1"></a>

#### バギングの幾何学的解釈
![twitter_ _ _11-19_170707](https://user-images.githubusercontent.com/25688193/30400863-388d60a8-9913-11e7-81b5-d2f6ddb2ab8f.png)


<a id="ID_11-5"></a>

### ランダムフォレスト [Random Forests]
![twitter_ 22-1_170802](https://user-images.githubusercontent.com/25688193/29311827-e44f4970-81ed-11e7-9e51-b6acc9187b77.png)

<a id="ID_11-5-1"></a>

#### ランダムフォレストの学習アルゴリズム
![twitter_ 22-2_170802](https://user-images.githubusercontent.com/25688193/29311828-e454f2e4-81ed-11e7-8571-21ae4bb9e86c.png)
![twitter_ 22-3_170802](https://user-images.githubusercontent.com/25688193/29311830-e46150de-81ed-11e7-95c2-6748c43ce6a4.png)
![twitter_ 22-4_170803](https://user-images.githubusercontent.com/25688193/29311831-e46479c6-81ed-11e7-8a8c-81644dd09049.png)
![twitter_ 22-5_170803](https://user-images.githubusercontent.com/25688193/29311832-e4716686-81ed-11e7-9155-292b1f4ce17a.png)

<a id="ID_11-5-2"></a>

#### ランダムフォレスト固有のデータ解析</br>（OBBランダムフォレスト固有のデータ解析（OOB 誤り率 [ out-of-bag error rate]、特徴の重要さ）
![twitter_ 22-6_170804](https://user-images.githubusercontent.com/25688193/29311833-e473a6d0-81ed-11e7-8f89-2a07870dbd16.png)
![twitter_ 22-7_170804](https://user-images.githubusercontent.com/25688193/29311834-e477f2b2-81ed-11e7-9e69-5ccb947e2189.png)
![twitter_ 22-8_170804](https://user-images.githubusercontent.com/25688193/29311835-e48033be-81ed-11e7-8158-fda1df1da929.png)


> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> ランダムフォレストのサンプルコード集。（練習プログラム）scikit-learn ライブラリを使用。</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/EnsembleLearning_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/RandomForests_scikit-learn)</br>



<a id="ID_12"></a>

## クラスター分析 [Clustering Analysis]

<a id="ID_12-1"></a>

### 標本化 [sapling] と量子化 [quantization]
![image](https://user-images.githubusercontent.com/25688193/30414801-3b212852-9960-11e7-964f-8ab4ef0f8846.png)

<a id="ID_12-2"></a>

### ベクトル量子化 [QV : quantization vector]
![image](https://user-images.githubusercontent.com/25688193/30414832-642e9298-9960-11e7-97c3-6fb0703ea9f7.png)

<a id="ID_12-2-1"></a>

#### k-means 法
![twitter_ _ _9-4_170623](https://user-images.githubusercontent.com/25688193/29311483-117f7628-81ed-11e7-927d-d69409eb61f3.png)

<a id="ID_12-2-2"></a>

#### 学習ベクトル量子化 [LQV : leaning quantization vector]
![twitter_ _ _9-5_170623](https://user-images.githubusercontent.com/25688193/29311485-118904ae-81ed-11e7-82b5-7cd3c5ca863d.png)

> 参考
>> My GitHub : Yagami360/MachineLearning_Exercises_Python_scikit-learn</br>
>> Python＆機械学習ライブラリ scikit-learn の使い方の練習コード集。機械学習の理論解説付き
>>> クラスター分析のサンプルコード集。（練習プログラム）。scikit-learn ライブラリを使用。</br>
>>> [MachineLearning_Exercises_Python_scikit-learn/ClusteringAnalysis_scikit-learn](https://github.com/Yagami360/MachineLearning_Exercises_Python_scikit-learn/tree/master/ClusteringAnalysis_scikit-learn)</br>

---

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

以下、同様の文献（はてなブログ形式）

<!-- はじめてのパターン認識 -->
[asin:4627849710:detail]

<!-- パターン認識と機械学習 上（ベイズ理論による統計的予測） -->
[asin:4621061224:detail]

<!-- パターン認識と機械学習 下（ベイズ理論による統計的予測） -->
[asin:4621061240:detail]

<!-- パターン認識と機械学習の学習普及版―ベイズ理論に負けないための数学 -->
[asin:4873100933:detail]

<!-- 情報理論の基礎―情報と学習の直観的理解のために (SGC Books) -->
[asin:4781912125:detail]

<!-- 言語処理のための機械学習入門 -->
[asin:4339027510:detail]

<!-- 情報数理の基礎と応用 (ライブラリ情報学コア・テキスト) -->
[asin:4781912109:detail]

<!-- Python機械学習プログラミング 達人データサイエンティストによる理論と実践 -->
[asin:B01HGIPIAK:detail]

<!-- Excelで学ぶ多変量解析―資料に隠れた大切な関係は多変量解析を駆使してあぶり出す -->
[asin:481633968X:detail]

<!-- 深層学習: Deep Learning -->
[asin:476490487X:detail]

<!-- 複素ニューラルネットワーク -->
[asin:B01GU5F48Q:detail]

<!-- TensorFlow機械学習クックブック Pythonベースの活用レシピ60+ -->
[asin:4295002003:detail]


