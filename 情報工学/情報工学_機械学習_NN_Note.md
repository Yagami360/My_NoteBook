# ニューラルネットワーク [NN :Neural Network]

ニューラルネットワークに関してのマイノートです。今後も随時追加予定です。

This is my notebook that summarizes about "Neural Network" and "Pattern recognition". I will add contents as needed.

![neuralnetworks](https://user-images.githubusercontent.com/25688193/30514787-10f19028-9b57-11e7-8091-de114932fd6a.png)

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
    1. CNN と 一般物体認識
        1. 局所特徴と大域特徴
    1. 一般物体認識を学習した CNN と転移学習
    1. タイル型畳み込み [Tiled convolution]<br>（プーリング層における移動不変性 [location invariant]の拡張）
    1. 逆畳み込みネットワーク [deconvolutional network]<br>（CNN の可視化）
1. [リカレントニューラルネットワーク [RNN : Recursive Neural Network]<br>＜階層型ニューラルネットワーク＞](#ID_4)
    1. [回帰結合ニューラルネットワークのアーキテクチャの種類](#ID_4-1)
        1. [隠れ層間で回帰構造をもつネットワーク](#ID_4-1-1)
            1. [通時的誤差逆伝搬法 [BPTT : back-propagation through time]](#ID_4-1-1-1)
        1. [隠教師強制と出力層間での回帰構造をもつネットワーク](#ID_4-1-2)
    1. LSTM [long short-term memory]
    1. GRU [gated recurrent unit]
1. [連想記憶ネットワーク（ホップフィールドネットワーク [Hopfield network] ）</br>(相互結合型ニューラルネットワーク [mutual connected neural networks]）)](#ID_x)
1. [](#ID_x)
1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## 概要 [Overview]

<a id="ID_1-1"></a>

### 全体 MAP図
![image](https://user-images.githubusercontent.com/25688193/30951582-c3720dc6-a45e-11e7-85af-1592d6020f8f.png)

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

$$ P_n = \dfrac{ e^{\frac{E_n}{k_B T}} }{ \sum_{i=1}^{n} e^{ \frac{E_i}{k_B \times T } } } $$

<!-- はてなブログ形式
[tex:{ P_n = \dfrac{ e^{\frac{E_n}{k_B T}} }{ \sum_{i=1}^{n} e^{ \frac{E_i}{k_B \times T } }  } } ]
-->

の形に対応している。<br>

この確率の式の分母を統計力学では分配関数<br>

![image](https://user-images.githubusercontent.com/25688193/31034696-21d2f636-a5a0-11e7-9f6d-81de5b7f9f39.png)

$$ Z = \sum_{i=1}^{n} e^{ \frac{-E_i}{k_B \times T} } $$

<!-- はてなブログ形式
[tex:{ Z = \sum_{i=1}^{n} e^{ \frac{-E_i}{k_B \times T} }　}]<br>
-->

といい重要な意味を持つが、これは、エントロピー最大化に繋がる話しであり、<br>

Helmholtz の自由エネルギーは、この分配関数 Z を用いて、<br>

![image](https://user-images.githubusercontent.com/25688193/31034742-51e4a0ae-a5a0-11e7-8d87-704124ad5467.png)

$$ F = - k_B \times T \times log_e{Z} $$

<!-- はてなブログ形式
[tex:{ F = - k_B \times T \times \log_e Z }]<br>
-->

で表現できるけど、これを使えば、カノニカルアンサンブルのエントロピー S が<br>

![image](https://user-images.githubusercontent.com/25688193/31034763-64b1dec2-a5a0-11e7-834d-e046799b55e1.png)

$$ S = - k_B \times \sum_{i=1}{n} P_i \times \log_e{P_i} $$<br>

<!-- はてなブログ形式
[tex:{ S = - k_B \times \sum_{i=1}{n} P_i \times \log_e P_i }]<br>
-->

と書ける。これはまさに、情報理論でいうとこのシャノンの情報量に対応している。


<a id="ID_1-5"></a>


### 学習方法の分類

<a id="ID_1-5-1"></a>

#### 教師あり学習 [supervised learning] と教師なし学習 [Unsupervised learning]
![image](https://user-images.githubusercontent.com/25688193/30948617-1cb9a46a-a44c-11e7-824b-1f0f23f6780a.png)

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
![image](https://user-images.githubusercontent.com/25688193/30858595-4e038b96-a2fb-11e7-9ac2-4e7131148034.png)
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


<a id="ID_4-1-2"></a>

#### 教師強制と出力層間での回帰構造をもつネットワーク
記載中...

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