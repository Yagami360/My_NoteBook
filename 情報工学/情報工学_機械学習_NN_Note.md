# ニューラルネットワーク [NN :Neural Network] / ディープラーニング [Deep Learning]

ニューラルネットワーク、ディープラーニングに関してのマイノートです。今後も随時追加予定です。

This is my notebook that summarizes about "Neural Network" and "Deep Learning". 
I will add contents as needed.

![neuralnetworks](https://user-images.githubusercontent.com/25688193/30514787-10f19028-9b57-11e7-8091-de114932fd6a.png)

尚、本記事内容に関連した Python & tensorflow ライブラリを用いた実装コード集は、以下の GitHub レポジトリにおいてあります。
- [Yagami360/MachineLearning_Exercises_Python_TensorFlow](https://github.com/Yagami360/MachineLearning_Exercises_Python_TensorFlow)


## 目次 [Contents]
1. [概要 [Overview]](#ID_1)
    1. [全体 MAP 図](#ID_1-1)
    1. [ニューラルネットワークの概要](#ID_1-2)
    1. [ニューラルネットワークの主動作](#ID_1-3)
    1. [活性化関数 [activate functions]](#ID_1-4)
        1. [sigmoid, tanh, softsign](#ID_1-4-1)
        1. [Relu, Relu6, softplus, ELU](#ID_1-4-2)
            1. [ReLu 関数による勾配消失問題 [vanishing gradient problem] への対応と softmax 関数](#ID_1-4-2-1)
    1. [学習方法の分類](#ID_1-5)
        1. [教師あり学習 [supervised learning] と教師なし学習 [Unsupervised learning]](#ID_1-5-1)
        1. [バッチ学習 [batch learning] とオンライン学習 [online learning]](#ID_1-5-2)
        1. [強化学習 [reinforcement learning]](#ID_1-5-3)
        1. [転移学習 [transfer learning]](#ID_1-5-4)
    1. [ニューラルネットワークにおける損失関数（評価関数、誤差関数）](#ID_1-6)
        1. [① 回帰問題の為の損失関数（評価関数、誤差関数）](#ID_1-6-2)
        1. [② 分類問題の為の損失関数（評価関数、誤差関数）](#ID_1-6-2)
1. [パーセプトロン [Perceptron] <br>（階層型ニューラルネットワーク、フィードフォワード型構造）](#ID_2)
    1. [単純パーセプトロン [Simple perceptron]](#ID_2-1)
        1. [単層パーセプトロンのアーキテクチャ [architecture]](#ID_2-1-0)
        1. [誤り訂正学習 [error correction learning rule]（パーセプトロンの学習規則 [perceptron learing rule] ）<br>＜教師あり学習、オンライン学習＞](#ID_2-1-1)
            1. [使用例](#ID_2-1-1-1)
        1. [最急降下法 [gradient descent method] による学習（重みの更新）</br>＜教師あり学習、パッチ学習＞](#ID_2-1-2)
            1. [使用例](#ID_2-1-2-1)
        1. [確率的勾配降下法 [stochastic gradient descent method]](#ID_2-1-3)
            1. [使用例](#ID_2-1-3-1)
    1. [多層パーセプトロン [ MLP : Multilayer perceptron]](#ID_2-2)
        1. [多層パーセプトロンのアーキテクチャ [architecture]](#ID_2-2-0)
        1. [最急降下法 [gradient descent method] による学習（重みの更新）<br>＜教師あり学習、パッチ学習＞](#ID_2-2-1)
        1. [確率的勾配降下法 [stochastic gradient descent method] <br>＜教師あり学習、オンライン学習＞](#ID_2-2-2)
        1. [誤差逆伝播法（バックプロパゲーション）[Backpropagation]<br>＜教師あり学習、バッチ学習 or オンライン学習＞](#ID_2-2-3)
            1. 誤差逆伝播法の学習特性
                1. 初期化依存性
                1. 中間層のノードの数と識別能力
                1. 中間層の数（層の深さ）と識別能力
                1. 過学習と正則化
    1. [パーセプトロンによる論理演算](#ID_2-3)
    1. [パーセプトロンの収束定理](#ID_2-4)
1. [畳み込みニューラルネットワーク [CNN :Convolutional Neural Network]<br>＜階層型ニューラルネットワーク、フィードフォワード型構造＞](#ID_3)
    1. [畳み込みニューラルネットワークの基本アーキテクチャ](#ID_3-1)
    1. [畳み込み [convolution] 処理について](#ID_3-2)
        1. [畳み込みの数学的な一般的な定義](#ID_3-2-1)
        1. [畳み込みニューラルネットワークにおける畳み込み](#ID_3-2-2)
        1. [畳み込みニューラルネットワークにおける畳み込み処理の具体的な例（画像データとそのフィルタ処理）](#ID_3-2-3)
        1. [より一般化した畳み込み層のアーキテクチャの元での定式化](#ID_3-2-4)
        1. [受容野の観点から見た、畳み込み層](#ID_3-2-5)
    1. [プーリング [pooling] 処理について](#ID_3-3)
        1. [平均プーリング [average pooling]](#ID_3-3-1)
        1. [最大プーリング [max pooling]](#ID_3-3-2)
        1. [Lp プーリング [Lp pooling]](#ID_3-3-3)
    1. [THE ALL CONVOLUTIONAL NETWORK](#ID_3-4)
    1. CNN と 一般物体認識
        1. 局所特徴と大域特徴
    1. 一般物体認識を学習した CNN と転移学習
    1. タイル型畳み込み [Tiled convolution]<br>（プーリング層における移動不変性 [location invariant]の拡張）
    1. 逆畳み込みネットワーク [deconvolutional network]<br>（CNN の可視化）
    1. VGG-16
    1. VGG-19
    1. [ResNet（残差ネットワーク）](#ResNet（残差ネットワーク）)
1. [リカレントニューラルネットワーク [RNN : Recursive Neural Network]<br>＜階層型ニューラルネットワーク＞](#ID_4)
    1. [リカレントニューラルネットワークのアーキテクチャの種類](#ID_4-1)
        1. [隠れ層間で回帰構造をもつネットワーク](#ID_4-1-1)
            1. [通時的誤差逆伝搬法 [BPTT : back-propagation through time]](#ID_4-1-1-1)
        1. 教師強制と出力層間での回帰構造をもつネットワーク
    1. [長・短期記憶（LSTM [long short-term memory]）モデル](#ID_4-2)
        1. [CEC [constant error carousel]](#ID_4-2-1)
        1. [重み衝突 [weight conflict] と入力ゲート [input gate]、出力ゲート [output gate]](#ID_4-2-2)
        1. [忘却ゲート [forget gate]](#ID_4-2-3)
        1. [覗き穴結合 [peephole connections]](#ID_4-2-4)
        1. [LSTM モデルの定式化](#ID_4-2-5)
    1. [GRU [gated recurrent unit]](#ID_4-3)
    1. [双方向 RNN [BiRNN : Bidirectional RNN]](#ID_4-4)
    1. [RNN Encoder-Decoder (Seqenence-to-sequence models)](#ID_4-5)
    1. [Attention](#ID_4-6)
        1. [LSTM を使用した場合の Attention](#ID_4-6-1)
1. 連想記憶ネットワーク（ホップフィールドネットワーク [Hopfield network] ）</br>(相互結合型ニューラルネットワーク [mutual connected neural networks]）)
1. 系列変換モデル [Sequence-to-Sequence model/seq2seq]
    1. RNN Encoder-Decoder
    1. [（外部リンク）Attention](http://yagami12.hatenablog.com/entry/2017/12/30/175113#ID_10-6)
    1. [（外部リンク）Memory Networks [MemN]](http://yagami12.hatenablog.com/entry/2017/12/30/175113#ID_10-7)
1. [生成モデル [generative model]](#ID_10)
    1. [GAN [Generative Adversarial Network]（敵対的ネットワーク）](#ID_10-1)
        1. [DCGAN [Deep Convolutional GAN]](#ID_10-1-1)
    1. VAE [Variational Autoencoder]
1. [ニューラルネットワーク、ディープラーニングによる物体検出 [object detection]](#ID_11)
    1. R-CNN
    1. Faster R-CNN
    1. [SSD [Single Shot muitibox Detecter]（単発検出器）](#ID_11-4)
    1. YOLO
        1. YOLO v1
        1. YOLO v2
1. [（外部リンク）ニューラルネットワーク、ディープラーニングによる自然言語処理（NLP）](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E8%87%AA%E7%84%B6%E8%A8%80%E8%AA%9E%E5%87%A6%E7%90%86_Note.md)
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## 概要 [Overview]

<a id="ID_1-1"></a>

### 全体 MAP図
![image](https://user-images.githubusercontent.com/25688193/34352847-44ef0fda-ea68-11e7-90c9-2a2c10f7a8a4.png)
![image](https://user-images.githubusercontent.com/25688193/34352981-eaa7eef6-ea68-11e7-8477-99d8bdfb3213.png)
![image](https://user-images.githubusercontent.com/25688193/34352889-7771a896-ea68-11e7-8e0c-39352581f62b.png)

<a id="ID_1-2"></a>

### ニューラルネットワークの概要
![twitter_nn1_1_160825](https://user-images.githubusercontent.com/25688193/30112643-09c7ef7a-934d-11e7-91d2-fcc93505baa0.png)
![twitter_nn1_2_160825](https://user-images.githubusercontent.com/25688193/30112644-09c88430-934d-11e7-9450-6d4861190175.png)

<a id="ID_1-3"></a>

### ニューラルネットワークの主動作
![twitter_nn3 -1_160827](https://user-images.githubusercontent.com/25688193/30112645-09c8e42a-934d-11e7-95f9-87e0ca316b2f.png)

ニューラルネットワーク、より広義には機械学習は、</br>
大きく分けて以下の３つの問題設定＆解決のための手法に分けることが出来る。</br>
① 回帰問題の為の手法。（単回帰分析、重回帰分析、等）</br>
② （クラスの）分類問題の為の手法（SVM、k-NN、ロジスティクス回帰、等）</br>
③ クラスタリング問題の為の手法（k-means法、等）

<a id="ID_1-4"></a>

### 活性化関数 [activate functions]
> 修正中...
![twitter_nn2-1_160826](https://user-images.githubusercontent.com/25688193/30112640-09b4803e-934d-11e7-993d-4e35263cda81.png)
![twitter_nn2-2_160826](https://user-images.githubusercontent.com/25688193/30112641-09b5d6d2-934d-11e7-861d-06792890d2f9.png)

<a id="ID_1-4-1"></a>

#### sigmoid, tanh, softsign
活性化関数のグラフ１
> 活性化関数の内、sigmoid, tanh, softsign 関数の図
![processingformachinelearning_tensorflow_1-2](https://user-images.githubusercontent.com/25688193/30211949-e16ce07a-94dd-11e7-9562-6d121aeeb59e.png)

<a id="ID_1-4-2"></a>

#### Relu, Relu6, softplus, ELU
活性化関数のグラフ２
> 活性化関数の内、Relu, Relu6, softplus, ELU 関数の図
![processingformachinelearning_tensorflow_1-1](https://user-images.githubusercontent.com/25688193/30203903-ac94e5ec-94be-11e7-867f-fc78b059ef44.png)

ReLu関数（ランプ関数）は、x=0 にて非連続で微分不可能な関数であるが、その他の領域では微分可能なので、ニューラルネットワークにおいては、微分可能な活性化関数として取り扱われることが多い。<br>
そして、この ReLu は、勾配が一定なので、ディープネットワークにおける学習アルゴリズムにおいて発生する、勾配損失問題 [vanishing gradient problem] に対応することが出来るのが最大の利点である。（後述）

<a id="ID_1-4-2-1"></a>

##### ReLu 関数による勾配消失問題 [vanishing gradient problem] への対応と softmax 関数
勾配消失問題 [vanishing gradient problem] とは、ニューラルネットワークの層が深くなるにつれて、誤差逆伝播法等の学習の際に損失関数の勾配（傾き）が 0 に近くなり、入力層に近い層で入出力誤差が消失してしまい、結果として、うまく学習（重みの更新）ができなくなるような問題である。<br>

この問題に対応するために開発されたのが、ReLU [rectified linear unit] や MaxOut という活性化関数である。<br>
これらの活性化関数では、勾配（傾き）が一定なので、誤差消失問題を起こさない。従って、深い層のネットワークでも学習が可能となり、現在多くのニューラルネットワークで採用されている。<br>

但し、これらの活性化関数を通して出力される値は、先に示したグラフのように負の値が出てきたりと、そのままでは扱いづらい欠点が存在する。

従って、softmax 関数を通じて出力を確率に変換するようにする。
この softmax 関数の式は以下のように与えられる。

```math
y_i=\dfrac{e^{x_i}}{e^{x_1}+e^{x_2}+\cdots +e^{x_n}}
```

![image](https://user-images.githubusercontent.com/25688193/30590115-37a895ae-9d78-11e7-9012-50cc868b6321.png)

> 参考サイト : [画像処理とか機械学習とか / Softmaxって何をしてるの？](http://hiro2o2.hatenablog.jp/entry/2016/07/21/013805)

##### 【Memo】softmax 関数と統計力学での分配関数の繋がり
ニューラルネットワークの softmax 関数の形は、<br>
統計力学で言う所のカノニカルアンサンブルでの sub system の微視的状態を与える確率の式<br>

![image](https://user-images.githubusercontent.com/25688193/31034610-bfe29f12-a59f-11e7-8d90-6541e8fa216c.png)

<!--
$$ P_n = \dfrac{ e^{\frac{E_n}{k_B T}} }{ \sum_{i=1}^{n} e^{ \frac{E_i}{k_B \times T } } } $$
-->

<!-- はてなブログ形式
[tex:{ P_n = \dfrac{ e^{\frac{E_n}{k_B T}} }{ \sum_{i=1}^{n} e^{ \frac{E_i}{k_B \times T } }  } } ]
-->

の形に対応している。<br>

この確率の式の分母を統計力学では分配関数<br>

![image](https://user-images.githubusercontent.com/25688193/31034696-21d2f636-a5a0-11e7-9f6d-81de5b7f9f39.png)<br>

<!--
$$ Z = \sum_{i=1}^{n} e^{ \frac{-E_i}{k_B \times T} } $$
-->

<!-- はてなブログ形式
[tex:{ Z = \sum_{i=1}^{n} e^{ \frac{-E_i}{k_B \times T} }　}]<br>
-->

といい重要な意味を持つが、これは、エントロピー最大化に繋がる話しであり、<br>

Helmholtz の自由エネルギーは、この分配関数 Z を用いて、<br>

![image](https://user-images.githubusercontent.com/25688193/31034742-51e4a0ae-a5a0-11e7-8d87-704124ad5467.png)<br>

<!--
$$ F = - k_B \times T \times log_e{Z} $$<br>
-->

<!-- はてなブログ形式
[tex:{ F = - k_B \times T \times \log_e Z }]<br>
-->

で表現できるけど、これを使えば、カノニカルアンサンブルのエントロピー S が<br>

![image](https://user-images.githubusercontent.com/25688193/31034868-dba484e4-a5a0-11e7-85fe-ba7d5e011a04.png)<br>

<!--
$$ S = - k_B \times \sum_{i=1}^{n} P_i \times \log_e{P_i} $$<br>
-->

<!-- はてなブログ形式
[tex:{ S = - k_B \times \sum_{i=1}^{n} P_i \times \log_e P_i }]<br>
-->

と書ける。これはまさに、情報理論でいうとこのシャノンの情報量に対応している。<br>


<a id="ID_1-5"></a>


### 学習方法の分類

<a id="ID_1-5-1"></a>

#### 教師あり学習 [supervised learning] と教師なし学習 [Unsupervised learning]

![image](https://user-images.githubusercontent.com/25688193/30948617-1cb9a46a-a44c-11e7-824b-1f0f23f6780a.png)<br>

<a id="ID_1-5-2"></a>

#### バッチ学習 [batch processing] とオンライン学習 [online learning]
![image](https://user-images.githubusercontent.com/25688193/30580233-c7f83474-9d56-11e7-8a0f-38a54892e3d0.png)

<a id="ID_1-5-3"></a>

#### 強化学習 [reinforcement learning]
![image](https://user-images.githubusercontent.com/25688193/30580261-dd196eea-9d56-11e7-8ae6-6f2df8557307.png)

<a id="ID_1-5-4"></a>

#### 転移学習 [transfer learning]
![image](https://user-images.githubusercontent.com/25688193/30949112-85641f60-a44f-11e7-9430-a0a2fd068e1e.png)

<a id="ID_1-6"></a>

### ニューラルネットワークにおける損失関数（評価関数、誤差関数）

損失関数（評価関数、誤差関数）は、モデルの出力と目的値（真の値、教師データ）との差（いいえ変えれば、誤差、距離）を計測する関数であり、モデルの学習に適用されるものである。</br>

ここで、ニューラルネットワーク、より広義には機械学習は、</br>
大きく分けて以下の２つの問題設定＆解決のための手法に分けることが出来た。</br>
① 回帰問題の為の手法。（単回帰分析、重回帰分析、等）</br>
② （クラスの）分類問題の為の手法（SVM、k-NN、ロジスティクス回帰、等）</br>
③ クラスタリング問題の為の手法（k-means法、等）

従って、損失関数も同様にして、回帰問題の為の損失関数と、分類問題の為の損失関数が存在することになる。

<a id="ID_1-6-1"></a>

##### ① 回帰の為の、損失関数（L2正則化、L1正則化）
![processingformachinelearning_tensorflow_2-1](https://user-images.githubusercontent.com/25688193/30248461-2ed858f4-9663-11e7-9e1e-880bd99ca0c7.png)

- L2 正則化の損失関数は、目的値への距離の２乗で表されるので、下に凸な２次関数の形状をしており、</br>
  目的値（この場合 0）の近くで急なカーブを描く。</br>
  この特性が、損失関数と扱う際に優れているのが特徴である。
- L1 正則化の損失関数は、目的値への距離の絶対値で表される損失関数である。</br>
  その為、目的値（この場合 0）からのズレが大きくなっても（ズレの大きなに関わらず）、その傾き（勾配）は一定である。</br>
  その為、L1 正則化は L2 正則化よりも、外れ値にうまく対応するケースが多いのが特徴である。</br>
  又、目的値（この場合 0）にて、関数が連続でないために、対応するアルゴリズムがうまく収束しないケースが存在することに注意が必要となる。

<a id="ID_1-6-2"></a>

##### ② 分類問題の為の損失関数（評価関数、誤差関数）
クラスの分類問題の為の損失関数は、現在の学習結果が与えられたデータに対してどの程度「良い感じなのか」を定量化するために使われる。（誤差逆伝播法時の計算等）<br>
分類問題でのニューラルネットワークの最終結果は、例えば２クラスの分類問題の場合、正解は -1 or 1（又は 0 or 1）の負例と正例となる。従って、損失関数による損失は、連続な値ではなく sign 化したもの 、即ち正解ラベルと、ニューラルネットワークの出力の符号が一致しているならば損失は 0（＝分類が成功）であり、符号が一致していなければ損失は 1 となる。
![processingformachinelearning_tensorflow_2-2](https://user-images.githubusercontent.com/25688193/30594195-2d46c742-9d88-11e7-8989-585977c7865b.png)


---

<a id="ID_2"></a>

## パーセプトロン [Perceptron] </br>（階層型ニューラルネットワーク、フィードフォワード型構造）

<a id="ID_2-1"></a>

### 単純パーセプトロン [Simple perceptron]

<a id="ID_2-1-0"></a>

#### 単層パーセプトロンのアーキテクチャ [architecture]
> 修正中...
![twitter_nn4 -1_160829](https://user-images.githubusercontent.com/25688193/30112642-09b65e90-934d-11e7-9cac-2472c4add901.png)

<a id="ID_2-1-1"></a>

#### 誤り訂正学習 [error correction learning rule]（パーセプトロンの学習規則 [perceptron learing rule] ）</br>＜教師あり学習、オンライン学習＞
![image](https://user-images.githubusercontent.com/25688193/30771972-171532fc-a08e-11e7-86ab-663fd81fbb75.png)
![image](https://user-images.githubusercontent.com/25688193/30772185-7c0aca0c-a091-11e7-8a22-f258792b99df.png)
![image](https://user-images.githubusercontent.com/25688193/30772194-922be5fa-a091-11e7-8f35-26f52b029e14.png)

<a id="ID_2-1-1-1"></a>

##### 使用例
![image](https://user-images.githubusercontent.com/25688193/30742460-1416beaa-9fd4-11e7-8fc0-2b7e565bf036.png)

<a id="ID_2-1-2"></a>

#### 最急降下法 [gradient descent method] による学習（重みの更新）</br>＜教師あり学習、パッチ学習＞
![image](https://user-images.githubusercontent.com/25688193/30624595-3a3797da-9df9-11e7-95eb-5edb913e080f.png)
![image](https://user-images.githubusercontent.com/25688193/30772096-ec426f7a-a08f-11e7-8fa6-47ce74a29bb9.png)
![image](https://user-images.githubusercontent.com/25688193/30772213-fbeaeaa4-a091-11e7-8838-e8ceccc4b96e.png)
![image](https://user-images.githubusercontent.com/25688193/30772274-78479b3c-a093-11e7-8f6b-6b7ed6c29751.png)

<a id="ID_2-1-2-1"></a>

##### 使用例
![image](https://user-images.githubusercontent.com/25688193/30742859-23c08942-9fd6-11e7-98e8-22925e2c7739.png)
![image](https://user-images.githubusercontent.com/25688193/30742886-46c8a88e-9fd6-11e7-88f0-fbd11f418483.png)

![image](https://user-images.githubusercontent.com/25688193/30743071-086eb712-9fd7-11e7-83d4-cc59e6ac1995.png)
![image](https://user-images.githubusercontent.com/25688193/30743081-1b63c196-9fd7-11e7-86f5-879868f4aed1.png)

<a id="ID_2-1-3"></a>

#### 確率的勾配降下法 [stochastic gradient descent method]
![image](https://user-images.githubusercontent.com/25688193/30772388-ac53aa3c-a094-11e7-80f2-28703a2931b8.png)
![image](https://user-images.githubusercontent.com/25688193/30772400-d949d8e0-a094-11e7-8d31-87ebc9e8913e.png)

<a id="ID_2-1-3-1"></a>

##### 使用例
![image](https://user-images.githubusercontent.com/25688193/30743175-85b4ecbe-9fd7-11e7-9e02-6b3ee77e52ea.png)
![image](https://user-images.githubusercontent.com/25688193/30743188-951dcc7a-9fd7-11e7-80ca-4b8f2c25717e.png)
![image](https://user-images.githubusercontent.com/25688193/30743212-a8f8eb4e-9fd7-11e7-9c34-61753d36105f.png)


<a id="ID_2-2"></a>

### 多層パーセプトロン [ MLP : Multilayer perceptron]

<a id="ID_2-2-0"></a>

#### 多層パーセプトロンのアーキテクチャ [architecture]
![image](https://user-images.githubusercontent.com/25688193/30770644-c6575a60-a070-11e7-9a4b-c31a0743abf7.png)
![image](https://user-images.githubusercontent.com/25688193/30770558-ed0b3fe8-a06e-11e7-99b9-15278ee6f60e.png)
![image](https://user-images.githubusercontent.com/25688193/30760907-32b178f8-a017-11e7-8605-b087b92c9442.png)
![image](https://user-images.githubusercontent.com/25688193/30770651-e0155c40-a070-11e7-94b4-9fa49980ff91.png)
![image](https://user-images.githubusercontent.com/25688193/30761470-541ad50a-a019-11e7-8ece-b0cf55e14cee.png)
> 【参考 URL】softmax関数について
>> https://mathtrain.jp/softmax<br>
>> http://s0sem0y.hatenablog.com/entry/2016/11/30/012350<br>

![image](https://user-images.githubusercontent.com/25688193/30770538-6591cad2-a06e-11e7-9440-290d3957af7e.png)
![image](https://user-images.githubusercontent.com/25688193/30770761-e01c8a26-a073-11e7-9e49-fc70a23bd63d.png)

![image](https://user-images.githubusercontent.com/25688193/30748067-111c05b4-9fea-11e7-8841-f6e9029ea2b4.png)

<a id="ID_2-2-1"></a>

#### 最急降下法 [gradient descent mesod] による学習（重みの更新）<br>＜教師あり学習、パッチ学習＞
![image](https://user-images.githubusercontent.com/25688193/30624595-3a3797da-9df9-11e7-95eb-5edb913e080f.png)
![image](https://user-images.githubusercontent.com/25688193/30772455-74ac9e16-a096-11e7-99b4-69618fdd8ab8.png)
![image](https://user-images.githubusercontent.com/25688193/30778507-db5903a8-a112-11e7-8a5e-65e356aa2a3c.png)
![image](https://user-images.githubusercontent.com/25688193/30778884-6f95d782-a11b-11e7-8e2d-885da200a2bf.png)
![image](https://user-images.githubusercontent.com/25688193/30778895-b24e28c2-a11b-11e7-8b5a-6a4129206fd1.png)
![image](https://user-images.githubusercontent.com/25688193/30778967-6d01b3ae-a11d-11e7-9ea7-f86b5a6dfeae.png)
![image](https://user-images.githubusercontent.com/25688193/30772701-111084a2-a09c-11e7-939e-d3f5a2198157.png)

<a id="ID_2-2-2"></a>

#### 確率的勾配降下法 [stochastic gradient descent method] <br>＜教師あり学習、オンライン学習＞
![image](https://user-images.githubusercontent.com/25688193/30773009-98407c24-a0a2-11e7-8e94-2bad0b818786.png)
![image](https://user-images.githubusercontent.com/25688193/30773013-a883396e-a0a2-11e7-867e-ad3e9e34188b.png)

<a id="ID_2-2-3"></a>

#### 誤差逆伝播法（バックプロパゲーション）[Backpropagation] <br>＜教師あり学習、バッチ学習 or オンライン学習＞
![image](https://user-images.githubusercontent.com/25688193/30778562-c4fc9074-a113-11e7-9df5-3af84b3e26fb.png)
![image](https://user-images.githubusercontent.com/25688193/30778693-392d659c-a117-11e7-9a2c-8658144bc5f2.png)
![image](https://user-images.githubusercontent.com/25688193/30778686-14bd91be-a117-11e7-8a16-e1651534fc32.png)
![image](https://user-images.githubusercontent.com/25688193/30779065-4543fc84-a120-11e7-82af-8028fa8e05ef.png)
![image](https://user-images.githubusercontent.com/25688193/30779458-65f39640-a12c-11e7-848a-fb9cd82e2248.png)

![image](https://user-images.githubusercontent.com/25688193/30780761-9f2678bc-a14d-11e7-8dfb-7e3d5e8591e9.png)
![image](https://user-images.githubusercontent.com/25688193/30846403-832289f4-a2d2-11e7-9dc7-2842bba5abf9.png)
![image](https://user-images.githubusercontent.com/25688193/30850059-4522b9aa-a2df-11e7-87b2-77b4b689dfd4.png)



<a id="ID_2-3"></a>

### パーセプトロンによる論理演算
![twitter_nn6-1_160829](https://user-images.githubusercontent.com/25688193/30112770-703f5f68-934d-11e7-845d-be2240ef4d17.png)
![twitter_nn6-2_160829](https://user-images.githubusercontent.com/25688193/30112772-7042419c-934d-11e7-9330-d8292a108c1c.png)

<a id="ID_2-4"></a>

### パーセプトロンの収束定理
パーセプトロンの学習は、** 線形分離可能な問題であれば、有限回の学習の繰り返しにより収束する ** ことが証明されている。<br>
このことをパーセプトロンの収束定理と呼ぶ。

<br>

---

<a id="ID_3"></a>

## 畳み込みニューラルネットワーク [CNN :Convolutional Neural Network]<br>＜階層型ニューラルネットワーク、フィードフォワード型構造＞
![image](https://user-images.githubusercontent.com/25688193/33005129-ca12465a-ce07-11e7-8393-3726b8c5eaf4.png)
![image](https://user-images.githubusercontent.com/25688193/30904563-47b0fd48-a3ad-11e7-8d6c-c1f3c2751131.png)

<a id="ID_3-1"></a>

### 畳み込みニューラルネットワークの基本アーキテクチャ
> 記載中...

<a id="ID_3-2"></a>

### 畳み込み [convolution] 処理について

<a id="ID_3-2-1"></a>

#### 畳み込みの数学的な一般的な定義
![image](https://user-images.githubusercontent.com/25688193/30863721-af4cee86-a30c-11e7-8d6d-b47244badc03.png)

<a id="ID_3-2-2"></a>

#### 畳み込みニューラルネットワークにおける畳み込み
![image](https://user-images.githubusercontent.com/25688193/30867484-0d67583a-a317-11e7-9740-d2449e794990.png)

<a id="ID_3-2-3"></a>

#### 畳み込みニューラルネットワークにおける畳み込み処理の具体的な例（画像データとそのフィルタ処理）
![image](https://user-images.githubusercontent.com/25688193/30872260-6c4409fe-a324-11e7-8758-9a9625a5283d.png)
![image](https://user-images.githubusercontent.com/25688193/30872283-77425900-a324-11e7-9cfc-4f7346cbada9.png)
![image](https://user-images.githubusercontent.com/25688193/30872618-adff2058-a325-11e7-94c5-7620941d8a43.png)
![image](https://user-images.githubusercontent.com/25688193/30874529-9e6564d0-a32b-11e7-904e-a08960e693f3.png)
![image](https://user-images.githubusercontent.com/25688193/30874745-3e52abce-a32c-11e7-9492-71b7f4f072e5.png)
![image](https://user-images.githubusercontent.com/25688193/30874981-f4e58672-a32c-11e7-952e-658c105c4782.png)
![image](https://user-images.githubusercontent.com/25688193/30874489-6f731b90-a32b-11e7-94ad-0025899d76e4.png)

> 参考サイト
>> [定番のConvolutional Neural Networkをゼロから理解する#畳み込みとは](https://deepage.net/deep_learning/2016/11/07/convolutional_neural_network.html#畳み込みとは)

<a id="ID_3-2-4"></a>

#### より一般化した畳み込み層のアーキテクチャの元での定式化
![image](https://user-images.githubusercontent.com/25688193/30882264-5eba369a-a343-11e7-84e3-57b5c66c28e7.png)
![image](https://user-images.githubusercontent.com/25688193/30882273-6c7c3e9a-a343-11e7-8225-893c3bde3700.png)
![image](https://user-images.githubusercontent.com/25688193/30882308-7f8b6a06-a343-11e7-9f50-0288bbfd944b.png)
![image](https://user-images.githubusercontent.com/25688193/30926162-3e669cf6-a3ef-11e7-8732-086483b4a2ec.png)
![image](https://user-images.githubusercontent.com/25688193/30884989-9c766018-a34c-11e7-8cf2-adfd0cc891a1.png)

<a id="ID_3-2-5"></a>

#### 受容野の観点から見た、畳み込み層
![image](https://user-images.githubusercontent.com/25688193/30904710-b736ff00-a3ad-11e7-9a4c-f73f76f71cc3.png)
![image](https://user-images.githubusercontent.com/25688193/30926213-5d706af0-a3ef-11e7-84c9-0216233e73ee.png)
![image](https://user-images.githubusercontent.com/25688193/30926318-abde4d10-a3ef-11e7-900a-8d9eb2842995.png)



<a id="ID_3-3"></a>

### プーリング [pooling] 処理について
![image](https://user-images.githubusercontent.com/25688193/30928885-c94bc0b4-a3f7-11e7-9b83-a86dd44abc95.png)
![image](https://user-images.githubusercontent.com/25688193/30928920-d8cf1b94-a3f7-11e7-86b7-3ab149639139.png)
![image](https://user-images.githubusercontent.com/25688193/30947089-aa6e4b62-a442-11e7-94c5-39b4a52f59e1.png)

<a id="ID_3-3-1"></a>

#### 平均プーリング [average pooling]
![image](https://user-images.githubusercontent.com/25688193/30947132-dfbf6eb8-a442-11e7-9b23-d6eeadc5e951.png)

<a id="ID_3-3-2"></a>

#### 最大プーリング [max pooling]
![image](https://user-images.githubusercontent.com/25688193/30947702-286b95c6-a446-11e7-92a2-6a4cd87dd706.png)

<a id="ID_3-3-3"></a>

#### Lp プーリング [Lp pooling]
![image](https://user-images.githubusercontent.com/25688193/30948182-27d90abe-a449-11e7-869d-4d14fbe22904.png)


<a id="ID_3-4"></a>

### THE ALL CONVOLUTIONAL NETWORK
論文URL : https://arxiv.org/abs/1412.6806 <br>
Keras での実装コード : https://github.com/MateLabs/All-Conv-Keras

従来の CNN に対して、Pooling 層を使わず Conv 層のみの構成（Pooing層 → 複数の小さい Conv 層に置き換わる）で同等 or それ以上のレベルの識別性能を持つことを主張したモデル。

---

<a id="ResNet（残差ネットワーク）"></a>

### ◎ ResNet（残差ネットワーク）
ResNet（残差ネットワーク）は、2015年度の ImageNet コンペティションと COCO セグメンテーションで第１位で優勝したモデルであるが、ただ単に、コンペで高い正解率を叩き出しただけではなく、その残差構造自体に本質的で重要な意味を持つ。<br>

一般的に、画像分類のタスクにおいて、CNNベースのニューラルネットワークの層の深さは重要な要素であり、基本的には、層の深さを深くするほど、CNN でより抽象的な構造を捉えることが出来るために、識別性能をより高めることが出来る。<br>
※ VGG や GoogLeNet などは、この観点から、層の深さをそれぞれ 16層（VGG-16）、19層（VGG-19）、22層（GoogLeNet）にして識別性能を高めている。

しかしながら、層の深さを深くしすぎると、下図の結果のように、逆に識別性能が低下してしまうことが経験的・実験的に知られている。<br>
※ 下図ではまた、学習データセットにおいても層が深いほうが正解率が低いので、層を深くしすぎたために過学習が発生して、識別性能が低下したというわけではないことを示している点に注意。<br>

![image](https://user-images.githubusercontent.com/25688193/58227928-db8c0180-7d67-11e9-97e7-ed4367e77019.png)<br>

層を深くすると性能が低下する理由としては、勾配消失問題や勾配爆発問題が考えられる。<br>
この勾配消失問題や勾配爆発問題は、batch norm などの正則化手法や dropout で防止することが出来るが、層を深くしすぎるこれらの手法も有効ではなくなってくる。<br>

ResNet では、このような非常に深い層のネットワークに対して、"shortcut connections" の構造を加えることにより、このような非常に深いネットワークにおいても、勾配消失問題や勾配爆発問題を防止することが出来るようにし、結果として、非常に深いネットワークでの高い識別性能を実現する。<br>

#### ☆ ResNet のアーキテクチャ
以下の図は、従来のCNNベースのアーキテクチャと、ResNet のアーキテクチャの基本構造を比較を示した図である。<br>

![image](https://user-images.githubusercontent.com/25688193/58298459-94107e80-7e16-11e9-8689-452a3a83f9d1.png)<br>

従来の CNNベースの構造と比較して、ResNet では、赤線で示した "sortcut connection" の構造が追加されている。<br>
この sortcut connection は、入力データ x を、従来のネットワークでの学習対象である出力関数 ![image](https://user-images.githubusercontent.com/25688193/58298536-d8038380-7e16-11e9-8666-ec236ce3a3d9.png) ところまで、恒等写像でスキップする。<br>
この際に、スキップされた入力データ x と出力関数 ![image](https://user-images.githubusercontent.com/25688193/58298536-d8038380-7e16-11e9-8666-ec236ce3a3d9.png) との差分を、<br>
残差関数<br>
![image](https://user-images.githubusercontent.com/25688193/58298486-ab4f6c00-7e16-11e9-9558-c3096104284c.png)<br>
として定義し、この残差関数 ![image](https://user-images.githubusercontent.com/25688193/58298572-fe292380-7e16-11e9-85df-15612a924d9a.png) をネットワークの学習対象とする。<br>
（※ この式は、入力データ x と出力関数 ![image](https://user-images.githubusercontent.com/25688193/58298536-d8038380-7e16-11e9-8666-ec236ce3a3d9.png) の次元が等しい条件を前提としていることに注意。）

そして、この学習された残差関数 ![image](https://user-images.githubusercontent.com/25688193/58298572-fe292380-7e16-11e9-85df-15612a924d9a.png) と入力データ x を元に、最終的な出力関数<br>
![image](https://user-images.githubusercontent.com/25688193/58298501-baceb500-7e16-11e9-9840-053233352a72.png)<br>
を決定する。<br>

この "sortcut connection" の経路では、従来の何層もある経路（上図の青線）での各層での誤差逆伝播の積み重ねによる勾配消失の影響を受けないので、
勾配消失問題を防ぐことが出来る。<br>
より詳細には、出力関数 ![image](https://user-images.githubusercontent.com/25688193/58298501-baceb500-7e16-11e9-9840-053233352a72.png) は、その微分が１に非常に近い値となるために、誤差逆伝播法による勾配計算時に、他の層をスキップ出来る。

上記では、入力データ x と出力関数 ![image](https://user-images.githubusercontent.com/25688193/58298536-d8038380-7e16-11e9-8666-ec236ce3a3d9.png) の次元が等しい条件のもとでの式となっていたが、これら入力データ x と出力関数の次元が異なる場合は、以下のような２つの方法で対応する。<br>

1. 線形変換 W_s  で入力データ x からの次元を一致させた上で、スキップして加算する。<br>
    即ち、![image](https://user-images.githubusercontent.com/25688193/58298961-61678580-7e18-11e9-95f4-ea1bf42f07b0.png)<br>

1. shortcut connection は恒等写像のまま（![image](https://user-images.githubusercontent.com/25688193/58298501-baceb500-7e16-11e9-9840-053233352a72.png)）であるが、増加した次元分の要素を、ゼロパディングで埋める。<br>
    ※ この２番目の手法では、パラメーター数は増加しない。<br>

<br>

この ResNet の基本構造を元に、VGG と同じように、conv 層を 34 層まで積み重ねていったものが、以下に示している ResNet-34 である。<br>
※ 下図（左）：VGG-19<br>
※ 下図（中央）：VGG-19 をベースに、shortcut connection なしの34層ネットワーク（ResNetとの性能の比較用）<br>
※ 下図（右）：ResNet-34<br>

![image](https://user-images.githubusercontent.com/25688193/58295951-89e98280-7e0c-11e9-866b-7d8974e1a91d.png)<br>

※ 実曲線は、入出力次元が一致する shortcut connections<br>
※ 点曲線は、入出力次元が一致しない shortcut connections<br>

以下の表は、このネットワーク構成の、詳細なパラメーターを示した図である。

![image](https://user-images.githubusercontent.com/25688193/58299408-19496280-7e1a-11e9-90f0-46b75d6f8fc9.png)<br>

この ResNet-34 は、3.6 億回のFLOPs（積乗演算）で、これは、VGG-19 のわずか 18% 程度になっていることに注目。<br>

#### ☆ ResNet の識別性能の実験結果
![image](https://user-images.githubusercontent.com/25688193/58296941-c9b26900-7e10-11e9-9a1a-5f60dd2f3ea7.png)

左図は、ResNet との性能差を公平に比較出来るように、VGGベースで、ResNet と同じパラメーター数、深さ、幅、計算可能コストを持ち、shortcut connection なしにしたネットワーク（plain network）での、層の深さを変えたときの識別性能を示した図である。<brr>
右図は、ResNet での、層の深さを変えたときの識別性能を示した図である。<br>
※ データセットは、ImageNet<br>
※ 細い線は、学習データセットでの誤識別率。
※ 太い線は、検証データセットでの誤識別率<br>

従来の shortcut connection なしのネットワーク（plain network）では、層の深さを深くしすぎると、逆に、識別性能は低下しているが、shortcut connection を導入した ResNet では、層の深さを深くすると、識別性能が上昇していることが見てとれる。<br>
※ この図では、34 層まで深くしているが、更に深くしていっても（例えば、1202層）、同様の傾向は成り立つ。<br>


- 【参考サイト】
    - [**【元論文】[1512.03385] Deep Residual Learning for Image Recognition**](https://arxiv.org/abs/1512.03385)
    - [**【論文翻訳（非公開）】GitHub/Yagami360/MachineLearning-Papers_Survey/papers/Deep_Residual_Learning_for_Image_Recognition/ResNet.md**](https://github.com/Yagami360/MachineLearning-Papers_Survey/blob/master/papers/Deep_Residual_Learning_for_Image_Recognition/ResNet.md)
    - [**Residual Network(ResNet)の理解とチューニングのベストプラクティス - DeepAge**](https://deepage.net/deep_learning/2016/11/30/resnet.html)
    - [ResNetの論文を読んだ - kumilog.net](https://www.kumilog.net/entry/resnet-paper)
    - [**ResNetの仕組み**](https://www.slideshare.net/KotaNagasato/resnet-82940994)
    - [ディープラーニング ResNet のヒミツ - Bridge over troubled Techs.](http://terada-h.hatenablog.com/entry/2016/12/13/192940)

---

<a id="ID_4"></a>

## リカレントニューラルネットワーク [RNN : Recursive Neural Network]<br>＜階層型ニューラルネットワーク＞
![image](https://user-images.githubusercontent.com/25688193/30980712-f06a0906-a4bc-11e7-9b15-4c46834dd6d2.png)
![image](https://user-images.githubusercontent.com/25688193/30981066-22f53124-a4be-11e7-9111-9514f04aed7c.png)

<a id="ID_4-1"></a>

### リカレントニューラルネットワーク（RNN）のアーキテクチャの種類

<a id="ID_4-1-1"></a>

#### 隠れ層間で回帰構造をもつネットワーク
![image](https://user-images.githubusercontent.com/25688193/31013864-0baf82cc-a553-11e7-9296-870f600f0381.png)
![image](https://user-images.githubusercontent.com/25688193/31013877-185db822-a553-11e7-9c5f-625acace78f8.png)
![image](https://user-images.githubusercontent.com/25688193/31016204-bcbc0cb0-a55e-11e7-86df-3ba574fa8bc2.png)
![image](https://user-images.githubusercontent.com/25688193/31017867-f379d312-a564-11e7-9d67-fc79a7dda26d.png)

<a id="ID_4-1-1-1"></a>

##### 通時的誤差逆伝搬法 [BPTT : back-propagation through time]
![image](https://user-images.githubusercontent.com/25688193/31018664-dacf44d4-a567-11e7-8014-34523646bfca.png)
![image](https://user-images.githubusercontent.com/25688193/31019688-7725288c-a56b-11e7-919d-d0be44d4be33.png)

<a id="ID_4-1-1-1-1"></a>

###### 通時的誤差逆伝搬法によるパラメータの更新式（誤差関数が最小２乗誤差）
![image](https://user-images.githubusercontent.com/25688193/31189494-64bc3a80-a973-11e7-90a8-348e97f93f47.png)
![image](https://user-images.githubusercontent.com/25688193/31189294-c48db61a-a972-11e7-9673-a7805c53eaf5.png)
![image](https://user-images.githubusercontent.com/25688193/31190398-f0e5337a-a975-11e7-8eff-ff74adf3a6ff.png)
![image](https://user-images.githubusercontent.com/25688193/31190919-835e326e-a977-11e7-966e-d3675cb83452.png)
![image](https://user-images.githubusercontent.com/25688193/31211718-661ae058-a9d6-11e7-96ae-075f35981fd1.png)

<a id="ID_4-1-2"></a>

#### 教師強制と出力層間での回帰構造をもつネットワーク
記載中...




<a id="ID_4-2"></a>

### 長・短期記憶（LSTM [long short-term memory]）モデル

<a id="ID_4-2-1"></a>

#### CEC [constant error carousel]
![image](https://user-images.githubusercontent.com/25688193/31226189-2d62a892-aa10-11e7-93e5-b32902d83702.png)
![image](https://user-images.githubusercontent.com/25688193/31226163-0eb9927a-aa10-11e7-9d06-306e4443c5a8.png)
![image](https://user-images.githubusercontent.com/25688193/31235831-6fa44284-aa2d-11e7-9377-845ea30837c5.png)
![image](https://user-images.githubusercontent.com/25688193/31226906-eb4288bc-aa12-11e7-9f16-621ed4d50063.png)

<a id="ID_4-2-2"></a>

#### 重み衝突 [weight conflict] と入力ゲート [input gate]、出力ゲート [output gate]
![image](https://user-images.githubusercontent.com/25688193/31236796-16687124-aa30-11e7-89b5-2da158274de7.png)
![image](https://user-images.githubusercontent.com/25688193/31246908-ed52d18e-aa49-11e7-946f-44f3fa177eb3.png)
![image](https://user-images.githubusercontent.com/25688193/31246932-fa855dc2-aa49-11e7-882d-462dd22be03d.png)

<a id="ID_4-2-3"></a>

#### 忘却ゲート [forget gate]
![image](https://user-images.githubusercontent.com/25688193/31247911-036bc036-aa4d-11e7-9f5f-117eaab0b738.png)
![image](https://user-images.githubusercontent.com/25688193/31247928-130b98b8-aa4d-11e7-89aa-ac27b1667666.png)
![image](https://user-images.githubusercontent.com/25688193/31248855-2cf3eb7e-aa50-11e7-99b7-4c81a093f679.png)
![image](https://user-images.githubusercontent.com/25688193/31249125-2453757e-aa51-11e7-9ce2-715edddf8232.png)

<a id="ID_4-2-4"></a>

#### 覗き穴結合 [peephole connections]
![image](https://user-images.githubusercontent.com/25688193/31272328-83122b86-aac5-11e7-84db-6a52bd8d2c44.png)
![image](https://user-images.githubusercontent.com/25688193/31272347-8f9d67bc-aac5-11e7-9fda-640bdb6a9d7f.png)
![image](https://user-images.githubusercontent.com/25688193/31279596-941088d2-aae4-11e7-9e30-dc28771800c4.png)

<a id="ID_4-2-5"></a>

#### LSTM モデルの定式化
![image](https://user-images.githubusercontent.com/25688193/31278352-91da316c-aadf-11e7-8ad6-963e7e235852.png)
![image](https://user-images.githubusercontent.com/25688193/31283264-169b4f16-aaf0-11e7-9f19-976dc2e09bc9.png)
![image](https://user-images.githubusercontent.com/25688193/31284097-8a2e6e84-aaf2-11e7-8e7d-df00110c5bf6.png)
![image](https://user-images.githubusercontent.com/25688193/31293857-b20586f6-ab13-11e7-85b2-460f9bab5e62.png)
![image](https://user-images.githubusercontent.com/25688193/31294053-706d763a-ab14-11e7-8aed-1fed8327d58c.png)


<a id="ID_4-3"></a>

### GRU [gated recurrent unit]
![image](https://user-images.githubusercontent.com/25688193/31338072-e514030c-ad38-11e7-908c-2446c32b60c6.png)
![image](https://user-images.githubusercontent.com/25688193/31306417-cfa02a3c-ab8a-11e7-8fb1-0579fe5aa0be.png)
![image](https://user-images.githubusercontent.com/25688193/31307146-b1ce34fa-ab98-11e7-862a-b139d330222e.png)
![image](https://user-images.githubusercontent.com/25688193/31308026-2bd77ff2-abaa-11e7-967e-04cff1579a36.png)


<a id="ID_4-4"></a>

### 双方向 RNN [BiRNN : Bidirectional RNN]
![image](https://user-images.githubusercontent.com/25688193/31332068-edadd682-ad1f-11e7-9f11-e7374b83465e.png)
![image](https://user-images.githubusercontent.com/25688193/31334064-78437f7a-ad27-11e7-84f2-decd65d1599d.png)
![image](https://user-images.githubusercontent.com/25688193/31335870-68a806d2-ad2f-11e7-9cd2-36648536cc64.png)
![image](https://user-images.githubusercontent.com/25688193/31335226-9d1c925a-ad2c-11e7-8f79-dccd9d931c41.png)
![image](https://user-images.githubusercontent.com/25688193/31335735-d0a5b780-ad2e-11e7-82ae-17cd33f2546c.png)


<a id="ID_4-5"></a>

### RNN Encoder-Decoder (Seqenence-to-sequence models)
![image](https://user-images.githubusercontent.com/25688193/31340555-7cd2efac-ad41-11e7-85f0-d70f0f9c7bee.png)
![image](https://user-images.githubusercontent.com/25688193/34071127-fd431a10-e2b4-11e7-8f45-18a9ca626a20.png)
![image](https://user-images.githubusercontent.com/25688193/31370130-2c510356-adc4-11e7-9a59-d2b93cfa4698.png)
![image](https://user-images.githubusercontent.com/25688193/31370139-372bbfd2-adc4-11e7-965c-96bc88661505.png)
![image](https://user-images.githubusercontent.com/25688193/31371878-45210ec6-adce-11e7-9096-3bbd77dee065.png)
![image](https://user-images.githubusercontent.com/25688193/31376678-b29f4ff0-ade0-11e7-9988-88602f28b32c.png)


<a id="ID_4-6"></a>

### Attention (Seqenence-to-sequence models)
![image](https://user-images.githubusercontent.com/25688193/34072063-05139170-e2c4-11e7-946a-0a351d215550.png)
![image](https://user-images.githubusercontent.com/25688193/34071346-81d4a840-e2b8-11e7-9b77-c9aa4a7d83fd.png)
![image](https://user-images.githubusercontent.com/25688193/34072066-1ed7304e-e2c4-11e7-933a-effdf05d8b89.png)
![image](https://user-images.githubusercontent.com/25688193/34072851-fcfc95dc-e2d1-11e7-8b60-b836f8e3530d.png)
![image](https://user-images.githubusercontent.com/25688193/34072877-7a5f9506-e2d2-11e7-8cb9-a890b36f09dc.png)


<a id="ID_4-6-1"></a>

### LSTM を使用した場合の Attention
![image](https://user-images.githubusercontent.com/25688193/34073766-afa857a4-e2e4-11e7-8ac6-ee1117f354dd.png)
![image](https://user-images.githubusercontent.com/25688193/34075906-8bb45cf6-e318-11e7-8875-8ee07a340eaa.png)
![image](https://user-images.githubusercontent.com/25688193/34075910-ae49a83e-e318-11e7-8e64-ac62bbe55250.png)
![image](https://user-images.githubusercontent.com/25688193/34076679-ba9c78aa-e331-11e7-95f9-70db54921e8b.png)
![image](https://user-images.githubusercontent.com/25688193/34076731-31053f9e-e333-11e7-9f03-bb7070f8ee38.png)

<br>

---

<a id="ID_5"></a>

## 連想記憶ネットワーク（ホップフィールドネットワーク [Hopfield network] ）</br>(相互結合型ニューラルネットワーク [mutual connected neural networks]）)
> 修正中...
![twitter_nn11-1_160904](https://user-images.githubusercontent.com/25688193/30112974-1a8ff1b2-934e-11e7-81de-933019772299.png)
![twitter_nn11-2_160904](https://user-images.githubusercontent.com/25688193/30112976-1a965e58-934e-11e7-98a7-f80bdee26b35.png)
![twitter_nn12-1_160904](https://user-images.githubusercontent.com/25688193/30112977-1aa3d1aa-934e-11e7-98fd-626e1a46fc30.png)
![twitter_nn13-1_160904](https://user-images.githubusercontent.com/25688193/30112975-1a9358fc-934e-11e7-871f-dd2b55ff3657.png)
![twitter_nn14-1_160905](https://user-images.githubusercontent.com/25688193/30112978-1aa4cc4a-934e-11e7-9a7b-97c4f9d415b5.png)
![twitter_nn14-2_160905](https://user-images.githubusercontent.com/25688193/30112973-1a8f9122-934e-11e7-8ef0-2b0f82c00645.png)
![twitter_nn15-1_160905](https://user-images.githubusercontent.com/25688193/30112979-1abb3e26-934e-11e7-8e8d-23a72b07fe7c.png)

---

<a id="ID_10"></a>

## 生成モデル [generative model]
> 以下の内容は、旧記事となります。<br>
> 最新の記事は、別記事（[生成モデル](https://github.com/Yagami360/My_NoteBook/blob/master/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6/%E6%83%85%E5%A0%B1%E5%B7%A5%E5%AD%A6_%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92_%E7%94%9F%E6%88%90%E3%83%A2%E3%83%87%E3%83%AB.md)）に移行していますので、こちらを参照ください。

![image](https://user-images.githubusercontent.com/25688193/35478872-4302b400-042c-11e8-80aa-a187b50eba30.png)

<a id="ID_10-1"></a>

### GAN [Generative Adversarial Network]（敵対的ネットワーク）
- 元論文「Generative Adversarial Nets」
    - arXiv.org : https://arxiv.org/abs/1406.2661
- 参考サイト
    - https://elix-tech.github.io/ja/2017/02/06/gan.html
    - http://mizti.hatenablog.com/entry/2016/12/10/224426
    - http://vaaaaaanquish.hatenablog.com/entry/2017/03/19/220817
    - http://yasuke.hatenablog.com/entry/generative-adversarial-nets

![image](https://user-images.githubusercontent.com/25688193/35478891-ac0a5494-042c-11e8-8781-39c88431fe8f.png)
![image](https://user-images.githubusercontent.com/25688193/35481685-c432d534-046b-11e8-954c-f9b88f5a07fb.png)
![image](https://user-images.githubusercontent.com/25688193/35481115-7b76b87a-0460-11e8-9f3f-293e6afdba22.png)
![image](https://user-images.githubusercontent.com/25688193/35488656-2b95c91c-04cf-11e8-8d06-67ea71c58a72.png)

> 記載中...


<a id="ID_10-1-1"></a>

#### DCGAN [Deep Convolutional GAN]
- 元論文「Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks」
    - arXiv.org : https://arxiv.org/abs/1511.06434

- TensorFlow での DCGAN の実装コード集
    - https://github.com/Yagami360/MachineLearning_Exercises_Python_TensorFlow/tree/master/GAN_DCGAN_TensorFlow

![image](https://user-images.githubusercontent.com/25688193/35545399-50f2a4bc-05b2-11e8-853e-11d38971630f.png)
![image](https://user-images.githubusercontent.com/25688193/35545437-72ebb95a-05b2-11e8-9219-e723ee344d54.png)
![image](https://user-images.githubusercontent.com/25688193/36059567-efac113c-0e7d-11e8-8bdd-329fbc70808a.png)
![image](https://user-images.githubusercontent.com/25688193/35549375-93ea4836-05c8-11e8-8279-a8d3d3a659c6.png)
![image](https://user-images.githubusercontent.com/25688193/35545532-cd39d9d2-05b2-11e8-9ab9-a3f4123ab8fd.png)
![image](https://user-images.githubusercontent.com/25688193/35545809-5d14a248-05b4-11e8-854e-caf830ef2972.png)
![image](https://user-images.githubusercontent.com/25688193/35549398-b4a58dce-05c8-11e8-9bd5-883c03aa4564.png)

> 記載中...

<br>

---

<a id="ID_11"></a>

## ■ ニューラルネットワーク、ディープラーニングによる物体検出 [object detection]
> [18/05/31] 別記事（コンピュータビジョン - 一般物体検出）に移行予定

<a id="ID_11-4"></a>

### ◎ SSD [Single Shot muitibox Detector]（単発検出器）

- 参考サイト
    - [元論文 : arXiv](https://arxiv.org/pdf/1512.02325.pdf)<br>
    - [Qiita : SSD:Single Shot Multibox Detector](https://qiita.com/de0ta/items/1ae60878c0e177fc7a3a)<br>
        - SSD の論文の日本語訳<br>
    - https://www.slideshare.net/KazukiMotohashi2/rcnn<br>
        - スライドの 37 ページ目から SSD の解説有り（Keras でのコード付き）  <br>
    - http://segafreder.hatenablog.com/entry/2018/03/11/152515<br>
    - https://www.slideshare.net/takanoriogata1121/ssd-single-shot-multibox-detector-eccv2016<br>
    - https://www.slideshare.net/ren4yu/single-shot<br>

- Python & TensorFlow での実装。<br>
  ChainerCV や OpenCV にある実装済み or 学習済み SSD モジュールのような高レベル API 使用せずに実装している。
    - https://github.com/Yagami360/MachineLearning_Exercises_Python_TensorFlow/tree/master/ObjectDetection_SSD_TensorFlow


<a id="ID_11-4-1"></a>

#### ☆ モデル（アーキテクチャ）
![image](https://user-images.githubusercontent.com/25688193/39536606-0e4f1416-4e72-11e8-91e2-82b516706bae.png)<br>

- SSD の基本的なアーキテクチャは、上図のように、フィードフォワード型（順方向）の多層 CNN をベースに構成される。<br>

- ネットワークの最初の部分のレイヤーは、画像分類にに使用される標準的なアーキテクチャ（上図では VGG-16）に基づいて構成され、これをベースネットワークという。<br>
    このベースネットワークで、特徴量を検出する。（**特徴量はより広い領域から抽出**）<br>

- その後のレイヤーは、マルチスケール特徴マップによる多様な物体検出のための補助的な構造であり、主な特徴 [key features] は以下のようになる。<br>
    - 直感的には、<br>
        「多層 CNN では、conv 層や pooling 層で、特徴マップがダウンサンプリングされて、後段に行くほど、特徴マップのグリッドサイズが小さくなるが、<br>
        このことは、各々の層の特徴マップには、色々なサイズの物体を検出出来る情報が含まれていることを意味している。<br>
        従って、SSD モデルの後段の特徴マップ（特徴レイヤー）の各グリッドでは、大きな物体の情報。前段では、小さな物体の情報を取得することが出来る。<br>
        そして、各グリッドにおける特徴量を使用して、バウンディングボックス（BBOX）のアスペクト比、所属クラス、座標のオフセットを学習させる。」<br>
        というのが、基本的なコンセプトである。<br>
        ![image](https://user-images.githubusercontent.com/25688193/39539054-a67a9344-4e79-11e8-9b98-b8a499919f29.png)<br>

	- **「検出のためのマルチスケール特徴マップ」**<br>
    畳み込み特徴レイヤーを、（途中で打ち切られている）ベースネットワークの最後尾に追加している。<br>
    これらのレイヤーは、特徴マップのサイズを小さくさせ（上図）、マルチスケールでの検出の予想を可能にする。（下図）<br>
    ![image](https://user-images.githubusercontent.com/25688193/39470645-ca231574-4d79-11e8-865d-b384a4b4bbd6.png)<br>

    検出を予想するための畳み込みモデルは、各特徴レイヤーにおいて異なっている。（モデル図の青線元のレイヤー）<br>
	（※ YOLO では、対照的に１つのスケールの特徴マップを扱っている）<br>

    - **「検出のための、畳み込み予想器」**<br>
		ベースネットワークの後尾に追加された各特徴レイヤーは、<br>
		畳み込みフィルタ（フィルタ行列）の集合を使用して、固定の検出予想の集合を生成可能である。
		p 個のチャンネルをもつサイズ m×n の特徴レイヤーに対しての、<br>
		潜在的なパラメータ予想のための基本要素は、3×3×p の小さなカーネル（カーネル行列）であり、<br>
		このカーネルは、予想カテゴリ（所属クラス）の **検出スコア（物体の中心座標が含まれているなら１となるようなスコア）**、<br>
        又は、デフォルトボックスの座標に関してのオフセット値を生成（算出）する。<br>
		又、バウンディングボックスの座標オフセットの出力値は、各特徴マップの位置に対するデフォルトボックスの位置に対して測定される。<br>
	
		SSD モデルは、（前述のように）いくつかの特徴レイヤーを、ベースネットワークの最後に追加するが、<br>
		**これらの特徴レイヤーは、異なるスケールとアスペクト比のデフォルトボックスに対するオフセット値と、それに付随する確信度を予測する。**<br>

    - **「デフォルトボックスとアスペクト比（デフォルトボックスと回帰によるオフセット予想）」**<br>
        ネットワークのトップで、複数の特徴マップに関して、各特徴マップのセル（グリッド）とデフォルトボックスの集合を関連付けている。<br>
	    その対応するセル（グリッド）に対して、各デフォルトボックスの位置が固定されるように、<br>
	    デフォルトボックスは、畳み込みのやり方で、特徴マップを隙間なく敷き詰め [tile] ている。（下図参照）<br>
        ![image](https://user-images.githubusercontent.com/25688193/40360882-7a247ac4-5e02-11e8-95d0-9ba5fdc37aa0.png)<br>
        ![image](https://user-images.githubusercontent.com/25688193/51079927-e3ca9500-1714-11e9-950f-bbef5b1c68b3.png)<br>
        
		各特徴マップのセル（グリッド）において、<br>
		検出したい物体が、各 BBOX 内に存在することを示す指標である検出スコア（物体の中心座標が含まれているなら１となる）と、セル中のデフォルトボックスのオフセット値を予想する。<br>
		このオフセット値は、具体的には、ある座標位置で k 個のボックスそれぞれに対し、<br>
	    c 個のクラスの検出スコア（所属クラスの確率）と、元のデフォルトボックスに対するオフセット値 (x,y,w,h) の４つ（x,yの中心座標２つ、幅w、高さh）を計算する。<br>
	    その結果、特徴マップに適用されるフィルタは、合計 (c+4)×k 個となり、<br>
	    m×n の特徴マップに対して、(c+4)×k×mn 個の出力が生成されることになる。<br>
		
    	幾つかの特徴マップで、異なるデフォルトボックスの形状を利用することにより、<br>
	    出力されるボックス（出力特徴マップ）の形状を、効率よく離散化 [discretize] することが出来る。<br>

    - **「デフォルトボックスとアスペクト比の選択（デフォルトボックスと回帰によるオフセット予想）の詳細」**<br>
	    異なるスケールの物体検出を取り扱うために、元画像を異なるサイズで処理し、それらの結果を結合する手法を提案している研究も存在する。<br>
	    しかしながら、この SSD のように、単一のネットワークの中の幾つかの異なるレイヤーの特徴マップを利用することで、
	    全ての物体のスケールについて、同じパラメータを共有しながら、同様の効果を得ることがことが出来る。<br>
	    （更に、こちらの手法では同一の単一のネットワークの使用するため、処理が軽くなるメリットがある。）<br>
		
    	SSD では、物体検出に下位と上位の特徴マップを使用する。<br>
	    以下の図は、**SSD のフレームワークで使用している２つの典型的な特徴マップ（８×８、４×４）** を示している。<br>
	    （実践的には、より多くの特徴マップを小さい計算コストで使用出来る。）<br>
        ![image](https://user-images.githubusercontent.com/25688193/39539054-a67a9344-4e79-11e8-9b98-b8a499919f29.png)<br>

	    又、**SSD では、特定の特徴マップが、特定のスケールの物体に対応するように学習させるために、**
	    **デフォルトボックスを ”敷き詰めて” 設計されている。**<br>
        ![image](https://user-images.githubusercontent.com/25688193/40360882-7a247ac4-5e02-11e8-95d0-9ba5fdc37aa0.png)<br>

	    **デフォルトボックスを中心とする提案領域は、物体のスケール値、中心座標、高さ、幅が合っていないことがあるため、**<br>
	    **スケール値、幅、高さ、中心座標に回帰する畳み込み層を追加している。（BBOXの形状回帰）**<br>

    	具体的には、今、m 個の特徴マップを予想に使用するケースにおいて、<br>
	    各特徴マップ k についてのデフォルトボックスのスケール ![image](https://user-images.githubusercontent.com/25688193/39475869-f53f3b46-4d94-11e8-8c20-3ca89df948d3.png) は、以下のようにして計算される。<br>
        ![image](https://user-images.githubusercontent.com/25688193/39475900-106b5c6a-4d95-11e8-80c6-2dfb8667d132.png)<br>

    	この式より、最下位のレイヤーのスケール 0.2 と最上位のレイヤーのスケールは 0.9 となり、<br>
	    中間レイヤーのスケールは、上式に従って規則的な間隔で設定される。<br>
	    又、デフォルトボックスのアスペクト比に関しては、![image](https://user-images.githubusercontent.com/25688193/39479352-f8164624-4d9f-11e8-9ed2-06a2557941d2.png) の異なるアスペクト比を設定する。<br>
	    このスケールとアスペクト比により、各デフォルトボックスに対して、<br>
	    幅 ![image](https://user-images.githubusercontent.com/25688193/39479366-0a19618a-4da0-11e8-816c-2f1207c30251.png) と、高さ ![image](https://user-images.githubusercontent.com/25688193/39479400-23209c84-4da0-11e8-93b3-63edbf9100d0.png) が設定される。<br>

- **「特徴マップとデフォルトボックスについて」**
    ![image](https://user-images.githubusercontent.com/25688193/39539151-e0c41b9c-4e79-11e8-8334-496d8b32e589.png)<br>

    - SSD が訓練中に必要とするのは、<br>
    入力画像（上図の(a)）と、各物体それぞれの正解ボックス（デフォルトボックスの内、各物体が収まるボックス。上図の赤枠と青枠）のみである。<br>
	
    - 各層での畳み込み処理のやり方 [in a convolutional fashion] において、<br>
    いくつかの特徴マップでの各位置（中心座標）において、異なるアスペクト比デフォルトボックスの少数の集合（上記例では４個）を、<br>
    異なるスケールの特徴マップ内（例えば、上記の (b) の 8×8 の特徴マップ内、(c) の４×４の特徴マップ内）で評価する。<br>
	
    - そして、これらのデフォルトボックスそれぞれにおいて、<br>
    形状のオフセット loc : ![image](https://user-images.githubusercontent.com/25688193/39470381-5d7065d6-4d78-11e8-88f6-eabc19bbb20c.png) と、全ての物体カテゴリー ![image](https://user-images.githubusercontent.com/25688193/39470406-7c7ca066-4d78-11e8-851e-c3c67423b306.png) に関する確信度 conf を予想する。<br>
	    - w : デフォルトボックスの幅、h : デフォルトの高さ、cx,cy : デフォルトボックスの左上座標

    - 訓練時には、最初にこれらのデフォルトボックスと正解 [ground truth] ボックスのマッチ度を図る。<br>
    上図の例では、２つのデフォルトボックスの内、１つ目はネコ、２つ目はイヌとマッチさせているが、<br>
    この組み合わせは正 [positive] として扱われ、残りは負 [negative] として扱われる。<br>
	
    - モデルの誤差（損失関数）は、<br>
    位置特定誤差 [localization loss] （例えば、Smooth L1）と、確信度誤差 [confidence loss] （例えば、softmax）との間の重み付き和 [weighted sum] である。<br>

<br>

#### ☆ 訓練（学習）アルゴリズム

- **「マッチング戦略」**<br>
	訓練では、どのデフォルトボックスが正解ボックスとなるのか決定する必要があり、<br>
    その結果を元にネットワークを学習させる。<br>
	各正解ボックスは、座標位置、アスペクト比、スケール値が異なる幾つかのデフォルトボックスから選択するが、<br>
	これらデフォルトボックスに対して、jaccard overlap （下図）の最良値（最もエリアが重複している）で、<br>
    各正解ボックスのマッチ度（エリアの重複度）を算出することになる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/39512883-7067f2f2-4e2d-11e8-8497-ac39f2aaba7c.png)<br>
	この際、ベストマッチした（最もエリアが重複している）デフォルトボックスだけでなく、<br>
	jaccard overlap が 0.5 の値よりも大きいデフォルトボックスを正解ボックスと判定させ、学習させる。<br>
	これにより、正解ボックスに複数に重なり合っているデフォルトボックスについて、高いスコア予想が可能になる。<br>

- **「損失関数」**<br>
    SSD の損失関数は、位置特定誤差（loc）と確信度誤差（conf）の重み付き和であり、<br>
    （SSD の学習は、複数の物体カテゴリーを扱うことを考慮して行われるため２つの線形和をとる。）以下の式で与えられる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/39518203-34d9c2fa-4e3d-11e8-8f49-b2319d2ef85c.png)<br>

    ここで、上式の位置特定誤差 ![image](https://user-images.githubusercontent.com/25688193/39518249-56dfca66-4e3d-11e8-926a-3928d5c800e4.png) は、<br>
	予想されたボックス（l）と正解ボックス（g）の間の Smooth L1 誤差（関数）であり、以下の式で与えられる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/39549447-d55ee236-4e98-11e8-997f-c2d0034aa0f7.png)<br>

	又、確信度誤差 ![image](https://user-images.githubusercontent.com/25688193/39518316-89254b4a-4e3d-11e8-9ee7-e583f941bc62.png) は、<br>
	所属クラスのカテゴリ（c）に対する softmax cross entropy 誤差（関数）であり、以下の式で与えられる。<br>
    ![image](https://user-images.githubusercontent.com/25688193/39549244-17c08608-4e98-11e8-8c72-08299eea27d5.png)<br>

- **ハードネガティブマイニング [hard negative mining]**<br>
	マッチング工程の後、有効なデフォルトボックスの数が多い場合多くのデフォルトボックスは、負 [negative] に判定され、正と負の訓練データの比率が不均衡になってしまう。<br>
	（＝典型的な画像の多くの面積は、背景によって占められるが、これを有効なデフォルトボックスとして採用すると、<br>
	背景しか出力しないネットワークでも、ある程度 loss 値を下げることが出来てしまい、結果として検出能力の低いモデルになってしまう。）<br>

	この問題に対する対策として、<br>
	負に判定される全訓練データを使用する代わりに、これらの（訓練データとしての） **デフォルトボックスに対しての誤差関数が高い順（降順）にソートし、**<br>
	**負と正の比率が、最大でも３：１になるように、誤差関数の値が上位のもののみを選択する。**<br>
    これにより、より速くモデルが最適化され、又、安定した学習に繋がる。<br>

- **データ拡張 [data augumentation]**<br>
	モデルを様々な物体の大きさと形状に対して、よりロバスト（堅牢）にするために、<br>
    各訓練画像は、以下のオプションをランダムに選択し、（画像中の領域の）サンプリングを行う。<br>
    
    - 元の入力画像全体を使用する。<br>
    - 物体画像との最小の jaccard overlap が、0.1 , 0.3 , 0.5 , 0.7 , 0.9 となるように、画像中の領域（サンプルパッチ）をサンプリングする。<br>
    - 画像中の領域（サンプルパッチ）をランダムにサンプリングする。<br>
    
	この各画像中の領域（サンプルパッチ）のサイズは、元の画像サイズの 0.1倍 ~ 1.0倍で、アスペクト比は 1/2 ~ 1.0 倍である。<br>
	但し、サンプルパッチの中に正解ボックスの中心座標が存在する場合は、正解ボックスの重複部分はそのままにする。<br>
	（サイズやアスペクト比を元の画像から変更しない）<br>


#### ☆ 物体検出（推論）フェイズ

##### top-k filtering
クラス所属の確信度が上位 k 個のもののみを抽出する。<br>

##### non-maximum suppression アルゴリズム
推論されたデータに対し、バウンディングボックスの重複防止のために non-maximum suppression アルゴリズムを適用する。<br>

![image](https://user-images.githubusercontent.com/25688193/40741748-2c50bcaa-6487-11e8-803a-aa06e40ab72c.png)<br>

参考サイト：<br>
- [物体検出におけるNon-Maximum Suppressionのアルゴリズム](https://meideru.com/archives/353)<br>


<br>

---

<a name="参考文献"></a>

## 参考文献

> はじめてのパターン認識 </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)</br>

> 深層学習: Deep Learning</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%B7%B1%E5%B1%A4%E5%AD%A6%E7%BF%92-Deep-Learning-%E7%9B%A3%E4%BF%AE-%E4%BA%BA%E5%B7%A5%E7%9F%A5%E8%83%BD%E5%AD%A6%E4%BC%9A/dp/476490487X)

> 複素ニューラルネットワーク(第2版) 2016年 06 月号 [雑誌]: 数理科学 別冊</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E8%A4%87%E7%B4%A0%E3%83%8B%E3%83%A5%E3%83%BC%E3%83%A9%E3%83%AB%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF-%E7%AC%AC2%E7%89%88-2016%E5%B9%B4-06-%E6%9C%88%E5%8F%B7/dp/B01GU5F48Q?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=B01GU5F48Q)

> Python機械学習プログラミング 達人データサイエンティストによる理論と実践 (impress top gear)</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/Python%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0-%E9%81%94%E4%BA%BA%E3%83%87%E3%83%BC%E3%82%BF%E3%82%B5%E3%82%A4%E3%82%A8%E3%83%B3%E3%83%86%E3%82%A3%E3%82%B9%E3%83%88%E3%81%AB%E3%82%88%E3%82%8B%E7%90%86%E8%AB%96%E3%81%A8%E5%AE%9F%E8%B7%B5-impress-top-gear/dp/4844380605)

> [第2版]Python機械学習プログラミング 達人データサイエンティストによる理論と実践 (impress top gear)</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/Python-%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0-%E9%81%94%E4%BA%BA%E3%83%87%E3%83%BC%E3%82%BF%E3%82%B5%E3%82%A4%E3%82%A8%E3%83%B3%E3%83%86%E3%82%A3%E3%82%B9%E3%83%88%E3%81%AB%E3%82%88%E3%82%8B%E7%90%86%E8%AB%96%E3%81%A8%E5%AE%9F%E8%B7%B5-impress-gear/dp/4295003379?SubscriptionId=AKIAJMYP6SDQFK6N4QZA&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4295003379)

> TensorFlow機械学習クックブック Pythonベースの活用レシピ60+</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/TensorFlow%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%82%AF%E3%83%83%E3%82%AF%E3%83%96%E3%83%83%E3%82%AF-Python%E3%83%99%E3%83%BC%E3%82%B9%E3%81%AE%E6%B4%BB%E7%94%A8%E3%83%AC%E3%82%B7%E3%83%9460-impress-top-gear/dp/4295002003?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4295002003)
>> 本書のレビュー記事 :<br> 
>> [【書籍紹介】TensorFlow機械学習クックブック](http://s0sem0y.hatenablog.com/entry/2017/09/08/005322)

> 詳解 ディープラーニング ~ TensorFlow・Keras による時系列データ処理</br>
> [amazonで詳細を見る](https://www.amazon.co.jp/exec/obidos/ASIN/4839962510/hikarus0sem0y-22/)<br>
>> 本書のレビュー記事 :<br> 
>> [【書籍紹介】詳解ディープラーニング TensorFlow・Kerasによる時系列データ処理](http://s0sem0y.hatenablog.com/entry/2017/06/25/025725)


---

以下、同様の文献（はてなブログ形式）

<!-- はじめてのパターン認識 -->
[asin:4627849710:detail]

<!-- Python機械学習プログラミング 達人データサイエンティストによる理論と実践 -->
[asin:B01HGIPIAK:detail]

<!-- 深層学習: Deep Learning -->
[asin:476490487X:detail]

<!-- 複素ニューラルネットワーク -->
[asin:B01GU5F48Q:detail]

<!-- TensorFlow機械学習クックブック Pythonベースの活用レシピ60+ -->
[asin:4295002003:detail]

<!-- 詳解 ディープラーニング ~ TensorFlow・Keras による時系列データ処理 ~-->
[asin:4839962510:detail]
