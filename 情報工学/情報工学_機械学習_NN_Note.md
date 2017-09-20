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
        1. [強化学習 [reinforcement learning]](#ID_1-5-1)
    1. [ニューラルネットワークにおける損失関数（評価関数、誤差関数）](#ID_1-6)
        1. [① 回帰問題の為の損失関数（評価関数、誤差関数）](#ID_1-6-2)
        1. [② 分類問題の為の損失関数（評価関数、誤差関数）](#ID_1-6-2)
    1. [ニューラルネットワークにおける基本的な学習規則（重みの更新）](#ID_1-7)
        1. [誤り訂正学習 [error correction learning rule]（パーセプトロンの学習規則 [perceptron learing rule] ）</br>＜教師あり学習、オンライン学習＞](#ID_1-7-1)
        1. [最急降下法 [gradient descent mesod] による学習（重みの更新）</br>＜教師あり学習、パッチ学習＞](#ID_1-7-2)
            1. [最急降下法の単層パーセプトロンでの適用](#ID_1-7-2-1)
            1. [最急降下法の多層パーセプトロンでの適用](#ID_1-7-2-2)
        1. [確率的勾配降下法 [stochastic gradient descent mesod] </br>＜教師あり学習、オンライン学習＞](#ID_1-7-3)
        1. [誤差逆伝播法（バックプロパゲーション）[Backpropagation]</br>＜教師あり学習＞](#ID_1-7-4)
1. [パーセプトロン [Perceptron] </br>（階層型ニューラルネットワーク、フィードフォワード型構造）](#ID_2)
    1. [単純パーセプトロン [Simple perceptron]](#ID_2-1)
        1. [誤り訂正学習 [error correction learning rule]（パーセプトロンの学習規則 [perceptron learing rule] ）</br>＜教師あり学習、オンライン学習＞](#ID_2-1-1)
        1. [最急降下法 [gradient descent mesod] による学習（重みの更新）</br>＜教師あり学習、パッチ学習＞](#ID_2-1-2)
    1. [多層パーセプトロン [ MLP : Multilayer perceptron]](#ID_2-2)
        1. [最急降下法 [gradient descent mesod] による学習（重みの更新）</br>＜教師あり学習、パッチ学習＞](#ID_2-2-1)
        1. [誤差逆伝播法（バックプロパゲーション）[Backpropagation]</br>＜教師あり学習＞](#ID_2-2-2)
    1. [パーセプトロンによる論理演算](#ID_2-3)
    1. [パーセプトロンの収束定理](#ID_2-4)
1. [畳み込みニューラルネットワーク [CNN :Convolutional Neural Network]](#ID_3)
1. [連想記憶ネットワーク（ホップフィールドネットワーク [Hopfield network] ）</br>(相互結合型ニューラルネットワーク [mutual connected neural networks]）)](#ID_x)
1. [](#ID_x)
1. [](#ID_x)

<a id="ID_1"></a>

## 概要 [Overview]

<a id="ID_1-1"></a>

### 全体 MAP図
![image](https://user-images.githubusercontent.com/25688193/30622620-bb362f1a-9ded-11e7-8052-9e07a8f762dc.png)

<a id="ID_1-2"></a>

### ニューラルネットワークの概要
![image](https://user-images.githubusercontent.com/25688193/30514810-482d5a7c-9b57-11e7-8d8c-adc2e292203a.png)
![twitter_nn1_1_160825](https://user-images.githubusercontent.com/25688193/30112643-09c7ef7a-934d-11e7-91d2-fcc93505baa0.png)
![twitter_nn1_2_160825](https://user-images.githubusercontent.com/25688193/30112644-09c88430-934d-11e7-9450-6d4861190175.png)

<a id="ID_1-3"></a>

### ニューラルネットワークの主動作
![twitter_nn3 -1_160827](https://user-images.githubusercontent.com/25688193/30112645-09c8e42a-934d-11e7-95f9-87e0ca316b2f.png)

ニューラルネットワーク、より広義には機械学習は、</br>
大きく分けて以下の２つの問題設定＆解決のための手法に分けることが出来る。</br>
① 回帰問題の為の手法。（単回帰分析、重回帰分析、等）</br>
② （クラスの）分類問題の為の手法（SVM、k-NN、ロジスティクス回帰、等）</br>

<a id="ID_1-4"></a>

### 活性化関数 [activate functions]
![twitter_nn2-1_160826](https://user-images.githubusercontent.com/25688193/30112640-09b4803e-934d-11e7-993d-4e35263cda81.png)
![twitter_nn2-2_160826](https://user-images.githubusercontent.com/25688193/30112641-09b5d6d2-934d-11e7-861d-06792890d2f9.png)

<a id="ID_1-4-1"></a>

#### sigmoid, tanh, softsign
活性化関数のグラフ１
> 活性化関数の内、Relu, Relu6, softplus, ELU 関数の図
![processingformachinelearning_tensorflow_1-1](https://user-images.githubusercontent.com/25688193/30203903-ac94e5ec-94be-11e7-867f-fc78b059ef44.png)
[拡大図]
![processingformachinelearning_tensorflow_1-1](https://user-images.githubusercontent.com/25688193/30203883-9ac00c48-94be-11e7-888d-fff494e5d1f7.png)

<a id="ID_1-4-2"></a>

#### Relu, Relu6, softplus, ELU
活性化関数のグラフ２
> 活性化関数の内、sigmoid, tanh, softsign 関数の図
![processingformachinelearning_tensorflow_1-2](https://user-images.githubusercontent.com/25688193/30211949-e16ce07a-94dd-11e7-9562-6d121aeeb59e.png)
[拡大]
![processingformachinelearning_tensorflow_1-2](https://user-images.githubusercontent.com/25688193/30211950-e16e1922-94dd-11e7-9320-7b16dd6006f6.png)

<a id="ID_1-4-2-1"></a>

##### ReLu 関数による勾配消失問題 [vanishing gradient problem] への対応と softmax 関数
勾配消失問題 [vanishing gradient problem] とは、ニューラルネットワークの層が深くなるにつれて、誤差逆伝播法等の学習の際に損失関数の勾配（傾き）が 0 に近くなり、入力層に近い層で誤差（損失関数値）が消失してしまい、うまく学習できなくなるような問題である。<br>

この問題に対応するために開発されたのが、ReLU [rectified linear unit] や MaxOut という活性化関数である。<br>
これらの手法では、誤差消失問題を起こさないため、深い層のネットワークでも学習が可能となり、現在多くのニューラルネットワークで採用されている。<br>

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
P_n = e^(E_n/k_b*T) / ∑{ e^(E_n/k_b*T) } <br>
[tex:{ P_n = \dfrac{ e^{\frac{E_n}{k_B T}} }{ \sum_{i=1}^{n} e^{ \frac{E_i}{k_B \times T } }  } } ]<br>
の形に対応している。<br>

この確率の式の分母を統計力学では分配関数<br>
Z=∑e^(-E_n/k_B*T)　<br>
[tex:{ Z=\sum_{i=1}^{n}e^( \frac{-E_i}{k_B \times T}　}]<br>
といい重要な意味を持つが、これは、エントロピー最大化に繋がる話しであり、<br>

Helmholtz の自由エネルギーは、この分配関数 Z を用いて、<br>
F=-k_B*T*log Z <br>
[tex:{ F = - k_B \times T \times \log_e Z }]<br>
で表現できるけど、これを使えば、カノニカルアンサンブルのエントロピー S が<br>
S= -k_B*∑ P_n*log P_n <br>
[tex:{ S = - k_B \times \sum_{i=1}{n} P_i \times \log_e P_i }]<br>
と書ける。これはまさに、情報理論でいうとこのシャノンの情報量に対応している。

<a id="ID_1-5"></a>


### 学習方法の分類

<a id="ID_1-5-1"></a>

#### 教師あり学習 [supervised learning] と教師なし学習 [Unsupervised learning]
> 記載中...

<a id="ID_1-5-2"></a>

#### バッチ学習 [batch processing] とオンライン学習 [online learning]
![image](https://user-images.githubusercontent.com/25688193/30580233-c7f83474-9d56-11e7-8a0f-38a54892e3d0.png)

<a id="ID_1-5-3"></a>

#### 強化学習 [reinforcement learning]
![image](https://user-images.githubusercontent.com/25688193/30580261-dd196eea-9d56-11e7-8ae6-6f2df8557307.png)


<a id="ID_1-6"></a>

### ニューラルネットワークにおける損失関数（評価関数、誤差関数）

損失関数（評価関数、誤差関数）は、モデルの出力と目的値（真の値、教師データ）との差（いいえ変えれば、誤差、距離）を計測する関数であり、モデルの学習に適用されるものである。</br>

ここで、ニューラルネットワーク、より広義には機械学習は、</br>
大きく分けて以下の２つの問題設定＆解決のための手法に分けることが出来た。</br>
① 回帰問題の為の手法。（単回帰分析、重回帰分析、等）</br>
② （クラスの）分類問題の為の手法（SVM、k-NN、ロジスティクス回帰、等）</br>

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


<a id="ID_1-7"></a>

### ニューラルネットワークにおける基本的な学習規則（重みの更新）

<a id="ID_1-7-1"></a>

#### 誤り訂正学習 [error correction learning rule]（パーセプトロンの学習規則 [perceptron learing rule] ）</br>＜教師あり学習、オンライン学習＞
![image](https://user-images.githubusercontent.com/25688193/30514984-f1ba6d2a-9b5a-11e7-8416-0771f9f87db2.png)
![image](https://user-images.githubusercontent.com/25688193/30628636-7a473ac4-9e12-11e7-8c4b-b342d38913e3.png)
![image](https://user-images.githubusercontent.com/25688193/30628670-9b6ad2ba-9e12-11e7-9894-d9c52653d4a5.png)

<a id="ID_1-7-2"></a>

#### 最急降下法 [gradient descent mesod] による学習（重みの更新）</br>＜教師あり学習、パッチ学習＞
![image](https://user-images.githubusercontent.com/25688193/30624595-3a3797da-9df9-11e7-95eb-5edb913e080f.png)

<a id="ID_1-7-2-1"></a>

##### 最急降下法の単層パーセプトロンでの適用
![image](https://user-images.githubusercontent.com/25688193/30639904-c548d7d4-9e3b-11e7-9492-ba2c6d2061ca.png)
![image](https://user-images.githubusercontent.com/25688193/30637199-9c51d226-9e32-11e7-9301-e9a66ca6e34c.png)
![image](https://user-images.githubusercontent.com/25688193/30637749-38a66b18-9e34-11e7-827a-c282cb8986c2.png)

<a id="ID_1-7-2-2"></a>

##### 最急降下法の多層パーセプトロンでの適用
![image](https://user-images.githubusercontent.com/25688193/30634693-e32e0104-9e2a-11e7-87d9-8b570b8af3b0.png)
![image](https://user-images.githubusercontent.com/25688193/30634719-f9f57a84-9e2a-11e7-9de0-3d8da1268785.png)
![image](https://user-images.githubusercontent.com/25688193/30636431-65a9b5ec-9e30-11e7-9b83-d3a87daa7513.png)

<a id="ID_1-7-3"></a>

#### 確率的勾配降下法 [stochastic gradient descent mesod] </br>＜教師あり学習、オンライン学習＞
> 記載中...

<a id="ID_1-7-4"></a>

#### 誤差逆伝播法（バックプロパゲーション）[Backpropagation]</br>＜教師あり学習＞
> 修正中...
![twitter_nn9-2 _160903](https://user-images.githubusercontent.com/25688193/30112775-70663048-934d-11e7-8280-b27a02dc1e16.png)
![twitter_nn9-3_160903](https://user-images.githubusercontent.com/25688193/30112774-706594d0-934d-11e7-89a7-50814730aafe.png)




<a id="ID_2"></a>

## パーセプトロン [Perceptron] </br>（階層型ニューラルネットワーク、フィードフォワード型構造）

<a id="ID_2-1"></a>

### 単純パーセプトロン [Simple perceptron]
> 修正中...
![twitter_nn4 -1_160829](https://user-images.githubusercontent.com/25688193/30112642-09b65e90-934d-11e7-9cac-2472c4add901.png)

<a id="ID_2-1-1"></a>

#### 誤り訂正学習 [error correction learning rule]（パーセプトロンの学習規則 [perceptron learing rule] ）</br>＜教師あり学習、オンライン学習＞
![image](https://user-images.githubusercontent.com/25688193/30514984-f1ba6d2a-9b5a-11e7-8416-0771f9f87db2.png)
![image](https://user-images.githubusercontent.com/25688193/30628636-7a473ac4-9e12-11e7-8c4b-b342d38913e3.png)
![image](https://user-images.githubusercontent.com/25688193/30628670-9b6ad2ba-9e12-11e7-9894-d9c52653d4a5.png)

<a id="ID_2-1-2"></a>

#### 最急降下法 [gradient descent mesod] による学習（重みの更新）</br>＜教師あり学習、パッチ学習＞
![image](https://user-images.githubusercontent.com/25688193/30624595-3a3797da-9df9-11e7-95eb-5edb913e080f.png)
![image](https://user-images.githubusercontent.com/25688193/30639904-c548d7d4-9e3b-11e7-9492-ba2c6d2061ca.png)
![image](https://user-images.githubusercontent.com/25688193/30637199-9c51d226-9e32-11e7-9301-e9a66ca6e34c.png)
![image](https://user-images.githubusercontent.com/25688193/30637749-38a66b18-9e34-11e7-827a-c282cb8986c2.png)


<a id="ID_2-2"></a>

### 多層パーセプトロン [ MLP : Multilayer perceptron]
> 修正中...
![twitter_nn5 -1_160829](https://user-images.githubusercontent.com/25688193/30112646-09d7f8fc-934d-11e7-81fa-4cc74b1e3e39.png)
![twitter_nn5-1_160829](https://user-images.githubusercontent.com/25688193/30112647-09da02d2-934d-11e7-96a1-a8c4592993cc.png)
![twitter_nn9-1_160902](https://user-images.githubusercontent.com/25688193/30112773-7050f1c4-934d-11e7-9343-398900bd8a2d.png)

<a id="ID_2-2-1"></a>

#### 最急降下法 [gradient descent mesod] による学習（重みの更新）</br>＜教師あり学習、パッチ学習＞
![image](https://user-images.githubusercontent.com/25688193/30624595-3a3797da-9df9-11e7-95eb-5edb913e080f.png)
![image](https://user-images.githubusercontent.com/25688193/30634693-e32e0104-9e2a-11e7-87d9-8b570b8af3b0.png)
![image](https://user-images.githubusercontent.com/25688193/30634719-f9f57a84-9e2a-11e7-9de0-3d8da1268785.png)
![image](https://user-images.githubusercontent.com/25688193/30636431-65a9b5ec-9e30-11e7-9b83-d3a87daa7513.png)

<a id="ID_2-2-2"></a>

#### 誤差逆伝播法（バックプロパゲーション）[Backpropagation]
> 修正中...
![twitter_nn9-2 _160903](https://user-images.githubusercontent.com/25688193/30112775-70663048-934d-11e7-8280-b27a02dc1e16.png)
![twitter_nn9-3_160903](https://user-images.githubusercontent.com/25688193/30112774-706594d0-934d-11e7-89a7-50814730aafe.png)


<a id="ID_2-3"></a>

### パーセプトロンによる論理演算
![twitter_nn6-1_160829](https://user-images.githubusercontent.com/25688193/30112770-703f5f68-934d-11e7-845d-be2240ef4d17.png)
![twitter_nn6-2_160829](https://user-images.githubusercontent.com/25688193/30112772-7042419c-934d-11e7-9330-d8292a108c1c.png)
![twitter_nn8-1 _160902](https://user-images.githubusercontent.com/25688193/30112777-70842ee0-934d-11e7-9486-d3d14be4d6bd.png)
![twitter_nn10-1_160903](https://user-images.githubusercontent.com/25688193/30112972-1a64417a-934e-11e7-96f1-775f232a2767.png)

<a id="ID_2-4"></a>

### パーセプトロンの収束定理
> 記載中...

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