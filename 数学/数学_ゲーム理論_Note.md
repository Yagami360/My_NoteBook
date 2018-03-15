# ゲーム理論 [Game Theory]

ゲーム理論 [Game Theory] に関してのマイノートです。逐次追加予定です。

![twitter_ _ _161001](https://user-images.githubusercontent.com/25688193/36145305-4fe93c50-10f4-11e8-8d99-c1cc8d50748a.jpg)

## 目次 [Contents]

1. [ゲーム理論 [Game Theory]](#ID_1)
    1. [概要](#ID_1-1)
    1. 全体 MAP 図
    1. [戦略形ゲーム [game in staregic form] / 標準形ゲーム [game in normal form]](#ID_1-3)
        1. [ナッシュ均衡点 [Nash equilibrium point]](#ID_1-3-1)
            1. [ゼロ和ゲームでのナッシュ均衡点と鞍点](#ID_1-3-1-1)
            1. [戦略の支配とナッシュ均衡点](#ID_1-3-1-2)
            1. [囚人のジレンマとナッシュ均衡点](#ID_1-3-1-3)
            1. [パレート最適 [Parete optimal]](#ID_1-3-1-4)
            1. [ナッシュ均衡点の一意性](#ID_1-3-1-5)
        1. [混合戦略 [mixed strategy] と期待利得 [expected payoff]](#ID_1-3-2)
            1. [（純戦略における）ナッシュ均衡点の非存在性](#ID_1-3-2-1)
            1. [純戦略 [pure strategy] と混合戦略 [mixed stratey]](#ID_1-3-2-2)
            1. [戦略形ゲームの混合拡大 [mixed extension] されたゲーム](#ID_1-3-2-3)
            1. [混合戦略による実現可能集合 [feasible set]](#ID_1-3-2-4)
        1. [角谷の不動点定理 [Kakutani fixed point theorem] とナッシュ均衡点の存在](#ID_1-3-3)
        1. [ミニマックス定理とゼロ和2人ゲームにおけるナッシュ均衡点の存在性](#ID_1-3-4)
        1. [ナッシュ均衡点の具体的な計算](#ID_1-3-5)
            1. [最適応答対応からのナッシュ均衡点の計算方法](#ID_1-3-5-1)
            1. [maxmin戦略, minmax戦略からのナッシュ均衡点の計算方法](#ID_1-3-5-2)
            1. シャープレイによるラベル法を用いた、ナッシュ均衡点の計算
        1. [「複数均衡」、「均衡選択」の問題](#ID_1-3-6)
            1. [利得支配 [payoff dominate] とリスク支配 [risk dominate]](#ID_1-3-6-1)
        1. [戦略形ゲームの応用例](#ID_1-3-7)
            1. [クールノー複占市場](#ID_1-3-7-1)
    1. [展開形ゲーム [game in extensive form]](#ID_1-4)
        1. [展開形ゲームを構成する要素（ゲームのルール）](#ID_1-4-1)
            1. [ゲームの木 [game tree]](#ID_1-4-1-1)
            1. [プレイヤー分割 [player partition]](#ID_1-4-1-2)
            1. [偶然手番の確率分布族](#ID_1-4-1-3)
            1. [情報分割](#ID_1-4-1-4)
            1. [利得関数](#ID_1-4-1-5)
            1. [ゲームのルールと情報完備ゲーム、情報不完備ゲーム](#ID_1-4-1-6)
        1. [展開形ゲームにおける戦略の概念とナッシュ均衡点](#ID_1-4-2)
            1. [（展開形ゲームにおける）純戦略 [pure strategy]](#ID_1-4-2-1)
            1. [（展開形ゲームにおける）混合戦略 [mixed strategy]](#ID_1-4-2-2)
            1. [局所戦略 [local strategy] と行動戦略 [behavior strategy]](#ID_1-4-2-3)
            1. [行動戦略と期待利得](#ID_1-4-2-4)
            1. [展開形ゲームの戦略形ゲームへの標準化](#ID_1-4-2-5)
            1. [展開形ゲームの戦略とナッシュ均衡点](#ID_1-4-2-6)
        1. [展開形ゲームの分解と合成](#ID_1-4-3)
            1. [展開形ゲームの部分ゲーム](#ID_1-4-3-1)
            1. [展開形ゲームの縮約ゲーム [truncated game]](#ID_1-4-3-2)
            1. [展開形ゲームの分解と合成に関するナッシュ均衡点の基本的な定理](#ID_1-4-3-3)
        1. [完全情報ゲーム](#ID_1-4-4)
        1. 完全記憶ゲーム
        1. 情報のインフレーション
    1. [ゲームの解とナッシュ均衡点の拡張](#ID_1-5)
        1. [部分ゲーム完全均衡点 [sub game perfect equilibrium point]](#ID_1-5-1)
        1. [変動ゲーム [perturbed game] と完全均衡点 [perfect equilibrium point]](#ID_1-5-2)
        1. [ベイジアン意思決定理論の立場からの完全均衡点](#ID_1-5-3)
        1. [逐次均衡点 [sequential equilibrium point]](#ID_1-5-4)
        1. [（弱）完全ベイジアン均衡点 [(weakly) perfect Bayesian equilibrium point]](#ID_1-5-5)
        1. 完全均衡点の存在定理
        1. 完全均衡点と逐次均衡点の計算方法
        1. 戦略の支配と安定性
    1. 情報不完備ゲーム
        1. ベイジアン均衡点
        1. ベイジアンゲーム
        1. 相関均衡点
    1. 繰り返しゲーム
        1. 繰り返し囚人のジレンマ
        1. フォーク定理
        1. 完全フォーク定理
    1. 交渉ゲーム
        1. ナッシュ交渉解
    1. 進化ゲーム
        1. 進化的に安定な戦略 [ESS : evolutionaly stable strategy]
        1. 中立的に安定な戦略 [NSS : neutrally stable strategy]
        1. レプリケータ・ダイナミクス
    1. [参考文献](#参考文献)

---

<a id="ID_1"></a>

## ゲーム理論 [Game Theory]

<a id="ID_1-1"></a>

## ■ 概要
ゲーム理論 [game theory] とは、<br>
社会システムなどの様々なシステムにおいて、複数の意思決定主体、或いは行動主体（プレイヤーという）が存在し、<br>
**各々のプレイヤーが十分に合理的 [rational] であるという前提の元**、ある一定の目的の実現に対し、相互に依存しながらそれを達成することを目指す状況。<br>
即ち、**ゲーム的状況 [game situations]** を数理モデルで定式化することで、このシステムの分析、解析、予想に応用するものである。

尚、ここで言う合理的とは、具体的には、<br>
1. 各プレイヤーが、利得の最大化を目指す。<br>
2. 相手の状況を可能な限り推測した上で、自身の行動を最適化する。<br>
3. 各プレイヤーが、相手のプレイヤーも同じく合理的であるという前提の元、行動を最適化する。<br>

ということを指す。<br>
とは言え、実際の社会システム等においては、プレイヤーは必ずしも合理的であるとは言いかねる。<br>
従って、これをうまくモデル化するにあたって、理想的な合理性の前提を緩和し、その合理性が様々な形で限定されている（＝限定合理性 [bounded rationality]）という前提のもとで、理論を構築するアプローチも存在する。

<br>

ここで、ゲーム理論で扱うゲーム、及びゲーム的状況は、以下のようなゲームに分類される。

- ゲームの利得 [payoff] 、効用 [utitly] で分類
    - **ゼロ和ゲーム（ゼロサムゲーム）  [zero-sum game]**<br>
    プレイヤーの目的が完全に相反し、ゲームにおける利得の合計がゼロになるようなゲーム。
    - **非ゼロ和ゲーム [non-zero-sum game]**<br>
    ゼロサムゲームとは異なり、プレイヤーの目的が完全には相反しておらず、ゲームにおける利得の合計が非ゼロになるようなゲーム。<br>
    一般に、社会システムにおけるゲーム的状況は、この非ゼロ和ゲームとなっていることが多い。

- ゲームのルール（プレイヤーの人数、目的、選択可能な行動等の規約）で分類１
    - **情報完備ゲーム  [game with complete information]**<br>
    ゲームに参加する全てのプレイヤーが、ゲームのルールを完全に知っており、<br>
    更に、全てのプレイヤーが、他のプレイヤーがこの事（全てのルールを知っている事）を相互に認識しているようなゲーム的状況にあるゲーム。<br>
    尚、この際のゲームのルールは、プレイヤー間の共有知識 [common knowledge] であるという。<br>
    チェス、将棋といったボードゲーム、野球などのスポーツは、この情報完備ゲームの典型的な例である。
    - **情報非完備ゲーム [game with incomplete information]**<br>
    情報完備ゲームとは異なり、ゲームのルールがプレイヤー間の共有知識となっていないようなゲーム的状況にあるゲーム。<br>
    一般に、社会システムにおけるゲーム的状況は、この情報非完備ゲームとなっていることが多い。

- ゲームのルールで分類２
    - **非協力ゲーム  [noncooperative game]**<br>
    ゲームの各プレイヤーが、以下の２つのルールを満たすようなゲーム的状況にあるゲーム。<br>
    (1) プレイヤー間でのコミュニケーションが不可能<br>
    (2) 拘束力のある合意（協力）が可能でない<br>
    従って、プレイヤーは各々独立した戦略を決定する（or ぜざる負えない）ことになり、
	この前提のもとに、ゲームの解としての均衡解 [equilibrium point]（ナッシュ均衡）の概念が生じる。
	- **協力ゲーム [cooperative game]**<br>
    非協力ゲームとは異なり、ゲームの各プレイヤーが互いに拘束力のある合意（協力）を行うことが出来るようなゲーム的状況にあるゲーム。<br>
    ここで、この協力ゲームは、非協力ゲームとは完全に相反するものではなく、非協力ゲームの枠組みを使用するゲームとみなすことが出来ることに注意が必要である。<br>
    即ち、例えば、プレイヤーの協力をその実現（協力の実現）に至るまでのプロセスから考えた場合、
    協力を得るための交渉に先立って、個々のプレイヤーは誰と協力すべきか？又、協力するにあたってどのくらいの利得を要求するか？等の個々のプレイヤーに独立した意思決定、即ち非協力ゲームを行うことになる。<br>
    このように、協力ゲームは、協力成立までのプロセスも考慮することで、非協力ゲームの枠組みを使用することになる。

- ゲームに対する数理モデル化の手法で分類
	- **戦略形ゲーム  [game in strategic form] / 標準形ゲーム [game in normal form]**<br>
    ゲーム理論におけるに最も基本的な数理モデルで、<br>
	各プレイヤーの戦略と利得の関係を関数を用いて定式化する手法。
    - **展開形ゲーム [game in extensive form]**<br>
    ゲームにおける戦略（選択）の時系列を木構造を用いて記述することにより、<br>
	ゲームの動的な構造（ダイナミクス）や情報構造を定式化する手法。
    - 提携形ゲーム [game in coalitional form]<br>
    プレイヤーの様々な提携にとって、実現可能な総利得の集合を記述し、提携行動の分析に用いる。


<a id="ID_1-2"></a>

<!--
## 全体 MAP 図
> 記載中...
-->

<a id="ID_1-3"></a>

## ■ 戦略形ゲーム [game in staregic form] / 標準形ゲーム [game in normal form]
戦略形ゲーム（標準形ゲーム）とは、先に記述したように、ゲーム理論における最も基本的な数理モデルであり、
ゲーム理論が扱うゲーム的状況（＝プレイヤーの利得が自身の戦略のみならず相手の戦略にも依存するような相互依存なシステム）を、関数や行列を用いて定式化するものである。

ここでは、まず、市場シェアという１つのゲームを例を元に、この戦略形ゲームの基本的な性質（特に、ナッシュ均衡点）を見ていく。

<!----------------------------------------------------------->

（例）市場シェアゲーム

![image](https://user-images.githubusercontent.com/25688193/36345101-515b5a6a-1468-11e8-9075-63c1d5afe7a2.png)

２つのプレイヤー（企業）A 社, B 社が市場競争しているとする。<br>
両社は共に、現時点で 50% の市場シェアを占有しているが、もし１社のみ新製品を発売するという戦略をとれば、
市場シェアを 70% 獲得することが出来るが、両社ともに新製品を販売するという戦略をとってしまった場合、市場シェアは現在と同じ 50% ずつという結果になってしまう。このような相互依存関係を表で書くと、上表のようになる。

<!----------------------------------------------------------->

この市場シェアゲームのように、<br>
**プレイヤーの戦略と利得（ここでは市場シェア）の関係によって定義されるゲームを、戦略形ゲームという。**

**より一般的には、戦略形 n 人ゲームは以下のような要素の組 G として定義される。**

![image](https://user-images.githubusercontent.com/25688193/36345107-6c457d42-1468-11e8-98ee-0e1eb2d67702.png)

- ![image](https://user-images.githubusercontent.com/25688193/36327291-7e063638-13a1-11e8-8e2c-109d8e5c6bce.png) はプレイヤー集合（各々の要素番号がプレイヤー番号を表す）
- ![image](https://user-images.githubusercontent.com/25688193/36345112-7d754a20-1468-11e8-8bf3-0b7167de3dd0.png) はプレイヤー i の選択可能な戦略、或いは戦略の集合
- ![image](https://user-images.githubusercontent.com/25688193/36327338-a9a4f324-13a1-11e8-8861-89ae1ac06caf.png) は、戦略 S の直積集合 ![image](https://user-images.githubusercontent.com/25688193/36345126-972ba0b8-1468-11e8-95b4-c60e86ba9071.png) 上の関数

ゲームは次のようにプレイ（ゲームプレイ）される。
1. 任意のプレイヤー i は、他のプレイヤーの戦略 ![image](https://user-images.githubusercontent.com/25688193/36345133-b15ca7a2-1468-11e8-9ba5-495059aed321.png) の選択を知らずに、自らの戦略 ![image](https://user-images.githubusercontent.com/25688193/36345140-cf08abca-1468-11e8-8712-a42fff19fef6.png) を選択する。
2. その結果、プレイヤー i は利得 ![image](https://user-images.githubusercontent.com/25688193/36328437-6b43afcc-13a5-11e8-8441-6b77e70abd22.png) を得る。
3. そして、任意のプレイヤーの目的である、自らの利得の最大化に従って戦略を選択する。
4. 尚、![image](https://user-images.githubusercontent.com/25688193/36345149-00346ec8-1469-11e8-800b-c5fdb1ad834c.png) で定義される戦略形ゲームのゲームプレイにおいて、G の各要素 N（任意のプレイヤー）, S（任意の戦略）, f（任意の利得） は、全てのプレイヤーが完全に知っている（共有知識）であるとする。

<br>

<!----------------------------------------------------------->

戦略形ゲーム ![image](https://user-images.githubusercontent.com/25688193/36345149-00346ec8-1469-11e8-800b-c5fdb1ad834c.png) において、
- 全てのプレイヤーの戦略集合 ![image](https://user-images.githubusercontent.com/25688193/36345112-7d754a20-1468-11e8-8bf3-0b7167de3dd0.png) が有限と時、有限ゲームであるといい、
- 全てのプレイヤーの戦略集合 ![image](https://user-images.githubusercontent.com/25688193/36345112-7d754a20-1468-11e8-8bf3-0b7167de3dd0.png) が無限と時、無限ゲームであるという。

本項で扱うのは、主に有限ゲームである。

<br>

<!----------------------------------------------------------->

戦略形ゲーム ![image](https://user-images.githubusercontent.com/25688193/36345149-00346ec8-1469-11e8-800b-c5fdb1ad834c.png) において、<br>
全ての戦略の組 ![image](https://user-images.githubusercontent.com/25688193/36329856-d64839aa-13aa-11e8-85ab-eb7b4a01559c.png) に対して、<br>
![image](https://user-images.githubusercontent.com/25688193/36329875-e89c9d44-13aa-11e8-9ebb-59568ddc72f7.png)　　が成り立つ時、このゲームを**ゼロサムゲーム [zero-sum game]** という。

この関係式が成り立たない（右辺が 0 でない）、<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/36329943-26730f9a-13ab-11e8-8bf9-6d3a79d2f95c.png)　　が成り立つ時、このゲームを**非ゼロサムゲーム [non-zero-sum game]** という。<br>
特に、右辺が定数 K となるとき、<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/36330114-c7691d5e-13ab-11e8-953b-4528953fac43.png)　　が成り立つ時、このゲームを**定和ゲーム [constant-sum game]** であるという。

<br>

<!----------------------------------------------------------->

非ゼロ和２人ゲーム（戦略形ゲーム） G において、<br>
プレイヤー１とプレイヤー２の戦略集合が、それぞれ ![image](https://user-images.githubusercontent.com/25688193/36345181-682cc610-1469-11e8-8a7c-162215534634.png) , ![image](https://user-images.githubusercontent.com/25688193/36345186-7c6033d8-1469-11e8-82fe-f009e385a36d.png) であるとき、<br>
このゲーム G の利得関数 f は、以下のような**双行列 [bimatrix]** で表現することが出来る。

![image](https://user-images.githubusercontent.com/25688193/36341324-b81de1c0-142f-11e8-8a57-57bf2be314d8.png)

この双行列 A において、プレイヤー１は行を選択し、プレイヤー２は列を選択するという意味となる。<br>
そして、双行列 A の (i,j) 成分 ![image](https://user-images.githubusercontent.com/25688193/36341329-d94a9118-142f-11e8-8c5b-4a4272f0c359.png) は、左側の数字 ![image](https://user-images.githubusercontent.com/25688193/36341343-136f324a-1430-11e8-9c61-8193626d3407.png) がプレイヤー１の利得、左側の数字 ![image](https://user-images.githubusercontent.com/25688193/36341345-26c2f390-1430-11e8-9e7d-8215a7401f02.png) がプレイヤー２の利得を表している。<br>

※ 尚、この双行列は、この非ゼロ和２人ゲーム G において、利得関数 f に対応していることより、利得行列 [payoff matrix]ともいう。<br>
そして、非ゼロ和２人ゲーム G が、この利得行列 A を用いて表現（定式化）出来ることより、双行列ゲーム [bimatrix game] ともいう。<br>

<br>

<!----------------------------------------------------------->

ゲームがゼロ和ゲームのとき、<br>
双行列 A の各成分に対し、![image](https://user-images.githubusercontent.com/25688193/36341429-795a3e6e-1431-11e8-8caa-2c648dd7d79a.png) の関係が成り立つことになる。<br>
この時、表記の利便性から、双行列 A におけるプレイヤー２の利得 ![image](https://user-images.githubusercontent.com/25688193/36341345-26c2f390-1430-11e8-9e7d-8215a7401f02.png) を省略して表記することが多い。<br>
つまり、ゼロ和ゲームの場合の双行列は、以下のようにプレイヤー１のみの利得行列で記載出来る。

![image](https://user-images.githubusercontent.com/25688193/36341433-9c059008-1431-11e8-9d44-371610ab9984.png)

<br>

---

<a id="ID_1-3-1"></a>

### ◎ ナッシュ均衡点 [Nash equilibrium point]
非協力ゲームでは、ゲームにおいて、各プレイヤーが合理的であるという前提のもとに、<br>
**「個々のプレイヤーが、他のプレイヤーがどのような戦略を選択するかを予想した上で、自身の最適な戦略を選択する」** という行動を、
如何にして解析するか？が大きなテーマである。<br>
**この問題を解析するにあたって、重要な概念が、ゲームにおける解の概念、即ち、ナッシュ均衡点 [Nash's equlibrium point] の概念**となる。

以下、この詳細を見ていく。

今、戦略形 n 人ゲーム ![image](https://user-images.githubusercontent.com/25688193/36345149-00346ec8-1469-11e8-800b-c5fdb1ad834c.png) において、<br>
全ての戦略の組を ![image](https://user-images.githubusercontent.com/25688193/36329856-d64839aa-13aa-11e8-85ab-eb7b4a01559c.png) とし、
プレイヤー i に対し、この全戦略の組から第 i 成分 ![image](https://user-images.githubusercontent.com/25688193/36345140-cf08abca-1468-11e8-8712-a42fff19fef6.png) を除いた戦略の組（つまり、自身以外の戦略の組）を ![image](https://user-images.githubusercontent.com/25688193/36345133-b15ca7a2-1468-11e8-9ba5-495059aed321.png) とおく。<br>
すると、全戦略の組 ![image](https://user-images.githubusercontent.com/25688193/36329856-d64839aa-13aa-11e8-85ab-eb7b4a01559c.png) に関する、プレイヤー i の利得は ![image](https://user-images.githubusercontent.com/25688193/36345333-a308a180-146b-11e8-946b-d4e643ee5fa2.png) と書ける。<br>

このとき、<br>
![image](https://user-images.githubusercontent.com/25688193/36345381-8eddb4b0-146c-11e8-9166-e78d87f19f3d.png)

![image](https://user-images.githubusercontent.com/25688193/36345520-6cfad410-146f-11e8-8c6a-40ac08223a11.png)

このナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/36345526-96638ca2-146f-11e8-87f7-630f1db7124d.png) でゲームがプレイされると、ゲームのプレイは、この点 ![image](https://user-images.githubusercontent.com/25688193/36345526-96638ca2-146f-11e8-87f7-630f1db7124d.png) で均衡することになる。


<!--------------------------------------------------------------------->

ナッシュ均衡点でゲームのプレイが均衡していく様子を見るために以下の図を示す。

![image](https://user-images.githubusercontent.com/25688193/36353378-3bad79fe-1509-11e8-8b1d-30fdd6fc8e61.png)

1. まず始めに、<br>
プレイヤー１がプレイヤー２の戦略を ![image](https://user-images.githubusercontent.com/25688193/36353399-58c38628-1509-11e8-9463-3fbcd2a53e9e.png) であると予想とし、<br>
プレイヤー２がプレイヤー１の戦略を ![image](https://user-images.githubusercontent.com/25688193/36353406-68e897d2-1509-11e8-88cb-24ff3d1d6115.png) であると予想としたとする。
2. すると、<br>
プレイヤー１の合理的な選択は、プレイヤー２の戦略 ![image](https://user-images.githubusercontent.com/25688193/36353399-58c38628-1509-11e8-9463-3fbcd2a53e9e.png) に対する最適応答 ![image](https://user-images.githubusercontent.com/25688193/36353425-aa544f5e-1509-11e8-950b-9a5da0edf8c3.png) となる。<br>
同様にして、プレイヤー２の合理的な選択は、プレイヤー１の戦略 ![image](https://user-images.githubusercontent.com/25688193/36353406-68e897d2-1509-11e8-88cb-24ff3d1d6115.png) に対する最適応答 ![image](https://user-images.githubusercontent.com/25688193/36353437-c64ff1d6-1509-11e8-99db-a96757f14a15.png) となる。<br>
3. すると、更に、<br>
プレイヤー１の合理的な選択は、プレイヤー２の戦略 ![image](https://user-images.githubusercontent.com/25688193/36353437-c64ff1d6-1509-11e8-99db-a96757f14a15.png) に対する最適応答 ![image](https://user-images.githubusercontent.com/25688193/36353442-e95431a6-1509-11e8-8646-11e5ae0d9cf2.png) となる。<br>
同様にして、プレイヤー２の合理的な選択は、プレイヤー１の戦略 ![image](https://user-images.githubusercontent.com/25688193/36353425-aa544f5e-1509-11e8-950b-9a5da0edf8c3.png) に対する最適応答 ![image](https://user-images.githubusercontent.com/25688193/36353458-04369a22-150a-11e8-93d1-397655c0ee8d.png) となる。
4. 以下同様の原理の繰り返しで、プレイヤー１とプレイヤー２の推論は、互いに最適応答となりうる状態、<br>
即ち、ナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/36353468-37319b98-150a-11e8-98cc-3555b8a976b4.png) に到達する。

そして、このナッシュ均衡点で互いの推論が停止する（均衡点）といった動作となる。

<br>

<!--------------------------------------------------------------------->

<a id="ID_1-3-1-1"></a>

#### ☆ ゼロ和ゲームでのナッシュ均衡点と鞍点 [saddle point]
次に、このナッシュ均衡点に関しての、いくつかの性質を見てみる。

![image](https://user-images.githubusercontent.com/25688193/36888456-e2e62b3e-1e38-11e8-8e24-ebf648a66fa5.png)

<!--------------------------------------------------------------------->

<a id="ID_1-3-1-2"></a>

#### ☆ 戦略の支配とナッシュ均衡点
次に、ナッシュ均衡点が、具体的にどの戦略の組になるのかを調べる際に有用な考えである戦略の支配について見てみる。

![image](https://user-images.githubusercontent.com/25688193/36390218-a0c32c8a-15e5-11e8-9dcc-6e3ec56c6022.png)

ここで、プレイヤー i の戦略 ![image](https://user-images.githubusercontent.com/25688193/36390286-ebc83374-15e5-11e8-905c-c44000646416.png) が、別の戦略 ![image](https://user-images.githubusercontent.com/25688193/36390303-fd00c3a4-15e5-11e8-8b40-94112387f641.png) に支配されるとき、
この戦略 ![image](https://user-images.githubusercontent.com/25688193/36390286-ebc83374-15e5-11e8-905c-c44000646416.png) は、他のプレイヤーのどのような戦略の組に対しても最適応答とはなり得ない。
従って、**ナッシュ均衡点は支配される戦略を含まない！**

<!--------------------------------------------------------------------->

<a id="ID_1-3-1-3"></a>

#### ☆ 囚人のジレンマとナッシュ均衡点

戦略形ゲームの有名な例として、囚人のジレンマ [prisoner's dilemma] というゲームがある。<br>
これは、以下の表のような利得関係にあるゲームである。

（例）囚人のジレンマ<br>
![image](https://user-images.githubusercontent.com/25688193/36390524-b2812138-15e6-11e8-9710-f47c038be625.png)

このゲームのプレイヤー（囚人）は、物理的に隔離されており、互いにコミュニケーションが取れないために、
両者にとって最も合理的である解と思われる互いに黙秘するという合意を事前に得ることが出来ない。（非協力ゲーム）

上表の刑期を利得（利得行列）で置き換えた表の "１例" として、以下のようなものを考える。

![image](https://user-images.githubusercontent.com/25688193/36390829-ad659412-15e7-11e8-9aa4-ab0f11b52d64.png)

上表の利得行列より、２人の囚人にとって、自白という戦略 ![image](https://user-images.githubusercontent.com/25688193/36391169-b14c4f70-15e8-11e8-8cba-fdd81e3eca3d.png) は、黙秘 ![image](https://user-images.githubusercontent.com/25688193/36391186-cb1eef16-15e8-11e8-8707-26dd0e7804eb.png) という戦略を支配していることが分かる。

![image](https://user-images.githubusercontent.com/25688193/36391197-d8c9e0a8-15e8-11e8-800a-6c110868eac2.png)

従って、先の支配戦略とナッシュ均衡点の関係性より、<br>
ナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/36393547-68eb903c-15f3-11e8-9b9a-84be2c36220b.png) という戦略の組となる。

この囚人のジレンマの例のように、**ナッシュ均衡点は、必ずしもプレイヤー全員の利得を最大化するような解ではない**ことに注意が必要である。

<!--------------------------------------------------------------------->

<a id="ID_1-3-1-4"></a>

#### ☆ パレート最適 [Pareto optimal]
先の囚人のジレンマの例で見たように、ナッシュ均衡点は、必ずしもプレイヤー全員の利得を最大化するようなゲームの解ではない。<br>
このプレイヤー全員の利得を最大化するような解に該当するのは、以下のパレート最適性の概念となる。<br>

![image](https://user-images.githubusercontent.com/25688193/36424159-b6497e6a-1685-11e8-961f-150c6bbc69d6.png)

先の囚人のジレンマでの、ナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/36393547-68eb903c-15f3-11e8-9b9a-84be2c36220b.png) は、全体の利得を最大化しておらずパレート最適ではないことが分かる。

<br>

<!--------------------------------------------------------------------->

<a id="ID_1-3-1-5"></a>

#### ☆ ナッシュ均衡点の一意性
先の囚人のジレンマの例では、ナッシュ均衡点は一意（１つ、１箇所）に決まるが、<br>
次の男女の争いのゲームに例が示すように、一般的に、ナッシュ均衡点は必ずしも一意に決まるわけではない。

（例）男女の争い [battle of sexes]<br>

![image](https://user-images.githubusercontent.com/25688193/36428974-a6b10f5e-1694-11e8-88a4-02df27503e48.png)

男性（プレイヤー１）と女性（プレイヤー２）が、ある夜のデートの行き先として、<br>
ボクシングを見に行くか？或いは、バレエを見に行くか？の選択肢（戦術）を持っている。<br>
男性はボクシングを好み、女性はバレエを好むとする。
しかしながら、この２人にとって、各々が好きなほうを見に出かけるより、一緒に出かけるほうが価値が高いとする。<br>
このようなゲームの利得行列の一例を表した表が、上表のようになる。<br>

この表より、ナッシュ均衡点は、(ボクシング, ボクシング)=(2,1), (バレエ,バレエ)=(1,2) の２つとなっており、<br>
ナッシュ均衡点は、一意に決まるわけではないことが分かる。<br>
又、この２つのナッシュ均衡点は、パレート最適であることも分かる。<br>
（但し、この２つのナッシュ均衡点のどちらかを選択するか？において、男女間で利害が発生する。）

---

<!--------------------------------------------------------------------->

<a id="ID_1-3-2"></a>

### ◎ 混合戦略 [mixed strategy] と期待利得 [expected payoff]

<!--------------------------------------------------------------------->

<a id="ID_1-3-2-1"></a>

#### ☆ （純戦略における）ナッシュ均衡点の非存在性
ナッシュ均衡点は、戦略形ゲームにおいて **（純戦略の範囲では）** 必ずしも存在するとは限らない。<br>
そのことを以下のコイン合わせゲームで見てみる。<br>

（例）コイン合わせゲーム [matching pennies]<br>

![image](https://user-images.githubusercontent.com/25688193/36430170-d2e2227c-1697-11e8-8c6e-6f257f1b86a1.png)

このゲームの内容は、以下のようなものである。<br>
プレイヤー１と２が、100円硬貨をトスしたものが、表か裏かを予想する。<br>
この時、<br>
1. ２人が共に同じ面を予想したら、プレイヤー２の勝利となり、プレイヤー１はプレイヤー２に 100 円支払う。
2. 逆に、２人が違う面を予想したらプレイヤー１の勝利となり、プレイヤー２はプレイヤー１に 100 円支払う。

このゲームは、ゼロ和２人ゲームであり、利得行列を図示すると、上表のようになる。<br>

この表（利得行列）から分かるように、このゲームでは、ナッシュ均衡点は存在しない。<br>
即ち、どの戦略の組においても、戦略を変更する動機をもつプレイヤーが存在している。<br>

<br>

<!--------------------------------------------------------------------->

<a id="ID_1-3-2-2"></a>

#### ☆ 純戦略 [pure strategy] と混合戦略 [mixed stratey]
今までは、ある戦略を確定的に１つ選択する方法を考えてきたが、これを純戦略という。<br>
これに対して、ある確率分布に従って戦術の選択を行う方法が考えられるが、これを混合戦略という。<br>

以下、先のコイン合わせゲームにおける混合戦略を考える。<br>
プレイヤー ![image](https://user-images.githubusercontent.com/25688193/36445314-48eafc36-16c1-11e8-8fae-8363b5a98a16.png) は、![image](https://user-images.githubusercontent.com/25688193/36445363-6bc7081c-16c1-11e8-9329-5d14ea2c5a28.png) をコインの表を選ぶ確率とすると、![image](https://user-images.githubusercontent.com/25688193/36445390-7c1f74d8-16c1-11e8-87f8-e64ab90b3d12.png) がコインの裏を選ぶ確率となり、
混合戦略は ![image](https://user-images.githubusercontent.com/25688193/36445414-8ee77fb6-16c1-11e8-8b78-fbe22dc2336a.png) で表せる。<br>

このとき、各々の純戦略の組が選択される確率（実現確率）の分布は、以下の表のように書ける。<br>

（例）コイン合わせゲームにおける、実現確率の分布

![image](https://user-images.githubusercontent.com/25688193/36445440-a8569946-16c1-11e8-8827-293045b12db0.png)

<!--------------------------------------------------------------------->

戦略形ゲームにおいて、各プレイヤーが混合戦略を用いる時、<br>
プレイヤーの利得の**確率分布** ![image](https://user-images.githubusercontent.com/25688193/36452611-9306b4ce-16d8-11e8-98d4-03c9dca1d2f2.png)（＝混合戦略 ![image](https://user-images.githubusercontent.com/25688193/36452660-bf0db3f6-16d8-11e8-9c29-9f1838087f67.png) が純戦略 ![image](https://user-images.githubusercontent.com/25688193/36452700-dc5734be-16d8-11e8-85f4-aae1ebb33562.png) に与える確率） が定まる。<br>

このような状況下で、プレイヤーの利得の確率分布 ![image](https://user-images.githubusercontent.com/25688193/36452611-9306b4ce-16d8-11e8-98d4-03c9dca1d2f2.png) をどのように評価して意思決定するか？によってゲームの振る舞いは異なってくるが、<br>
ここでは、プレイヤーは利得の期待値（＝期待利得）を最大化するように行動すると仮定することにする。<br>
（このような仮定を**期待効用仮説**という。）<br>

<br>

<!--------------------------------------------------------------------->

<a id="ID_1-3-2-3"></a>

#### ☆ 戦略形ゲームの混合拡大 [mixed extension] されたゲーム 
![image](https://user-images.githubusercontent.com/25688193/36478756-5c24dc6c-1749-11e8-96a5-fa1b0d0cc297.png)

期待利得関数 ![image](https://user-images.githubusercontent.com/25688193/36478954-31ce4ff6-174a-11e8-83a2-ccef106ef77a.png) は、先の定義より、

![image](https://user-images.githubusercontent.com/25688193/36478890-e7612e7a-1749-11e8-8e7d-d23c9b5900a1.png)

と書けるので、
直積集合 ![image](https://user-images.githubusercontent.com/25688193/36478905-fda740b6-1749-11e8-86bd-4d0ec563407b.png) 上で連続（滑らかに繋がっている）で、各変数 q_j  に関して線形な関数である。
（![image](https://user-images.githubusercontent.com/25688193/36478970-44c55e2e-174a-11e8-947d-3768d748fc98.png) のときは直線、![image](https://user-images.githubusercontent.com/25688193/36478991-5a62e49a-174a-11e8-97d5-742c252e825e.png) のときは平面）

<br>

<!--------------------------------------------------------------------->

<a id="ID_1-3-2-4"></a>

#### ☆ 混合戦略による実現可能集合 [feasible set]
戦略形ゲームの混合拡大（されたゲーム）では、利得として、期待利得を考えるので、<br>
次に、プレイヤーの実現可能な期待利得ベクトルの集合（＝混合戦略による実現可能集合）を考える。<br>

![image](https://user-images.githubusercontent.com/25688193/36479845-843b417e-174d-11e8-8e9c-88ce7ea9f6b8.png)

<br>

<!--------------------------------------------------------------------->

以下、幾つかの代表的な戦略形ゲームにおいて、実現可能集合がどのようになるか具体的に見てみる。

（例）囚人のジレンマにおける実現可能集合<br>
![image](https://user-images.githubusercontent.com/25688193/36480421-989b7c5e-174f-11e8-9cf1-31b3fa41c6dc.png)<br>
![image](https://user-images.githubusercontent.com/25688193/36508181-51c6e73c-179f-11e8-99ce-4ece6e49dc00.png)

囚人のジレンマにおける実現可能集合は、上表の利得行列より、上図のような凸集合になる。<br>
利得行列の表と実現可能集合の図から分かるように、<br>
この囚人のジレンマにおける**ナッシュ均衡点の利得ベクトル**は (自白,自白)=(-3,-3) である。<br>
尚、このナッシュ均衡点はパレート最適ではない。

<br>

<!--------------------------------------------------------------------->

（例）男女の争いにおける実現可能集合<br>
![image](https://user-images.githubusercontent.com/25688193/36480460-c099896c-174f-11e8-9d6a-413f298499d8.png)<br>
![image](https://user-images.githubusercontent.com/25688193/36508404-fa8f90e4-179f-11e8-8032-85e47ba657d6.png)

男女争いゲームにおける実現可能集合は、上表の利得行列より、上図のような**非凸集合**になる。（詳細は後述）<br>
（※**ナッシュ均衡点は、この例のように必ずしも凸集合になるとは限らない。**）

そして、利得行列の表と、実現可能集合の図より分かるように、<br>
この男女ゲームにおけるナッシュ均衡点の利得ベクトルは、
(ボクシング,バレエ)=(2,1), (バレエ, ボクシング)=(1,2) の２点となる。<br>

以下、上図の実現可能集合の算出過程を示す。<br>

> まず、プレイヤー１（男性）がボクシングを選択する確率を ![image](https://user-images.githubusercontent.com/25688193/36508727-d54bcd24-17a0-11e8-9e41-0a944a1b9d45.png)
> プレイヤー２（女性）がボクシングを選択する確率を ![image](https://user-images.githubusercontent.com/25688193/36508765-f10752cc-17a0-11e8-96c0-1245f1025c34.png) とすると、<br>	
>
> プレイヤー１の期待利得 ![image](https://user-images.githubusercontent.com/25688193/36508857-3b9c86e0-17a1-11e8-9f25-919c474859d6.png) は、<br>
> ![image](https://user-images.githubusercontent.com/25688193/36509996-ea4cc6de-17a4-11e8-8147-321e137b95f4.png)<br>
>
> 同様にして、プレイヤー２の期待利得 ![image](https://user-images.githubusercontent.com/25688193/36509667-c0ea10b8-17a3-11e8-8962-2958ed1cc6ef.png) は、<br>
> ![image](https://user-images.githubusercontent.com/25688193/36510011-f9881f40-17a4-11e8-83e4-936a12a3812e.png)<br>
> 
> 今、![image](https://user-images.githubusercontent.com/25688193/36510075-295e3a9c-17a5-11e8-8dea-6b8d137a1149.png) とおくと、<br>
> ![image](https://user-images.githubusercontent.com/25688193/36539752-3120e682-181b-11e8-8d0d-42701a5cec8b.png)<br>
> x と y は、![image](https://user-images.githubusercontent.com/25688193/36539445-327d6ea2-181a-11e8-8054-3b5a2cc3d247.png) の解であるので、<br>
> ![image](https://user-images.githubusercontent.com/25688193/36539836-7a320040-181b-11e8-878f-c8cf094e476a.png)<br>
> ![image](https://user-images.githubusercontent.com/25688193/36540319-3eb8f2c4-181d-11e8-9018-62fcc37dca4d.png) を代入すると（途中計算略）<br>
> ![image](https://user-images.githubusercontent.com/25688193/36540282-1e408246-181d-11e8-95ea-6852c244af08.png)<br>

---

<a id="ID_1-3-3"></a>

### ◎ 角谷の不動点定理 [Kakutani fixed point theorem] とナッシュ均衡点の存在

先のコイン合わせのゲームのように、<br>
ナッシュ均衡点は、（戦略形ゲームにおいて）”純戦略の範囲では” 必ずしも存在するとは限らない。
しかしながら、<br>
混合戦略まで拡大して考えると、ナッシュ均衡点は、少なくとも１つは存在する！<br>
このことは、角谷の不動点定理を用いて、証明することが出来る。<br>

以下、そのことの詳細を見ていく。<br>

まず、その為の前段階として、最適応答対応なるものを定義する。<br>
![image](https://user-images.githubusercontent.com/25688193/36756149-9a4647f8-1c51-11e8-90f4-3116184e8e38.png)

この最適応答対応と不動点に関して、以下の定理が成り立つ。<br>
![image](https://user-images.githubusercontent.com/25688193/36772281-f0f1d0b8-1c97-11e8-9cf3-05232c4b92db.png)

<!------------------------------------------------------------------->

<a id="ID_1-3-3-1"></a>

#### ☆ 角谷の不動点定理
![image](https://user-images.githubusercontent.com/25688193/36775477-89391630-1ca5-11e8-9f4e-2af6001c69f6.png)

- 参考URL
    - [角谷の不動点定理 - Wikipedia ](https://ja.wikipedia.org/wiki/%E8%A7%92%E8%B0%B7%E3%81%AE%E4%B8%8D%E5%8B%95%E7%82%B9%E5%AE%9A%E7%90%86)

<!------------------------------------------------------------------->

<a id="ID_1-3-3-1-1"></a>

##### ☆ 角谷の不動点定理に関した補足事項
![image](https://user-images.githubusercontent.com/25688193/36775514-b2bdeb2a-1ca5-11e8-9950-79a8c2af5ff7.png)

![image](https://user-images.githubusercontent.com/25688193/36779281-cb59539c-1cb2-11e8-87a9-420b7761de9b.png)

<!------------------------------------------------------------------->

<a id="ID_1-3-3-1-2"></a>

#### ☆ ナッシュ均衡点の存在性の定理
この角谷の不動点定理を用いて、戦略形ゲームにおけるナッシュ均衡点の存在を証明することが出来る。<br>
![image](https://user-images.githubusercontent.com/25688193/36813495-1e8ff998-1d18-11e8-8912-52b6093fa30d.png)

（証明）<br>
最適応答対応（写像）B と、その不動点 ![image](https://user-images.githubusercontent.com/25688193/36814592-5d577da6-1d1b-11e8-9549-de4c40ca6113.png) に関しての定理より、<br>
（混合戦略の組 ![image](https://user-images.githubusercontent.com/25688193/36814561-3e9e8fda-1d1b-11e8-9dc2-ee159640856d.png) がナッシュ均衡点 ⇔ ![image](https://user-images.githubusercontent.com/25688193/36814561-3e9e8fda-1d1b-11e8-9dc2-ee159640856d.png) が不動点。即ち、![image](https://user-images.githubusercontent.com/25688193/36814592-5d577da6-1d1b-11e8-9549-de4c40ca6113.png) が成り立つ）<br>
最適応答対応 B が、角谷の不動点定理の条件（コンパクトな凸性、上半連続性）を満たすことを示せば良い。<br>

> 記載中...

<br>

---

<a id="ID_1-3-4"></a>

### ◎ ミニマックス定理とゼロ和2人ゲームにおけるナッシュ均衡点の存在性
ゼロ和２人ゲームにおける、ナッシュ均衡点の存在は、鞍点の存在と同値となるが、<br>
これは更に、ミニマックス定理と同値となる。<br>

以下、そのことの詳細を見ていく。<br>

<a id="ID_1-3-4-1"></a>

#### ☆ 保証水準、maxmin 戦略、minmax 戦略
![image](https://user-images.githubusercontent.com/25688193/36819188-ad013e7c-1d2b-11e8-82d4-9def519b6a56.png)

![image](https://user-images.githubusercontent.com/25688193/36887585-341aec28-1e35-11e8-80e2-eed071a8db58.png)

![image](https://user-images.githubusercontent.com/25688193/36887890-78150282-1e36-11e8-8409-92c91bef11e8.png)

![image](https://user-images.githubusercontent.com/25688193/36888248-f5ecf286-1e37-11e8-9fb2-e88bcef71925.png)

![image](https://user-images.githubusercontent.com/25688193/36888266-0bb6c790-1e38-11e8-9bc1-4f480657f856.png)

この２つの定理より、ミニマックス定理が成り立つ。<br>
![image](https://user-images.githubusercontent.com/25688193/36834868-969dd874-1d77-11e8-8f44-b218d335cf03.png)

<br>

---

<a id="ID_1-3-5"></a>

### ◎ ナッシュ均衡点の計算方法
ゼロ和２人ゲームにおける、ナッシュ均衡点の具体的な計算方法について示す。<br>

<a id="ID_1-3-5-1"></a>

#### ☆ 最適応答対応からのナッシュ均衡点の計算方法
いま、以下の表のようなゼロ和２人ゲームがあったとする。<br>
![image](https://user-images.githubusercontent.com/25688193/36834460-52970566-1d76-11e8-8ee0-ba953d02d2c5.png)


ここで、各利得値（利得行列の値）は、<br>
![image](https://user-images.githubusercontent.com/25688193/36834505-6d743282-1d76-11e8-94c3-2708ca3f3ebc.png)<br>
![image](https://user-images.githubusercontent.com/25688193/36834533-885b29a2-1d76-11e8-9101-b0182bfbbf5b.png) という条件を満たすとする。

まず、混合戦略によるナッシュ均衡点を計算するための前段階として、
各プレイヤーの最適応答対応を求める。

プレイヤー i (i=1,2) の混合戦略を ![image](https://user-images.githubusercontent.com/25688193/36834636-d5deece0-1d76-11e8-81c1-d97ac4b4e8e4.png) とすると、<br>

プレイヤー１の純戦略と期待利得の関係は、以下の表のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/36875561-cb0753fc-1df3-11e8-9493-c4e4433bb11a.png)

従って、プレイヤー１の最適応答対応<br>
![image](https://user-images.githubusercontent.com/25688193/36875738-aabfb232-1df4-11e8-8d8d-8488e0734234.png)
は、<br>
![image](https://user-images.githubusercontent.com/25688193/36875829-3b111416-1df5-11e8-8662-e5e98c4e48ff.png) の関係より、<br>
![image](https://user-images.githubusercontent.com/25688193/36877200-590f8cca-1dfc-11e8-9e46-49dd02513834.png)<br>
ここで、<br>
![image](https://user-images.githubusercontent.com/25688193/36874820-b58c4580-1df0-11e8-8e1a-a830ecbe1496.png)<br>
![image](https://user-images.githubusercontent.com/25688193/36874844-c8b74d12-1df0-11e8-93d0-3a4d3865474a.png) とおいている。<br>

<!------------------------------------------------------------------>

同様にして、<br>
プレイヤー２の純戦略と期待利得の関係は、以下の表のようになり、<br>
![image](https://user-images.githubusercontent.com/25688193/36875871-74097ce0-1df5-11e8-9f20-2fa3569ef723.png)<br>

従って、プレイヤー２の最適応答対応<br>
![image](https://user-images.githubusercontent.com/25688193/36875886-9052ff0c-1df5-11e8-935d-d473495df0e0.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/36875902-aafda88e-1df5-11e8-99f7-b9e950eee609.png) の関係より、<br>
![image](https://user-images.githubusercontent.com/25688193/36877214-6db034cc-1dfc-11e8-9887-bba71e9351cd.png)<br>
ここで、<br>
![image](https://user-images.githubusercontent.com/25688193/36876273-8e5f8bfa-1df7-11e8-8368-bb08e304f1eb.png)<br>
![image](https://user-images.githubusercontent.com/25688193/36876289-a0270e9e-1df7-11e8-822b-d37683af671b.png) とおいている。<br>

<!------------------------------------------------------------------>

このプレイヤー１とプレイヤー２の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/36877519-f02d3dfe-1dfd-11e8-9472-692ce77a7305.png) を図示すると、以下のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/36877606-5ebe8700-1dfe-11e8-8e74-236e15a0b773.png)<br>

よって、このゲームのナッシュ均衡点は、上図（オレンジの点）より、<br>
- 純戦略の組 ![image](https://user-images.githubusercontent.com/25688193/36877735-07d9e19a-1dff-11e8-861b-ad75c5222832.png)<br>
- 及び、混合戦略の組 ![image](https://user-images.githubusercontent.com/25688193/36877753-1ac34044-1dff-11e8-9969-d89e9053e90b.png)<br>

が該当する。

<br>

<!------------------------------------------------------------------------------------>

<a id="ID_1-3-5-2"></a>

#### ☆ maxmin戦略, minmax戦略からのナッシュ均衡点の計算方法
次に、このゼロ和２人ゲームのナッシュ均衡点を maxmin戦略, minmax戦略から導出してみる。

（例）コイン合わせゲーム（ゼロ和２人ゲーム）<br>
![image](https://user-images.githubusercontent.com/25688193/36878105-c6c852f2-1e00-11e8-9321-f5330b2b221d.png)<br>
![image](https://user-images.githubusercontent.com/25688193/36878122-d7bcddb2-1e00-11e8-87ce-b7cd4af1bdff.png)<br>

プレイヤー１の期待利得関数 ![image](https://user-images.githubusercontent.com/25688193/36881161-049f8a46-1e10-11e8-945f-e1effd5a1a43.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/36881221-5d8a73fa-1e10-11e8-9ddb-a8a037af3951.png) となる。<br>
よって、プレイヤー１の maxmin 戦略は、<br>
![image](https://user-images.githubusercontent.com/25688193/36886538-5a19bc2e-1e30-11e8-9003-6d9cd6836e48.png)<br>
と書けるが、期待利得関数 ![image](https://user-images.githubusercontent.com/25688193/36883498-0f66f01e-1e1e-11e8-8e93-5b0c2e699822.png) の（確率変数 ![image](https://user-images.githubusercontent.com/25688193/36883503-215c0e12-1e1e-11e8-8224-43f29b7309f4.png) に関する）線形性より、<br>
min 項の最小化は、![image](https://user-images.githubusercontent.com/25688193/36883512-34fbf9c8-1e1e-11e8-89e8-aee83edeca73.png) 或いは ![image](https://user-images.githubusercontent.com/25688193/36883520-4b3e431c-1e1e-11e8-9286-373bd5ae5d01.png) の条件下で実現される。（＝線形なので、端っこの条件時に最小化）<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/36886591-8e9da1ae-1e30-11e8-9218-9cb583b8be67.png)<br>
を満たす解 ![image](https://user-images.githubusercontent.com/25688193/36883564-912d2df2-1e1e-11e8-9d63-39be2ade740c.png) が、プレイヤー１の maxmin 戦略となる。<br>

この maxmin 式を図で書くと、以下の図のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/36883865-66f9a9f0-1e20-11e8-9c17-83873f2201ae.png)

上図より、プレイヤー１の maxmin 戦略となる ![image](https://user-images.githubusercontent.com/25688193/36883564-912d2df2-1e1e-11e8-9d63-39be2ade740c.png) は、![image](https://user-images.githubusercontent.com/25688193/36883892-9e457aba-1e20-11e8-885c-f36cee060765.png) となる。<br>

<br>

<!------------------------------------------------------------------------------------->


同様にして、<br>
プレイヤー２の期待利得関数 ![image](https://user-images.githubusercontent.com/25688193/36886653-c9c5fff6-1e30-11e8-808b-a3f5ea49fd8e.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/36886795-66173c12-1e31-11e8-8707-112b9fe671e0.png) となる。<br>

プレイヤー２の minmax 戦略は、<br>
![image](https://user-images.githubusercontent.com/25688193/36886838-a02e0552-1e31-11e8-8413-abba733d735a.png)<br>
と書けるが、期待利得関数 ![image](https://user-images.githubusercontent.com/25688193/36886653-c9c5fff6-1e30-11e8-808b-a3f5ea49fd8e.png) の（確率変数 ![image](https://user-images.githubusercontent.com/25688193/36886260-d1a6c31a-1e2e-11e8-9128-3ea5ae8972ae.png) に関する）線形性より、<br>
max 項の最大化は、![image](https://user-images.githubusercontent.com/25688193/36886337-3db7cc0c-1e2f-11e8-878a-7dcc54bb3176.png) 或いは ![image](https://user-images.githubusercontent.com/25688193/36886352-4c24c1aa-1e2f-11e8-9730-f87195198877.png) の条件下で実現される。（＝線形なので、端っこの条件時に最小化）<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/36886871-c46ced16-1e31-11e8-9841-9c072b465010.png)<br>
を満たす解 ![image](https://user-images.githubusercontent.com/25688193/36886894-e606857c-1e31-11e8-9bfb-b115ea153b9c.png) が、プレイヤー２の minmax 戦略となる。<br>

この minmax 式を図で書くと、以下の図のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/36887008-732293a6-1e32-11e8-83db-b63dc8efcada.png)

上図より、プレイヤー２の minmax 戦略となる ![image](https://user-images.githubusercontent.com/25688193/36886894-e606857c-1e31-11e8-9bfb-b115ea153b9c.png) は、![image](https://user-images.githubusercontent.com/25688193/36887031-8bef11a2-1e32-11e8-8c24-a9b504f7b6c4.png) となる。

まとめると、<br>
プレイヤー１の maxmin 戦略は、![image](https://user-images.githubusercontent.com/25688193/36887052-ab17f558-1e32-11e8-88fe-7862b786ed98.png)<br>
プレイヤー２の minmax 戦略は、![image](https://user-images.githubusercontent.com/25688193/36887031-8bef11a2-1e32-11e8-8c24-a9b504f7b6c4.png)<br>
となり、両者は一致しているので、<br>
ミニマックス定理より、この点 ![image](https://user-images.githubusercontent.com/25688193/36887069-be59210a-1e32-11e8-9214-4a6266edf0e8.png) はナッシュ均衡点となる。<br>

<br>

<!------------------------------------------------------------------------------------>

---

<a id="ID_1-3-5-3"></a>

#### ☆ シャープレイによるラベル法を用いた、ナッシュ均衡点の計算

> 記載中...

<br>

---

<a id="ID_1-3-6"></a>

### ◎ 「複数均衡」、「均衡選択」の問題
これまでの戦略形ゲームにおけるナッシュ均衡点の例で見てきたように、<br>
一般に、戦略形ゲームにおいて、ナッシュ均衡点は複数存在するが、<br>
それらの内、どの均衡点が、ゲームにおいて実際に実現されるか？という結論は、<br>
ナッシュ均衡点の理論のみでは導けていない。<br>

この複数個のナッシュ均衡点の内、<br>
どの均衡点がゲームにおいて実際に実現されるかの原理を提供する理論（枠組み）は、**「複数均衡」、「均衡選択」の問題** と呼ばれる。<br>

以下、この枠組みの初歩的な内容を見ていく。<br>

<a id="ID_1-3-6-1"></a>

#### ☆ 利得支配 [payoff dominate] とリスク支配 [risk dominate]
まず、以下２人ゲームを例を考える。<br>

（例）２人ゲームの利得関数表<br>
![image](https://user-images.githubusercontent.com/25688193/36895252-a2f1f04e-1e51-11e8-963f-efcb8360c4ce.png)

このゲームのナッシュ均衡点は、<br>
![image](https://user-images.githubusercontent.com/25688193/36895272-b3970f56-1e51-11e8-9182-f3e339be95eb.png) と ![image](https://user-images.githubusercontent.com/25688193/36895295-c3d54f54-1e51-11e8-8cbf-4adbae784ac8.png) となるが、<br>
均衡点 A では、均衡点 B より、大きな利得を得ることが出来る。<br>

このとき、ナッシュ均衡点 A はナッシュ均衡点 B を利得支配 [payoff dominate] するという。<br>
（※先の、戦略の支配、パレート最適と同様の概念）<br>

合理的なプレイヤーは、利得支配するほうのナッシュ均衡点 A を選択すると考えられるので、<br>
このゲームにおいて、実際に実現されるナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/36895272-b3970f56-1e51-11e8-9182-f3e339be95eb.png) となる。<br>

<br>

<!-------------------------------------------------------------------------->

次に、別の２人ゲームの例を考える。<br>

（例）２人ゲームの利得関数表<br>
![image](https://user-images.githubusercontent.com/25688193/36895974-2f67f166-1e54-11e8-9910-d6e9454bfb3d.png)

このゲームにおいてもナッシュ均衡点は、<br>
![image](https://user-images.githubusercontent.com/25688193/36895272-b3970f56-1e51-11e8-9182-f3e339be95eb.png) と ![image](https://user-images.githubusercontent.com/25688193/36895295-c3d54f54-1e51-11e8-8cbf-4adbae784ac8.png) となるが、<br>

先の例とは異なり、２つのナッシュ均衡点の間に利得支配の関係性は存在しない。<br>
従って、どちらの均衡点がゲームの解となるのか？このままでは不明である。<br>
（プレイヤーが、どちらの均衡点を選択するか迷ってしまう。）<br>

これは例えば、<br>
プレイヤー１は均衡点 A のほうが、均衡点 B より、より高い利得を得ることが出来るが、<br>
プレイヤー２の立場は逆であり、それ故に、相手が均衡点 B に従えば、戦略 (a,b) の組が選択されてしまい、<br>
結果的に、利得が 0 になってしまうというリスクが存在する。<br>
といった具合である。<br>

**このリスクによって、選択するナッシュ均衡を判断できないか？** というのが、<br>
**リスク支配 [risk dominate]** の基本的な概念である。<br>

具体的には、この例の場合、<br>

- プレイヤー１にとって、<br>
  プレイヤー２が、均衡点 A に従う（選択する）確率 p が 3/(5+3)=0.375 以上であると予想できる場合、<br>
  戦略 a の期待利得は、戦略 b の期待利得を上回るため、均衡点 A を選択したほうが良い。<br>
- 同様に、プレイヤー２にとって、<br>
  プレイヤー１が、均衡点 B に従う（選択する）確率 p が 2/(6+2)=0.25 以上であると予想できる場合、<br>
  戦略 b の期待利得は、戦略 a の期待利得を上回るため、均衡点 A を選択したほうが良い。<br>
- ここで、各プレイヤーが、<br>
  相手プレイヤーの戦略選択の確率 p が一様分布（ランダム分布）であると予想できるとき、<br>
  プレイヤー１がリスクを背負っも、均衡点 A を選択したほうが良い確率が 1−0.375=0.675 であるのに対し、<br>
  プレイヤー２がリスクを背負っも、均衡点 B を選択したほうが良い確率が 1−0.25=0.75 である。<br>
- 従って、この２つの確率 0.675, 0.75 を比較して、どちらの均衡点を選択すべきか推論する。<br>
  即ち、 0.75 > 0.675 なので、プレイヤー１は、自らがリスクを賭けて均衡点 A を選択する動機よりも強い動機で、<br>
  相手プレイヤー２が、均衡点 B を選択するであるうと推論し、結果、均衡点 A ではなく B を選択する。<br>
  同様にプレイヤー２も、プレイヤー１のこのような推論を推論し、自らの選択として、均衡点 B を選択する。<br>
- 最終的に、２人のプレイヤーは、均衡点 B を選択し、このゲームの２つの均衡点の解として、均衡点 B が選択される。<br>
  **このとき、ナッシュ均衡点 B は、ナッシュ均衡点 A をリスク支配するという。**<br>
- ここで、0.75 > 0.625 の関係は、6/((6+2))> 5/((5+3))  又は 6×3>5×2 の関係より算出されており、同値である。<br>
  つまり、２つの均衡点の内、（プレイヤーの）均衡点からの **離脱損失 [deviation loss] の積** が大きいほうの均衡点が、<br>
  他の均衡点をリスク支配していると考えることが出来る。

<br>

この 2×2 の非ゼロ和ゲームにおけるリスク支配の概念を一般化すると、以下のように定義できる。<br>
![image](https://user-images.githubusercontent.com/25688193/36897866-afab06f4-1e5b-11e8-8a8b-d61d60d87989.png)

<br>

<!--------------------------------------------------------->

均衡選択の問題が複雑となる大きな原因は、<br>
この利得支配とリスク支配の対象が、ゲームによっては、それぞれ対立してしまうことに起因する。<br>

例えば、以下のような非ゼロ和２人ゲームを考える。<br>

（例）非ゼロ和２人ゲームの利得関数表<br>
![image](https://user-images.githubusercontent.com/25688193/36921428-af996600-1ea7-11e8-9ec3-065cc77833e1.png)<br>

このゲームにおいてもナッシュ均衡点は、<br>
![image](https://user-images.githubusercontent.com/25688193/36895272-b3970f56-1e51-11e8-9182-f3e339be95eb.png) と ![image](https://user-images.githubusercontent.com/25688193/36895295-c3d54f54-1e51-11e8-8cbf-4adbae784ac8.png) となるが、<br>

これまでの例とは異なり、<br>
ナッシュ均衡点 A は、ナッシュ均衡点 B を利得支配するが、<br>
逆に、ナッシュ均衡点 B は、ナッシュ均衡点 A をリスク支配している。<br>

即ち、<br>
プレイヤー１，２共に、均衡点 A を選択すれば、均衡点 B より大きな利得を得ることが出来る（ A が B を利得支配）が、<br>
均衡点 A を選択すると、利得が 9 → 0 になるリスクが存在する。（ B が A をリスク支配）<br>

このように、利得支配とリスク支配が対立してしまうようなゲームにおいては、<br>
利得支配とリスク支配のどちらをどの程度優先させるべきか？という問題が生じる。<br>
この問題は、プレイヤーが利得支配とリスク支配のどちら行動原理を、ゲーム理論の前提である合理性の概念として採用するかに依存するが、<br>
ハーサニとゼルテンの理論では、利得支配を優先させる。<br>
又、これはとは別に、進化ゲームなどの、より広義のアプローチから、均衡点の選択の問題を取り扱う手法も存在する。<br>

<br>

---

<a id="ID_1-3-7"></a>

### ◎ 戦略形ゲームの応用例

<a id="ID_1-3-7-1"></a>

#### ☆ クールノー複占市場
企業１と企業２という２つの企業が、同質な財を市場に供給しているとする。<br>

企業 i (=1,2) の供給量を ![image](https://user-images.githubusercontent.com/25688193/36930774-904572a0-1eeb-11e8-9837-86852cce8aac.png) とし、<br>
財の価格 p は、市場（逆）需要関数<br>
![image](https://user-images.githubusercontent.com/25688193/36930779-a301c268-1eeb-11e8-81ab-22d91f8edd0a.png) により定まるとする。<br>
![image](https://user-images.githubusercontent.com/25688193/36930783-b33d28fc-1eeb-11e8-856a-58698f851e6c.png)<br>

又、企業 i の費用関数を<br>
![image](https://user-images.githubusercontent.com/25688193/36930793-db12e1e6-1eeb-11e8-9190-e601b64985aa.png)<br>
（ ![image](https://user-images.githubusercontent.com/25688193/36930799-224bca1e-1eec-11e8-913c-629291918451.png) : 企業 i が、財１単位を生産するための限界費用）<br>

このときの企業 i の利潤関数は、<br>
![image](https://user-images.githubusercontent.com/25688193/36930803-32984b86-1eec-11e8-923d-5fe51151df14.png) となるとする。<br>

そして、企業１と企業２は利潤（利得）の最大化を目的として、各々の供給量を調整する。<br>

供給量の組 ![image](https://user-images.githubusercontent.com/25688193/36930810-560f8f3e-1eec-11e8-97df-db2eaafb4e77.png) がクールノー＝ナッシュ均衡 [Carnot-Nash equilibrium] であるとは、<br>
利潤関数 ![image](https://user-images.githubusercontent.com/25688193/36930814-6586914c-1eec-11e8-95e6-08fc81615434.png) に関して、<br>
![image](https://user-images.githubusercontent.com/25688193/36930818-8027a0ea-1eec-11e8-8265-ee4f75856831.png)<br>
が成り立つときのことを言う。<br>

以下、このクールノー＝ナッシュ均衡の値を、具体的に求めてみる。<br>

まず、企業１の利潤関数<br>
![image](https://user-images.githubusercontent.com/25688193/36931397-c048ab14-1ef7-11e8-8d49-54adf44e2bc7.png)<br>

を、![image](https://user-images.githubusercontent.com/25688193/36931410-d8515ecc-1ef7-11e8-99df-6658f30c8ea2.png) の値の範囲によって場合分けすると、<br>

![image](https://user-images.githubusercontent.com/25688193/36931411-eb530778-1ef7-11e8-8b2a-97a6bf283956.png)<br>

そして、この利潤関数より、企業１の最適応答対応<br>
![image](https://user-images.githubusercontent.com/25688193/36932859-101f1dce-1f13-11e8-9465-bb32ecb346f4.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/36932911-01e9e0a8-1f14-11e8-945f-faf57378168a.png)

同様にして、企業２の最適応答対応は、<br>
![image](https://user-images.githubusercontent.com/25688193/36932917-15c5a864-1f14-11e8-801c-7d2955b20f6a.png)<br>

企業１と企業２の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/36933002-1baa842e-1f15-11e8-80b3-c9f04c438689.png) を図示すると、以下のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/36933070-8f96b91a-1f16-11e8-92a0-35cc79b86e42.png)<br>
上図の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/36933002-1baa842e-1f15-11e8-80b3-c9f04c438689.png) の交点 E は、クールノー＝ナッシュ均衡となり、<br>
![image](https://user-images.githubusercontent.com/25688193/36933181-2a6494de-1f18-11e8-8d12-74735e575cfa.png) となる。


<br>

---

<a id="ID_1-4"></a>

## ■ 展開形ゲーム [game in extensive form]
ゲームにおける戦略（選択）の時系列を**木構造を用いて記述**することにより、<br>
ゲームの動的な構造（ダイナミクス）や情報構造を定式化する手法。<br>
より詳細には、プレイヤーの幾つかの手番の系列と、各手番でのプレイヤーによる選択を木構造でモデル化する。<br>

まず、クールノー複占市場を例に、この展開形ゲームを構築してみる。<br>

（例）不確実性下での複占市場<br>
以下のような系（不確実性下での複占市場）を考える。<br>

1. 企業１と企業２が同質財を生産し、市場に供給している。
	
2. 各企業 i の財の供給量の選択は、<br>
	- 高水準：![image](https://user-images.githubusercontent.com/25688193/36942634-dea92f20-1fba-11e8-9319-ec877f75346a.png)<br>
	- 低水準：![image](https://user-images.githubusercontent.com/25688193/36942636-f1ac45e4-1fba-11e8-96e5-69f5ce44e062.png)<br>
   の２通りであるとする。<br>
	
3. 財の価格は、市場需要関数に依存して定まるが、<br>
   市場の状態に、 好景気（G）と不景気（B)の２種類の状態（景気）があり、<br>
   この景気状態によって、需要関数が上下にシフトし、財の価格が変動する。<br>
	
4. 結果的に、企業の利潤は、２つの企業の供給量と市場の状態（好景気 or 不景気）に依存する。<br>

この系における、企業の意思決定のプロセスを、以下の図のような木構造（**ゲームの木**という）で表現する。<br>
![image](https://user-images.githubusercontent.com/25688193/36942931-d90591d2-1fc2-11e8-9c38-9fb06b1025e4.png)

上図のゲームの木において、<br>
1. まず、木の底点 ![image](https://user-images.githubusercontent.com/25688193/36944227-2e6a936c-1fdb-11e8-8911-3ab03c1fa84d.png) は、このゲームの出発点であり、<br>
   このノードで市場の状態である、 好景気（G）と不景気（B)が決定され、<br>
   この状態によって、左右に枝分かれする。<br>
   この際、好景気（G） or 不景気（B）になる確率は、何れも 1/2 であり、等確率で発生する。<br>
   このような偶然メカニズムを総称して、自然 [nature] と呼び、<br>
   自然が発生する手番を、**偶然手番 [chance move]** と呼ぶ。<br>
	
2. 木の定点で市場の状態が定まると、ゲームのフェイズは、<br>
   次に、好景気（G）or 不景気（B）に依存して、分岐ノード ![image](https://user-images.githubusercontent.com/25688193/36944234-4cc654ea-1fdb-11e8-82ed-573629eb7704.png) に移行する。<br>
   このノードでは、企業１の手番（意思決定）である供給量の調整が行われ、<br>
   高水準：![image](https://user-images.githubusercontent.com/25688193/36944241-620a487a-1fdb-11e8-9690-881107e7d261.png) or 低水準：![image](https://user-images.githubusercontent.com/25688193/36944243-76fcda72-1fdb-11e8-8d1d-be86455ab09f.png) が選択される。<br>

3. 次に、ゲームのフェイズは、
   市場の状態、及び企業１の手番に依存して、分岐ノード ![image](https://user-images.githubusercontent.com/25688193/36944248-8ab9e33e-1fdb-11e8-8f22-6fc3831a4525.png) に移行する。<br>
   このノードでは、企業２の手番（意思決定）である供給量の調整が行われ、<br>
   高水準：![image](https://user-images.githubusercontent.com/25688193/36944271-e2e3320e-1fdb-11e8-97ff-ab86b2c40835.png) or 低水準：![image](https://user-images.githubusercontent.com/25688193/36944276-f0b46952-1fdb-11e8-86e1-6973c1d3cb8e.png) が選択される。<br>

4. 最後に、ゲームのフェイズは、<br>
   先の企業２の手番の選択によって、木の末端ノードに到着し、<br>
   各企業は、ノードに対応した利得を得た後（上図では、上側の数字が企業１の利得、下側の数字が企業２の利得を示している。）、ゲームは終了する。<br>

<!----------------------------------------------------------->

<a id="ID_1-4-1"></a>

### 展開形ゲームを構成する要素（ゲームのルール）
展開形ゲームとは、この例のようなゲームの木を用いて記述されるゲームの１つの表現形式であり、<br>
形式的には、以下の５つの要素の組<br>
![image](https://user-images.githubusercontent.com/25688193/36944372-1e9b96a4-1fde-11e8-84f2-9419b596a7ac.png)<br>

- K : ゲームの木<br>
- P : プレイヤーの分割<br>
- p : 偶然手番の確率分布族<br>
- U : 情報分割<br>
- h : 利得関数<br>

から構成され、この５つの要素を、ゲームのルールという。<br>

<a id="ID_1-4-1-1"></a>

#### ① ゲームの木 [game tree] : K
![image](https://user-images.githubusercontent.com/25688193/36955566-8f137bf2-206c-11e8-9e78-f91d38cbb809.png)<br>
ゲームの木（K） は、上図のように、初期点 0 を持つ有限な有向木であり、<br>
点（ノード）と枝（エッジ）から構成される。<br>
任意の点 x へ初期点 0 を結ぶ枝とその点（ノード）の系列を、点 x へのパス（道）という。<br>
ゲームの木では、任意の点 x に対して、初期点 0 からのパスは一意に決まる。<br>

ここで、<br>

- 任意の異なる点 x, y に対し、点 y が点 x へのパス上に存在するとき、<br>
  x は y の後にある、或いは、y は x の前にあるといい、x > y で表現する。<br>
- x > y で、特に x と y が１つの枝で結合されているとき、x と y ノードは隣接しており、<br>
  x を y の直後の点、或いは、y を x の直前の点という。<br>
- 点 w が x > w となる点 x を持たない、即ち末端ノードにあるとき、<br>
  w を木の頂点といい、この頂点からなる集合を W で表す。<br>
- 木のノードの内、頂点以外の点を、手番 [move] といういい、<br>
  その全体を集合 X で表す。<br>
- 手番 x に対して、x と x の直後の点を結ぶ１本の枝を、<br>
  手番 x における選択肢 [alternative] といい、その全体（２本）を A(x) で表す。<br>
	
そして、ゲームの木の１つの頂点に対し、初期点 0 とその頂点を結ぶパスを、ゲームのプレイという。<br>
言い換えると、ゲームの木におけるゲームのプレイとは、<br>
初期点 0 から始まって、各手番でプレイヤーが１つの選択肢を選択することによって、<br>
ゲームが進行し、最後に１つの頂点に到達してゲーム終了することである。<br>


<a id="ID_1-4-1-2"></a>

#### ② プレイヤー分割 [player partition] : P
![image](https://user-images.githubusercontent.com/25688193/36959252-7247d7c6-2084-11e8-9b6f-3c0b4d418cea.png)<br>

プレイヤー分割 ![image](https://user-images.githubusercontent.com/25688193/36959269-8b7e2f06-2084-11e8-883b-6b681e2b37ff.png) は、ゲームの木 K の手番全体である X の分割の１つである。（上図参照）<br>
0 以外の添字 i =1,2, ... ,n は、このゲームに参加するプレイヤーを表し、集合 ![image](https://user-images.githubusercontent.com/25688193/36959996-6944bc9e-2088-11e8-8592-8d52c20e0d0f.png) は、プレイヤー i の手番の全体を表す。<br>
又、集合 ![image](https://user-images.githubusercontent.com/25688193/36971560-8d17597a-20af-11e8-86f5-8825ff70b186.png) は、ゲームにおける偶然手番の全体の集合を表す。<br>
（偶然手番では、プレイヤーの意志とは無関係にある偶然メカニズムにより、枝の選択が行われる。）<br>

すると、<br>
1. ![image](https://user-images.githubusercontent.com/25688193/36959301-ac89c426-2084-11e8-8c09-f9c1e01f858f.png)<br>
2. 任意の２人のプレイヤー分割 ![image](https://user-images.githubusercontent.com/25688193/36959353-eb53ca62-2084-11e8-9093-56bc61cfdba6.png) に対して、![image](https://user-images.githubusercontent.com/25688193/36959363-fc33f064-2084-11e8-8338-305642c99673.png)<br>
3. ![image](https://user-images.githubusercontent.com/25688193/36959379-0d48a700-2085-11e8-94b8-7ca05d2ba4ba.png)<br>
の関係が成り立つ。<br>


<a id="ID_1-4-1-3"></a>

#### ③ 偶然手番の確率分布族 : p
![image](https://user-images.githubusercontent.com/25688193/36981641-0c681a0e-20d1-11e8-87ee-b6d6c0cafd23.png)<br>

ゲームの全ての偶然手番 ![image](https://user-images.githubusercontent.com/25688193/36981718-36f52e2e-20d1-11e8-8960-a5a957865b70.png) に対して、<br>
x での選択肢の集合 A(x) 上の、１つの確率分布 ![image](https://user-images.githubusercontent.com/25688193/36981748-4a1fcab8-20d1-11e8-8413-aa395b4f59f4.png) が定められている。<br>
この確率分布 ![image](https://user-images.githubusercontent.com/25688193/36981748-4a1fcab8-20d1-11e8-8413-aa395b4f59f4.png) が、x の各選択肢 ![image](https://user-images.githubusercontent.com/25688193/36981793-68098230-20d1-11e8-8649-b539c7a44df1.png) に付与する確率を ![image](https://user-images.githubusercontent.com/25688193/36981826-80c014a6-20d1-11e8-9d07-9fed56358419.png) と書くと、<br>
![image](https://user-images.githubusercontent.com/25688193/36981854-90916ec0-20d1-11e8-95d4-fced440e87de.png)

の関係が成り立つ。（確率の定義より）<br>

この偶然手番での確率分布 ![image](https://user-images.githubusercontent.com/25688193/36981748-4a1fcab8-20d1-11e8-8413-aa395b4f59f4.png) の具体的な形は、<br>
過去のデータからの（客観的な）統計的手法で推定される確率分布であったり、<br>
プレイヤーが自らの限定的な情報や知識から、主観的な判断により推定される確率分布であったりする。<br>


<a id="ID_1-4-1-4"></a>

#### ④ 情報分割：U
![image](https://user-images.githubusercontent.com/25688193/37014674-8fdad4ac-2145-11e8-8f50-94281c74d1d9.png)<br>
**プレイヤーが、ある手番でどのような選択を行うかは、**<br>
**そのゲームにおける、それ以前の手番（プレイ）の結果で得られる情報に大きく依存する。**<br>
**このような構造をモデルに取り入れるために、情報分割の概念を導入する。**<br>
以下、その詳細について。<br>

情報分割 ![image](https://user-images.githubusercontent.com/25688193/37008787-3102a694-2127-11e8-8f1f-710774cf43bd.png) は、![image](https://user-images.githubusercontent.com/25688193/37008802-420ad39e-2127-11e8-8192-e50d39d6a42e.png) の更なる分割（細分割）であり、<br>
![image](https://user-images.githubusercontent.com/25688193/37008859-7dbcad4a-2127-11e8-9104-4dd450de52c5.png)<br>
が成り立つ。そして、この情報分割 ![image](https://user-images.githubusercontent.com/25688193/37008869-91a1e730-2127-11e8-86c7-e5e48cd69518.png) に属する集合 ![image](https://user-images.githubusercontent.com/25688193/37008885-a0cba50c-2127-11e8-94e1-cc7c7aebc024.png) を、プレイヤー i の情報集合という。<br>

そして、このプレイヤー i の情報集合 u に、以下のような性質を持たせる。<br>
今、ゲームのプレイにより、プレイヤー i の情報集合 u 中に手番 x に到達したとする。<br>
このとき、このプレイヤー i は、<br>
(性質１)　情報集合 u のある手番 x に到達したことを知ることが出来る。<br>
(性質２)　しかし、情報集合 u の数ある手番の中で、どの手番に到達したか？は知ることが出来きない。<br>

この２つの性質により、プレイヤーはそれぞれの手番において、<br>
ゲームの過去のプレイに関して把握している情報を定義することが出来る。<br>

更に、次の２つの性質が、情報集合の意味から必要とされる。<br>
（性質３）情報集合 u は、同じプレイと２回以上交点してはならない。<br>
（性質４）情報集合 u に含まれる全ての手番は、同じ数の枝（選択肢）を持つ。<br>
（性質５）情報分割 ![image](https://user-images.githubusercontent.com/25688193/37014809-7a9710f0-2146-11e8-9c4c-af951df82320.png) に属する全ての情報集合は、ただ１つの偶然手番から構成される。<br>

例えば、（性質３）or（性質５）が満たされない情報分割のケースとして、以下の図のようなケースが考えられる。<br>
![image](https://user-images.githubusercontent.com/25688193/37030559-b790ff88-217e-11e8-8136-2e6c13ae68a1.png)<br>
情報分割をこのように分割してしまった場合、<br>
プレイヤーは、初期点 0 での行動の選択を把握することが出来ないことになるが、<br>
これは、今考えてるゲームの条件としては適切ではない。<br>


<a id="ID_1-4-1-5"></a>

#### ⑤ 利得関数：h
![image](https://user-images.githubusercontent.com/25688193/37031791-82208620-2183-11e8-9e27-ce76c8f4857b.png)<br>
利得関数 h は、ゲームの木 K の各頂点 ![image](https://user-images.githubusercontent.com/25688193/37032009-569c6ef0-2184-11e8-8f1b-1bca4e39380e.png) に対して、<br>
利得ベクトル ![image](https://user-images.githubusercontent.com/25688193/37032024-6477314a-2184-11e8-9fcc-ba26ab9ce12f.png) を対応させる。<br>
（この利得ベクトルの第 i 成分は、プレイヤー i の利得を表している。）<br>

<!---------------------------------------------------------------------->

<a id="ID_1-4-1-6"></a>

#### ☆ ゲームのルールと情報完備ゲーム、情報不完備ゲーム
展開形ゲームは、（先に見たように）<br>
５つの要素（ゲームの木、プレイヤー分割、偶然手番の確率分布族、情報分割、利得関数）で構成されるが、<br>
これらの５つの要素を、（展開形ゲームにおける）ゲームのルールという。<br>

展開形ゲームのプレイにおいて、<br>
各プレイヤーは、このゲームのルールを知っているか否か？の違いは、このプレイに大きな影響を及ぼす。<br>
従って、この情報の違いにより、展開形ゲームを分類する。<br>

具体的には、以下の共有知識なるものを定義する。<br>

- **共有知識**<br>
 「ゲームのルールを全てのプレイヤー完全に知っていて、更に、他のプレイヤーもゲームのルールを知っている。」<br>
  という事実を、全てのプレイヤーが共通に知っていると仮定する。<br>
  このとき、このゲームのルールは、全てのプレイヤーの共有知識であるという。<br>

そして、共有知識の有無でゲームを、情報完備ゲーム or 情報不完備ゲームに分類する。<br>
- **（展開形ゲームの）情報完備ゲーム [game with complete information]**<br>
  ゲームのルールが、全てのプレイヤーの共有知識である（＝全てのプレイヤーが共有知識を持っている）<br>
  ようなゲーム的状況にある展開形ゲーム<br>
- **（展開形ゲームの）情報不完備ゲーム [game with incomplete information]**<br>
  ゲームのルールが、必ずしも全てのプレイヤーの共有知識でない（＝全てのプレイヤーが共有知識を持っているとは限らない）<br>
  ようなゲーム的状況にある展開形ゲーム<br>

<br>

---

<a id="ID_1-4-2"></a>

### ◎ 展開形ゲームにおける戦略の概念とナッシュ均衡点
展開形ゲームでは、一般的に、<br>
各プレイヤーが複数の手番を持ち、実際にゲームをプレイする前に、各手番でどのような選択を行うのかを計画することが出来る。<br>
このようなプレイヤーの行動、選択計画を、（展開形ゲームにおける）戦略という。<br>
ここでは、この戦略の概念に含まれる、（展開形ゲームにおける）**純戦略**、**混合戦略**、**局所戦略**、**行動戦略**を見ていく。<br>


<a id="ID_1-4-2-1"></a>

#### ☆ （展開形ゲームにおける）純戦略 [pure strategy]
![image](https://user-images.githubusercontent.com/25688193/37066733-22dca1e6-21ea-11e8-8eb6-e28b15d6cc15.png)<br>


例えば、先の複占市場のゲームにおいては、<br>
![image](https://user-images.githubusercontent.com/25688193/37067273-63ed828e-21ec-11e8-86f3-c90de71e2dfa.png)<br>

企業１（プレイヤー分割 ![image](https://user-images.githubusercontent.com/25688193/37067347-a8332476-21ec-11e8-90ce-344abb3f54f3.png) の情報分割 ![image](https://user-images.githubusercontent.com/25688193/37067361-b649dbcc-21ec-11e8-93c1-09808e0d57b0.png) が対応）の純戦略は、<br>
![image](https://user-images.githubusercontent.com/25688193/37067367-c66a76ec-21ec-11e8-9883-2baa3425a4ef.png)<br>
の４通り存在する。<br>

一方、企業２（プレイヤー分割 ![image](https://user-images.githubusercontent.com/25688193/37067385-e0d099d0-21ec-11e8-86a8-0482f1419db8.png) の情報分割 ![image](https://user-images.githubusercontent.com/25688193/37067417-0842b00c-21ed-11e8-9e03-e5f29435086e.png) が対応）の純戦略は、<br>
![image](https://user-images.githubusercontent.com/25688193/37067434-19c271aa-21ed-11e8-8d17-f93febd2f188.png)<br>
の２通りのみである。（情報分割が ![image](https://user-images.githubusercontent.com/25688193/37067417-0842b00c-21ed-11e8-9e03-e5f29435086e.png) のみであるため）<br>
尚、この企業２の情報分割が ![image](https://user-images.githubusercontent.com/25688193/37067417-0842b00c-21ed-11e8-9e03-e5f29435086e.png) のみであるということは、<br>
企業２が、この分割内のどの手番に存在しているのか把握出来ないことを意味する。<br>
即ち、企業２は、市場の状態（好景気 or 不景気）や、それに応じた企業１の供給量（高水準 or 低水準）を把握できない。<br>
それ故に、企業２の戦略は、上表の２種類しか存在し得ない。<br>



<a id="ID_1-4-2-2"></a>

#### ☆ （展開形ゲームにおける）混合戦略 [mixed strategy]
![image](https://user-images.githubusercontent.com/25688193/37073990-91cc32ec-220d-11e8-9952-88bc1dda995f.png)<br>

例えば、先の複占市場のゲームにおいては、<br>
企業１の混合戦略 ![image](https://user-images.githubusercontent.com/25688193/37075382-e4e319b2-2214-11e8-9287-1474cde2db99.png) は、それぞれ以下の表のようになり、<br>
![image](https://user-images.githubusercontent.com/25688193/37075393-f6e196c0-2214-11e8-8161-336b9232407d.png)<br>
![image](https://user-images.githubusercontent.com/25688193/37075432-1c90b1ee-2215-11e8-9376-494cc6fd4374.png)
となる。<br>

一方、企業２の混合戦略 q_2 は、それぞれ以下の表のようになり、<br>
![image](https://user-images.githubusercontent.com/25688193/37075489-5db3172a-2215-11e8-86d7-db95082ea23d.png)<br>
![image](https://user-images.githubusercontent.com/25688193/37075516-86ab2c62-2215-11e8-9b39-c2b5234d0deb.png)<br>
となる。<br>



<a id="ID_1-4-2-3"></a>

#### ☆ 局所戦略 [local strategy] と行動戦略 [behaivor strategy]
![image](https://user-images.githubusercontent.com/25688193/37084276-67b9652e-2235-11e8-9586-58443b25c38a.png)<br>

例えば、複占市場ゲームにおいては、<br>
企業１の局所戦略は、それぞれ以下の表のようになり、<br>
![image](https://user-images.githubusercontent.com/25688193/37085119-94dcead8-2237-11e8-8e2e-27effaabed4b.png)<br>
行動戦略 ![image](https://user-images.githubusercontent.com/25688193/37085367-38dc0bbe-2238-11e8-821e-4afafcb4c718.png) は、これらの局所戦略の組み合わせである、<br>
![image](https://user-images.githubusercontent.com/25688193/37085173-aee31056-2237-11e8-8129-b60b854838c1.png)<br>
となる。<br>

一方、企業２の局所戦略は、それぞれ以下の表のようになり、<br>
![image](https://user-images.githubusercontent.com/25688193/37085394-4922ec7c-2238-11e8-84c3-cf9974f664a8.png)<br>
行動戦略 ![image](https://user-images.githubusercontent.com/25688193/37085449-685cf74a-2238-11e8-85ce-ba72108c84d4.png) は、これらの局所戦略の組み合わせである、<br>
![image](https://user-images.githubusercontent.com/25688193/37085472-7630417e-2238-11e8-83d1-4814397362ac.png)<br>
となる。<br>



<a id="ID_1-4-2-4"></a>

#### ☆ 行動戦略と期待利得
展開形ゲームにおける期待利得を導入するための前段階として、いくつかの定義を行う。<br>
![image](https://user-images.githubusercontent.com/25688193/37091800-d6ad9290-224c-11e8-88a9-9e5896411649.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37091853-01627c6c-224d-11e8-8a4e-5d8ea39d1322.png)：<br>
  プレイヤーの行動戦略の組。<br>
- ![image](https://user-images.githubusercontent.com/25688193/37091869-0e839b38-224d-11e8-8cac-629a6cddde01.png)：<br>
  プレイヤー i が、情報分割の集合 ![image](https://user-images.githubusercontent.com/25688193/37091913-2b9d32c4-224d-11e8-829c-1c5db787d1c9.png) において、枝（選択肢）![image](https://user-images.githubusercontent.com/25688193/37091926-39b105f2-224d-11e8-8bfd-3cdef185c9a3.png) を選択する確率。<br>
- ![image](https://user-images.githubusercontent.com/25688193/37091943-4879ffda-224d-11e8-8f80-3038122b023b.png)：<br>
  ゲームの木の頂点 ![image](https://user-images.githubusercontent.com/25688193/37091989-7f66a728-224d-11e8-8e7a-464aa6eeeca0.png) に対して、初期点 0 から w へのパス上に存在する全ての枝の集合。<br>
  この集合 ![image](https://user-images.githubusercontent.com/25688193/37092017-8efebdb0-224d-11e8-9c0f-1b398a544e6f.png) は、偶然手番の枝の集合 ![image](https://user-images.githubusercontent.com/25688193/37092039-a0360eee-224d-11e8-88f2-2548ea2a9d5b.png) と、プレイヤー i のプレイヤー分割上の枝の集合 ![image](https://user-images.githubusercontent.com/25688193/37092059-af35880c-224d-11e8-8c27-d4288d84e3c5.png) から構成される。<br>
- ![image](https://user-images.githubusercontent.com/25688193/37092072-be08e3e2-224d-11e8-8fec-4fb528ad25fd.png)：<br>
  偶然手番の枝の集合 ![image](https://user-images.githubusercontent.com/25688193/37096979-a7c1ae7e-225d-11e8-8606-031594665553.png) に含まれる（偶然手番の）全ての枝 e が選択される確率。<br>
  即ち、<br>
  ![image](https://user-images.githubusercontent.com/25688193/37096942-8f9451ee-225d-11e8-887e-7c015ae35071.png)<br>

<br>

<!----------------------------------------------------------->

行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37132787-00e2d828-22d3-11e8-8993-07958456c7e0.png) に従って、ゲームがプレイされる場合において、<br>
ゲームの木の頂点 ![image](https://user-images.githubusercontent.com/25688193/37132800-17e558de-22d3-11e8-9a97-5945dfa59907.png) に到達する確率、<br>
即ち、行動戦略 b の組の元での、頂点 w の実現確率 [realizization probability] は、<br>
![image](https://user-images.githubusercontent.com/25688193/37132839-433ebbd8-22d3-11e8-8a07-8794ad5e6efc.png)<br>
で定義される。<br>
そして、![image](https://user-images.githubusercontent.com/25688193/37132861-601757e2-22d3-11e8-97c0-3672964c0e13.png) の場合、頂点 w は、行動戦略 b の元で到達可能であるという。<br>

<br>

<!----------------------------------------------------------->

又、純戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37132901-abb4dc92-22d3-11e8-9789-db59d8e73619.png) の元での、<br>
頂点 w の実現確率 ![image](https://user-images.githubusercontent.com/25688193/37132925-bcf2ddec-22d3-11e8-8bdf-99441d78ffc7.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/37132945-e568b882-22d3-11e8-912f-b127f4043208.png)<br>

<br>

<!----------------------------------------------------------->

更に、混合戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37133252-868479c6-22d5-11e8-839b-c8c25fa3f193.png) によってゲームがプレイされる時の、<br>
頂点 w が到達される確率 ![image](https://user-images.githubusercontent.com/25688193/37133264-96910906-22d5-11e8-8558-cbbb144afe11.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/37133379-6506c0d2-22d6-11e8-8a53-93ae491e8446.png)<br>

<br>

<!----------------------------------------------------------->

これらの実現確率、到達可能な頂点を用いて、展開形ゲームにおける期待利得を定義すること出来る。<br>
即ち、<br>
プレイヤーの行動戦略、或いは混合戦略の組を ![image](https://user-images.githubusercontent.com/25688193/37133593-b952f1c8-22d7-11e8-941a-81f74adbe5e2.png) とすると、<br>
この戦略の組に対する、プレイヤー i の期待利得 ![image](https://user-images.githubusercontent.com/25688193/37133630-f5595f7c-22d7-11e8-98a6-fde9a93c9811.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/37133774-9fbf9bca-22d8-11e8-983b-645cc88fda63.png)<br>
ここで、![image](https://user-images.githubusercontent.com/25688193/37133609-dddd572c-22d7-11e8-834b-255e66eedcc7.png) は、この戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37133593-b952f1c8-22d7-11e8-941a-81f74adbe5e2.png) の元での、頂点 w の実現確率となっており、<br>
**この期待利得の式は、到達可能な頂点での利得の期待値となっていることが分かる。**<br>
（「頂点wの実現確率」×「その頂点における利得」を各頂点について計算し和をとったもの）<br>


<a id="ID_1-4-2-5"></a>

#### ☆ 展開形ゲームの戦略形ゲームへの標準化
展開形ゲームにおける、プレイヤーの戦略と期待利得の概念から、<br>
展開形ゲームから戦略形ゲームへの標準化を考えることが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/37137607-d505ed32-22e9-11e8-90fa-9e4f5358135b.png)<br>

例えば、先の複占市場の場合、<br>
![image](https://user-images.githubusercontent.com/25688193/37138301-f42d4248-22ec-11e8-8ea9-2867b0c16379.png)<br>
上図の展開形ゲームから、以下の表のような戦略形ゲームを構築することが出来る。<br>
![image](https://user-images.githubusercontent.com/25688193/37138319-04db3212-22ed-11e8-8253-02a5b69416b0.png)<br>


<a id="ID_1-4-2-6"></a>

#### ☆ 展開形ゲームの戦略とナッシュ均衡点
戦略形ゲームにおいて、ナッシュ均衡点を定義することが出来たが、<br>
展開形ゲームの同様に、ナッシュ均衡点を定義することが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/37138837-f3952236-22ee-11e8-9394-0d056eb71973.png)<br>

---

<a id="ID_1-4-3"></a>

### ◎ 展開形ゲームの分解と合成
チェスや将棋などを展開形ゲームで記述すると、そのモデルは大規模で複雑なものとなり、<br>
当然、このような展開形ゲームを解析することが困難になってくる。<br>
このような大規模な展開形ゲームを解析するのに有効な手法として、ゲームの分解と合成という手段がある。<br>

以下、複占市場のゲームを例に、このゲームの分解と合成を見ていく。<br>

先の複占市場のゲームにおいて、<br>
企業１、企業２共に、市場の状態（不景気：B、好景気：G）を知ることが出来るケースを考える。<br>
（※先の複占市場のゲームでは、企業１のみ市場の状態を知ることが出来きていた。）<br>

このケースにおける展開形ゲームの木は、以下の図のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/37153099-01fe9e8a-231f-11e8-82b7-39aaf1e0fec4.png)<br>

一方、先の複占市場ゲームにおいて、企業１のみが、景気の状態を知ることが出来ていたモデルは、以下の図のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/37153131-18679ea6-231f-11e8-92e1-685532a4af26.png)<br>

２つを比較すると、企業２の情報分割が、![image](https://user-images.githubusercontent.com/25688193/37153200-40f0e99a-231f-11e8-97bf-9d553c680773.png) のように１つ → ２つになっていることが分かる。<br>

複占市場のゲームにおいて、企業１、２共に景気の状態を知ることが出来るモデルの図において、<br>
赤字の枠で囲んだ箇所は、展開形ゲームの木の一部であるが、<br>
この部分のみで１つの小さな展開形ゲームの木の構造をなしていることが分かる。<br>
このような部分木を、展開形ゲームの部分ゲームという。<br>


<a id="ID_1-4-3-1"></a>

#### ☆ 展開形ゲームの部分ゲーム
より一般的には、展開形ゲームの部分ゲームを以下のように定義することが出来る。<br>
![image](https://user-images.githubusercontent.com/25688193/37193539-bda792e8-23ad-11e8-9170-1ee3e2c3d6aa.png)<br>

（例）部分ゲームを構成する展開形ゲーム<br>
![image](https://user-images.githubusercontent.com/25688193/37193016-9961688e-23ab-11e8-8584-a9688dccb07f.png)<br>

（例）部分ゲームを構成しない（出来ない）展開形ゲーム<br>
![image](https://user-images.githubusercontent.com/25688193/37193036-aeded8fe-23ab-11e8-8fc8-67e39a894ac4.png)<br>


<a id="ID_1-4-3-2"></a>

#### ☆ 部分ゲームの行動戦略
展開形ゲームの部分ゲームは、それ自身で１つのより小さな展開形ゲームを構成しているため、<br>
展開形ゲームのときと同じように、部分ゲームに対しても、その行動戦略というものが定義出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/37196770-6daf6500-23bb-11e8-8a09-d6c4c9e3e7b7.png)<br>


<a id="ID_1-4-3-2"></a>

#### ☆ 展開形ゲームの縮約ゲーム [truncated game]
![image](https://user-images.githubusercontent.com/25688193/37202945-7656a9ca-23cf-11e8-99a0-db7c5daa2f14.png)<br>

例えば、先の複占市場ゲームにおいて、<br>
部分ゲームでの行動戦略の組として、![image](https://user-images.githubusercontent.com/25688193/37208319-531487b0-23e4-11e8-9f6f-fe7899fefd4f.png) が取られた場合の縮約ゲームは、以下の図のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/37237910-ae46286c-245e-11e8-9325-78e935dbb643.png)<br>
![image](https://user-images.githubusercontent.com/25688193/37237913-b9b44cb0-245e-11e8-9a96-ec0f0dbde558.png)<br>


> 記載中...


<a id="ID_1-4-3-3"></a>

#### ☆ 展開形ゲームの分解と合成に関するナッシュ均衡点の基本的な定理
ここでは、展開形ゲームの部分ゲームと縮約ゲームの概念を用いて、<br>
展開形ゲームの分解と合成に関する、ナッシュ均衡点の基本的な定理を見ていく。<br>

そのために、まず以下の（部分ゲームの）到達可能性を定義する。<br>
![image](https://user-images.githubusercontent.com/25688193/37218305-5d23c788-2403-11e8-9805-f25f078a7edb.png)<br>

展開形ゲームの分解に関する、ナッシュ均衡点の基本的な定理は、<br>
以下のような、展開形ゲームにおけるナッシュ均衡点の分解定理と呼ばれるものである。<br>
![image](https://user-images.githubusercontent.com/25688193/37237818-7f40c59c-245c-11e8-9236-d88d89c1d1bc.png)<br>

この展開形ゲームにおけるナッシュ均衡点の分解定理がもたらす重要な意味は、<br>
**展開形ゲームのナッシュ均衡点は、均衡プレイ上 [on-equilibrium play] （＝行動戦略がナッシュ均衡点であるようなゲームプレイ）にある全ての部分ゲームに、ナッシュ均衡点を導く（＝元の展開形ゲームでのナッシュ均衡点から、部分ゲームでのナッシュ均衡点を構築できる）ということである！**<br>
**これはまた、逆説的に言うと、ナッシュ均衡点は、均衡プレイ上にない [off-equilibruim play] 部分ゲームには、必ずしもナッシュ均衡点を導かないということでもある。**<br>

<br>

<!----------------------------------------------------------------------------->

次に、展開形ゲームの合成に関する、ナッシュ均衡点の基本的な定理を見ていく。<br>
これは、以下のような、展開形ゲームにおけるナッシュ均衡点の合成定理と呼ばれるものである。<br>
![image](https://user-images.githubusercontent.com/25688193/37238696-37c45978-246f-11e8-8bdb-7a5a36a4bba7.png)<br>

この展開形ゲームにおけるナッシュ均衡点の合成定理より、<br>
**部分ゲームにおけるナッシュ均衡点と、縮約ゲームにおけるナッシュ均衡点を合成することにより、**<br>
**元の展開形ゲーム全体におけるナッシュ均衡点が得られることが分かる！**<br>

<br>

以下、この展開形ゲームにおけるナッシュ均衡点の合成定理の応用例として、<br>
先の複占市場ゲームを考える。<br>

まず、この展開形ゲームにおける部分ゲームとして、以下の図のような部分ゲームを考えると、<br>
![image](https://user-images.githubusercontent.com/25688193/37238873-1395fd50-2473-11e8-8f00-4e6fe37a35d6.png)<br>

この部分ゲームにおける利得関数は、以下の表のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/37238880-2967774e-2473-11e8-9da1-2636351d0916.png)<br>
この表より、部分ゲームでのナッシュ均衡点は ![image](https://user-images.githubusercontent.com/25688193/37238882-4227b046-2473-11e8-9c2d-68cad4fd24e6.png) となることが分かる。<br>


次に、この部分ゲームとその行動戦略で縮約したゲームは、以下の図のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/37239581-bbea63ca-2481-11e8-8c6b-3f92a1fd1916.png)<br>
この縮約ゲームにおける利得関数は、以下の表のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/37239585-d0fe9420-2481-11e8-8479-b4e7be7af706.png)<br>
この表より、縮約ゲームでのナッシュ均衡点は ![image](https://user-images.githubusercontent.com/25688193/37239590-e6955fbc-2481-11e8-84fc-a46e332fd883.png) となることが分かる。<br>

従って、この部分ゲームのナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37238882-4227b046-2473-11e8-9c2d-68cad4fd24e6.png) と縮約ゲームのナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37239590-e6955fbc-2481-11e8-84fc-a46e332fd883.png) から構成される、<br>
元の展開形ゲームの行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37239593-1cf8e1be-2482-11e8-9e82-580798f99efb.png) は、<br>
ナッシュ均衡点の合成定理より、ナッシュ均衡点になる。<br>


---

<a id="ID_1-4-4"></a>

### ◎ 完全情報ゲーム [game with perfect information]
展開形ゲームの重要なサブクラスの１つに、完全情報ゲームがある。<br>
この完全情報ゲームにおいては、純戦略によるナッシュ均衡点が必ず存在する。<br>
以下、そのことを見ていく。<br>

まず、完全情報ゲームの定義を行う。<br>
![image](https://user-images.githubusercontent.com/25688193/37241604-3d227faa-249f-11e8-8280-8538f2579ccf.png)<br>

<br>

<!---------------------------------------------------------------->

この完全情報ゲームにおいて成り立つナッシュ均衡点に関する定理が、<br>
以下の完全情報ゲームの基本定理と呼ばれるものである。<br>
![image](https://user-images.githubusercontent.com/25688193/37248304-41a66dfc-2512-11e8-8388-21e1cefbeb0f.png)<br>

この完全情報の基本定理が導く重要な結論は、<br>
**完全情報ゲームでは、偶然手番の確率分布や利得関数がどのような形状であろうとも、**<br>
**純戦略によるナッシュ均衡点が少なくとも１つ存在するということである。**<br>
このようなゲームは、**確定的 [determinate]** であると呼ばれるが、<br>
この言葉を用いると、この定理は、完全情報ゲームが確定的であることを示している。<br>
又、この定理を逆説的に言うと、<br>
完全情報ゲームの木の長さが無限の長さで、かつ利得関数が複雑な形の関数になる場合は、<br>
必ずしも、純戦略によるナッシュ均衡点が存在するとは限らないことが知られている。<br>

<br>

<!---------------------------------------------------------------->

この完全情報の基本定理は、また、純戦略によるナッシュ均衡点の具体的な計算方法も示してくれる。<br>
即ち、<br>
最初に、ゲームの木の頂点に１番近い手番の最適行動を求め、<br>
次に、この求められた最適行動を前提として、木の頂点に２面目に近い手番でプレイヤーの最適行動を求める。<br>
以下、これらの処理を順次繰り返し、<br>
最後に、ゲームの初期点でのプレイヤーの最適行動を求める。<br>
結果として、得られたプレイヤーの最適行動は、この完全情報ゲームにおける純戦略でのナッシュ均衡点となる。<br>
といった具合である。<br>

このように、完全情報ゲームにおいて、<br>
木の頂点から初期点に向かって、順次、各情報分割の集合での最適行動を求め、<br>
それらを合成（＝次の最適行動の前提）して、ゲーム全体でのナッシュ均衡点を構成していく手法を、<br>
後向き帰納法 [backward indutcion] という。<br>

<br>

（例）男女の争いゲーム（レディーファーストのルール）<br>
![image](https://user-images.githubusercontent.com/25688193/37248719-6c221324-251c-11e8-9ffb-6a6cd44572f5.png)<br>
男女ゲームの争いゲームにおいて、レディーファーストルールを適用して、<br>
ゲームのプレイにおいて、最初に女性がプレイ出来るようにする。<br>
すると、男性は、女性の選択を知った上で、自身の選択を行うことになるので、<br>
このゲームは、完全情報ゲームとなる。（下図）<br>
![image](https://user-images.githubusercontent.com/25688193/37248725-7e9e6980-251c-11e8-8c81-28dbd2bf1ce9.png)<br>

後ろ向き帰納法に従って、このゲームにおける純戦略のナッシュ均衡点を求めると、<br>
まず、女性が、自身の最適行動である、バレエを選択する。<br>
次に、男性が、女性のバレエの選択を知った上での自身の最適行動であるバレエを選択する。<br>
そして、この選択（純戦略）の組 (バレエ,バレエ)=(1,2) が、このゲームにおけるナッシュ均衡点となっている。<br>
尚、レディーファーストルールを適用しない男女ゲームにおいては、<br>
ナッシュ均衡点は、(ボクシング,ボクシング)=(2,1) , (バレエ, バレエ)=(1,2) の２つしていたが、<br>
レディーファーストルールを適用することで、<br>
女性により望ましい選択である (バレエ, バレエ)=(1,2) が選択されていることが分かる。<br>


---

<a id="ID_1-5"></a>

## ■ ゲームの解とナッシュ均衡点の拡張
ここでは、まず、ゲーム理論における解の意味を改めて考えることで、<br>
従来のナッシュ均衡点より強い意味での均衡点の存在を定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/37266526-06527a38-25fe-11e8-9944-b1d8c559bac3.png)<br>

> 記載中...


<a id="ID_1-5-1"></a>

### ◎ 部分ゲーム完全均衡点 [sub game perfect equilibrium point]
まず、以下のチェーンストアゲームの例を考える。<br>
![image](https://user-images.githubusercontent.com/25688193/37266531-1f937f24-25fe-11e8-95cb-e9d748a0d6d2.png)<br>
![image](https://user-images.githubusercontent.com/25688193/37266543-316f2e64-25fe-11e8-8cc8-503129e4b303.png)<br>

- あるチェーンストアが A 町に支店をもっており、ある商品をこの町で独占販売している。<br>
- この市場に対し、ある事業家が、以下の２通りの選択をとり得る。<br>
    - 「小売店を開業し、チェーンストアと同じ商品を販売する。（IN）」<br>
    - 「他の事業に資金を投資する。（OUT）」<br>
- 事業家が、小売店を開業しない場合（OUT）、<br>
    - チェーンストアは、独占利得５を得ることが出来る。<br>
    - 一方、事業家は、他の事業投資の結果、確実に利潤１を得ることが出来る。<br>
- 事業家が、小売店を開業する場合（IN）、<br>
	- チェーンストアの経営戦略として、以下の２通りの選択をとり得る。<br>
		- 「小売店と協調する。（CO）」<br>
		- 「商品の値段を値下げし、小売店と競合する。（AG）」<br>
	- チェーンストアが、小売店と協調する場合、双方は共に、利潤２を得ることが出来る。<br>
	- 一方、チェーンストアが、小売店と競合する場合、双方で値下げ競争が行われ、<br>
      その結果、利潤は共に０になってしまう。<br>

このゲームの全ての手番は、ただ１つの情報分割の集合から構成されているので、<br>
このゲームは、完全情報ゲームとなる。<br>

従って、純戦略によるナッシュ均衡点が、必ず存在する。<br>
このナッシュ均衡点を後ろ向き帰納法で求めると、純戦略の組 <br>
![image](https://user-images.githubusercontent.com/25688193/37268164-ee57c3c0-2607-11e8-9a26-f11c988f7471.png)<br>
はナッシュ均衡点となることが分かる。<br>

又、利潤関数の表より、<br>
![image](https://user-images.githubusercontent.com/25688193/37268178-0409fcba-2608-11e8-985a-0aaa39961013.png)<br>
もナッシュ均衡点になることが分かる。<br>

<br>

<!----------------------------------------------------------->

ここで、この２つのナッシュ均衡点の意味を考える。<br>
１つ目のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268164-ee57c3c0-2607-11e8-9a26-f11c988f7471.png) では、<br>
「事業家は、小売店を開業し、チェーンストアは小売店と協調する」という意味での均衡状態にある。<br>

２つ目のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268178-0409fcba-2608-11e8-985a-0aaa39961013.png) では、<br>
「チェーンストアが、仮に事業家が小売店を開業すれば値下げ競争で対抗してくることを知った上で、<br>
事業家は、これを回避して、他の事業に投資する。」という意味での均衡状態にある。<br>

この２つのナッシュ均衡点は、このゲームの解として適切なのか？を３つの視点から考えてみる。<br>
その結果、２つ目のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268178-0409fcba-2608-11e8-985a-0aaa39961013.png) は、<br>
このチェーンストアゲームの解としては、適切でないことが分かる（後述）<br>

1. 第１の視点（ゲームの情報分割集合でのプレイヤーの利得最大化行動に基づく視点）<br>
   １つ目の視点は、ゲームの情報分割集合でのプレイヤーの利得最大化行動に基づく視点である。<br>
   ２つ目のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268178-0409fcba-2608-11e8-985a-0aaa39961013.png) では、チェーンストアは、AG の選択を行うが、<br>
   これはチェーンストアの情報分割の集合内での利得最大化行動（CO⇒利得２，AG⇒利得０）に反している。<br>
   このチェーンストアの情報分割の集合は、２つ目のナッシュ均衡点のゲームプレイ（事業家 OUT の選択）において、<br>
   到達されない情報分割ではあるが、チェーンストアの行動自体が最初の事業家の選択に影響を与える。<br>
   従って、この手番がゲームプレイで到達されなくとも、チェーンストアの行動は利得最大化行動に基づかなくてはならない。<br>
   ![image](https://user-images.githubusercontent.com/25688193/37268961-ca5e6e20-260b-11e8-95da-ad118a2cada2.png)<br>
   更に、事業家が、チェーンストアの最適行動が CO であることを合理的に予想するならば、<br>
   ２つ目のナッシュ均衡点の行動 OUT ではなく、IN を選択し、より高い利得を得る（利潤：１ → ２）ように行動する考えられる。<br>
   その意味で、２つ目のナッシュ均衡点は、離脱する動機を持つ（＝自己拘束性をもたない）。<br>
   従って、この意味（自己拘束性をもたない）でも、このゲームの解として不適切であると言える。<br>

2. 第２の視点（プレイヤーの合理性の微小な不完全さに対する安定性）<br>
   ２つ目の視点は、プレイヤーの合理性の微小な不完全さに対する安定性に関する視点である。<br>
   一般的なゲーム理論では、プレイヤーは完全な合理性に基づき意思決定を行う主体としてモデル化される。（行動の模範的理論）<br>
   今、このチェーンストアのゲームにおいて、事業家の合理性に僅かな不完全さが加わり、<br>
   ナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268178-0409fcba-2608-11e8-985a-0aaa39961013.png) のゲームプレイにおいて、<br>
   過って微小な確率ではあるが、OUT → IN に選択する可能性が発生したとする。<br>
   このとき、微小な確率ではあるが、チェーンストアの情報分割集合にゲームが到達し、<br>
   期待利得を最大化するチェーンストアの行動は、AG → CO に変化してしまう。<br>
   このように、２つ目のナッシュ均衡点は、プレイヤーの合理性の僅かな変化に対し不安定であり、<br>
   この観点からも、２つ目のナッシュ均衡点、このゲームの解として不適切であると言える。<br>

3. 第３の視点（戦略の支配の観点からの視点）<br>
   ３つ目の視点は、戦略の支配の考えに基づく視点である。<br>
   チェーンストアの戦略 AG は、利得関数の表から分かるように、戦略 CO に支配されている戦略である。<br>
   従って、チェーンストアの意思決定において、支配戦略 CO を選択するのが妥当であり、<br>
   この意味からも、２つ目のナッシュ均衡点は、このゲームの解として不適切であると考えられる。<br>

以上、３つの視点から、２つ目のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268178-0409fcba-2608-11e8-985a-0aaa39961013.png) が、このゲームの解として不適切であることを見てきたが、<br>
逆に、１つ目のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268164-ee57c3c0-2607-11e8-9a26-f11c988f7471.png) は、この３つの視点で要求される事項を満たしており、<br>
このゲームの解として 適切であると考えられる。<br>

そして、２つ目のナッシュ均衡点の問題点を改めて見直してみると、<br>
この問題点は、**”均衡プレイにおいて、到達されない部分ゲームでの、ナッシュ均衡点を導かない”** ことに帰着されることが分かる。<br>
先の展開形ゲームにおけるナッシュ均衡点の分解定理で見てきたように、<br>
ナッシュ均衡点は、均衡プレイによって、到達可能な部分ゲームに対しては、ナッシュ均衡点を導く。<br>
従って、このチェーンストアゲームにおけるナッシュ均衡点の解としての不完全（不適切）さを解消するためには、<br>
**”均衡プレイによって到達されない部分ゲームに対しても、**<br>
**ナッシュ均衡点を導くようにナッシュ均衡点を概念を強くしたものを定義し、**<br>
**これをゲームの解として採用すればよい”** ことが分かる。<br>

<br>

<!------------------------------------------------------------------------->

このナッシュ均衡点の概念を強くしたものが、以下の部分ゲーム完全均衡点である。<br>
![image](https://user-images.githubusercontent.com/25688193/37271459-56b89df0-2616-11e8-9500-9918f30708e7.png)<br>

この定義に基づくと、先のチェーンストアゲームにおいて、<br>
２つ目のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268178-0409fcba-2608-11e8-985a-0aaa39961013.png) は、ナッシュ均衡点を導かない部分ゲームが存在するため、部分ゲーム完全均衡点でない。<br>
一方、１つ目のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37268164-ee57c3c0-2607-11e8-9a26-f11c988f7471.png) は、全ての部分ゲームに対しナッシュ均衡点を導くため、部分ゲーム完全均衡点である。（下図参照）<br>
![image](https://user-images.githubusercontent.com/25688193/37271970-7a040310-2618-11e8-8f44-d3a9a860ec01.png)<br>

<br>

<!------------------------------------------------------------------------->

展開形ゲームにおけるナッシュ均衡点の重要な定理として、<br>
展開形ゲームにおけるナッシュ均衡点の分解定理と合成定理があったが、<br>
この部分ゲーム完全均衡点に関しても、これに該当する定理が成り立つ。<br>
![image](https://user-images.githubusercontent.com/25688193/37272524-3422b9ac-261a-11e8-980d-4240632a415d.png)<br>

この部分ゲーム完全均衡点の分解、合成定理は、言い換えると、<br>

1. 展開形ゲームにおける部分ゲーム完全均衡点は、<br>
   部分ゲームと縮約ゲームにおける、それぞれの部分ゲーム完全均衡点に分解することが出来る。<br>

2. 逆に、部分ゲームと縮約ゲームにおける、それぞれの部分ゲーム完全均衡点を合成することにより、<br>
   元の展開形ゲームにおける部分ゲーム完全均衡点を構成することが出来る。<br>

ということを示している。<br>

<br>

<!------------------------------------------------------------------------->

次に、部分ゲーム完全均衡点の存在性に関する定理を示す。<br>
![image](https://user-images.githubusercontent.com/25688193/37274236-693db1b4-261f-11e8-824e-a33d725e0c70.png)<br>

尚、この定理の証明は、<br>
1. 部分ゲームが、極小（部分ゲームが、それ自身以外の部分ゲームを含まない）である場合に対し、<br>
   この部分ゲームでのナッシュ均衡点を求める。<br>
2. 先の部分ゲームでのナッシュ均衡点を前提として、<br>
   ２番目に大きな部分ゲームに対し、ナッシュ均衡点を求める。<br>
3. 以下、この操作を繰り返し、それらを合成することで、ゲーム全体での部分ゲーム完全均衡点を求める。<br>

という手順で証明することが出来る。（詳細略）<br>
この手法は、部分ゲーム完全均衡点に関する後向き帰納法と呼ばれる。<br>

---

<a id="ID_1-5-2"></a>

### ◎ 変動ゲーム [perturbed game] と完全均衡点 [perfect equilibrium point]
部分ゲームナッシュ均衡点は、完全情報ゲームのように、<br>
多くの部分ゲームを持つようなゲームの分析においては、非常に有効となる。<br>
しかしながら、展開形ゲームが、それ自身以外に部分ゲームを持たないようなゲームにおいては、<br>
ナッシュ均衡点と部分ゲーム完全均衡点は同値となる。<br>

この点から予想されるように、<br>
一般の展開形ゲームにおいて、部分ゲーム完全均衡点は、ゲームの解として不適切となる可能性が考えられる。<br>

以下、そのことの詳細を見ていく。<br>

<br>

<!------------------------------------------------------>

まず、以下の図のような３人展開形ゲーム ![image](https://user-images.githubusercontent.com/25688193/37284612-8ca5b2f8-263f-11e8-8feb-4eabb37f35a0.png) を考える。<br>
![image](https://user-images.githubusercontent.com/25688193/37294029-46cf7ed0-2658-11e8-913c-4356b9f2e302.png)<br>
この展開形ゲーム ![image](https://user-images.githubusercontent.com/25688193/37284612-8ca5b2f8-263f-11e8-8feb-4eabb37f35a0.png) における、プレイヤー i(i=1,2,3) の行動戦略を<br>
![image](https://user-images.githubusercontent.com/25688193/37294094-6bbf1796-2658-11e8-88a8-a9dfb7cf14e1.png)<br>
とする。<br>
又、プレイヤー全体の行動戦略の組を ![image](https://user-images.githubusercontent.com/25688193/37294176-9121a9a4-2658-11e8-8091-bc59bd89b013.png) と書くことにする。<br>

このゲームは、上図から分かるように、<br>
![image](https://user-images.githubusercontent.com/25688193/37284612-8ca5b2f8-263f-11e8-8feb-4eabb37f35a0.png) 自身以外の部分ゲームをもたないので（プレイヤー１，２，３を含む部分ゲームは、展開形ゲーム全体のみ）、<br>
ナッシュ均衡点と部分ゲーム完全均衡点は一致する。<br>
従って、ナッシュ均衡点を求めてみる。<br>

<br>

<!------------------------------------------------------>

まず、プレイヤー１の期待利得の計算式<br>
![image](https://user-images.githubusercontent.com/25688193/37296671-023ad7ea-265f-11e8-9750-1ce60f1f0910.png)<br>
の関係式より、期待利得の式を計算し、（途中計算略）<br>

又、プレイヤー１の最適応答対応は、<br>
![image](https://user-images.githubusercontent.com/25688193/37296716-20c56950-265f-11e8-9973-b9af6bc80d9c.png)<br>
の関係式に、計算した期待利得の式を適用すると、<br>

プレイヤー１の最適応答対応は、<br>
![image](https://user-images.githubusercontent.com/25688193/37297383-ea7575be-2660-11e8-9f19-01bb1b4e1b92.png)<br>
となる。<br>

同様にして、<br>
プレイヤー２の最適応答対応は、<br>
![image](https://user-images.githubusercontent.com/25688193/37297188-6cdc50dc-2660-11e8-80bc-76428269f299.png)<br>
プレイヤー３の最適応答対応は、<br>
![image](https://user-images.githubusercontent.com/25688193/37297411-fd857b36-2660-11e8-83cb-8271ab7daa45.png)<br>

これらのプレイヤー１，２，３の最適応答対応の式を、グラフ化すると以下の図のようになる。<br>

- プレイヤー１の最適応答対応のグラフ<br>
   ![image](https://user-images.githubusercontent.com/25688193/37322051-be2b1640-26be-11e8-91ed-793730f500c7.png)<br>
- プレイヤー２の最適応答対応のグラフ<br>
   ![image](https://user-images.githubusercontent.com/25688193/37322067-ce3da818-26be-11e8-968d-582fc6779a3f.png)<br>
- プレイヤー３の最適応答対応のグラフ<br>
   ![image](https://user-images.githubusercontent.com/25688193/37322074-df5f53bc-26be-11e8-95be-df949f643a9c.png)<br>

上図の各最適応答対応のグラフにおいて、<br>
例えば、プレイヤー１の最適応答対応のグラフで、<br>
R と表示している領域は、その領域でのプレイヤー２と３の行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37319711-96a46b86-26b3-11e8-917f-59745f3a5786.png) に対しての、<br>
プレイヤー１の最適応答が R であることを示している。<br>
又、R と L の領域の境界線上は、最適応答が R or L であることを示している。<br>

そして、２つのタイプのナッシュ均衡点をそれぞれ、<br>
●：タイプ１のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37319728-a910272e-26b3-11e8-8c81-37620a845f6a.png) <br>
○：タイプ２のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37319750-b9e2ba62-26b3-11e8-9d98-06151858f025.png) <br>
で示している。<br>

<br>

<!------------------------------------------------------------------>

この２つのタイプのナッシュ均衡点（●、○）に対して、（先のチェーンストアゲームの時と同様にして）<br>
プレイヤーの利得最大化行動、及びプレイヤーの合理性の微小な不完全さに対する安定性の観点から、<br>
これらのナッシュ均衡点の、ゲームの解としての妥当性を調べてみる。<br>

まず、タイプ２のナッシュ均衡点（○）の代表点として、<br>
純戦略による均衡点 ![image](https://user-images.githubusercontent.com/25688193/37322333-339b651e-26c0-11e8-9643-a28fd1d8a7da.png) を考える。（上図で赤丸○で記載）<br>

![image](https://user-images.githubusercontent.com/25688193/37322840-5df958cc-26c3-11e8-9367-488528f0a020.png)<br>

- このナッシュ均衡点での均衡プレイでは、上図（オレンジ線の箇所）のように、<br>
  プレイヤー１が L を選択し、プレイヤー２が R を選択し、利得ベクトル (3,2,2) が得られる。<br>
- プレイヤー２の情報分割集合は、この均衡プレイでは到達されないが、<br>
  タイプ２のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37322333-339b651e-26c0-11e8-9643-a28fd1d8a7da.png) に従い、<br>
  もし自分の手番（＝プレイヤー２の情報分割集合）が到達された場合、R を選択する。<br>
- しかしながら、このプレイヤー２の選択 R は、<br>
  タイプ２のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37322333-339b651e-26c0-11e8-9643-a28fd1d8a7da.png) に従い、プレイヤー３の行動が R であることを前提とした場合の、<br>
  利得最大化行動に反する。（プレイヤー２自身の利得が、4 → 1 になってしまうため）<br>
  この意味で、タイプ２のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37322333-339b651e-26c0-11e8-9643-a28fd1d8a7da.png) は、このゲームの解としての不適切である。<br>
- 又、タイプ２のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37322333-339b651e-26c0-11e8-9643-a28fd1d8a7da.png) のゲームプレイにおいて、<br>
  もしプレイヤー１が、過って微小な確率ではあるが、L → R を選択する可能性が発生したとする。<br>
  このとき、プレイヤー２の利得最大化行動は、R ではなく L に変化してしまう。<br>
  このように、このタイプ２のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37322333-339b651e-26c0-11e8-9643-a28fd1d8a7da.png) は、<br>
  プレイヤーの合理性の僅かな変化に対し、不安定であり、<br>
  この観点からも、タイプ２のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37322333-339b651e-26c0-11e8-9643-a28fd1d8a7da.png) は、ゲームの解としての不適切である。<br>


<br>

<!------------------------------------------------------------------>

次に、タイプ１のナッシュ均衡点（●）![image](https://user-images.githubusercontent.com/25688193/37323749-1476907e-26c9-11e8-9f19-6df318463a14.png) に対しても、<br>
プレイヤーの利得最大化行動、及びプレイヤーの合理性の微小な不完全さに対する安定性の観点から、<br>
これらのナッシュ均衡点の、ゲームの解としての妥当性を調べてみる。<br>

![image](https://user-images.githubusercontent.com/25688193/37322920-d9ff1a10-26c3-11e8-857b-aec54d4d9412.png)<br>

- タイプ１のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37323749-1476907e-26c9-11e8-9f19-6df318463a14.png) での均衡プレイでは、上図（オレンジ線の箇所）のように、<br>
  プレイヤー１は R を選択し、プレイヤー２は R を選択し、利得ベクトル (1,1,1) が得られる。 <br>
- プレイヤー３の情報分割集合は到達されないが、<br>
  タイプ１のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37323749-1476907e-26c9-11e8-9f19-6df318463a14.png) に従い、<br>
  プレイヤー３は、もし自分の手番（＝プレイヤー２の情報分割集合）が到達された場合に、<br>
  確率 ![image](https://user-images.githubusercontent.com/25688193/37324037-931c776c-26ca-11e8-9efb-e57be6162418.png) の範囲で R を選択する。（最適応答対応のグラフ中のタイプ１のナッシュ均衡点●より）<br>
  ![image](https://user-images.githubusercontent.com/25688193/37324066-b7a01954-26ca-11e8-87dc-6dbcca7ec72d.png)<br>
- プレイヤー３の情報分割集合が到達された場合において、<br>
  右側の手番（＝初期点で R → プレイヤー２の手番で L の選択後の手番）が到達された場合は、<br>
  プレイヤー３の利得最大化行動は L である。（プレイヤー３の利得が 0 → 1）<br>
  一方、左側の手番（＝初期点で L 選択後の手番）が到達された場合は、<br>
  その利得最大化行動は R である。（プレイヤー３の利得が 0 → 2）<br>
- しかしながら、**”プレイヤー３はこの２つのどちらの分岐点にゲームのプレイが到達されているか知らないので”**<br>
  （＝**２つの手番はプレイヤー３の同じ情報分割集合内**）、<br>
  プレイヤー３の確率 ![image](https://user-images.githubusercontent.com/25688193/37324037-931c776c-26ca-11e8-9efb-e57be6162418.png) の範囲で R を選択するといった、タイプ１のナッシュ均衡点に基づく均衡戦略は、自身の利得最大化行動に反しているとは言えない。<br>
  （少なくとも、タイプ２のナッシュ均衡点での利得最大化行動との背反に比べればましである。）<br>
  従って、このゲームの解としては、タイプ２のナッシュ均衡点より、タイプ１のナッシュ均衡点のほうが望ましい。<br>

<br>

<!-------------------------------------------------------------------------->

これら２つのタイプのナッシュ均衡点の議論より、<br>
プレイヤーの利得最大化行動、或いは、プレイヤーの合理性の微小な不完全さに対する安定性の観点から、<br>
部分ゲーム完全均衡点の概念を更に強くする必要性があると考えられるが、<br>

ここで問題になるのは、<br>
**情報分割集合が複数の分岐点を含むような展開形ゲームにおいて、**<br>
**均衡プレイによって到達されない [off-equilibrium play] 情報分割集合での利得最大化行動をどのように定義すればよいのか？**<br>
ということである。<br>
この問題は、先のタイプ１のナッシュ均衡点の安定性の議論で見たきたように、<br>
情報分割集合が複数の分岐点を含む場合、プレイヤー自身がどの分岐点にゲームが到達されたのか知りえないことに起因する。<br>
（情報分割集合が、先のチェーンストアゲームのときのように、単一の分岐点のみを含む場合であれば、どの分岐点に到達されたのか？という問題は発生しないので、このような問題は発生しない。）<br>

<br>

<!-------------------------------------------------------------------------->

この問題の解決策として、まず始めに思いつくのが、ベイジアンの考えに従った意思決定である（ベイジアン意思決定理論）。<br>
即ち、「プレイヤーは、情報分割集合内のどの分岐点に到達されたのか？を”主観的な予想”（＝主観確率）で意思決定し、その予想のもとで利得最大化行動を行うようにする。」といった解決法である。<br>
しかしながら、このような情報分割集合が複数の分岐点を含むゲームにおいては、<br>
そもそもこの主観確率を定めるにあたっての判断材料が存在せず、主観確率を特定化して定式化することが出来ない。<br>
従って、このベイジアン意思決定に基づくアプローチは、このゲームにおいて有効ではない。<br>
※ 尚、このベイジアンによるアプローチは、後述で定義する変動ゲームの枠組みでは、<br>
（ベイズの公式を適用する際に、分母項が常に正の値となることにより、）有効となる。（後述）<br>


<a id="ID_1-5-2-1"></a>

#### ☆ 変動ゲーム [perturbed game]
この問題の解決策の別のアプローチとして、<br>
**プレイヤーの合理性の微小な不完全さに安定性の観点に基づくアプローチ**が考えられる。<br>
このアプローチにより、プレイヤーの利得最大化行動と矛盾するようなナッシュ均衡点を除外した、<br>
**完全均衡点**の概念を導出（定義）することが出来る。（後述）<br>

展開形ゲームにおけるプレイヤーの不完全を、以下の意味で設定する。<br>
![image](https://user-images.githubusercontent.com/25688193/37334464-49c85412-26ef-11e8-9b6e-ebfe968d4cf9.png)<br>

プレイヤー i の情報分割集合 ![image](https://user-images.githubusercontent.com/25688193/37334518-75f4a8d8-26ef-11e8-99dd-d7f6f720fd51.png) に対して、<br>
このプレイヤー i の合理性が、ある微小な正の確率 ![image](https://user-images.githubusercontent.com/25688193/37334633-c8bb2074-26ef-11e8-9c42-dabe015ad15e.png) で破綻し、<br>
更に、情報分割集合 ![image](https://user-images.githubusercontent.com/25688193/37334518-75f4a8d8-26ef-11e8-99dd-d7f6f720fd51.png) における全ての枝 ![image](https://user-images.githubusercontent.com/25688193/37334683-e86f8608-26ef-11e8-9ab2-63569d15efcf.png) を、確率 ![image](https://user-images.githubusercontent.com/25688193/37334700-f828d45a-26ef-11e8-985b-60739b9852bd.png) で選択してしまう。<br>

このとき、この同時確率（合理性が破綻し、かつ、枝 c を選択してしまう確率）は、<br>
確率の乗積した ![image](https://user-images.githubusercontent.com/25688193/37334797-3b70afd0-26f0-11e8-8108-da32c803a3ed.png) となるが、<br>

これを、この展開形ゲームの情報分割集合において、枝 c を選択する確率 ![image](https://user-images.githubusercontent.com/25688193/37334850-63eed5e0-26f0-11e8-82ae-1eafaa0f7aaa.png) に組み込むと、<br>
![image](https://user-images.githubusercontent.com/25688193/37334876-725e309e-26f0-11e8-8717-72921b482f3d.png)<br>

という戦略の制限条件となる。<br>
**この制約条件により、枝 c を選択してしまう確率は常に 0 より大きくなるので、**<br>
**プレイヤーは純戦略を取ることが出来ず、戦略が一定の確率以上で変動することになる。**<br>


その意味で、戦略の選択に、このような制約が加わった展開形ゲームを、**変動ゲーム [perturbed game]** といい。<br>
![image](https://user-images.githubusercontent.com/25688193/37340843-c2e72554-2702-11e8-9bcd-defa89dc97fd.png)<br>
で表す。<br>


<a id="ID_1-5-2-2"></a>

#### ☆ 完全均衡点 [perfect equilibrium point]
そして、この変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37341027-625c9466-2703-11e8-8fae-2938d5954b26.png) に対しても、（展開形ゲーム Γ のときと同様にして）<br>
ナッシュ均衡点が定義出来るが、<br>
展開形ゲーム ![image](https://user-images.githubusercontent.com/25688193/37341064-87257a60-2703-11e8-9fe0-8cbd76b7d82b.png) の完全均衡点は、変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37341027-625c9466-2703-11e8-8fae-2938d5954b26.png) におけるナッシュ均衡点の極限点として、<br>
以下のように定義出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/37342452-f78225ac-2707-11e8-988a-29b25671e50b.png)<br>

この完全均衡点の定義より、<br>
プレイヤーの合理性が微小な不安定を持ち、その結果、展開形ゲームが変動ゲームに変化した場合においても、<br>
展開形ゲームの完全均衡点は、変動ゲームでのナッシュ均衡点に連続的に近づきながら収束し、<br>
又、変動要因である η が 0 に近づき、その結果、戦略が変動しなくなる。<br>
この意味で、**完全均衡点は、プレイヤー合理性の微小な不安定に対して安定である** と言える。<br>

---

<a id="ID_1-5-3"></a>

### ◎ ベイジアン意思決定理論の立場からの完全均衡点
先の展開形ゲームにおける完全均衡点の導出では、<br>
変動ゲームに対する合理性の微小な不完全さに対する安定性の観点から導出した。<br>
ここでは、<br>
変動ゲームの導入により、ベイジアンのアプローチ（ベイジアン意思決定理論）から、完全均衡点を再定義出来ることを示す。<br>
尚、以下の議論では、展開形ゲームが、完全記憶ゲームであることを前提とする。<br>

<br>

<!-------------------------------------------------------------->

展開形ゲーム ![image](https://user-images.githubusercontent.com/25688193/37358457-7d07f578-272e-11e8-9501-6973ecb75a05.png) の変動ゲームを ![image](https://user-images.githubusercontent.com/25688193/37358525-a5673290-272e-11e8-8691-54241636cdb7.png) とし、<br>
この変動ゲームにおける、行動戦略の組を ![image](https://user-images.githubusercontent.com/25688193/37358554-b761fa98-272e-11e8-8e36-058df219f750.png) とする。<br>

この行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37358994-cf667d7a-272f-11e8-94a2-31343c6bc15a.png) のもとで、変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37359100-0b73039c-2730-11e8-924e-43e9d792fa89.png) の手番 x が到達される確率を ![image](https://user-images.githubusercontent.com/25688193/37359180-45640470-2730-11e8-94ce-636d0a9bbf94.png) とおく。<br>
このとき、変動ゲームにおいては、手番 x の到達確率は常に正の値となる。<br>
（変動ゲームでは、行動戦略がある一定の確率で変動するため、どの手番も到達可能になるため。）<br>

又、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37358994-cf667d7a-272f-11e8-94a2-31343c6bc15a.png) のもとで、プレイヤー i の情報分割集合 u が到達される確率を<br>
![image](https://user-images.githubusercontent.com/25688193/37359440-eef77e18-2730-11e8-8baf-ad321e97ab6b.png)<br>
で定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/37360266-13461df4-2733-11e8-91b3-a839baf26a7a.png)<br>

そして、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37358994-cf667d7a-272f-11e8-94a2-31343c6bc15a.png) のもとで、<br>
プレイヤー i の情報分割集合 u が到達され、かつ、u 内の手番 x が到達される条件付き確率を考える。<br>
この条件付き確率は、ベイズの公式を用いて、<br>

![image](https://user-images.githubusercontent.com/25688193/37445960-146d9b18-285e-11e8-9eb0-1ff8125a6565.png)<br>

ここで着目すべきことは、<br>
**ベイズの公式から、情報分割集合 u 内の手番 x が到達された条件付き確率を得ることが出来るということは、**<br>
**情報分割集合 u のどの手番に到達しているかの事後確率を会得したこと**<br>
を意味している点である。<br>

そして、変動ゲームでは、<br>
行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37358994-cf667d7a-272f-11e8-94a2-31343c6bc15a.png) のもとで情報分割集合 u が到達される確率 ![image](https://user-images.githubusercontent.com/25688193/37360795-8b9cf330-2734-11e8-95af-45aa111f3b1b.png) の値が、常に正の値であるために、<br>
ベイズの公式の分母項が 0 でないため、上記ベイズの公式は常に定義可能である。<br>
このことが、ベイジアンのアプローチからの完全均衡点の再定義を可能にする。（後述）<br>

<br>

<!--------------------------------------------------------------------------->

![image](https://user-images.githubusercontent.com/25688193/37381532-f875201c-2780-11e8-8afc-aed3ba7ab85f.png)<br>

行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37358994-cf667d7a-272f-11e8-94a2-31343c6bc15a.png) のもとで、<br>
手番 x が到達された後、頂点 z が到達される条件付き確率は、<br>
![image](https://user-images.githubusercontent.com/25688193/37381459-a69e1d48-2780-11e8-8e3d-05b9ae705470.png)<br>
と書ける。<br>

変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37359100-0b73039c-2730-11e8-924e-43e9d792fa89.png) での行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37358994-cf667d7a-272f-11e8-94a2-31343c6bc15a.png) に対して、<br>
プレイヤー i の **”情報分割集合 u での” 条件付き期待利得** は、<br>
![image](https://user-images.githubusercontent.com/25688193/37381773-6504cf10-2782-11e8-9ddf-504101148ece.png)<br>
で表現できる。<br>

<br>

<!--------------------------------------------------------------------------->

ここで、これまでの議論をまとめると、<br>
変動ゲームにおいて、情報分割集合 u に、ゲームのプレイが到達された時に、<br>
プレイヤー i の、ベイジアン意思決定理論に基づく最適行動とは、<br>
他のプレイヤーの行動を前提として、<br>
ベイズの公式で与えられる、情報分割集合 u 内の手番 x が到達される事後確率 ![image](https://user-images.githubusercontent.com/25688193/37382067-fe4f07e8-2783-11e8-8543-d07c10eaad00.png) のもとでの、<br>
条件付き期待利得 ![image](https://user-images.githubusercontent.com/25688193/37382093-2c7b237c-2784-11e8-9cb1-ceb4b94d7492.png) を最大化する行動戦略である。<br>

次に、変動ゲームでのナッシュ均衡点では、<br>
ゲームのプレイが、どの情報分割集合に到達してされようとも、<br>
全てのプレイヤーは、上記の意味での最適行動を選択することを示す。<br>

![image](https://user-images.githubusercontent.com/25688193/37446090-a21ed102-285e-11e8-9368-aa9b27ce765e.png)<br>

この定理（変動ゲームにおけるナッシュ均衡点１）より、<br>
変動ゲームにおけるナッシュ均衡点では、
全てのプレイヤーは、各々の情報分割集合 u に到達したときの条件付き期待利得を最大化するように行動することが分かるが、<br>
これは、先のチェーンストアゲームでみたように、<br>
変動ゲームではない通常の展開形ゲームでのナッシュ均衡点では、必ずしも成り立たない性質である。<br>

<br>

<!---------------------------------------------------------------------------------->

先の定理（変動ゲームにおけるナッシュ均衡点１）は、<br>
プレイヤーの各情報分割集合 u 内での条件付き期待利得の最大化を行っている。<br>
これは言い換えると、<br>
この条件付き期待利得の最大化が、情報分割集合 u 以降の全ての情報分割集合での全ての局所戦略を、
同時に選択されることで得られることを表している。<br>

そこで、次の定理（変動ゲームにおけるナッシュ均衡点２）で、<br>
変動ゲームにおいて、プレイヤーのゲーム全体での期待利得の最大化は、<br>
個々の情報分割集合内での局所戦略による期待利得の最大化によって得られることを示す。<br>

![image](https://user-images.githubusercontent.com/25688193/37385690-6ef2c9a8-2798-11e8-8c5a-260105a39644.png)<br>

<br>

<!---------------------------------------------------------------------------------->

この２つの変動ゲームにおけるナッシュ均衡点の定理より、<br>
変動ゲームにおいて、以下の２つのことは同値となることが分かる。<br>

1. 情報分割集合 u 以降の全ての局所戦略を同時に選択することで得られる”大域的な意味での”利得最大化<br>
2. 情報分割集合 u 以降の各情報分割集合内での、<br>
   局所戦略の選択による”局所的な意味での”利得最大化を逐次、繰り返して得られる利得最大化<br>

これは、動的計画法における最適化原理に対応した挙動である。<br>

---

<a id="ID_1-5-4"></a>

### ◎ 逐次均衡点 [sequential equilibrium point]
先のベイジアン意思決定理論の立場からの完全均衡点の導出では、<br>
変動ゲームというゲームを導入することにより、<br>
ベイズの公式を用いて、この情報分割集合内でのプレイヤーの事後確率の設定が可能になり、<br>
結果、その予想のもとでの利得最大化、及びナッシュ均衡点、その極限としての完全均衡点を構築することが出来た。<br>

しかしながら、このような操作（変動ゲームの導入、ベイジアンに基づく予想形成）を用いて、<br>
完全均衡点を具体的に計算することは必ずしも容易ではないという問題点が存在する。<br>

この問題を解決策として、<br>
期待利得最大化と予想形成の手続きを分離することにより、<br>
完全均衡点よりも弱い均衡点の概念である、逐次均衡点の概念を定義出来る。<br>
そして、この逐次均衡点によるゲームの解の算出という方法がある。<br>

以下、この逐次均衡点の詳細を見ていく。<br>

<br>

<!---------------------------------------------------------------------------------->

そのための前段階として、<br>
まず、事後確率に基づく予想という意味合いでの **”信念”** という用語を定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/37445828-6ddd7980-285d-11e8-9130-846beed9de01.png)<br>

展開形ゲーム Γ での行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37402083-8c8b536a-27cd-11e8-8bec-4c94473a6b75.png) と信念（事後確率） ρ が与えられたとき、<br>
プレイヤー i の情報分割集合 ![image](https://user-images.githubusercontent.com/25688193/37402169-dd999f78-27cd-11e8-9e62-f56068fe288b.png) における条件付き期待利得は、<br>
![image](https://user-images.githubusercontent.com/25688193/37412150-b5260094-27e7-11e8-8e74-379fa9db4dbf.png)<br>
で表現できる。<br>

<br>

<!---------------------------------------------------------------------------------->

展開形ゲーム Γ において行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37410823-bf747e2a-27e4-11e8-95ea-dfc3df9dfec3.png) が、全ての枝に正の確率を付与する場合、<br>
すべての選択肢が選択される可能性があるため、<br>
このときの行動戦略の組 b を、**完全に確率的 [completely mixed]** であるという。<br>

又、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37410823-bf747e2a-27e4-11e8-95ea-dfc3df9dfec3.png) が、完全に確率的であるとき、<br>
ベイズの公式の分母項が常に正の値になるので、このベイズの公式を用いて、<br>
行動戦略 b のもとで、信念（事後確率） ρ が付与する情報分割集合 u 中の手番 x が選択される条件付き確率 ![image](https://user-images.githubusercontent.com/25688193/37412449-47d146ec-27e8-11e8-9c4c-da0045d3311f.png) が定義できる。<br>
このような信念 ρ を、**行動戦略 b から導かれる信念（事後確率）** という。

<br>

<!---------------------------------------------------------------------------------->

この展開形ゲームにおける信念の概念を導入することにより、<br>
展開形ゲームにおけるゲームの解としての逐次均衡点を定義できる。<br>

![image](https://user-images.githubusercontent.com/25688193/37447185-39531dd0-2864-11e8-9eab-cd443bd3c687.png)<br>

<br>

<!---------------------------------------------------------------------------------->

逐次均衡点の定義では、<br>
逐次均衡点となる戦略の変動は、プレイヤーの予想形成（＝ベイズの公式による事後確率）のみに適用され、<br>
逐次均衡点の定義の２つ目の条件である、プレイヤーの最適行動（＝利得最大化）の条件とは独立である。<br>

従って、行動戦略の組 b に対して、<br>
この b と整合的な（＝逐次均衡点の定義の２つ目の条件が成り立つ）予想 ρ が見つかれば、<br>
この行動戦略の組が逐次均衡点であることを調べるのは、比較的簡単である。<br>

このことを、先の展開形３人ゲームの例で見てみる。<br>


- タイプ２のナッシュ均衡点：![image](https://user-images.githubusercontent.com/25688193/37420901-4f5648dc-27fb-11e8-8e25-103658af8364.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37420857-2c5ab2fa-27fb-11e8-88fd-43b4f5a68923.png)<br>
    このタイプ２のナッシュ均衡点でのゲームプレイ（均衡プレイ）では、<br>
    プレイヤー２の情報分割集合は到達されないが、（上図参照）<br>
    プレイヤー２の情報分割集合は、ただ１つの手番しか含まないので、<br>
    仮に予想に反して、このプレイヤー２の情報分割集合が到達された場合においても、<br>
    プレイヤー２は、このただ１つの手番に確率１を付与するような、自明な信念 ρ を持つ。<br>
    この信念 ρ は、明らかに収束済みであるので、<br>
	このプレイヤー２の自明な信念 ρ は、タイプ２のナッシュ均衡点（行動戦略）![image](https://user-images.githubusercontent.com/25688193/37420901-4f5648dc-27fb-11e8-8e25-103658af8364.png) と整合的である。<br>
	又、プレイヤー２の均衡戦略 R は、プレイヤー３の均衡戦略 R に対して最適でない（利得：4 → 1）ので、<br>
	（逐次均衡点の条件２より）タイプ２のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37420901-4f5648dc-27fb-11e8-8e25-103658af8364.png) は、逐次均衡点でない。<br>

- タイプ１のナッシュ均衡点：![image](https://user-images.githubusercontent.com/25688193/37420935-6d6e36f4-27fb-11e8-9531-44470c4999a6.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37451039-984adab2-2873-11e8-9501-c3182ef1feef.png)<br>
	このタイプ１のナッシュ均衡点でのゲームプレイ（均衡プレイ）では、<br>
	プレイヤー３の情報分割集合のみが到達されない。（上図参照）<br>
    以下、タイプ１のナッシュ均衡点（行動戦略）と整合的な信念を求める。<br>
	- プレイヤー３の情報分割集合は、２つの手番を持つが、右側の手番（0 → R → L）を x とおく。<br>
	- タイプ１のナッシュ均衡点に収束する完全に確率的である行動戦略の列を ![image](https://user-images.githubusercontent.com/25688193/37451126-ec84810a-2873-11e8-95ba-1df97d0317de.png) とする。<br>
	- ここで、この行動戦略の列 ![image](https://user-images.githubusercontent.com/25688193/37451149-02a61caa-2874-11e8-9669-56056604bf29.png) の k 番目の要素 ![image](https://user-images.githubusercontent.com/25688193/37451167-1454c4ce-2874-11e8-94d7-995e9afb0fff.png) において、<br>
		- プレイヤー１が L を選択する確率（＝微小な不完全さによる変動確率）を ![image](https://user-images.githubusercontent.com/25688193/37451194-3499b87a-2874-11e8-820d-2c783d4ab91c.png) とする。<br>
		- プレイヤー２が L を選択する確率（＝微小な不完全さによる変動確率）を ![image](https://user-images.githubusercontent.com/25688193/37451222-46a391e4-2874-11e8-9d38-6236e39fae7e.png) とする。<br>
		- プレイヤー３が R を選択する確率（＝微小な不完全さによる変動確率）を ![image](https://user-images.githubusercontent.com/25688193/37451485-fa3d0582-2874-11e8-87b4-dc34c882eb11.png) とする。<br>
		- ここで、k → ∞ の操作で、この合理性の微小な不完全さによる変動確率 ![image](https://user-images.githubusercontent.com/25688193/37451521-2127dc6c-2875-11e8-84af-3ba56eb0f291.png) は、0 に収束するとする。<br>
	- 行動戦略 ![image](https://user-images.githubusercontent.com/25688193/37451167-1454c4ce-2874-11e8-94d7-995e9afb0fff.png) のもとで、プレイヤー３の情報分割集合 u が到達され、その内部の手番 x が到達される条件付き確率は、
	ベイズの公式より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37451593-543e1e86-2875-11e8-87c9-bea00bccbb00.png)<br>
    - この条件付き確率 ![image](https://user-images.githubusercontent.com/25688193/37452144-1102f72a-2877-11e8-9524-7d14e46410d4.png) が k → ∞ の操作で収束するならば、逐次均衡点の条件１（整合性）を満たし、<br>
    この条件付き確率 ![image](https://user-images.githubusercontent.com/25688193/37452144-1102f72a-2877-11e8-9524-7d14e46410d4.png) は、プレイヤー３の整合的な信念となる。<br>
    - 今、全ての k に対して、![image](https://user-images.githubusercontent.com/25688193/37452220-45a88d1e-2877-11e8-9a2a-ce3e60334030.png) が成り立つとする。（a は 0 以上の実数）<br>
    このとき、条件付き確率 ![image](https://user-images.githubusercontent.com/25688193/37452144-1102f72a-2877-11e8-9524-7d14e46410d4.png) は、k → ∞ の極限で、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37452243-599642da-2877-11e8-996c-6cc89d6709c9.png)<br>
    の値に収束する<br>
    - この収束値 a/(a+1) は、区間 [0,1] で連続なので確率となり、<br>
    情報分割集合でのプレイヤー３の全ての信念は、タイプ１のナッシュ均衡点と整合的である。<br>
    ![image](https://user-images.githubusercontent.com/25688193/37452679-a67b5b20-2878-11e8-9ef0-998530510ea3.png)<br>
    - プレイヤー３の信念が、手番 x に与える確率を p とすると、<br>
	R と L に対する、プレイヤー３の条件付き期待利得は、それぞれ 2×(1−p) と 1×p となるので、<br>
	2(1−p) ≤ p<br>
    即ち、2/3 ≤ p ≤ 1 ならば、<br>
	プレイヤー３の均衡戦略 L は、信念に対して最適である。<br>
    - プレイヤー１とプレイヤー２の情報分割集合が、タイプ１のナッシュ均衡点により到達可能であり、<br>
	又、このナッシュ均衡点の行動戦略は、自明な信念で、他のプレイヤーの均衡戦略に対して最適である。<br>
	プレイヤー３の結果（ナッシュ均衡点と整合な信念の存在とその最適性）と合わせて、<br>
	このタイプ１のナッシュ均衡点は、逐次均衡点であると言える。<br>


<br>

---

<a id="ID_1-5-5"></a>

### ◎ （弱）完全ベイジアン均衡点 [(weakly) perfect Bayesian equilibrium point]
> 記載中...

---


<a name="参考文献"></a>

## 参考文献

- ゲーム理論入門 (日経文庫―経済学入門シリーズ)<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%B2%E3%83%BC%E3%83%A0%E7%90%86%E8%AB%96%E5%85%A5%E9%96%80-%E6%97%A5%E7%B5%8C%E6%96%87%E5%BA%AB%E2%80%95%E7%B5%8C%E6%B8%88%E5%AD%A6%E5%85%A5%E9%96%80%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E6%AD%A6%E8%97%A4-%E6%BB%8B%E5%A4%AB/dp/4532108292?SubscriptionId=AKIAIAVGBNTUU4E5P2DA&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4532108292)


---

以下、同様の文献（はてなブログ形式）

<!-- ゲーム理論入門 (日経文庫―経済学入門シリーズ) -->
[]
