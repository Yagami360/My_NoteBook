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
        1. [完全均衡点 [perfect equilibrium point]](#ID_1-5-2)
            1. [変動ゲーム [perturbed game] と完全均衡点 [perfect equilibrium point]](#ID_1-5-2-1)
            1. [ベイジアン意思決定理論の立場からの完全均衡点](#ID_1-5-2-2)
            1. [完全均衡点の計算方法](#ID_1-5-2-3)
        1. [逐次均衡点 [sequential equilibrium point]](#ID_1-5-3)
            1. [逐次均衡点の計算](#ID_1-5-3-1)
        1. [（弱）完全ベイジアン均衡点 [(weakly) perfect Bayesian equilibrium point]](#ID_1-5-4)
        1. [完全均衡点の存在定理](#ID_1-5-5)
        1. [戦略の支配と完全均衡点](#ID_1-5-6)
        1. [戦略の安定性と強完全均衡点](#ID_1-5-7)
        1. [各種均衡点の応用例](#ID_1-5-8)
    1. [情報不完備ゲーム [game with incomplete information]](#ID_1-6)
        1. [情報不完備ゲームの定式化](#ID_1-6-1)
        1. [ベイジアンゲームと情報不完備ゲーム](#ID_1-6-2)
        1. [ベイジアン均衡点](#ID_1-6-3)
        1. [ベイジアンゲームの例](#ID_1-6-4)
        1. 相関均衡点
    1. [繰り返しゲーム [repeated game]](#ID_1-7)
        1. [繰り返し囚人のジレンマ](#ID_1-7-1)
        1. [（無限回）繰り返しゲームの定式化](#ID_1-7-2)
        1. [フォーク定理（繰り返しゲームにおけるナッシュ均衡点の基本定理）](#ID_1-7-3)
        1. [完全フォーク定理](#ID_1-7-4)
        1. [有限回繰り返しゲーム](#ID_1-7-5)
    1. [交渉ゲーム](#ID_1-8)
        1. [交渉問題の定式化](#ID_1-8-1)
        1. [ナッシュ交渉解 [Nash bargaining solution]](#ID_1-8-2)
        1. [非協力交渉モデル１（要求ゲーム）](#ID_1-8-3)
        1. [非協力交渉モデル２（提案応答ゲーム）](#ID_1-8-4)
    1. 協力ゲーム
        1. 協力ゲームの定式化
    1. [進化ゲーム [evolutionary game]](#ID_1-10)
        1. [進化的に安定な戦略 [ESS : evolutionaly stable strategy]](#ID_1-10-1)
        1. [レプリケータ・ダイナミクス [RD : replicator dynamics]](#ID_1-10-2)
            1. [レプリケータ・ダイナミクスの解の性質](#ID_1-10-2-1)
            1. [レプリケータ・ダイナミクスの例](#ID_1-10-2-2)
        1. 社会進化の動学ゲーム
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

### ◎ 完全均衡点 [perfect equilibrium point]

<a id="ID_1-5-2-1"></a>

#### ☆ 変動ゲーム [perturbed game] と完全均衡点 [perfect equilibrium point]
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
![image](https://user-images.githubusercontent.com/25688193/37504914-f2b68396-2924-11e8-9ccf-ba68b0e6b5a6.png)<br>
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


##### ☆ 変動ゲーム [perturbed game]
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


##### ☆ 完全均衡点 [perfect equilibrium point]
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

<a id="ID_1-5-2-2"></a>

#### ☆ ベイジアン意思決定理論の立場からの完全均衡点
先の展開形ゲームにおける完全均衡点の導出では、<br>
変動ゲームに対する合理性の微小な不完全さに対する安定性の観点から導出した。<br>
ここでは、<br>
**変動ゲームの導入により、ベイジアンのアプローチ（ベイジアン意思決定理論）から、**<br>
**完全均衡点における、プレイヤーの最適行動（利得最大化）を定義出来ることを示す。**<br>
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

![image](https://user-images.githubusercontent.com/25688193/37513584-d4340082-2948-11e8-9812-307595cb11e1.png)<br>

ここで着目すべきことは、<br>
**ベイズの公式から、情報分割集合 u 内の手番 x が到達された条件付き確率を得ることが出来るということは、**<br>
**情報分割集合 u のどの手番に到達しているかの（主観確率の一種である）事後確率を会得したこと**<br>
を意味している点である。<br>

そして、変動ゲームでは、<br>
行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37358994-cf667d7a-272f-11e8-94a2-31343c6bc15a.png) のもとで情報分割集合 u が到達される確率 ![image](https://user-images.githubusercontent.com/25688193/37360795-8b9cf330-2734-11e8-95af-45aa111f3b1b.png) の値が、常に正の値であるために、<br>
ベイズの公式の分母項が 0 でないため、上記ベイズの公式は常に定義可能である。<br>
このことが、ベイジアンのアプローチからの完全均衡点での最適行動（利得最大化）の設定を可能にする。（後述）<br>

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
**変動ゲームにおいて、** 情報分割集合 u に、ゲームのプレイが到達された時に、<br>
**プレイヤー i の、ベイジアン意思決定理論に基づく最適行動とは、**<br>
**他のプレイヤーの行動を前提として、**<br>
**ベイズの公式で与えられる、情報分割集合 u 内の手番 x が到達される事後確率 ![image](https://user-images.githubusercontent.com/25688193/37382067-fe4f07e8-2783-11e8-8543-d07c10eaad00.png) のもとでの、**<br>
**条件付き期待利得 ![image](https://user-images.githubusercontent.com/25688193/37382093-2c7b237c-2784-11e8-9cb1-ceb4b94d7492.png) を最大化する行動戦略である。**<br>

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

<a id="ID_1-5-2-3"></a>

#### ☆ 完全均衡点の計算
以下の３人展開形ゲームを用いて、完全均衡点の具体的な計算方法を示す。<br>

![image](https://user-images.githubusercontent.com/25688193/37506052-7f33a17c-292b-11e8-9f80-211fdfa20a80.png)<br>

展開形ゲーム Γ の変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37506082-99d04b5c-292b-11e8-916f-17ecec4e0910.png) において、<br>
プレイヤー i(=1,2,3) の行動戦略（行動 R を選択する確率）![image](https://user-images.githubusercontent.com/25688193/37506100-abdd1bcc-292b-11e8-8788-e3da32f232ea.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/37506122-c26a736c-292b-11e8-9227-e0a8005e2f37.png)<br>
の制約を受ける。<br>

ここで、展開形ゲーム Γ における、各プレイヤーの最適応答は、<br>
![image](https://user-images.githubusercontent.com/25688193/37506215-25582af0-292c-11e8-8683-65e8d136c94e.png)<br>
であったが（途中計算略）、<br>

変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37506082-99d04b5c-292b-11e8-916f-17ecec4e0910.png) においては、各プレイヤーの最適応答対応は、<br>
![image](https://user-images.githubusercontent.com/25688193/37506244-4ae057a2-292c-11e8-82c4-ba879b5cfb08.png)<br>
となる。<br>

以下、![image](https://user-images.githubusercontent.com/25688193/37506278-72094582-292c-11e8-990e-36e25b7cefac.png) の値によって、３つのケースに場合分けして考える。<br>

1. ![image](https://user-images.githubusercontent.com/25688193/37507014-f7149efe-292f-11e8-88fb-ac406581047e.png) の場合のナッシュ均衡点<br>
    - この場合、プレイヤー２の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37507054-25bb360a-2930-11e8-809b-a3eb96f5c725.png) の式より、![image](https://user-images.githubusercontent.com/25688193/37507067-39554322-2930-11e8-8e59-733a6bcff803.png) となる。<br>
    - ![image](https://user-images.githubusercontent.com/25688193/37507082-4ecf1de0-2930-11e8-9edb-80a60dd0afdc.png) が十分に 0 に近い場合（![image](https://user-images.githubusercontent.com/25688193/37507122-72709fe4-2930-11e8-9da7-acaeb5e5a6db.png)）、<br>
	![image](https://user-images.githubusercontent.com/25688193/37507181-9cbdbe08-2930-11e8-9503-4a35472cc425.png) となるが、<br>
	このとき、プレイヤー１の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37507829-c827679e-2933-11e8-8381-7f3f95591336.png) の条件の右辺は、![image](https://user-images.githubusercontent.com/25688193/37507865-edd5271a-2933-11e8-8a63-d9770d7a5120.png) となり、<br>
	今の ![image](https://user-images.githubusercontent.com/25688193/37507014-f7149efe-292f-11e8-88fb-ac406581047e.png) の条件と合わせて、![image](https://user-images.githubusercontent.com/25688193/37507946-428e155a-2934-11e8-81cd-fdf1635f4301.png) の関係が成り立つ。<br>
	従って、プレイヤー１の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37507829-c827679e-2933-11e8-8381-7f3f95591336.png) の式より、![image](https://user-images.githubusercontent.com/25688193/37507903-14493af8-2934-11e8-91dd-e05d0223e82d.png) の関係が成り立つ。<br>
    - このとき、プレイヤー３の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37508000-809b228e-2934-11e8-9105-b492439f2955.png) の条件式は、<br>
    左辺が、![image](https://user-images.githubusercontent.com/25688193/37508031-9fc5e2fc-2934-11e8-938d-03e397dc46af.png)<br>
    右辺は、![image](https://user-images.githubusercontent.com/25688193/37508055-b749e7ac-2934-11e8-8209-275adb8a71db.png)<br>
    となり、プレイヤー３の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37508000-809b228e-2934-11e8-9105-b492439f2955.png) の式は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37510181-a812dcd6-293d-11e8-9c66-d00c1421aca6.png)<br>
    と書き換えられる。<br>
    - この内、今の条件 ![image](https://user-images.githubusercontent.com/25688193/37507014-f7149efe-292f-11e8-88fb-ac406581047e.png) と矛盾しないのは、<br>
        - ![image](https://user-images.githubusercontent.com/25688193/37508209-7c86db88-2935-11e8-9e2b-d4599f0a07dd.png) の場合で、![image](https://user-images.githubusercontent.com/25688193/37508250-a403d1c0-2935-11e8-999e-895df1671c6a.png)<br>
        - ![image](https://user-images.githubusercontent.com/25688193/37508269-b55270bc-2935-11e8-9109-ff75de6d8459.png) の場合で、![image](https://user-images.githubusercontent.com/25688193/37508312-de432c64-2935-11e8-9dad-1ab57117a762.png)<br>
        の２通りである。<br>

2. ![image](https://user-images.githubusercontent.com/25688193/37506306-92125648-292c-11e8-8c98-80e41e75dbaf.png) の場合のナッシュ均衡点<br>
    - この場合、プレイヤー２の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37509061-0ce4339e-2939-11e8-9d3b-5218dd89eb9a.png) の式より、![image](https://user-images.githubusercontent.com/25688193/37509104-4713a982-2939-11e8-9428-1d3544e38567.png) となる。<br>
    - 又、プレイヤー１の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37509132-6fb1121c-2939-11e8-8df7-f5beef0333a3.png) の条件は、![image](https://user-images.githubusercontent.com/25688193/37509151-85ac8ef2-2939-11e8-9b85-1580885dd195.png) となり、<br>
	プレイヤー１の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37509132-6fb1121c-2939-11e8-8df7-f5beef0333a3.png) の式より、![image](https://user-images.githubusercontent.com/25688193/37509316-2ee04c34-293a-11e8-8d47-f125d9876d7c.png) の関係が成り立つ。<br>
    - 一方、今の条件 ![image](https://user-images.githubusercontent.com/25688193/37506306-92125648-292c-11e8-8c98-80e41e75dbaf.png) を満たすためには、<br>
    プレイヤー３の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37508000-809b228e-2934-11e8-9105-b492439f2955.png) の条件式は、![image](https://user-images.githubusercontent.com/25688193/37509369-71c8b73e-293a-11e8-86e2-1b387df9360d.png) となる。<br>
    左辺：![image](https://user-images.githubusercontent.com/25688193/37509397-8c82358c-293a-11e8-9089-0735ff9078a7.png)<br>
    右辺：![image](https://user-images.githubusercontent.com/25688193/37509416-a3bd7a9a-293a-11e8-8719-3d95df0a5b40.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37509507-f410f918-293a-11e8-9091-1205118fed6a.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37509443-b624d52a-293a-11e8-8a91-0a49206a4642.png) より、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37509548-141209dc-293b-11e8-9b15-fbd35399f8cd.png) が成り立つ。


3. ![image](https://user-images.githubusercontent.com/25688193/37510374-35bed4f4-293e-11e8-84e9-6b2fa0297d9d.png) の場合のナッシュ均衡点<br>
    - この場合、プレイヤー２の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37507054-25bb360a-2930-11e8-809b-a3eb96f5c725.png) の式より、![image](https://user-images.githubusercontent.com/25688193/37507067-39554322-2930-11e8-8e59-733a6bcff803.png) となる。<br>
    - ![image](https://user-images.githubusercontent.com/25688193/37507082-4ecf1de0-2930-11e8-9edb-80a60dd0afdc.png) が十分に 0 に近い場合（![image](https://user-images.githubusercontent.com/25688193/37507122-72709fe4-2930-11e8-9da7-acaeb5e5a6db.png)）、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37510464-7ca5f1f4-293e-11e8-8cb5-0801af3d3a47.png) となるが、<br>
    このとき、プレイヤー１の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37509132-6fb1121c-2939-11e8-8df7-f5beef0333a3.png) の条件は、![image](https://user-images.githubusercontent.com/25688193/37510545-cc228490-293e-11e8-8f83-b6628eaeb885.png) となり、<br>
	プレイヤー１の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37509132-6fb1121c-2939-11e8-8df7-f5beef0333a3.png) の式より、![image](https://user-images.githubusercontent.com/25688193/37510578-ef872490-293e-11e8-886b-6f65cdc80add.png) の関係が成り立つ。<br>
    - このとき、プレイヤー３の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37508000-809b228e-2934-11e8-9105-b492439f2955.png) の条件式は、<br>
    左辺が、![image](https://user-images.githubusercontent.com/25688193/37510631-2fe95eae-293f-11e8-9907-cc9e521d9025.png)<br>
    右辺は、![image](https://user-images.githubusercontent.com/25688193/37510673-492c8774-293f-11e8-97f9-9c5714a6785c.png)<br>
    となり、プレイヤー３の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37508000-809b228e-2934-11e8-9105-b492439f2955.png) の式は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37510708-6adf96c2-293f-11e8-89ea-fb029a3f7d29.png)<br>
    と書き換えられる。<br>
    - ![image](https://user-images.githubusercontent.com/25688193/37510793-adc81392-293f-11e8-97e0-548bcb19261d.png) が十分に 0 に近い場合（ ![image](https://user-images.githubusercontent.com/25688193/37510818-c799a042-293f-11e8-8d44-261d0dee64d6.png) ）、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37510835-d8805982-293f-11e8-9854-9fd225d1eb28.png) の関係が成り立つが、<br>
    このときの、プレイヤー３の最適応答対応 ![image](https://user-images.githubusercontent.com/25688193/37508000-809b228e-2934-11e8-9105-b492439f2955.png) は、![image](https://user-images.githubusercontent.com/25688193/37510860-f797663a-293f-11e8-9c87-ddcfa1ea014e.png) となり、<br>
    これは、今の条件 ![image](https://user-images.githubusercontent.com/25688193/37510374-35bed4f4-293e-11e8-84e9-6b2fa0297d9d.png) と矛盾する。<br>
    従って、このケース（ ![image](https://user-images.githubusercontent.com/25688193/37510374-35bed4f4-293e-11e8-84e9-6b2fa0297d9d.png) ）では、ナッシュ均衡点は存在しない。<br>

<br>

これら３つのケースでの（変動ゲームでの）ナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37511284-a4c47fc2-2941-11e8-987b-8cd952d6e271.png) をまとめると、以下のようになる。<br>

- ![image](https://user-images.githubusercontent.com/25688193/37511316-bd9866b2-2941-11e8-8a6f-efec81fe7c54.png) が成り立つ場合、<br>
    この変動ゲームでのナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/37511423-1e6e54ba-2942-11e8-9e17-54e4dd249b78.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37511550-8f8ee3d0-2942-11e8-9ee0-3e8de6135808.png) が成り立つ場合、<br>
    この変動ゲームでのナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/37511573-a681aea6-2942-11e8-8a35-634e89461509.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37511721-39b740a0-2943-11e8-9cc5-7405ac77bfc2.png) が成り立つ場合、<br>
    この変動ゲームでのナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/37511610-d54d38cc-2942-11e8-84e5-ef633912f8a8.png)<br>


の極限操作にて、これらのナッシュ均衡点は、<br>

- ![image](https://user-images.githubusercontent.com/25688193/37511744-4f3742ae-2943-11e8-81fa-bed96a6c9cae.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37511778-69d575fe-2943-11e8-91e5-aa669da120ef.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37511800-7b622d26-2943-11e8-99a2-559cad98a285.png)<br>

に収束する。<br>

変動ゲームにおいて、ナッシュ均衡点に収束するので、<br>
![image](https://user-images.githubusercontent.com/25688193/37512004-2c988658-2944-11e8-93a0-2f924ec8eff0.png)<br>
は、元の展開形ゲームにおける完全均衡点である。<br>

<br>

---

<a id="ID_1-5-3"></a>

### ◎ 逐次均衡点 [sequential equilibrium point]
先のプレイヤーの合理性の微小な不完全さに対する安定性の観点からの完全均衡点の定義、<br>
及び、ベイジアン意思決定理論の立場からの完全均衡点における最適行動の設定では、<br>
変動ゲームというゲームを導入することにより、<br>
ベイズの公式を用いて、この情報分割集合内でのプレイヤーの事後確率の設定が可能になり、<br>
結果、その予想のもとでの利得最大化、及びナッシュ均衡点、その極限としての完全均衡点を構築することが出来た。<br>

しかしながら、このような操作（変動ゲームの導入、ベイジアンに基づく予想形成）を用いて、<br>
完全均衡点を具体的に計算することは必ずしも容易ではないという問題点が存在する。<br>

この問題を解決策として、<br>
**期待利得最大化と予想形成の手続きを分離することにより、**<br>
**完全均衡点よりも弱い均衡点の概念である、逐次均衡点の概念を定義出来る。**<br>
そして、この逐次均衡点をゲームの解として算出する方法がある。<br>

以下、この逐次均衡点の詳細を見ていく。<br>

<br>

<!---------------------------------------------------------------------------------->

そのための前段階として、<br>
まず、**主観確率の一種である事後確率に基づく予想という意味合いでの ”信念”** という用語を定義する。<br>

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

![image](https://user-images.githubusercontent.com/25688193/37536650-8d57a88a-298e-11e8-9750-7f08a3dfc21c.png)<br>

<br>

<!---------------------------------------------------------------------------------->

逐次均衡点の定義では、<br>
逐次均衡点となる戦略の変動は、プレイヤーの予想形成（＝逐次均衡点の定義の１つ目の条件）のみに適用され、<br>
逐次均衡点の定義の２つ目の条件である、プレイヤーの最適行動（＝利得最大化）の条件とは独立である。<br>

従って、行動戦略の組 b に対して、<br>
この b と整合的な（＝逐次均衡点の定義の１つ目の条件が成り立つ）予想 ρ が見つかれば、<br>
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
	しかしながら、プレイヤー２の均衡戦略 R は、プレイヤー３の均衡戦略 R に対して最適でない（利得：4 → 1）ので、<br>
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
    - 次に、このナッシュ均衡点の最適性（逐次均衡点の条件２）を調べる。<br>
    プレイヤー３の信念が、手番 x に与える確率を p とすると、<br>
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

<a id="ID_1-5-3-1"></a>

#### ☆ 逐次均衡点の計算
以下の３人展開形ゲームを用いて、逐次均衡点の具体的な計算方法を示す。<br>

![image](https://user-images.githubusercontent.com/25688193/37516227-cb49fd2a-2950-11e8-899d-fefbc1861a6a.png)<br>

この展開形ゲーム Γ において、<br>
プレイヤー３の情報分割集合は、右側と左側の２つの手番を持つ。<br>
（＝どちらの手番にゲームのプレイが到達されているのか知りえない。）<br>

ゲームのプレイにより、この情報分割集合が到達された際に、<br>
どの手番が到達されているのか？に関するプレイヤーの信念（事後確率）を、<br>

![image](https://user-images.githubusercontent.com/25688193/37516476-9568f002-2951-11e8-9fbd-1f91f985740d.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37516558-e0783648-2951-11e8-90e6-becaece725e8.png) : プレイヤー３の情報分割集合に内、右側の手番に付与される確率（＝右側の手番が到達されているとする主観確率）<br>
- ![image](https://user-images.githubusercontent.com/25688193/37516592-f870f1f4-2951-11e8-9187-dec62534f187.png) : プレイヤー３の情報分割集合に内、左側の手番に付与される確率（＝左側の手番が到達されているとする主観確率）<br>

この信念 μ のもとでの、プレイヤー３の最適行動（利得最大化行動）は、<br>
![image](https://user-images.githubusercontent.com/25688193/37516796-b4695a22-2952-11e8-9f57-5d3ce8451236.png)<br>
となる。（途中計算略）<br>

以下、この確率 ![image](https://user-images.githubusercontent.com/25688193/37519083-3237bc5c-295b-11e8-8580-4343090b80a4.png) の範囲で場合分けして考える。<br>

- ![image](https://user-images.githubusercontent.com/25688193/37519119-54559c1e-295b-11e8-85a2-3986696c400c.png) の場合<br>
    - このときの、プレイヤー３の最適応答は、上式より、![image](https://user-images.githubusercontent.com/25688193/37519294-e9ecf402-295b-11e8-800b-a45e23c76396.png) (R)<br>
    - すると、これに対するプレイヤー２の最適応答は、![image](https://user-images.githubusercontent.com/25688193/37519345-1791633e-295c-11e8-83d0-2e1c2dbdcd2b.png) (L)<br>
    - 更に、これらに対する、プレイヤー１の最適応答は、![image](https://user-images.githubusercontent.com/25688193/37519452-7f1f286a-295c-11e8-9fbf-1ec700a74292.png) (R)<br>
    - 結果的に、最適応答の行動戦略として、![image](https://user-images.githubusercontent.com/25688193/37519558-de33d38c-295c-11e8-9fc8-57ef33b6f72c.png) : (R,L,R) が得られる。<br>
    - しかしながら、このときの、プレイヤー３の信念 ![image](https://user-images.githubusercontent.com/25688193/37519611-163d81ec-295d-11e8-82ee-78e3390a8613.png) は、<br>
	![image](https://user-images.githubusercontent.com/25688193/37519119-54559c1e-295b-11e8-85a2-3986696c400c.png) であるため、収束しておらず、この最適応答の行動戦略 b と整合的でない。<br>
    - 従って、プレイヤー３の信念 μ に対する、逐次均衡点は存在しない。<br>

- ![image](https://user-images.githubusercontent.com/25688193/37519653-50efb792-295d-11e8-9205-0b12b9a7d8e4.png) の場合<br>
    - このときの、プレイヤー３の最適応答は、（プレイヤー３の最適応答の式より）![image](https://user-images.githubusercontent.com/25688193/37519875-2ce8af60-295e-11e8-8ccf-0d3f071b6315.png)<br>
    - すると、これに対するプレイヤー２の最適応答は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37520771-b401166a-2961-11e8-8a20-aabe5354ff1f.png)<br>
    （途中計算略）<br>
    - 更に、これらに対するプレイヤー１の最適応答を、上式の範囲で場合分けして考える。<br>    
        - ![image](https://user-images.githubusercontent.com/25688193/37522109-4e5d64da-2966-11e8-89b1-b6af01124d48.png) の場合<br>
            上式より、プレイヤー２の最適応答は、![image](https://user-images.githubusercontent.com/25688193/37521997-f48c4138-2965-11e8-9c13-9621084e77a3.png) となる。<br>
            このときの、プレイヤー１の期待利得は、R を選択すると 1、L を選択すると ![image](https://user-images.githubusercontent.com/25688193/37522136-61e88570-2966-11e8-9879-a97ca4fb9918.png) となるので、<br>
            プレイヤー１の最適行動は、![image](https://user-images.githubusercontent.com/25688193/37522228-ad983286-2966-11e8-8d5b-96443aa9fa9b.png) となる。<br>
            結果的に、最適行動の行動戦略として、![image](https://user-images.githubusercontent.com/25688193/37523581-b83acaba-296a-11e8-8b47-e059b2b6c24a.png) が得られる。<br>
            この行動戦略が、信念 μ と整合的であるか調べるために、<br>
            プレイヤー１と２の行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37522460-52573bfa-2967-11e8-9adb-b5884cd3576a.png)、プレイヤー３の信念 ![image](https://user-images.githubusercontent.com/25688193/37522496-6eeb0fda-2967-11e8-81c3-8a1579f71acb.png) をベイズの公式に適用すると、<br>
            ![image](https://user-images.githubusercontent.com/25688193/37522533-92037f16-2967-11e8-95e9-800eeb213727.png)<br>
            となるが、今、![image](https://user-images.githubusercontent.com/25688193/37522587-b86d60e0-2967-11e8-8e87-9c4243909c1a.png) なので、これをベイズの公式に代入すると、<br>
            ![image](https://user-images.githubusercontent.com/25688193/37522704-18061de4-2968-11e8-9ce9-abb71ccb947a.png) という関係式が導かれる。<br>
            この条件 ![image](https://user-images.githubusercontent.com/25688193/37522748-3d801b6a-2968-11e8-873a-ca80ab6a449e.png) を満たし、かつ、![image](https://user-images.githubusercontent.com/25688193/37522772-568aa99a-2968-11e8-8bd4-d11e64b05365.png) に収束する行動戦略の列が存在するので、<br>
            プレイヤー３の信念 ![image](https://user-images.githubusercontent.com/25688193/37522825-79a3cd94-2968-11e8-938b-b92143bfa202.png) は、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37523581-b83acaba-296a-11e8-8b47-e059b2b6c24a.png) と整合的である。<br>
            従って、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37523581-b83acaba-296a-11e8-8b47-e059b2b6c24a.png) は、信念 ![image](https://user-images.githubusercontent.com/25688193/37523102-4804235a-2969-11e8-8b2b-b59444acc5b1.png) を持つ逐次均衡点である。<br>

        - ![image](https://user-images.githubusercontent.com/25688193/37523696-12bc440a-296b-11e8-8ed6-7f8e0a40ff19.png) の場合<br>
            このときのプレイヤー２の最適応答は、![image](https://user-images.githubusercontent.com/25688193/37523755-3a9bee1c-296b-11e8-8419-bcf6b77b25c2.png) となる。<br>
            このときの、プレイヤー１の期待利得の大小関係（計算略）より、プレイヤー１の最適行動は、![image](https://user-images.githubusercontent.com/25688193/37523846-80a76d00-296b-11e8-8794-3b9a4e5331ef.png) となる。<br>
            結果的に、最適行動の行動戦略として、![image](https://user-images.githubusercontent.com/25688193/37523980-e073fbfe-296b-11e8-805f-ed851b9e2a24.png) が得られる。<br>
            先の議論と同様にして、<br>
            ベイズの公式から導かれる条件 ![image](https://user-images.githubusercontent.com/25688193/37522748-3d801b6a-2968-11e8-873a-ca80ab6a449e.png) を満たし、<br>
            かつ、![image](https://user-images.githubusercontent.com/25688193/37522772-568aa99a-2968-11e8-8bd4-d11e64b05365.png) に収束する行動戦略の列が存在するので、<br>
            プレイヤー３の信念 ![image](https://user-images.githubusercontent.com/25688193/37522825-79a3cd94-2968-11e8-938b-b92143bfa202.png) は、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37523980-e073fbfe-296b-11e8-805f-ed851b9e2a24.png) と整合的である。<br>
            従って、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37523980-e073fbfe-296b-11e8-805f-ed851b9e2a24.png) は、信念 ![image](https://user-images.githubusercontent.com/25688193/37523102-4804235a-2969-11e8-8b2b-b59444acc5b1.png) を持つ逐次均衡点である。<br>

        - ![image](https://user-images.githubusercontent.com/25688193/37523721-21c87644-296b-11e8-8b17-66057f372d52.png) の場合<br>
            このときのプレイヤー２の最適応答は、![image](https://user-images.githubusercontent.com/25688193/37524122-373d6934-296c-11e8-90d5-e96153ee659e.png) となる。<br>
            これらに対するプレイヤー１の最適行動は、![image](https://user-images.githubusercontent.com/25688193/37532087-5ec0c324-2981-11e8-8743-d3cb5723b558.png) となる。<br>
            結果的に、最適行動の行動戦略として、![image](https://user-images.githubusercontent.com/25688193/37532114-7493d042-2981-11e8-92eb-bdc7902a564e.png) が得られる。<br>
            この行動戦略は、ベイズの公式から導かれる条件 ![image](https://user-images.githubusercontent.com/25688193/37522748-3d801b6a-2968-11e8-873a-ca80ab6a449e.png) を満たさないので、<br>
            プレイヤー３の信念 ![image](https://user-images.githubusercontent.com/25688193/37522825-79a3cd94-2968-11e8-938b-b92143bfa202.png) は、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37532114-7493d042-2981-11e8-92eb-bdc7902a564e.png) と整合的ではない。<br>
            従って、この行動戦略の組 b は、逐次均衡点ではない。<br>

- ![image](https://user-images.githubusercontent.com/25688193/37519671-60fbddb4-295d-11e8-827b-b859bd463b65.png) の場合<br>
    - このときのプレイヤー３の最適行動は、![image](https://user-images.githubusercontent.com/25688193/37532771-50306182-2983-11e8-980b-ba1af9b0ca00.png) (L) となる。<br>
    - すると、これに対するプレイヤー２の最適応答は、![image](https://user-images.githubusercontent.com/25688193/37532806-6a5a59d2-2983-11e8-9916-8a318ac00833.png)(R)<br>
    - 結果的に、最適応答の行動戦略として、![image](https://user-images.githubusercontent.com/25688193/37532834-8916d710-2983-11e8-97ea-6a12810f231c.png) : (R,L,L) が得られる。<br>
    - この行動戦略が、信念 μ と整合的であるか調べるために、<br>
        プレイヤー１と２の行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37522460-52573bfa-2967-11e8-9adb-b5884cd3576a.png)、プレイヤー３の信念 ![image](https://user-images.githubusercontent.com/25688193/37522496-6eeb0fda-2967-11e8-81c3-8a1579f71acb.png) をベイズの公式に適用すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/37522533-92037f16-2967-11e8-95e9-800eeb213727.png)<br>
        となるが、今、![image](https://user-images.githubusercontent.com/25688193/37519671-60fbddb4-295d-11e8-827b-b859bd463b65.png) なので、これをベイズの公式に代入すると、<br>
        ![image](https://user-images.githubusercontent.com/25688193/37532996-02a4925c-2984-11e8-90a7-4225f8bc20fa.png) という関係式が導かれる。<br>
        このベイズの公式から導かれる条件を満たし、かつ、![image](https://user-images.githubusercontent.com/25688193/37533032-1c77909e-2984-11e8-88e8-7dda82d70d6b.png) に収束する行動戦略の列が存在するので、<br>
        プレイヤー３の信念 ![image](https://user-images.githubusercontent.com/25688193/37522496-6eeb0fda-2967-11e8-81c3-8a1579f71acb.png) は、行動戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37532834-8916d710-2983-11e8-97ea-6a12810f231c.png) と整合的である。<br>
        従って、この行動戦略の組 b は、逐次均衡点である。<br>

<br>

---

<a id="ID_1-5-4"></a>

### ◎ （弱）完全ベイジアン均衡点 [(weakly) perfect Bayesian equilibrium point]
逐次均衡点の定義において、<br>
信念は、行動戦略（ナッシュ均衡点）と整合的でなくてはならなかった。<br>

これに対し、完全ベイジアン均衡点は、<br>
（均衡プレイ外の情報分割集合での信念は、）**どのような信念も整合的であるとして、**<br>
**逐次均衡点における整合性に関する条件を取り払い、**<br>
逐次均衡点の概念を弱めたものとなる。<br>

![image](https://user-images.githubusercontent.com/25688193/37552419-325458ba-29f8-11e8-8613-0933208b961b.png)<br>

---

<a id="ID_1-5-5"></a>

### ◎ 完全均衡点の存在定理
ここでは、まず、戦略形ゲームにおける完全均衡点を定義し、戦略形ゲームにおける完全均衡点の存在定理を示す。<br>
その後、展開形ゲームにおける完全均衡点の存在定理を示す。<br>


今、![image](https://user-images.githubusercontent.com/25688193/37553306-b24cb93a-2a08-11e8-9799-61dcb87322d3.png) を戦略形 n 人ゲームとする。<br>
このとき、展開形ゲームのときと同様にして、<br>
戦略形ゲーム G の変動ゲーム<br>

![image](https://user-images.githubusercontent.com/25688193/37553308-c4af801c-2a08-11e8-8640-efeb202264a8.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37553311-d4e1af6e-2a08-11e8-8441-8a8f3c9bfd1d.png)<br>
    プレイヤー i の全ての純戦略 ![image](https://user-images.githubusercontent.com/25688193/37565645-5342a81c-2af0-11e8-9eb0-734b03e2b2b1.png) に対して、正の確率 ![image](https://user-images.githubusercontent.com/25688193/37565648-640cbe76-2af0-11e8-873c-3b6f3dd82772.png) を付与する関数。<br>
    プレイヤーの合理性の微小な不完全さに起因する。<br>
    ![image](https://user-images.githubusercontent.com/25688193/37553321-2e0ca9e0-2a09-11e8-907d-2075e77677ee.png)<br>

を定義することが出来る。<br>

ここで、混合戦略がある微小な一定の確率以上で変動するように、<br>
この変動ゲームにおける全ての混合戦略に対して、<br>
![image](https://user-images.githubusercontent.com/25688193/37553825-6de5ab12-2a12-11e8-9803-c3c3f9d838f8.png)<br>
という条件を課す。<br>

![image](https://user-images.githubusercontent.com/25688193/37556712-1d13f5f6-2a3d-11e8-93d5-18ac1a51c1aa.png)<br>

![image](https://user-images.githubusercontent.com/25688193/37563089-4db20782-2abc-11e8-85a9-f1561af8aadf.png)<br>

![image](https://user-images.githubusercontent.com/25688193/37563108-fb208e8e-2abc-11e8-8c81-758a11cdea3b.png)<br>
展開形ゲームでのナッシュ均衡点では、<br>
プレイヤーの利得最大化行動が、行動戦略の全体に対して行われるのに対して、<br>
**展開形ゲームでの局所均衡点は、**<br>
**プレイヤーの利得最大化行動が、各々の情報分割集合内に対して行われるのが特徴的である。**<br>

それ故、「展開形ゲームのナッシュ均衡点 ⇒ 展開形ゲームの局所均衡点」の関係は成り立つが、<br>
この逆の、「展開形ゲームの局所均衡点 ⇒ 展開形ゲームのナッシュ均衡点」の関係は成り立たない。<br>

<br>

<!------------------------------------------------------------------------>

しかしながら、変動ゲームにおいては、<br>
以下の定理が示すように、ナッシュ均衡点と、局所均衡点は同値となる。<br>
![image](https://user-images.githubusercontent.com/25688193/37563228-655be67a-2abf-11e8-8a13-1b05a7ce504a.png)<br>

<br>

<!------------------------------------------------------------------------>

展開形ゲーム Γ における完全均衡点の存在定理の前段階として、<br>
まず、展開形ゲーム Γ から、以下のような標準形ゲームを構成する。<br>

今、展開形ゲーム Γ において、<br>
偶然手番を除く、全ての情報分割集合に対して、![image](https://user-images.githubusercontent.com/25688193/37563856-24c3fe00-2acd-11e8-8872-e3299eee70b4.png) という番号付けを行う。<br>

そして、この各情報分割集合 ![image](https://user-images.githubusercontent.com/25688193/37563866-52de73e2-2acd-11e8-8c45-9eb7d076c6cb.png) に対して、<br>
この情報分割集合内での局所戦略を選択する１人のエージェント j なるものを考える。<br>
このエージェント j の純戦略の集合は、これに対応する情報分割集合 ![image](https://user-images.githubusercontent.com/25688193/37563872-899506e4-2acd-11e8-9345-840584ec0409.png) での選択肢の全体 ![image](https://user-images.githubusercontent.com/25688193/37563882-b8163754-2acd-11e8-99fb-038f39d26ca4.png) となる。<br>
![image](https://user-images.githubusercontent.com/25688193/37564002-b2e8c172-2ad0-11e8-873e-eeca50294d31.png)<br>
全てのエージェントの純戦略の組 a=(a_1,a_2,…,a_n )  に対して、<br>
エージェント j の利得を、<br>
![image](https://user-images.githubusercontent.com/25688193/37564019-f9b6688e-2ad0-11e8-973a-d4a9e991fd5c.png)<br>

- i : 情報分割集合 ![image](https://user-images.githubusercontent.com/25688193/37564032-29c5aaee-2ad1-11e8-8648-5cd03d6c1d5b.png) をもつ、元の展開形ゲーム Γ のプレイヤー i<br>
- ![image](https://user-images.githubusercontent.com/25688193/37564042-47d7a4d8-2ad1-11e8-9189-8280845f94d3.png) : 元の展開形ゲーム Γ における純戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37564070-b0fc45fe-2ad1-11e8-91a0-413eeb14f70b.png) に対するプレイヤー i の期待利得<br>

このようにして、展開形ゲームから構成される戦略形ゲーム<br>
![image](https://user-images.githubusercontent.com/25688193/37564126-c09c82ac-2ad2-11e8-9301-97fd9f1068de.png)<br>
を、**元の展開形ゲームのエージェント標準形 [agent normal form]** という。<br>

![image](https://user-images.githubusercontent.com/25688193/37565599-7328c798-2aef-11e8-8bbe-cbd4457edb1c.png)<br>

<br>

---

<a id="ID_1-5-6"></a>

### ◎ 戦略の支配と完全均衡点
これまでの議論では、<br>
展開形ゲームにおけるナッシュ均衡点の、ゲームの解としての不十分さを<br>

1. 情報分割集合におけるプレイヤーの最適化行動（利得最大化行動）<br>
2. プレイヤーの合理性の微小な不完全さに対する安定性<br>

の観点から見てきた。<br>
ここでは、更に、３つ目の観点である<br>

3. 戦略の支配<br>

の観点から、ナッシュ均衡点の問題点を見ていく。<br>

<br>

<!---------------------------------------------------------------------->

展開形ゲームでの（行動戦略による）完全均衡点と、戦略形ゲームでの（混合戦略による）完全均衡点は、<br>
１対１に対応しているので、以下、戦略形ゲーム上で考えていく。<br>

![image](https://user-images.githubusercontent.com/25688193/37568121-246ab466-2b14-11e8-95bd-386433a3ae06.png)<br>

> 記載中...

![image](https://user-images.githubusercontent.com/25688193/37588710-671da4ac-2ba6-11e8-826e-afb09c939593.png)<br>

<br>

---

<a id="ID_1-5-7"></a>

### ◎ 戦略の安定性と強完全均衡点
完全均衡点の定義より、<br>
完全均衡点であるためには、少なくとも１つの収束する連続な変動ゲームの列 ![image](https://user-images.githubusercontent.com/25688193/37833074-badeb8fc-2eed-11e8-8d54-5430dcd7aa5e.png)<br>
存在する必要がある。<br>
これは、少なくとも１つ必要がなだけであるので、<br>
逆に言えば、変動ゲームの列のとり方（η のとり方）によっては、連続に変化しない列も存在し得る。<br>

このことを先の３人展開形ゲームで見ていく。<br>
![image](https://user-images.githubusercontent.com/25688193/37642601-1b6231f2-2c61-11e8-86d8-90ce042f01eb.png)<br>

この展開形ゲーム Γ の変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37643672-ab5e8244-2c64-11e8-97e5-6fa9e287d106.png) において、<br>
プレイヤー i(=1,2,3) の行動戦略（行動 R を選択する確率）![image](https://user-images.githubusercontent.com/25688193/37643748-e1551282-2c64-11e8-93b9-c49a0187e7a9.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/37643782-fd9ad274-2c64-11e8-87e3-58affe469709.png)<br>
の制約を受けるとし、<br>

この展開形ゲームにおける変動ゲームのナッシュ均衡点の計算の結果をまとめると、<br>
プレイヤー１，２の合理性の微小な不完全さ ![image](https://user-images.githubusercontent.com/25688193/37643817-1fd6656a-2c65-11e8-9377-f584649864f8.png) の範囲に応じて、以下のようになった。（先の計算結果参照）<br>

- 領域 A : ![image](https://user-images.githubusercontent.com/25688193/37644056-e1e12ce4-2c65-11e8-8075-eb3c133478f4.png)<br>
    この変動ゲームでのナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/37644215-615c170e-2c66-11e8-8c59-d40d89d50dbe.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37644289-aa1c8cc6-2c66-11e8-8dbe-678ab972b269.png) の極限操作にて、このナッシュ均衡点は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/37644315-c17a2ba8-2c66-11e8-9ddb-30cab5451cd7.png) に収束する。<br>
    変動ゲームにおいて、ナッシュ均衡点に収束するので、<br>
    この均衡点は、元の展開形ゲームにおける完全均衡点である。<br>

- 領域 C : ![image](https://user-images.githubusercontent.com/25688193/37644102-0b825afa-2c66-11e8-87c5-d3c2949b0369.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37644289-aa1c8cc6-2c66-11e8-8dbe-678ab972b269.png) の極限操作にて、このナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/37644464-4284e760-2c67-11e8-8dca-61929a087dc3.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37644371-f08e6918-2c66-11e8-828a-f806689b71c3.png) に収束する。<br>
    変動ゲームにおいて、ナッシュ均衡点に収束するので、<br>
    この均衡点は、元の展開形ゲームにおける完全均衡点である。<br>

- 領域 B : ![image](https://user-images.githubusercontent.com/25688193/37644136-2b34e3fe-2c66-11e8-8f77-669988085498.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37644289-aa1c8cc6-2c66-11e8-8dbe-678ab972b269.png) の極限操作にて、このナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/37644495-643ce7a4-2c67-11e8-9e58-2ca8d9fa53be.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/37644546-832510c4-2c67-11e8-85f2-d153a90e9e6f.png) に収束する。<br>
    変動ゲームにおいて、ナッシュ均衡点に収束するので、<br>
    この均衡点は、元の展開形ゲームにおける完全均衡点である。<br>

<br>

<!------------------------------------------------------------------------>

この変動ゲームにおけるプレイヤー１，２の合理性の微小な不完全さ ![image](https://user-images.githubusercontent.com/25688193/37643817-1fd6656a-2c65-11e8-9377-f584649864f8.png) の範囲に応じた<br>
完全均衡点への収束（ ![image](https://user-images.githubusercontent.com/25688193/37644289-aa1c8cc6-2c66-11e8-8dbe-678ab972b269.png) の極限操作）の様子を図示すると、以下の図ようになる。<br>

![image](https://user-images.githubusercontent.com/25688193/37642450-782ccbe6-2c60-11e8-9450-57af6a980783.png)<br>

- 領域 A : ![image](https://user-images.githubusercontent.com/25688193/37644056-e1e12ce4-2c65-11e8-8075-eb3c133478f4.png)<br>
    上図の青で塗りつぶた領域が対応している。<br>
    上図の青矢印で示したように、<br>
    この領域での変動ゲームのナッシュ均衡点は、完全均衡点 ![image](https://user-images.githubusercontent.com/25688193/37698217-edc523de-2d24-11e8-9303-207d7c7f37dd.png) に収束する。<br>
    そして、その完全均衡点の安定性は、この領域 A 内で保証される。<br>

- 領域 B : ![image](https://user-images.githubusercontent.com/25688193/37644136-2b34e3fe-2c66-11e8-8f77-669988085498.png)<br>
    上図の緑で塗りつぶた領域が対応している。<br>
    上図の緑矢印で示したように、<br>
    この領域での変動ゲームのナッシュ均衡点は、完全均衡点 ![image](https://user-images.githubusercontent.com/25688193/37698268-3f066906-2d25-11e8-8ce3-4eda102c361f.png) に収束する。<br>
    そして、その完全均衡点の安定性は、この領域 B 内で保証される。<br>

- 領域 C : ![image](https://user-images.githubusercontent.com/25688193/37644102-0b825afa-2c66-11e8-87c5-d3c2949b0369.png)<br>
    上図の赤線領域が対応している。<br>
    この曲線 C 上の変動ゲームでは、<br>
    ナッシュ均衡点を適当に選択すれば、それらは全て完全均衡点 ![image](https://user-images.githubusercontent.com/25688193/37698286-5fdca898-2d25-11e8-95e1-eb971a50b634.png) に収束する。<br>
    そして、この完全均衡点の安定性は、曲線 C 上での変動ゲームに対してのみ保証される。<br>
    これは、プレイヤー１と２の合理性が互いに強い相関がある（![image](https://user-images.githubusercontent.com/25688193/37698303-7b338c4c-2d25-11e8-89c6-01d75366d23f.png) に対する = の関係式）ことを示しており、<br>
    このような状況は、限定的なものとなってしまう。<br>

**このように、完全均衡点の安定性は、変動ゲームの列のとり方（ η のとり方）に依存している。**

<br>

<!------------------------------------------------------------------------>

完全均衡点の安定性に関する、<br>
このような変動ゲームの列の選択への依存性を解決するために、**強完全均衡点**を導入する。<br>

![image](https://user-images.githubusercontent.com/25688193/37701516-a616306a-2d32-11e8-9cf5-19e38696c475.png)<br>

- cf : 完全均衡点
    > ![image](https://user-images.githubusercontent.com/25688193/37701301-bff511be-2d31-11e8-8f5d-db26079247b8.png)<br>

<br>

完全均衡点の定義では、<br>
変動ゲームの列 ![image](https://user-images.githubusercontent.com/25688193/37700714-de73fe04-2d2f-11e8-8a5f-f51294ad94d9.png) が存在することを **必要として**、<br>
それらが２つの収束性（連続性）<br>

1. 展開形ゲーム Γ を構成する全ての枝 c に対して、![image](https://user-images.githubusercontent.com/25688193/37700801-3a606b58-2d30-11e8-9d6d-70e4df33ff3e.png)<br>
    （＝変動要因である η が 0 に近づき、その結果、戦略が変動しなくなる。）<br>

2. 変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37700867-6502e6d8-2d30-11e8-98f6-fc59bc0b7e20.png) のナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/37700904-8008c38a-2d30-11e8-9314-669e1e274602.png) が存在して、![image](https://user-images.githubusercontent.com/25688193/37701004-cac0f2a8-2d30-11e8-8725-834d7f1aeda0.png)<br>
    （＝変動ゲームでのナッシュ均衡点が、元の展開形ゲームでの均衡点に収束する。）<br>

に関する条件を満たすような均衡点であった。<br>

一方、強完全均衡点の定義では、<br>
１つ目の収束性（連続性）に関する条件を満たすような<br>
変動ゲームの列 ![image](https://user-images.githubusercontent.com/25688193/37700714-de73fe04-2d2f-11e8-8a5f-f51294ad94d9.png) が存在することを **前提として**、<br>
それらが、２つ目の収束性（連続性）に関する条件を満たすような均衡点である。<br>

従って、<br>
完全均衡点では、展開形ゲーム Γ からどのような変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/37701623-fe2358dc-2d32-11e8-8c05-5835202856b7.png) を構成しようとも、<br>
その変動ゲームにおいて、連続的に変化出来る（＝収束する）均衡点である。<br>
**これにより、強完全均衡点は、完全均衡点よりも強い安定性を持つ。**<br>

<br>

<!------------------------------------------------------------------------>

**しかしながら、先の展開形３人ゲームのように、強完全均衡点は必ずしも存在するとは限らない。**<br>
以下、このことの簡単な条件を見ていく。<br>

![image](https://user-images.githubusercontent.com/25688193/37710289-885c0630-2d50-11e8-80ac-f79c20428c3b.png)<br>

![image](https://user-images.githubusercontent.com/25688193/37710918-83dffc86-2d52-11e8-8f35-e15c964c5957.png)<br>


---

<a id="ID_1-5-8"></a>

### ◎ 各種均衡点の応用列

#### ☆ 湖の汚染（組織参加のジレンマ）

- 工場 1, 2, ... , n が、以下のような生産活動を行っている。<br>
    - 湖の水を使って紙パルプを生産し、その後、排水を湖に流す。<br>
- このとき、工場の経営者が取りうる選択肢は、以下の２つの何れかである。<br>
    - C : 工場の排水に浄化装置を付ける。<br>
        - このとき、浄化装置を設置するのに、費用 K がかかる。<br>
    - D : 工場の排水に浄化装置を付けない。<br>
        - このとき、紙パルプを生産にあたって、使用する湖の水の浄化コストに kL かかる。<br>
        （ k は、浄化装置を設置していない工場数で、![image](https://user-images.githubusercontent.com/25688193/37724374-edfe2b94-2d73-11e8-97e1-fcd252a97131.png) ）
- 工場の経営者は、費用が最小化するように選択を行う。<br>

工場 i(=1,2,...,n) の戦略を ![image](https://user-images.githubusercontent.com/25688193/37724607-851c5366-2d74-11e8-9e21-e83c2031266d.png) (C or D) とすると、<br>
その費用関数は、<br>
![image](https://user-images.githubusercontent.com/25688193/37724645-9566317e-2d74-11e8-966d-dab7a27d4741.png)<br>

今、![image](https://user-images.githubusercontent.com/25688193/37752912-a90e2ef2-2ddd-11e8-9279-19c38d723e3e.png) が成り立つと仮定すると、<br>
全ての工場 i で、戦略 D は、戦略 C を支配する戦略である。<br>

従って、このゲームのナッシュ均衡点は、<br>
![image](https://user-images.githubusercontent.com/25688193/37753020-45a262ec-2dde-11e8-88a5-092d0ed9cb6b.png)<br>
となり、この結果、湖は汚染される。<br>

このときの工場 i の均衡費用は、<br>
![image](https://user-images.githubusercontent.com/25688193/37753069-72862f1e-2dde-11e8-997a-ff9f4fa4ac87.png)<br>
となるが、<br>
全ての工場が浄化装置を付けた場合の工場 i の費用 K と比較すると、<br>
![image](https://user-images.githubusercontent.com/25688193/37753089-86de29e4-2dde-11e8-862b-304f28a9aad6.png) の関係より、全ての工場が浄化装置を付けた場合のほうがコストが安く、<br>
ナッシュ均衡点は、パレート最適ではないことが分かる。<br>

つまり、全ての工場が浄化装置を付けた場合のほうがコストが安いにも関わらず、<br>
非協力状態のもと自らの利潤を追求した結果、より高コストな結果を生んでしまう。<br>
その意味で、この問題は、囚人のジレンマと同じような状況が発生している。<br>

次に、このような状況を回避することを目的として、<br>
ゲームのルールを拡張する。<br>
具体的には、以下のような、ゲームを考える。<br>

- 工場は、湖の水を浄化するための共同組織を作る。<br>
- この共同組織は、メンバー全員が合意すれば、廃水を浄化しないメンバーに対し、罰金 ρ を課すことが出来る。<br>
- この罰金の額は、ρ > K−L  である。

そして、この共同組織の設立が可能であるかを分析するための、<br>
以下のような３段階のゲームを考える。<br>

1. 参加決定段階<br>
    まず、全ての工場 i (=1,2, ... ,n) は、以下の２つの選択肢を、他の工場とは独立して行う。<br>
    - 組織に参加する。（ ![image](https://user-images.githubusercontent.com/25688193/37763027-5567b150-2e01-11e8-9f85-4887e5fad7d6.png) ）<br>
    - 組織に参加しない。（ ![image](https://user-images.githubusercontent.com/25688193/37763170-b110ff20-2e01-11e8-9fdd-603a23e2cc9e.png) ）<br>

2. 交渉段階<br>
    組織に参加したメンバーは、罰金 ρ ( > K−L) の制度を設けるか否かを、独立して全員一致ルールで採択する。<br>
    但し、この罰金は、組織の非メンバーには効力を持たない。<br>

3. 行動決定段階<br>
    この上で、全ての工場 i (=1,2, ... , n) は、以下の２つの選択肢を、他の工場とは独立して行う。<br>
    - 浄化装置を付ける。（ ![image](https://user-images.githubusercontent.com/25688193/37763241-e354d2f4-2e01-11e8-9606-0acf285c1e95.png) ）<br>
    - 浄化装置を付けない。（ ![image](https://user-images.githubusercontent.com/25688193/37765185-e8c484be-2e06-11e8-858e-018c03ee06d1.png) ）<br>
    この場合で、組織に加入している＆組織が罰金を設けている場合は、罰金 ρ が課せられる。<br>



> 記載中...

---

<a id="ID_1-6"></a>

## ■ 情報不完備ゲーム [game with incomplete information]
情報不完備ゲームにおいては、<br>
各プレイヤーは、他プレイヤーの利得関数に関して、正確な知識を持たない。<br>

ここでは、主に戦略形ゲームにおいて、<br>
各プレイヤーが、他プレイヤーの利得関数についての知識を持たないケースを取り扱うが、<br>
ここでの議論の本質は、<br>
プレイヤーの集合や戦略集合などの、利得関数以外のゲームの構成要素に関して、<br>
プレイヤーが完全な知識をもたないケースにも適用可能である。<br>

<a id="ID_1-6-1"></a>

### ◎ 情報不完備ゲームの定式化
**このような情報不完備ゲームを定式化するにあたって、**<br>
**最初に直面する問題は、**<br>
**「プレイヤーが利得関数を完全には知らない。」**<br>
**という事象をどのようにモデル化すればよいか？という問題である。**<br>

ハーサニによる情報不完備ゲームの理論では、これを以下のように考える。<br>

n 人戦略形ゲーム ![image](https://user-images.githubusercontent.com/25688193/37817019-8ef5092e-2eb8-11e8-8246-088fadb4cf68.png) において、<br>
**プレイヤー i の利得関数**<br>
![image](https://user-images.githubusercontent.com/25688193/37817068-bde2c492-2eb8-11e8-8016-1399dc78480c.png)（ ![image](https://user-images.githubusercontent.com/25688193/37817092-da67c996-2eb8-11e8-9603-7d48a08b5d89.png) : プレイヤー i の純戦略、或いは、混合戦略で、この関数の独立変数）<br>
**の形状を、決定するある変数 c が存在して、**<br>
**全てのプレイヤーは、この（形状の）決定変数 c の真の値を知らないとする。**<br>
各プレイヤーが、この変数 c に関して、プレイヤー度にどのような情報を得ているのか明示するために、<br>
この変数 c は、プレイヤー数 n と同じ要素個 ![image](https://user-images.githubusercontent.com/25688193/37817648-d89cb9c6-2eba-11e8-9aef-8b1272d08f22.png) に分解出来るとする。<br>
各プレイヤー i は、そのインデックスに対応した第 i 成分の ![image](https://user-images.githubusercontent.com/25688193/37817859-86f7dda2-2ebb-11e8-8b94-753aa62fe2d6.png) の値を知ることは出来るが、<br>
他の ![image](https://user-images.githubusercontent.com/25688193/37817871-98bb5442-2ebb-11e8-8570-318d0545aeba.png) の真の値を知ることは出来ない。<br>

この各プレイヤー i に対する ![image](https://user-images.githubusercontent.com/25688193/37817859-86f7dda2-2ebb-11e8-8b94-753aa62fe2d6.png) は、**情報ベクトル**（或いは、**属性ベクトル**）といい、<br>
利得関数に影響を与えるようなプレイヤーに固有の社会的、物理的、心理的要素などからによる、複数の成分をもつベクトルとなる。<br>
このプレイヤーの情報ベクトル、或いは属性ベクトル ![image](https://user-images.githubusercontent.com/25688193/37817859-86f7dda2-2ebb-11e8-8b94-753aa62fe2d6.png) は、そのプレイヤーのみが真の値を知ることが出来るので、<br>
プレイヤーの個人情報を表しているとも言える。<br>
以下では、この情報ベクトル、属性ベクトルを総称して、**タイプ**と呼ぶことにする。<br>

ここまでの議論をまとめると、<br>
「**プレイヤーの利得関数は、全てのプレイヤーの戦略変数とタイプ（情報ベクトル）に依存する。**<br>
**そして、各プレイヤーは、自分のタイプを知ることは出来るが、他のプレイヤーのタイプを知ることは出来ない。**」<br>

<br>

<!------------------------------------------------------------------>

ハーサニによる情報不完備ゲームの理論では、これに加えて、<br>
このような不確実性下でのプレイヤーの意思決定に関して、以下のベイジアン仮説を採用する。<br>

![image](https://user-images.githubusercontent.com/25688193/38017648-9713082e-32ad-11e8-8806-95080c7a7d10.png)<br>

以上の準備をもとに、情報不完備ゲームは以下のように定義できる。<br>
![image](https://user-images.githubusercontent.com/25688193/37831324-66087228-2ee8-11e8-9601-616bd0b4aa97.png)<br>


<a id="ID_1-6-2"></a>

### ◎ ベイジアンゲームと情報不完備ゲーム
ハーサニの理論では、更に、<br>
この主観的同時確率分布の族、即ちプレイヤー i(=1,2, ... ,n) がもつ条件付き確率の族<br>
![image](https://user-images.githubusercontent.com/25688193/37863370-77a1f654-2fa0-11e8-8b55-50056f8708dd.png)<br>
に以下のような、整合性に関する条件を仮定する。<br>

![image](https://user-images.githubusercontent.com/25688193/37863414-16ca4c2c-2fa1-11e8-903e-0d089b251219.png)<br>

情報不完備ゲームにおいて、上記の意味で、プレイヤー主観確率が整合性であるならば、<br>
次のようなベイジアンゲームと呼ばれる、情報完備ゲームを構築することが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/37863719-7a1602e4-2fa6-11e8-9eb1-10cec5fc3e9f.png)<br>

このベイジアンゲーム ![image](https://user-images.githubusercontent.com/25688193/37872831-a5ab9b0e-304a-11e8-9b6d-e765d6f77450.png) は、以下のようにプレイされる。<br>

1. 全てのプレイヤーのタイプの組 ![image](https://user-images.githubusercontent.com/25688193/37872847-d3a5d0ce-304a-11e8-9106-d8bb02773d72.png) が、<br>
    確率分布 ![image](https://user-images.githubusercontent.com/25688193/37872851-eb297e94-304a-11e8-8c65-7aa5dbe8ad8f.png) （全てのタイプの組み合わせに正の確率を付与する確率分布）にもとづいて実現される。<br>
2. プレイヤー i は、自分のタイプ ![image](https://user-images.githubusercontent.com/25688193/37872854-fdb5f236-304a-11e8-82c1-7d49c43a77ce.png) の実現値のみを知った上で、<br>
    他のプレイヤーとは独立に、自身の行動戦略 ![image](https://user-images.githubusercontent.com/25688193/37873668-63a715e6-305c-11e8-84c2-4f2a2416689f.png) を選択する。（![image](https://user-images.githubusercontent.com/25688193/37873684-a6249f4c-305c-11e8-927d-40f4ab6d5cbc.png)）<br>
3. ゲームのプレイの最後に、プレイヤー i は、利得 ![image](https://user-images.githubusercontent.com/25688193/37872860-29a97868-304b-11e8-823a-06b17fae829f.png) を得る。<br>

又、ベイジアンゲームは、情報完備ゲームであるが、（プレイヤーのタイプが）<br>
ハーサニの情報不完備ゲーム理論では、<br>
情報不完備ゲームと、ベイジアンゲームを（ゲーム理論的には）同値とみなす。（＝ベイズの同値仮説）<br>
（これにより、ベイジアンゲームを情報不完備ゲームと呼ぶことが多いが、本来は違うゲーム的状況を表している。）<br>

- ベイズの同値仮説<br>
    情報不完備ゲームと、そこから導かれるベイジアンゲームは、<br>
    プレイヤーの戦略上の観点からは、同値であり、<br>
    プレイヤーの戦略の選択は、どちらのルールでも同じ決定ルール（解概念）に従う。<br>
	
以下では、情報不完備ゲーム ![image](https://user-images.githubusercontent.com/25688193/37872875-52cb0ba8-304b-11e8-85ca-a8f6ef12e775.png) を、情報完備ゲームであるベイジアンゲーム ![image](https://user-images.githubusercontent.com/25688193/37872877-622ce9f4-304b-11e8-8f81-375e9e232088.png) に変換して分析する。<br>

---

<a id="ID_1-6-3"></a>

### ◎ ベイジアン均衡点
情報不完備ゲーム ![image](https://user-images.githubusercontent.com/25688193/37952132-c082eca8-31d9-11e8-8127-a0b45a77bd6c.png) において、<br>
プレイヤー i の条件付き期待利得は、<br>
![image](https://user-images.githubusercontent.com/25688193/37952153-d75e57aa-31d9-11e8-97c7-2868d5c54ee4.png)<br>
と定義できる。<br>

この条件付き期待利得 ![image](https://user-images.githubusercontent.com/25688193/37952201-f928a4f8-31d9-11e8-905e-dac65e0494b9.png) より、<br>
情報完備ゲームにおけるナッシュ均衡点とよく似た概念である、<br>
情報不完備ゲームにおけるベイジアン均衡点なるものを定義できる。<br>

![image](https://user-images.githubusercontent.com/25688193/37952963-8051ce12-31dc-11e8-856b-aa6c9ff974da.png)<br>

<br>

<!------------------------------------------------------------------->

この（情報不完備ゲームにおける）ベイジアン均衡点は、その定義からも分かるように、<br>
（情報完備ゲームにおける）ナッシュ均衡点とよく似た概念をである。<br>
そのことを以下に示す。<br>

そのために、まず、ベイジアンゲームにおける期待利得、及びナッシュ均衡点を定義する。<br>

情報不完備ゲーム ![image](https://user-images.githubusercontent.com/25688193/37956894-84acbc46-31e7-11e8-8e10-bddac4eaeb0d.png) から構成されるベイジアンゲーム ![image](https://user-images.githubusercontent.com/25688193/37956927-9b97d2ba-31e7-11e8-8d8e-ede8818539a0.png) において、<br>
全てのプレイヤーの戦略の組 ![image](https://user-images.githubusercontent.com/25688193/37956992-cd3eebbe-31e7-11e8-8b98-ab27ad44c4f1.png) に対してのプレイヤー i の期待利得は、<br>
![image](https://user-images.githubusercontent.com/25688193/38023143-70e15278-32bc-11e8-801f-2edcfa463849.png)<br>
と定義できる。<br>

このベイジアンゲームにおけるナッシュ均衡点と、情報不完備ゲームにおけるベイジアン均衡点に関して、<br>
以下の定理が成り立つ。<br>

![image](https://user-images.githubusercontent.com/25688193/37958522-b5ab5768-31eb-11e8-8dbd-221f0133eca4.png)<br>

<br>

<!------------------------------------------------------------------->

先のベイズ同値仮説は、<br>
プレイヤーの戦略の選択が、<br>
情報不完備ゲームにおいても、そこから構成されるベイジアンゲーム（情報完備ゲーム）においても、<br>
同じ（ゲームの）解概念に従うことを要求する。<br>
よって、この定理（＝情報不完備ゲームにおけるベイジアン均衡点とベイジアンゲームにおけるナッシュ均衡点は同じ）より、<br>
**情報完備ゲームのナッシュ均衡点を解概念として採用すれば、**<br>
**情報不完備ゲームの適切な解概念は、（ベイズ同値仮説に従う限り、）ベイジアン均衡点である** と言える。<br>

<br>

---

<a id="ID_1-6-4"></a>

### ◎ ベイジアンゲームの例
ベイジアンゲームの例として、<br>
先の男女ゲームをベイジアンゲームの枠組みで考える。<br>

このゲームの利得関数の表は、以下のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/37875007-3d5a9ec2-3074-11e8-9e28-ce0905b8345d.png)<br>

ここで、このゲームをベイジアンゲームに拡張するために、<br>
各プレイヤーの個人情報であるタイプの概念を導入する。

1. タイプ１（ ![image](https://user-images.githubusercontent.com/25688193/37875029-93aec5fa-3074-11e8-8648-4515b41dcb4c.png) ）：ボクシングのほうが、バレエより好きである。<br>
2. タイプ２（ ![image](https://user-images.githubusercontent.com/25688193/37875035-a9cebdea-3074-11e8-9d05-f71b23a1880e.png) ）：バレエのほうが、ボクシングより好きである。<br>

そして、このタイプの組み合わせ (i, j) に応じたゲーム ![image](https://user-images.githubusercontent.com/25688193/37875045-bc76e62a-3074-11e8-89b8-6761be18553c.png) を考える。<br>

- ![image](https://user-images.githubusercontent.com/25688193/37875051-dbf5b940-3074-11e8-915c-22152c80be5c.png) の男女ゲーム<br>
	プレイヤー１（男性）のタイプが、タイプ１で、<br>
	プレイヤー２（女性）のタイプが、タイプ２である場合（ 1, 2 ）の利得関数の表は<br>
    ![image](https://user-images.githubusercontent.com/25688193/37875056-ef1f1bba-3074-11e8-9fa7-0b2ed982f41a.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37875070-3b6d9d48-3075-11e8-916f-0f0f7122b521.png) の男女ゲーム<br>
    プレイヤー１（男性）のタイプが、タイプ１で、<br>
	プレイヤー２（女性）のタイプが、タイプ１である場合（ 1, 1 ）の利得関数の表は<br>
    ![image](https://user-images.githubusercontent.com/25688193/37875080-5620232c-3075-11e8-8b2f-368355249379.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37875099-af059eea-3075-11e8-81ec-e7397b34a36a.png) の男女ゲーム<br>
    プレイヤー１（男性）のタイプが、タイプ２で、<br>
    プレイヤー２（女性）のタイプが、タイプ２である場合（ 2, 2 ）の利得関数の表は<br>
    ![image](https://user-images.githubusercontent.com/25688193/37875105-c14ef11e-3075-11e8-8f79-d2d9041413f6.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/37875226-3d26ee80-3077-11e8-9750-ec29a0e48417.png) の男女ゲーム<br>
    プレイヤー１（男性）のタイプが、タイプ２で、<br>
    プレイヤー２（女性）のタイプが、タイプ１である場合（ 2, 1 ）の利得関数の表は<br>
    ![image](https://user-images.githubusercontent.com/25688193/37875261-6610b150-3077-11e8-89ed-9a4b53e6d0b8.png)<br>

女性のタイプに関する、男性の主観確率（予想）は、<br>
![image](https://user-images.githubusercontent.com/25688193/37891337-ee21cdb2-310e-11e8-87b4-e48d73e6c9ab.png)<br>

男性のタイプに関する、女性の主観確率（予想）は、<br>
![image](https://user-images.githubusercontent.com/25688193/37891350-02b8e260-310f-11e8-8012-9598be9e5195.png)<br>

男性と女性の予想（主観確率）が、整合性であるとは、<br>
主観的同時確率 ![image](https://user-images.githubusercontent.com/25688193/37891638-f20ef822-310f-11e8-8a65-09835dc06c32.png) が存在して、これが全てのプレイヤー（男性＆女性）で等しいことを要求するので、<br>
![image](https://user-images.githubusercontent.com/25688193/37891874-d30b353e-3110-11e8-86c2-d50511f13a99.png)<br>
という関係式が成り立つ。<br>

この（第３式 /第１式）より、<br>
![image](https://user-images.githubusercontent.com/25688193/37893063-dcd7cd44-3114-11e8-8c7a-019a11dc8a9e.png)<br>

又、（第４式 /第２式）より、<br>
![image](https://user-images.githubusercontent.com/25688193/37893091-ef43648e-3114-11e8-8331-2d02a00fecb3.png)<br>

よって、<br>
![image](https://user-images.githubusercontent.com/25688193/37893128-0bcaf4be-3115-11e8-8d6b-c446313c4b22.png)<br>

という関係式が成り立つ。<br>

今、![image](https://user-images.githubusercontent.com/25688193/37893173-2eeb8116-3115-11e8-9eb2-b61dea99db50.png) のときを考えると、<br>
これらは、この関係式を満たすので、<br>

女性のタイプに関する、男性の主観確率（予想）は、<br>
![image](https://user-images.githubusercontent.com/25688193/37893206-4df9de2c-3115-11e8-9eea-2d6fcbb8b323.png)<br>

男性のタイプに関する、女性の主観確率（予想）は、<br>
![image](https://user-images.githubusercontent.com/25688193/37893259-6bfa3f8e-3115-11e8-90db-6d8d22ed0f4a.png)<br>

又、![image](https://user-images.githubusercontent.com/25688193/37893364-b99964cc-3115-11e8-81a3-ad697a3a84f4.png) のとき ![image](https://user-images.githubusercontent.com/25688193/37893394-d7d6f882-3115-11e8-87d9-33c4e4c644af.png) が成り立つので、<br>
男性のタイプと女性のタイプの（主観的）同時確率分布 ![image](https://user-images.githubusercontent.com/25688193/37893633-9cacccb8-3116-11e8-8cb6-ca8bb0cfbb5a.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/37893664-b155b44a-3116-11e8-8100-1a2d0f33b290.png)<br>

この（主観的）同時確率分布 ![image](https://user-images.githubusercontent.com/25688193/37893633-9cacccb8-3116-11e8-8cb6-ca8bb0cfbb5a.png) による、偶然手番をもつ展開形ゲームは、<br>
以下の図のように表現できる。<br>

![image](https://user-images.githubusercontent.com/25688193/38023249-b83f6196-32bc-11e8-9313-ba2c45392ec7.png)<br>

ベイジアンゲームにおいて、<br>
プレイヤー i は、自分のタイプ ![image](https://user-images.githubusercontent.com/25688193/37902854-c5b74ed4-3130-11e8-9d29-fc86971059b4.png) の実現値のみを知った上で、<br>
他のプレイヤーとは独立に、自身の行動戦略 ![image](https://user-images.githubusercontent.com/25688193/37902884-da3ace26-3130-11e8-91cb-e1d3d4ae9714.png) を選択する（ ![image](https://user-images.githubusercontent.com/25688193/37902928-07cfca26-3131-11e8-915e-188c6b5da402.png) ）ので、<br>
プレイヤー i の純戦略は、以下の表のような４通りの組み合わせになる。<br>
![image](https://user-images.githubusercontent.com/25688193/37902958-21017666-3131-11e8-8005-20e89b617318.png)<br>



> 記載中...

---

<a id="ID_1-7"></a>

## ■ 繰り返しゲーム [repeated game]
これまでに議論したゲームは、ゲームのプレイが一回のみ行われることを前提としてきた。<br>
しかしながら、応用上の多くの系では、ゲーム的状況は継続的であるので、<br>
ゲームのプレイが、繰り返しプレイされるモデルのほうが適切であると考えられる。<br>

ここでは、このような同一のゲームが繰り返し行われるような状況、<br>
即ち、**繰り返しゲーム [repeated game]** を考える。<br>

この繰り返しゲームでのポイントは、<br>
「**このゲームで、プレイヤーが過去のプレイの結果に依存して行動を選択できる場合に、**<br>
**協力、裏切り、仕返しなどの多様な行動パターンが可能となるが、**<br>
**その結果として、これまで見てきたナッシュ均衡点、部分ゲーム完全均衡点の概念を用いて、**<br>
**どのようなプレイヤーの行動が、繰り返しゲームにおける非協力均衡点として実現されるか？**」という点である。<br>


<a id="ID_1-7-1"></a>

### ◎ 繰り返し囚人のジレンマ
まず、以下の表の利得関数をもつ囚人のジレンマゲーム G を考える。<br>

（例）囚人のジレンマ<br>
![image](https://user-images.githubusercontent.com/25688193/38077303-81273e24-3373-11e8-80b6-af923552ace7.png)<br>

各プレイヤーは、行動 C（協力：cooperatio）、或いは、行動 D（裏切り：defection）の行動を選択し得る。<br>
このときのゲーム ![image](https://user-images.githubusercontent.com/25688193/38077329-98022a0a-3373-11e8-8f5b-736bec810575.png) の唯一のナッシュ均衡点は、(D, D) である。（裏切り D が、協力 C を支配する戦略であるため）<br>

今、この囚人のジレンマゲーム ![image](https://user-images.githubusercontent.com/25688193/38077329-98022a0a-3373-11e8-8f5b-736bec810575.png) が、無限に繰り返されるようなゲーム的状況を考える。<br>
但しこのとき、各プレイヤーは過去のゲームのプレイの結果を完全に知ることが出来るとする。<br>

このような新しいゲームを、元のゲーム ![image](https://user-images.githubusercontent.com/25688193/38077329-98022a0a-3373-11e8-8f5b-736bec810575.png) の繰り返しゲームといい、![image](https://user-images.githubusercontent.com/25688193/38077386-c6bcd62e-3373-11e8-82d9-e10dccede9f4.png) で表す。<br>
また、この元のゲーム ![image](https://user-images.githubusercontent.com/25688193/38077329-98022a0a-3373-11e8-8f5b-736bec810575.png) を繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38077386-c6bcd62e-3373-11e8-82d9-e10dccede9f4.png) の成分ゲーム [component game] といい、<br>
繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38077386-c6bcd62e-3373-11e8-82d9-e10dccede9f4.png) のほうを、元のゲーム ![image](https://user-images.githubusercontent.com/25688193/38077329-98022a0a-3373-11e8-8f5b-736bec810575.png) のスーパーゲーム [super game] という。<br>

この繰り返し囚人のジレンマゲーム ![image](https://user-images.githubusercontent.com/25688193/38077386-c6bcd62e-3373-11e8-82d9-e10dccede9f4.png) における、各プレイヤー i (=1,2) の取りうる戦略は、<br>
過去のプレイの結果に依存して、ゲームのプレイの毎回の行動を決定する行動であるが、<br>
そのような代表的な戦略として、ここでは、以下の４つの戦略を考える。<br>

1. all-C : 過去のプレイの結果によらず、常に行動 C（協力）を選択する。<br>
	
2. all-D : 過去のプレイの結果によらず、常に行動 D（裏切り）を選択する。<br>
	
3. トリガー [trigger] : 最初は行動 C を選択し、<br>
    以降は双方のプレイヤーが行動 C を選択する限り、行動 C を選択し続ける。<br>
    しかし、１回でも一方が行動 D を選択すれば、その後、行動 D を選択し続ける。<br>
	
4. しっぺ返し [tit for tat] : 最初は行動 C を選択し、以降は相手の前回の行動と同じ行動を選択する。<br>

繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38077386-c6bcd62e-3373-11e8-82d9-e10dccede9f4.png) における、プレイヤーの戦略が定まると、<br>
毎回のゲームプレイにおける、プレイヤーの利得を定めることが出来る。<br>

具体的には、２人のプレイヤーが共に all-C 戦略を選択したとすると、<br>
２人のプレイヤーは毎回のゲームプレイにおいて、利得 5 を得ることが出来る。<br>
ここで、t 回目のゲームプレイにおける、プレイヤーの利得 5 を、<br>
現在のゲームプレイでの現在利得に換算したものを ![image](https://user-images.githubusercontent.com/25688193/38077609-7f5f2e5c-3374-11e8-83bc-ef47afa25676.png) と評価する。<br>
（このような δ を、将来利得に対する割引因子 [discount factor] という。）<br>
このときの、（この無限回のゲームプレイにおける）割引利得の総和（割引利得和）は、<br>
![image](https://user-images.githubusercontent.com/25688193/38077640-a0f45e52-3374-11e8-881f-3a70552ec5b0.png)<br>
となるが、<br>
各プレイヤーは、この割引利得和を最大化しようと行動すると前提する。<br>

このようにして算出した、４つの戦略に対応する割引利得和は、以下の表のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/38077672-bb82a1ac-3374-11e8-93f5-f759a359d897.png)<br>

この利得行列の表より、ナッシュ均衡点を求めてみると、<br>

- 戦略の組 (all-D, all-D) は、割引因子 δ の値に関わらず、ナッシュ均衡点である。<br>
    （裏切り D が、協力 C を支配する戦略であるため）<br>
- 割引因子 δ ≥ 1/9 のとき、<br>
    - 戦略の組 (トリガー, トリガー) はナッシュ均衡点である。<br>
	（このとき、協力の戦略の組 (C, C) がプレイされている。）
	- 戦略の組 (しっぺ返し, しっぺ返し) はナッシュ均衡点である。<br>
	（このとき、協力の戦略の組 (C, C) がプレイされている。）<br>

このように、囚人のジレンマが継続的にプレイされるとき（繰り返し囚人のジレンマゲーム）、<br>
**プレイヤーの（将来利得に対する）割引因子 δ が十分に大きければ**（今の例では、δ ≥ 1/9 のとき）、<br>
**２人のプレイヤーの協力行動が、繰り返しゲームにおける非協力均衡点として実現可能である。**<br>
（＝協力行動が、ナッシュ均衡点となる。）<br>

<br>

<!------------------------------------------------------------------>

今の例では、プレイヤーの戦略を４つの戦略（ all-C, all-D, トリガー、しっぺ返し）に制限して考えたが、<br>
**可能な全ての戦略においても、囚人のジレンマにおけるプレイヤーの協力行動が、**<br>
**その繰り返しゲームにおける非協力均衡点のプレイとして実現出来る。**<br>
以下、このとこを示す。<br>

まず、囚人のジレンマにおける、一般的な利得関数を考えると、以下の表ようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/38083867-d1d879e8-3385-11e8-8c72-94a545340f15.png)<br>

このとき、トリガー戦略に対して、以下の性質が成り立つ。<br>

- 繰り返し囚人のジレンマゲームにおいて、<br>
    プレイヤーの将来利得に対する割引因子 δ の値が、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38084690-d62fd074-3388-11e8-8235-f185146384ae.png)<br>
    であるならば、**トリガー戦略の組は、このゲームのナッシュ均衡点となる。**<br>

	- （証明）<br>
    	２人のプレイヤーがトリガー戦略を用いるとき、プレイヤーの割引利得和は、<br>
	    ![image](https://user-images.githubusercontent.com/25688193/38084650-afbf96f4-3388-11e8-9453-d7fa9aa7dce8.png)<br>
    	となる。<br>
        
		プレイヤー１が、ゲームの t 回目のプレイにおいて、行動を C → D に変更したとすると、<br>
		（プレイヤー２はトリガー戦略を用いるので）t+1 以降のゲームプレイにおいて、<br>
		行動 D が選択され続けることになる。<br>
		従って、”t 回目以降の”ゲームプレイでのプレイヤー１の割引利得は、<br>
		![image](https://user-images.githubusercontent.com/25688193/38089896-e1070ad6-339b-11e8-991e-36219b54fb8c.png)<br>
		となる。<br>

		この２つの割引利得和（行動 C のトリガー戦略継続、t 回目で行動 C→D）を比較すると、<br>
		![image](https://user-images.githubusercontent.com/25688193/38084690-d62fd074-3388-11e8-8235-f185146384ae.png) の関係式より、<br>
		![image](https://user-images.githubusercontent.com/25688193/38090032-50dcbcca-339c-11e8-8295-7e9253b3693f.png)<br>
		となる。<br>
		
		つまり、行動を C → D に変更することで、長期的な利得が下がるために、<br>
		プレイヤーが戦略を変更する動機を持たず、このときのトリガー戦略の組はナッシュ均衡点である。<br>

<br>

又、しっぺ返し戦略に対して、以下の性質が成り立つ。<br>

- 繰り返し囚人のジレンマゲームにおいて、<br>
	プレイヤーの将来利得に対する割引因子 δ の値が、<br>
	![image](https://user-images.githubusercontent.com/25688193/38084725-f615bfd4-3388-11e8-961e-d7ad095a106d.png)<br>
	であるならば、**しっぺ返し戦略の組は、このゲームのナッシュ均衡点となる。**<br>

    - （証明）<br>
		２人のプレイヤーが共にしっぺ返し戦略を用いるとき、プレイヤーの割引利得和は、<br>
		![image](https://user-images.githubusercontent.com/25688193/38098159-3e5f844a-33b2-11e8-9687-1bf2c49a8f5b.png)<br>
		となる。<br>

		プレイヤー１が、ゲームの t 回目のプレイにおいて、行動を C → D に変更したとすると、<br>
		すると、t+1 回目以降のゲームプレイにおいて、<br>
		プレイヤー２の行動は、しっぺ返し戦略の元、行動 C or D が選択されることになる。<br>
        このときの t+1 回目以降のゲームプレイの様子を樹形図で書くと、以下の図のようになる。<br>
        <br>
        又、このゲームプレイの樹形図の行動の組を遷移図で書き直すと、以下の図のようになる。<br>
        ![image](https://user-images.githubusercontent.com/25688193/38098202-5b30aae0-33b2-11e8-80ed-a008eb2c80c5.png)<br>
        又、このゲームプレイの樹形図の行動の組を遷移図で書き直すと、以下の図のようになる。<br>
        ![image](https://user-images.githubusercontent.com/25688193/38099397-76655114-33b5-11e8-8bd9-9200f288b96c.png)<br>

        この行動の組の遷移図より、<br>
        プレイヤー１が、しっぺ返し戦略からどのように戦略を離脱しても、割引利得和が大きくならないためには、<br>
        ![image](https://user-images.githubusercontent.com/25688193/38102024-eebc534a-33bc-11e8-853e-a7489be2fdc0.png)<br>
        の３つの条件を満たせば良いことが分かる。<br>

        > 記載中...

<br>

---

<a id="ID_1-7-2"></a>

### ◎ （無限回）繰り返しゲームの定式化
![image](https://user-images.githubusercontent.com/25688193/38132103-96cc2cea-3444-11e8-9049-a7b3e429d5f0.png)<br>

そして、この（無限回）繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38132136-c1533698-3444-11e8-869a-91ac1cbff1f3.png) は、以下のようにルールを持つ。<br>

1. 毎回のゲームプレイにおいて、各プレイヤーは成分ゲーム G の行動を他のプレイヤーとは独立して選択する。<br>
2. 行動を選択する際に、各プレイヤーは過去のゲームプレイの結果を、完全に知ることが出来る。<br>
3. 全てのプレイヤーは、割引因子 δ (0 < δ < 1) による割引利得和を最大化しようと行動する。<br>

<br>

---

<a id="ID_1-7-3"></a>

### ◎ フォーク定理（繰り返しゲームにおけるナッシュ均衡点の基本定理）
ここでは、繰り返しゲームにおけるナッシュ均衡点の基本定理であるフォーク定理をみていく。<br>
そのためにまず、繰り返しゲームにおけるナッシュ均衡点を定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/38133868-e74b057c-344b-11e8-8ed6-5882d277e63d.png)<br>

先の繰り返し囚人のジレンマゲームでみたように、<br>
ナッシュ均衡点は、均衡点から離脱したプレイヤーに対して、処罰行動を与えているとみなすことも出来る。<br>
この処罰行動の内、最も基本的な処罰の方法は、プレイヤーに対してミニマックス行動を用いることである。<br>
（他のプレイヤーがプレイヤー i に対するミニマックス行動を選択すれば、<br>
このプレイヤー i は、高々ミニマックス利得しか得られなくなるので、ミニマックス行動は、処罰行動を与える。）<br>

![image](https://user-images.githubusercontent.com/25688193/38135276-3f103100-3452-11e8-8ce8-230984d76ae4.png)<br>

![image](https://user-images.githubusercontent.com/25688193/38137061-692ef31c-345d-11e8-8e02-516c940b25e0.png)<br>

この個人合理的の概念を用いて、<br>
以下のような繰り返しゲームにおけるナッシュ均衡点と割引因子の値に関しての重要な定理（フォーク定理）が示せる。<br>

![image](https://user-images.githubusercontent.com/25688193/38190529-95b8a59c-369f-11e8-939b-45aa43efc714.png)<br>

<br>

<!----------------------------------------------------------->

このフォーク定理の内容を、囚人のジレンマゲームで考える。<br>

（例）囚人のジレンマゲームの利得関数<br>
![image](https://user-images.githubusercontent.com/25688193/38141067-88d692a6-3471-11e8-91b2-b482801a10cf.png)<br>

純戦略による実現可能な利得ベクトルの集合（下図）を見やすくするために、<br>
プレイヤー i の行動集合を区間 ![image](https://user-images.githubusercontent.com/25688193/38141113-b2423c9e-3471-11e8-86c9-6bf10e243a3d.png) の範囲で連続化する。<br>

協力行動（C）：![image](https://user-images.githubusercontent.com/25688193/38141199-02278516-3472-11e8-8391-f8fe32d2a6e6.png)<br>
裏切り行動（D）：![image](https://user-images.githubusercontent.com/25688193/38142109-1d7c4ece-3476-11e8-94a0-ca8163b07994.png)<br>
⇒ ![image](https://user-images.githubusercontent.com/25688193/38142307-c638b390-3476-11e8-8e02-f55938f5b047.png) は、純戦略の選択確率となっている。<br>

行動の組 ![image](https://user-images.githubusercontent.com/25688193/38142285-ac7c9f5c-3476-11e8-87ae-ece7aa9c8012.png) に対して、プレイヤーの利得を<br>
![image](https://user-images.githubusercontent.com/25688193/38142720-6fd51b72-3478-11e8-8850-c504af7a63b6.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38142741-7fc922bc-3478-11e8-9f5e-f642a1b41a2d.png)<br>

このような実現可能な利得ベクトルび実現可能領域の集合 ![image](https://user-images.githubusercontent.com/25688193/38142827-e3a0d352-3478-11e8-9c0b-b20f79d3f8a8.png) を図示すると、<br>
以下のようになる。<br>

![image](https://user-images.githubusercontent.com/25688193/38160080-09a016fc-34f2-11e8-852d-88b7addfa553.png)<br>

ナッシュ均衡点 (-3,-3) を起点に、利得値 ![image](https://user-images.githubusercontent.com/25688193/38160089-3a9b942a-34f2-11e8-97b3-ff9239340b1a.png) の点集合が、<br>
個人合理的な行動の組 a による利得ベクトル全体となる。（赤枠部分）<br>
よって、フォーク定理より、割引因子 δ の値がが十分に大きい時、<br>
これらの個人合理的な行動の組による利得ベクトル全体が、繰り返しゲームにおけるナッシュ均衡点により実現可能なである。<br>

---

<a id="ID_1-7-4"></a>

### ◎ 完全フォーク定理
![image](https://user-images.githubusercontent.com/25688193/38162508-4e9e1788-351d-11e8-807a-3f9d6d672545.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/38162410-b4a6efa2-351b-11e8-84e9-e21d46a9bd63.png) : 割引因子 δ をもつ成分ゲーム G の繰り返しゲーム<br>
- ![image](https://user-images.githubusercontent.com/25688193/38162415-ded4e324-351b-11e8-9fad-3d2e688ecc1f.png) : 繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38162410-b4a6efa2-351b-11e8-84e9-e21d46a9bd63.png) におけるプレイヤー i の戦略<br>
- ![image](https://user-images.githubusercontent.com/25688193/38162423-efad8bce-351b-11e8-8a49-445a7e743bc8.png) : t 回目のゲームプレイまでのゲームの履歴（上図の赤線部分）<br>
- ![image](https://user-images.githubusercontent.com/25688193/38162436-248ac1e0-351c-11e8-8719-a8ce1b9197f8.png) : 繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38162410-b4a6efa2-351b-11e8-84e9-e21d46a9bd63.png) の履歴 ![image](https://user-images.githubusercontent.com/25688193/38162431-0d6ea2ba-351c-11e8-99f5-61bf55b5289d.png) 以降の部分ゲーム<br>
- ![image](https://user-images.githubusercontent.com/25688193/38162470-dc2c80c2-351c-11e8-9d54-3420cd75cbc9.png) : 戦略 ![image](https://user-images.githubusercontent.com/25688193/38162415-ded4e324-351b-11e8-9fad-3d2e688ecc1f.png) が部分ゲーム ![image](https://user-images.githubusercontent.com/25688193/38162436-248ac1e0-351c-11e8-8719-a8ce1b9197f8.png) に導く戦略（上図の赤線部分）で、<br>
    部分ゲームにおける m 回目の任意の履歴（上図の赤点線部分）![image](https://user-images.githubusercontent.com/25688193/38162475-ef205028-351c-11e8-817b-6fe188107a2b.png) に対し、以下の式で定義出来る。<br>
    ![image](https://user-images.githubusercontent.com/25688193/38162482-022edd10-351d-11e8-931c-83a7ecf48d65.png)<br>

![image](https://user-images.githubusercontent.com/25688193/38163751-3062847c-3534-11e8-9d31-095e2beef2fd.png)<br>
この繰り返しゲームにおける部分ゲーム完全均衡点の定義は、<br>
先に定義した以下の展開形ゲームにおける部分ゲーム完全均衡点の一般的な定義を、<br>
繰り返しゲームに適用したものとなっている。<br>

- cf :<br>
    ![image](https://user-images.githubusercontent.com/25688193/38163757-4bdffd42-3534-11e8-889e-1f614194af52.png)

<br>

<!--------------------------------------------------------------->

まず、繰り返し囚人のジレンマゲームでのしっぺ返し戦略が、部分ゲーム完全均衡点になるか否かを見てみる。<br>

（例）ナッシュ均衡点が部分ゲーム完全均衡点とはならない例（繰り返し囚人のジレンマゲームでのしっぺ返し戦略）<br>
![image](https://user-images.githubusercontent.com/25688193/38172161-f10b7dd4-35e1-11e8-9c7e-3518ef7ea2f8.png)<br>
繰り返し囚人のジレンマゲームにおけるしっぺ返し戦略は、先にみたように、<br>
割引因子 δ が十分に大きい時（δ≥1/9）、このゲームにおけるナッシュ均衡点となる。<br>
しっぺ返し戦略は、初手として C を選択し、以降は前回の相手の選択と同じ選択を行う戦略であった。<br>
従って、<br>

1. プレイヤー１、２が初期手番として、D, C を選択すると、<br>
	履歴 ![image](https://user-images.githubusercontent.com/25688193/38172165-1108a378-35e2-11e8-8abe-c9b0edf84658.png) 以降のゲーム（部分ゲーム）のプレイの推移は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38172167-260d61d2-35e2-11e8-8eb5-e0e7251d6c1c.png)<br>
	となる。<br>
	プレイヤー１が C でプレイヤー２が D を選択したときの、プレイヤー２の利得は 6。<br>
	プレイヤー１が D でプレイヤー２が C を選択したときの、プレイヤー２の利得は -4。<br>
	よって、このときの履歴 ![image](https://user-images.githubusercontent.com/25688193/38172165-1108a378-35e2-11e8-8abe-c9b0edf84658.png) 以降の部分ゲームの割引利得和は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38172179-549e10f0-35e2-11e8-92f2-1486ac32376e.png)<br>

2. プレイヤー２が、２回目のゲームプレイ以降に、初期行動が C であるしっぺ返し戦略に変更すると、<br>
	履歴 ![image](https://user-images.githubusercontent.com/25688193/38172165-1108a378-35e2-11e8-8abe-c9b0edf84658.png) 以降のゲーム（部分ゲーム）のプレイの推移は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38172210-cce5ac76-35e2-11e8-8bd8-d98a038eeb23.png)<br>
	となる。<br>
	プレイヤー１、２共に C を選択したときの、プレイヤー２の利得は 5。<br>
	よって、このときの履歴 ![image](https://user-images.githubusercontent.com/25688193/38172165-1108a378-35e2-11e8-8abe-c9b0edf84658.png) 以降の部分ゲームの割引利得和は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38172218-f722a5de-35e2-11e8-82f6-c1ea686fd7f5.png)<br>

今、δ≥1/9 のとき<br>
![image](https://user-images.githubusercontent.com/25688193/38172225-323087fe-35e3-11e8-852b-bcdc66a11715.png)<br>
となるので、<br>
しっぺ返し戦略は、履歴 ![image](https://user-images.githubusercontent.com/25688193/38172165-1108a378-35e2-11e8-8abe-c9b0edf84658.png) 以降の部分ゲームに対して、ナッシュ均衡点を導かない。<br>
従って、しっぺ返し戦略は、この繰り返し囚人のジレンマゲームの部分ゲーム完全均衡点とはならない。<br>

<br>

<!--------------------------------------------------------------->
繰り返しゲームの部分ゲーム完全均衡点を構成するために、<br>
まず、繰り返しゲームの成分ゲームにおけるナッシュ均衡点を処罰とする戦略を考える。<br>

![image](https://user-images.githubusercontent.com/25688193/38190578-df39eca8-369f-11e8-84a7-498752110598.png)<br>

- cf :<br>
    ![image](https://user-images.githubusercontent.com/25688193/38186494-4646158c-368e-11e8-9736-350cc82633a1.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/38190529-95b8a59c-369f-11e8-939b-45aa43efc714.png)<br>

この定理より、割引因子が十分に大きい時、<br>
全てのプレイヤーが成分ゲーム G のナッシュ均衡点より、<br>
厳密に大きな利得を得ることの出来る行動の組 a（ ![image](https://user-images.githubusercontent.com/25688193/38189273-5d9c970e-369a-11e8-95fe-a6eda0a38e22.png) ）は、<br>
この成分ゲーム G の繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38189302-7d9a161c-369a-11e8-8e32-b69be1a3876d.png) の部分ゲーム完全均衡点により実現できることが分かる。<br>
（従って、プレイヤーのミニマックス利得とナッシュ均衡点での利得が等しいようなゲームでは、<br>
フォーク定理が部分ゲーム完全均衡点に関しても成り立つことになる。）<br>

<br>

---

<a id="ID_1-7-5"></a>

### ◎ 有限回繰り返しゲーム
ここまでは、ゲームのプレイが際限なく、無限回繰り返されるゲームを見てきたが、<br>
次に、ゲームのプレイが有限回のみ行われるような繰り返しゲームを見ていく。（有限回繰り返しゲーム）<br>

戦略形ゲームを ![image](https://user-images.githubusercontent.com/25688193/38190093-adf58fd2-369d-11e8-999e-5ac6ed9218e3.png) とすると、これから構成される有限ゲームは、![image](https://user-images.githubusercontent.com/25688193/38190071-950cce40-369d-11e8-8d17-0b12074548b9.png) と書ける。<br>
ここで、T は、ゲームプレイの回数であり、全てのプレイヤーの共有知識である。<br>
無限回繰り返しゲームの時と同様にして、全てのプレイヤーは、過去のゲームプレイの結果を完全に知ることが出来る。<br>

<br>

<!-------------------------------------------------------------------------------->

そして、有限回繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38190071-950cce40-369d-11e8-8d17-0b12074548b9.png) における戦略は、無限回繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38189302-7d9a161c-369a-11e8-8e32-b69be1a3876d.png) の場合と同様に定義出来る。<br>

具体的には、有限回繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38190071-950cce40-369d-11e8-8d17-0b12074548b9.png) において、<br>
プレイヤーの戦略の組 s=(s_1,s_2,…,s_n )  に対して、各ゲームプレイにおける履歴からなる行動の組の列<br>
![image](https://user-images.githubusercontent.com/25688193/38190817-f65e6476-36a0-11e8-8455-7bf9daf2e1a2.png)<br>
が定まる。<br>

この行動の組の列（履歴）![image](https://user-images.githubusercontent.com/25688193/38191537-22a2614c-36a4-11e8-9085-470f96a0bcc5.png) に対する、各プレイヤー i の評価基準として、<br>
平均利得<br>
![image](https://user-images.githubusercontent.com/25688193/38191567-3c72303e-36a4-11e8-928e-40ca3d67a393.png)<br>
を考える。<br>

すると、（無限回繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38189302-7d9a161c-369a-11e8-8e32-b69be1a3876d.png) の場合と同様にして、）<br>
有限回繰り返しゲーム ![image](https://user-images.githubusercontent.com/25688193/38190071-950cce40-369d-11e8-8d17-0b12074548b9.png) における、ナッシュ均衡点、部分ゲーム完全均衡点を定義することが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/38196297-28f7c5dc-36bd-11e8-8887-905a2dd67a7a.png)<br>

囚人のジレンマゲームは、この定理の前提条件（ナッシュ均衡点による利得＝ミニマックス利得）を満たす。<br>
従って、この定理より、囚人のジレンマゲームの有限回繰り返しゲームにおけるナッシュ均衡点は、<br>
成分ゲームでのナッシュ均衡点 e が繰り返されるものに限る（![image](https://user-images.githubusercontent.com/25688193/38231815-3871dd4e-374f-11e8-9239-a505ce7ed66a.png)）<br>

即ち、囚人のジレンマゲームの有限回繰り返しゲームでは、<br>
ナッシュ均衡点は、(D:裏切り,D:裏切り) の戦略の組となるので、<br>
（無限回繰り返しゲームとは異なり、）プレイヤーの協力行動は実現しない。<br>

---

<a id="ID_1-8"></a>

## ■ 交渉ゲーム

<a id="ID_1-8-1"></a>

### ◎交渉問題の定式化
これまで取り上げてきた非協力ゲームは、<br>
プレイヤーは互いに独立に、自身の利得を最大化するような戦略を選択するようなゲームであった。<br>
しかしながら、囚人のジレンマ等の例のように、<br>
多くの非協力ゲームにおけるナッシュ均衡点は、必ずしもパレート最適ではない。<br>

このとき、各プレイヤーが互いに協力行動を行うことにより、<br>
各々のプレイヤーの利得を改善することが出来るケースが多く存在する。<br>

以下では、このような協力行動を如何にして定式化して、協力ゲームのモデルに取り入れるか？を考える。<br>

まず、協力の方法というものを考えると、これらは多様であり、<br>
協力によって、どのような状態を実現するかについてのプレイヤーの利害が一致するとは限らない。<br>
従って、プレイヤーは協力すべきかの否か？、又、協力の結果としてどのような状態を実現すべきか？について、<br>
各プレイヤー間の話し合いにより決定することになる。<br>
即ち、**まず始めに「交渉問題」が生じる** ことになる。<br>
従って、協力ゲームのモデル構築にあたって、最初にすべきことは交渉問題の定式化である。<br>

<br>

<!--------------------------------------------------------------------->

ここでは、まず、ナッシュの交渉理論で語られる、２人交渉問題を見てみる。<br>

（例）利得配分をめぐるコンフリクト（２人交渉問題）<br>
- プレイヤー A と B は、共同事業を行うことにより、100 万円の利得を得ることが出来る。<br>
- この共同事業を始める前に、プレイヤー A と B は、この 100 万円の利得を、<br>
    各々の利得としてどのように配分するか？についての交渉を行い、合意する必要がある。<br>
- もし合意に達しなければ、両者は共同事業を行わず、各プレイヤーの利得は 0 円となってしまう。<br>
- このとき、プレイヤー A と B は、話し合いの結果、合意に達するか？又、配分はどのようになるか？を解析する。<br>
    （但し、各プレイヤーは、完全に合理的な選択を行うものとする。）<br>

プレイヤー A の分配額を ![image](https://user-images.githubusercontent.com/25688193/38237857-4575f174-3763-11e8-9add-cb4893f9e8f9.png)  、プレイヤー B の分配額を ![image](https://user-images.githubusercontent.com/25688193/38237885-584f22e8-3763-11e8-80b0-de5de639a6fd.png) とすると、<br>
![image](https://user-images.githubusercontent.com/25688193/38237991-7ec4aee8-3763-11e8-86a6-379f3bd7e08f.png)<br>
の関係が成り立つ。<br>
これを図示すると、以下の図のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/38238021-904d5322-3763-11e8-9c12-f99f003eadbc.png)<br>

<br>

<!------------------------------------------------------------------>

この例を元に、２人交渉問題を、一般化して定式化すると、以下のようになる。<br>

![image](https://user-images.githubusercontent.com/25688193/38238885-3c1c9698-3766-11e8-9424-5242381f709a.png)<br>

次に、交渉理論の基本的な概念を定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/38243073-647e67e6-3771-11e8-8063-b437a296c83b.png)<br>

<br>

<!------------------------------------------------------------------->

先の例では、交渉問題として、利得分配をめぐる交渉の例をみたが、<br>
次に、行動の選択をめぐる交渉問題の例をみてみる。<br>

（例）男女の争い（２人交渉問題）<br>
![image](https://user-images.githubusercontent.com/25688193/38244808-bd10e2a8-3776-11e8-8591-11f13ea2a323.png)<br>

この男女ゲームのナッシュ均衡点は、既にみたように、以下の３つのナッシュ均衡点をもつ。<br>
① 純戦略によるナッシュ均衡点１：(ボクシング, ボクシング)<br>
② 純戦略によるナッシュ均衡点２：(バレエ, バレエ)<br>
③ 混合戦略によるナッシュ均衡点：( (3/5,2/5), (2/5,3/5))<br>

これらのナッシュ均衡点は、男女間のコンフリクトを解決するような解ではない。<br>
即ち、２つの純戦略によるナッシュ均衡点は、パレート最適であるが、<br>
どちらのナッシュ均衡点を選ぶかに関して、男女間のコンフリクトが発生する。<br>
又、混合戦略によるナッシュ均衡点は、パレート最適ではない。<br>

この男女ゲームにおいて、男女間の話し合いにより互いの戦略を決定できるケースを考える。<br>
このコンフリクトの自然な解決法は、<br>
２つの純戦略によるナッシュ均衡点（ (ボクシング, ボクシング) or (バレエ, バレエ) ）を、<br>
それぞれ確率 1/2 で選択するようにする解決法である。<br>
このような戦略を、２人の**相関戦略 [correlated strategy]** という。<br>

<br>

<!----------------------------------------------------------------->

次に、一般の戦略形ゲームから、どのようにして交渉問題が構築されるのか見てみる。<br>

- ![image](https://user-images.githubusercontent.com/25688193/38245680-1754fb5c-377a-11e8-9cb3-d1431681632c.png) : 戦略形２人ゲーム<br>
- ![image](https://user-images.githubusercontent.com/25688193/38245696-25bd7598-377a-11e8-9eaf-38c22c717aaa.png) : プレイヤー i の純戦略の集合<br>
- ![image](https://user-images.githubusercontent.com/25688193/38245712-361c3348-377a-11e8-8a39-d89de4616d04.png) : プレイヤー i の利得関数<br>
- ![image](https://user-images.githubusercontent.com/25688193/38245809-91d801ee-377a-11e8-8011-25fc213d4969.png) : 純戦略の組で、プレイヤーの相関純戦略 [correlated pure strategy] という。<br>
- ![image](https://user-images.githubusercontent.com/25688193/38245830-a0de5a1c-377a-11e8-885d-cee21f702fa1.png) 上の同時確率分布 q : プレイヤーの相関混合戦略 [correlated mixed strategy] という。<br>

このプレイヤーの期待利得 ![image](https://user-images.githubusercontent.com/25688193/38245845-b8ce3908-377a-11e8-80f2-b4312480cd62.png) によるベクトル（＝期待利得ベクトル）の全体が、<br>
プレイヤーの実現可能集合 U となる。<br>
即ち、<br>
![image](https://user-images.githubusercontent.com/25688193/38245859-c89db78c-377a-11e8-9d65-29dd02319ab9.png)<br>

男女ゲームの例では、下図の (-1,-1) - (1,2) - (2,1) で結ばれる三角形内部部分（赤線内）が、<br>
相関混合戦略による実現可能集合 U となる。<br>
![image](https://user-images.githubusercontent.com/25688193/38249217-e94852fc-3785-11e8-84f0-d86c59b69f43.png)<br>

戦略形ゲームから交渉問題を定式化するにあたっての困難さは、<br>
多くのケースで、交渉の不一致点が予め定まらないことに起因する。<br>
より詳細には、この交渉の不一致点が、どのような交渉ルールの元で話し合いが行われるか？<br>
更には、交渉が決裂した場合にどのような行動が可能であるか？に依存することに起因する。<br>

このような問題を解決するための、一般的な導入方法は確立されていない。<br>
そのため、ここでは、交渉の実現可能集合と交渉の不一致点が、予め与えられているケースのみを取り扱う。<br>

<br>

---

<a id="ID_1-8-2"></a>

### ◎ ナッシュ交渉解 [Nash bargaining solution]
交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38264790-0ad5c5c0-37af-11e8-9e5b-1b746c52032e.png) において、主に問題となるのは、<br>

1. （他からの強制なしに）プレイヤー間の自発的な話し合いにより、協力の合意が実現するか？<br>
2. もし協力が実現するならば、実現可能集合 U の中の、どの利得ベクトルが選択されるのか？<br>

といった問題である。<br>


以下、このような交渉問題での問題を、ゲーム理論のモデルを用いて分析することを考える。<br>

<br>

<!------------------------------------------------------------------------->

２つ目の問題（もし協力が実現するならば、実現可能集合 U の中の、どの利得ベクトルが選択されるのか？）は、<br>
交渉問題への公理論的アプローチで解決する。<br>
**即ち、もし、交渉において合意が実現されるならば、合意点が満たすべきいくつかの性質を公理（仮定）として提示し、**<br>
**１つの公理系から出発し、演繹（えんえき）的に導出される解の性質を解明するアプローチである。**<br>
**（＝公理論的アプローチ）**<br>
この公理系から導出した交渉問題の解は、**ナッシュ交渉解 [Nash bargaining solution]** と呼ばれる。<br>

<br>

<!------------------------------------------------------------------------->

１つ目の問題（プレイヤー間の自発的な話し合いにより、協力の合意が実現するか？）は、<br>
交渉問題への非協力アプローチで解決する。<br>
**即ち、交渉における合意の可能性自体を分析するために、合意に至る交渉のプロセスを、非協力ゲームとしてモデル化し、**<br>
**この非協力ゲームの非協力均衡点の帰結として、合意の実現を説明する。（＝非協力アプローチ）**<br>
そして、この非協力均衡点は、先の公理論的アプローチから導出された交渉解として実現される。<br>

<br>

<!------------------------------------------------------------------------->

ここでは、まず、公理論的アプローチについて説明する。<br>

![image](https://user-images.githubusercontent.com/25688193/38265996-7624f672-37b2-11e8-9cb9-9fcfc91218c6.png)<br>

ナッシュ交渉解の公理系を述べる前に、<br>
ナッシュ交渉解の公理系で重要となる２つの概念（対称性、効用の正１次変換）を定義する。<br>

![image](https://user-images.githubusercontent.com/25688193/38266696-496fcb8c-37b4-11e8-81b6-2dbe186ab404.png)<br>

![image](https://user-images.githubusercontent.com/25688193/38291043-e6b5cc48-3818-11e8-86e8-819acb0678af.png)<br>

これらの準備の元で、ナッシュ交渉解 f が満たすべき４つの公理を挙げていく。<br>

![image](https://user-images.githubusercontent.com/25688193/38296120-55384b2a-382b-11e8-96d3-8940949bb54a.png)<br>

この公理１（パレート最適性）は、<br>
合理的プレイヤーによる交渉の合意点として、以下の意味で自然なものとなっている。<br>
即ち、例えば、２つの利得ベクトル ![image](https://user-images.githubusercontent.com/25688193/38296166-74d669b2-382b-11e8-8913-6827207c28e5.png) と ![image](https://user-images.githubusercontent.com/25688193/38296206-9b2ed0d6-382b-11e8-8b74-385ba53bf1e6.png) において、<br>
![image](https://user-images.githubusercontent.com/25688193/38296256-c815b5ba-382b-11e8-94a5-9368684cc636.png) が成り立つような場合を考えると、<br>
プレイヤー１は、（より利得の高い）利得ベクトル ![image](https://user-images.githubusercontent.com/25688193/38296166-74d669b2-382b-11e8-8913-6827207c28e5.png) を好んで選択すると思われる。<br>
プレイヤー２にとっては、![image](https://user-images.githubusercontent.com/25688193/38296277-deaefe9e-382b-11e8-83c2-3a39e9dd2c36.png) となるので、２つの利得ベクトルに差異はないが、<br>
この利得ベクトル ![image](https://user-images.githubusercontent.com/25688193/38296166-74d669b2-382b-11e8-8913-6827207c28e5.png) に反対する理由も存在しない。<br>
従って、プレイヤー１，２は、話し合いにおいて、利得ベクトル ![image](https://user-images.githubusercontent.com/25688193/38296166-74d669b2-382b-11e8-8913-6827207c28e5.png) を好んで選択すると思われる。<br>

![image](https://user-images.githubusercontent.com/25688193/38296871-a99310f4-382d-11e8-888c-b697c0ca852f.png)<br>

![image](https://user-images.githubusercontent.com/25688193/38296961-f7f0ca8e-382d-11e8-8529-7fc956af655e.png)<br>

この公理３（効用の正１次変換からの独立性）は、<br>
交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38299264-7c186eb0-3834-11e8-87e3-cf333934343b.png) が、交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38299297-92e2cd7a-3834-11e8-8a54-e5330ba16373.png) から正１次変換から得られる時に、<br>
これら２つの交渉問題は、実質的は、同じ状況を記述していることを意味している。<br>
これは、例えば、利得の配分問題で、利得として円とドルどちらを採用しようが、<br>
そのゲーム的状況は本質的は変わらないといったものである。<br>

![image](https://user-images.githubusercontent.com/25688193/38299327-b0dce9b4-3834-11e8-84b0-53e7f0f06e57.png)<br>

![image](https://user-images.githubusercontent.com/25688193/38301488-a4abf88c-383a-11e8-905e-d49619ec33f0.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38301509-b617772c-383a-11e8-9542-2144191b2946.png)<br>

<br>

<!-------------------------------------------------------------------------->

そして、この４つの公理系から、交渉問題の解（＝ナッシュ交渉解）を一意に導出することが出来る。<br>

![image](https://user-images.githubusercontent.com/25688193/38347061-d9a162e0-38d3-11e8-83b9-bd0b576163dd.png)<br>

この定理で述べられているところの、<br>
４つの公理から、ナッシュ交渉解が一意に定まるという点を見てみる。<br>

- 交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38311135-6214f6d0-3859-11e8-88d1-3ca906544f2b.png) から、公理３の効用の１次変換<br>
    ![image](https://user-images.githubusercontent.com/25688193/38346686-bd295624-38d1-11e8-9f47-2a27c38504d0.png)<br>
    によって、（交渉不一致点 d をづらすことにより、）交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38311178-8441a21c-3859-11e8-9616-e076468b0513.png) を構成出来る。<br>
    このとき、ナッシュ交渉解 f は、公理３によって、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38311213-95a3f2d0-3859-11e8-9aca-5b919cf67ed6.png)<br>
    と書ける。<br>
    従って、一般性を失うことなく、<br>
    交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38311178-8441a21c-3859-11e8-9616-e076468b0513.png) において、![image](https://user-images.githubusercontent.com/25688193/38311510-546e2bc2-385a-11e8-9ee0-c20222b4527e.png) を仮定してもよい。<br>

- 最初に、実現可能集合として、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38315019-86bd6978-3862-11e8-8dbc-ea9fa3a73e2d.png)<br>
    を考える。<br>
    このとき、交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38315103-b516d52a-3862-11e8-967b-41760dbce794.png) は対称であるので、<br>
    公理１と公理２より、この交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38315103-b516d52a-3862-11e8-967b-41760dbce794.png) の交渉解は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38315689-f352a30e-3863-11e8-8652-3516389db47c.png)<br>
    でなくてはならない。<br>
    ![image](https://user-images.githubusercontent.com/25688193/38347497-d1bff73c-38d6-11e8-9789-7edf7faac9a0.png)<br>

- 次に、実現可能集合として、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38347205-fb571866-38d4-11e8-9d57-d8740f81336d.png)<br>
	を考える。<br>
    この実現可能集合からなる交渉問題は、効用の１次変換<br>
    ![image](https://user-images.githubusercontent.com/25688193/38347221-0ecbbbc2-38d5-11e8-9bc8-7d23fd28d002.png)<br>
	によって、<br>
	交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38347246-2ab95010-38d5-11e8-8354-b5adb9005c1b.png) を、交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38347258-3d319f04-38d5-11e8-9f4e-33352f5f29de.png) に変換することが出来る。<br>
    ここで、![image](https://user-images.githubusercontent.com/25688193/38347290-7f12c416-38d5-11e8-8ff3-d8f4d7764782.png) なので、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38347301-9326ba16-38d5-11e8-9252-fe133a4cbb9a.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/38347313-aa3f18ec-38d5-11e8-9b5f-e9e1960fa89d.png)<br>
    ![image](https://user-images.githubusercontent.com/25688193/38347511-e824f75c-38d6-11e8-9f88-7b9c27f89f69.png)<br>

以上のことより、<br>
交渉領域が直線で表せる場合（上図の赤線部分）において、ナッシュ交渉解は、<br>
原点 0 を通り、この直線に直交するような直線（＝各プレイヤーの利得を最大化するような方向）とのただ１つの交点で、<br>
一意に与えられることが分かる。（上図の２つの図の赤丸部分）<br>


次に、一般的な交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38348878-5e50b440-38df-11e8-9639-131d0053a0f9.png) のナッシュ交渉解が、どのようにして一意に定まるのか見てみる。<br>

![image](https://user-images.githubusercontent.com/25688193/38349620-e2b1e904-38e2-11e8-9814-6c6492457919.png)<br>

- 今、実現可能集合 U は、凸集合なので、<br>
    この集合を含むパレート最適な境界線（赤線部分）を含む多面体 S からなる交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38350387-0c634830-38e6-11e8-961e-90621356f19c.png) を構成出来る。<br>
    （公理４より、交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38350420-266907a6-38e6-11e8-856a-471abd887268.png) と交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38350435-36a3bde6-38e6-11e8-9839-455d5b9d2038.png) は等しい。）<br>
- 先に見たように、交渉領域が直線（赤線部分）で与えられる交渉問題は、ただ１つのナッシュ交渉解 ![image](https://user-images.githubusercontent.com/25688193/38350495-7b2722a0-38e6-11e8-8002-3e290987c8aa.png) をもつ。<br>
- 交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38350420-266907a6-38e6-11e8-856a-471abd887268.png) と交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38350435-36a3bde6-38e6-11e8-9839-455d5b9d2038.png) は等しいので、<br>
    この S でのナッシュ交渉解 ![image](https://user-images.githubusercontent.com/25688193/38350495-7b2722a0-38e6-11e8-8002-3e290987c8aa.png) は、U でのナッシュ交渉解にもなる。<br>
- 更に、ナッシュ交渉解の定義にあるナッシュ積は、d=0 のとき、![image](https://user-images.githubusercontent.com/25688193/38350604-f5165f68-38e6-11e8-89c6-0f5d485ac8d9.png) という双曲線になるが、<br>
	これはパレート最適な直線（赤線部分）と点 ![image](https://user-images.githubusercontent.com/25688193/38350495-7b2722a0-38e6-11e8-8002-3e290987c8aa.png) で接する。<br>
    （＝双曲線の傾きが ![image](https://user-images.githubusercontent.com/25688193/38350627-0cfc0b78-38e7-11e8-95d9-57b8f7ea9532.png) となるため）<br>
	これは、点 ![image](https://user-images.githubusercontent.com/25688193/38350495-7b2722a0-38e6-11e8-8002-3e290987c8aa.png) が、交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38350420-266907a6-38e6-11e8-856a-471abd887268.png) の交渉領域上で、２人のプレイヤーのナッシュ積 ![image](https://user-images.githubusercontent.com/25688193/38350646-267c5f08-38e7-11e8-8963-2573ab3f6ae4.png) を最大化する点であることを意味しており、その意味でも、点 ![image](https://user-images.githubusercontent.com/25688193/38350495-7b2722a0-38e6-11e8-8002-3e290987c8aa.png) が、ナッシュ交渉解となることが分かる。<br>


<br>

---

<a id="ID_1-8-3"></a>

### ◎ 非協力交渉モデル１（要求ゲーム）
先の議論で、公理論的アプローチによって導出した、ナッシュ交渉解が、<br>
交渉におけるプレイヤーの戦略的な利得最大化の帰結として説明出来る。<br>
ここでは、このナッシュによる非協力交渉モデルを見ていく。<br>

交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38351383-24c359a2-38ea-11e8-97f3-0658daabcbf4.png) を考える。<br>
このとき、ナッシュ交渉解の公理３（効用の正１次変換）より、<br>
この問題の一般性を失うことなく d=0 とすることが出来る。<br>

以下では、議論を単純化するために、（交渉問題の定義の条件に加えて）以下の２つの仮定が成り立つものとする。<br>

![image](https://user-images.githubusercontent.com/25688193/38356549-fcaef906-38fa-11e8-9e64-8e4c5a8b0abd.png)<br>

２つ目の仮定の行う前に、以下のような最大利得ベクトル m を定義する。<br>
実現可能集合 U の個人合理性を満たすような利得ベクトルの内、プレイヤー i の最大利得を、以下のように定義する。<br>
![image](https://user-images.githubusercontent.com/25688193/38356634-378df55e-38fb-11e8-9851-df9136bf65ef.png)<br>

![image](https://user-images.githubusercontent.com/25688193/38354541-f6af67da-38f4-11e8-9525-3b8e24cb5876.png)<br>

（交渉問題の定義の条件に加えて）この２つの仮定を満たすような、交渉問題 ![image](https://user-images.githubusercontent.com/25688193/38354585-161a0242-38f5-11e8-9a62-22fc13d3f32d.png) の例は、以下の図のようになる。<br>

![image](https://user-images.githubusercontent.com/25688193/38358138-6d2681d2-38ff-11e8-8a57-0f015498dd45.png)<br>

<br>

<!----------------------------------------------------------->

これらの仮定を元に、交渉の非協力２人ゲームを定式化する。<br>

- プレイヤー i の戦略集合 ![image](https://user-images.githubusercontent.com/25688193/38362213-f7c49d28-390a-11e8-87ae-8749bbfdab74.png) は、非負な実数全体 ![image](https://user-images.githubusercontent.com/25688193/38362326-5b73978e-390b-11e8-9940-fb7ed921ca17.png) となる。
- プレイヤー i の利得関数は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38362367-89a03ebe-390b-11e8-8247-119b7896335c.png)<br>
    で定義され、<br>
	このときの、プレイヤー i の戦略 ![image](https://user-images.githubusercontent.com/25688193/38362531-20f9e184-390c-11e8-9d36-a151879d7922.png) を、プレイヤー i の利得の要求額という。<br>
- ゲームは以下のようにプレイ（ナッシュの要求ゲーム）される。<br>
    1. ２人のプレイヤーが、同時に利得の要求額 x_i  を提示する。<br>
    2. もし、要求の組 ![image](https://user-images.githubusercontent.com/25688193/38362706-caef66b4-390c-11e8-8ca8-ff39207e9855.png) が実現可能であれば、プレイヤーはそれぞれ要求した利得を得る。<br>
    3. もし、要求の組 ![image](https://user-images.githubusercontent.com/25688193/38362706-caef66b4-390c-11e8-8ca8-ff39207e9855.png) が実現可能でないならば、交渉は決裂し、各々の利得は 0 になってしまう。<br>

このように、交渉領域と要求ゲームにおけるナッシュ均衡点が同じになるので、<br>
わざわざ、要求ゲームのモデルを用いて、交渉問題を解析することは、あまり意味のないことのように思える。<br>

しかしながら、**要求ゲームの利得関数 ![image](https://user-images.githubusercontent.com/25688193/38363847-2fadf7c4-3911-11e8-8d05-216f5101c74e.png) を微分可能となるように微小に変化させれば、（＝変動関数）**<br>
**ナッシュ交渉解が、要求ゲームの唯一のナッシュ均衡点として生じることが示されている。**（後述）<br>
このアプローチを、微分近似アプローチという。<br>

<br>

<!----------------------------------------------------------->

次に、この近似アプローチについて見ていく。<br>

ナッシュの要求ゲームの利得関数 ![image](https://user-images.githubusercontent.com/25688193/38379716-8b420438-393c-11e8-9b3b-13d10800cfd3.png) は、その定義<br>
![image](https://user-images.githubusercontent.com/25688193/38379737-a1fbd668-393c-11e8-83ce-72ce5cad95cc.png)<br>
から分かるように、実現可能集合 U の境界で不連続である。（＝微分不可能）<br>
従って、微分可能になるように、微分可能な関数で近似することを考える。<br>

- ![image](https://user-images.githubusercontent.com/25688193/38379788-c907cc80-393c-11e8-933d-2e86f0e88fe7.png) : プレイヤーの要求の組 ![image](https://user-images.githubusercontent.com/25688193/38379818-db31af3e-393c-11e8-83f9-f16a13e22fb7.png) が実現可能である確率<br>
    この確率 ![image](https://user-images.githubusercontent.com/25688193/38379788-c907cc80-393c-11e8-933d-2e86f0e88fe7.png) は、以下の条件を満たす。<br>
    - ![image](https://user-images.githubusercontent.com/25688193/38379868-08b7265a-393d-11e8-8880-5ea0e86737a8.png) から区間 [0, 1] への微分可能な関数で、<br>
    実現可能集合 U 上で ![image](https://user-images.githubusercontent.com/25688193/38379899-1cc540be-393d-11e8-8817-5668cf46a5af.png) となる。<br>

要求の組 ![image](https://user-images.githubusercontent.com/25688193/38379929-3722e07e-393d-11e8-93a8-7db039dbb29e.png) に対して、プレイヤー i の期待利得は、<br>
![image](https://user-images.githubusercontent.com/25688193/38379970-5a41cf20-393d-11e8-8dda-fdcafe44bc0a.png)<br>
で与えられる。（値とその確率分布の積）<br>

要求ゲームの元の利得関数 ![image](https://user-images.githubusercontent.com/25688193/38379716-8b420438-393c-11e8-9b3b-13d10800cfd3.png) では、<br>
プレイヤーの要求の組 ![image](https://user-images.githubusercontent.com/25688193/38379818-db31af3e-393c-11e8-83f9-f16a13e22fb7.png) が実現可能集合 U の外に僅かでも外れれば、合意は成立せず、<br>
結果、プレイヤーの利得は 0 になってしまう。<br>

一方、変動ゲーム ![image](https://user-images.githubusercontent.com/25688193/38379716-8b420438-393c-11e8-9b3b-13d10800cfd3.png) では、このような場合（＝実現可能集合外部に外れる）でも、<br>
正の確率で、合意が成立する可能性が存在する。<br>

この変動ゲームは、プレイヤーが互いの効用関数について少しだけ不確実である場合や、<br>
交渉の物理的条件・制度的条件に、僅かな不確実さが存在するような状況を記述している。<br>
これにより、例えば、100 万円の分配交渉で分配総額が 101 万円になってしまう可能性などが発生する。<br>

![image](https://user-images.githubusercontent.com/25688193/38417284-ad81a184-39d2-11e8-861d-38ea408d8d7b.png)<br>

![image](https://user-images.githubusercontent.com/25688193/38417148-2fdd9e4a-39d2-11e8-8b11-4fa8d0f2b46f.png)<br>

> 記載中...

<br>

---

<a id="ID_1-8-4"></a>

### ◎ 非協力交渉モデル２（提案応答ゲーム）
現実の多くの交渉では、合意が実現するまで、提案と応答が繰り返されることが多い。<br>
このような挙動をモデルに取り込んだのが、ルービンシュタインによる非協力交渉モデルである。<br>
このモデルでは、プレイヤーの**時間選好 [time preference]** が合意の実現に、重要な役割を果たす。<br>

以下、その詳細を見ていく。<br>

- 今、２人のプレイヤー１，２が、一定の金額 M の配分について交渉するケースを考える。<br>
    （議論の簡単のため、M=1 とおく。）<br>
- 交渉の実現可能な分配の集合を、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38431683-fb23519e-39ff-11e8-80d7-052dadc6eccc.png)<br>
    とする。（ ![image](https://user-images.githubusercontent.com/25688193/38431698-0f3e4a30-3a00-11e8-929d-b018a9529c1e.png) は、プレイヤー i の分配額）<br>
- 分配に関して合意がなされなければ、各々の分配額は 0 となる。<br>

そして、以下のようなルールでゲームプレイされる。<br>

1. ラウンド１<br>
    まず始めに、プレイヤー１が分配 ![image](https://user-images.githubusercontent.com/25688193/38431762-4c2e97d8-3a00-11e8-8d6c-227ee90f1513.png) を提案する。<br>
	次に、プレイヤー２が提案 ![image](https://user-images.githubusercontent.com/25688193/38431803-755f6c4a-3a00-11e8-9420-10b7269900ff.png) を受け入れるか否か決定する。<br>
	もしプレイヤー２が提案を受け入れると、ゲームは終了し、提案 ![image](https://user-images.githubusercontent.com/25688193/38431803-755f6c4a-3a00-11e8-9420-10b7269900ff.png) が合意される。<br>
    もしプレイヤー２が提案を拒否すると、ゲームは次のラウンドに進むことになる。<br>

2. ラウンド２<br>
	プレイヤー２が、分配 ![image](https://user-images.githubusercontent.com/25688193/38431962-f0a46b1c-3a00-11e8-9cee-e780bf57a4bc.png) を提案する。<br>
	プレイヤー１が、その提案を受け入れるか否か決定する。<br>
	もしプレイヤー１が提案を受け入れると、ゲームは終了し、提案 ![image](https://user-images.githubusercontent.com/25688193/38431987-029a7e74-3a01-11e8-93e1-5bd04637930f.png) が合意される。<br>
	もしプレイヤー１が提案を拒否すると、ゲームは次のラウンドに進むことになる。<br>
    以降、同様のルールが適用されていく。<br>

3. 交渉では、合意が実現するまで、プレイヤー１，２が提案を繰り返す。<br>
    奇数ラウンドでは、プレイヤー１が提案し、偶数ラウンドでは、プレイヤー２が提案する。<br>

このゲームは、提案応答ゲームと呼ばれ、ゲームの木が無限の長さをもつ完全情報ゲームとして定式化される。<br>

![image](https://user-images.githubusercontent.com/25688193/38452274-b776d6a6-3a7b-11e8-9730-a1ea77b9ff7c.png)<br>

以下、この提案応答ゲーム Γ を定式化する。<br>

- この提案応答ゲーム Γ の起こりうる結果の全体は、![image](https://user-images.githubusercontent.com/25688193/38452510-9473a49a-3a80-11e8-8a59-00aa48d9d968.png) と書ける。<br>
    （d : 合意が実現しないという結果、T : 自然数）<br>

- そして、プレイヤー i は、ゲームの結果に対して、以下のような効用関数 ![image](https://user-images.githubusercontent.com/25688193/38452520-b2361968-3a80-11e8-91dd-21073e0d929e.png) をもつとする。<br>
    ![image](https://user-images.githubusercontent.com/25688193/38452529-e177f3d6-3a80-11e8-85cb-d1c54b71d5e0.png)<br>

- また、この提案応答ゲーム Γ における、プレイヤーの純戦略は、以下のように定義出来る。<br>
    - プレイヤー１の戦略 ![image](https://user-images.githubusercontent.com/25688193/38452533-046847b0-3a81-11e8-819f-b228a9dd2dbd.png) は、関数列 ![image](https://user-images.githubusercontent.com/25688193/38452537-19acfeae-3a81-11e8-9257-9d5eababb3c9.png) で、<br>
        1. ラウンド t が奇数の場合、![image](https://user-images.githubusercontent.com/25688193/38452541-378dc282-3a81-11e8-9f06-221b06f12cb4.png)<br>
        ![image](https://user-images.githubusercontent.com/25688193/38452550-644f7540-3a81-11e8-9f4f-8558fca65c0a.png) は、実現可能集合 X の (t-1) 個の直積集合で、ラウンド t 以前に拒否された提案の全体である。<br>
        これは、また、提案応答ゲームのルールより、ラウンド t 以前のゲームプレイの履歴の集合となる。<br>
        2. ラウンド t が偶数の場合、![image](https://user-images.githubusercontent.com/25688193/38452571-c88b8512-3a81-11e8-9df0-0fabe51f64d0.png)<br>

    - プレイヤー２の戦略 ![image](https://user-images.githubusercontent.com/25688193/38452682-e358277c-3a83-11e8-8c32-813c23402a81.png) は、関数列 ![image](https://user-images.githubusercontent.com/25688193/38452686-f7b5c04e-3a83-11e8-88c8-2ace4f232297.png) で、<br>
        1. ラウンド t が奇数の場合、![image](https://user-images.githubusercontent.com/25688193/38452693-23fb8102-3a84-11e8-9ccd-572f824c2a24.png)<br>
        2. ラウンド t が偶数の場合、![image](https://user-images.githubusercontent.com/25688193/38452700-35389e96-3a84-11e8-8578-0eba8da226ea.png)<br>

- そして、このプレイヤーの戦略の組 ![image](https://user-images.githubusercontent.com/25688193/38454215-f560e976-3a9d-11e8-9c3d-4abc516fef01.png) に対して、ゲームの結果（＝分配）![image](https://user-images.githubusercontent.com/25688193/38454218-0a829b60-3a9e-11e8-8ea6-cc97226d15aa.png) が一意に定まる。<br>
    このとき、戦略の組 ![image](https://user-images.githubusercontent.com/25688193/38454215-f560e976-3a9d-11e8-9c3d-4abc516fef01.png) に対するプレイヤー i の利得は、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38454229-3641d3d8-3a9e-11e8-80e3-79a31b13e511.png)<br>
    で定義出来る。<br>

この提案応答ゲームに対して、以下のナッシュ均衡点に関する定理が成り立つ。<br>

![image](https://user-images.githubusercontent.com/25688193/38464032-a8463a84-3b41-11e8-85fb-9d8b38b5feb6.png)<br>

この定理は、全てのパレート最適な利得ベクトルが、<br>
提案応答ゲームにおけるナッシュ均衡点として実現されることを示している。<br>

これは、前述の要求ゲームにおけるナッシュ均衡点の結論と同じであるが、<br>
要求ゲームとは異なり、提案応答ゲームでは、部分ゲーム完全均衡点が一意に存在し、<br>
更に、将来利得に対する割引因子 δ が１に近づくにつれて、ナッシュ均衡点の利得ベクトルは、ナッシュ交渉解に収束する。<br>

![image](https://user-images.githubusercontent.com/25688193/38540336-9c3b0418-3cd6-11e8-9b43-e75a04b331ea.png)<br>

この提案応答ゲームにおける部分ゲーム完全均衡点では、<br>
最初のラウンドで合意が実現し、その際の利得分配は、（この定理の条件１にあるように）<br>
![image](https://user-images.githubusercontent.com/25688193/38542897-0c2654f6-3cde-11e8-8bb6-fb34acec0a6b.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38542938-22da612e-3cde-11e8-9f8a-2b14084cb488.png)<br>
によって特徴づけられる。<br>

つまり、提案者は応答者に対し、<br>
次のラウンド以降の交渉で得られる割引利得（ ![image](https://user-images.githubusercontent.com/25688193/38543081-8b71461c-3cde-11e8-8c4c-cc64b359b801.png) ）と等しい利得を提案する。<br>
（即ち、定理の条件１の関係式：![image](https://user-images.githubusercontent.com/25688193/38543129-b04565ea-3cde-11e8-9a52-86eb033bd5f7.png) ）<br>
これは、言い換えると、<br>
利得配分は、応答者にとって、受諾と拒否が無差別になるレベルで合意されることを意味している。<br>

特に、２人のプレイヤーが同じ割引因子をもつとき、（![image](https://user-images.githubusercontent.com/25688193/38543369-5e40e638-3cdf-11e8-9862-81722ab26582.png)）<br>
利得配分の式は、<br>
![image](https://user-images.githubusercontent.com/25688193/38543393-6eaf054a-3cdf-11e8-9fd7-253b018a509d.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38543440-80c2beca-3cdf-11e8-802c-8b687a0b5c85.png)<br>
となる。<br>

![image](https://user-images.githubusercontent.com/25688193/38543487-99513eda-3cdf-11e8-8dde-009ce26b6a3c.png)<br>

ここで、プレイヤー１の提案 ![image](https://user-images.githubusercontent.com/25688193/38547645-92a33ede-3cea-11e8-993a-50691d9e58e0.png) とプレイヤー２の提案 ![image](https://user-images.githubusercontent.com/25688193/38547674-a8c6adb8-3cea-11e8-8b44-2bf38dc9e97f.png) は、<br>
同じナッシュ積 ![image](https://user-images.githubusercontent.com/25688193/38547701-bdb5aa76-3cea-11e8-98b5-99e05d4c51e0.png) をもち、<br>
利得配分は、提案者側に有利になる。（上図参照）<br>

そして、プレイヤー１と２の割引因子 δ が限りなく１に近い時、<br>
２人の提案 ![image](https://user-images.githubusercontent.com/25688193/38547747-ddee0216-3cea-11e8-843b-b79ed9ef9632.png) は、ナッシュ交渉解 ![image](https://user-images.githubusercontent.com/25688193/38547771-f0f5a652-3cea-11e8-80c4-636380d99f1e.png) に近づく。<br>


<br>

---

<a id="ID_1-10"></a>

## ■ 進化ゲーム [evolutionary game]

これまで見てきたゲームのモデルは、<br>
プレイヤーが完全に合理的な意思決定主体であることを前提としてモデルを構築してきた。<br>
これは、本来不合理さを持ち合わせるはずである意思決定主体を、完全に合理的であると仮定することによって、<br>
モデルの構築を単純化出来るが故であるとも言える。<br>

しかしながら、このようなモデルでは、現実の行動をうまく説明出来ないようなケースも多々存在する。<br>
（チェーンストアパラドックス、有限回繰り返し囚人のジレンマ等）<br>
そこで、理想的な完全な合理性を前提としない、限定合理性 [bounded rationally] の元で、<br>
モデルを構築することが考えられる。<br>

このような限定合理性によるアプローチの枠組みとして、<br>
行動の動的（ダイナミック）なプロセスを解析するアプローチ（進化ゲーム）がある。<br>

<br>

<!------------------------------------------------------------------------->

この進化ゲームの考えは、元々、生物学での生物進化、生物社会ゲームの考えに由来する。<br>
この生物進化、生物社会ゲームの基本的な考えは、以下のようなものである。<br>

- ある単一の種から構成される大規模集団（母集団）を考える。<br>
- この生物社会ゲームにおけるプレイヤーに相当する個体は、様々な行動様式や形態を表現する表現型によってモデル化される。<br>
    例えば、ある種のオスは、互いにの縄張り争いにおいて、<br>
    相手が傷つくまで争う（タカ戦略）、或いは、儀式的な威嚇によって決着を図ろうとする（ハト戦略）<br>
    の２つの異なる行動様式を取りうる。<br>
- そして、遺伝により、親から子へ行動様式が継承される。<br>
- このような集団内で、ランダムに選択された２つの行動様式が対戦する。<br>
	この対戦における勝者は、（縄張りの支配等の理由により、）より多くの子孫を残すことが出来る。<br>
- このとき、次世代に残せる子の係数の期待値としての、個体の適応度なるものを定義出来る。<br>
- 多数の生物個体がランダムに相互作用を繰り返す系において、<br>
	適応度の高い個体（及びその子孫）の数が増加し、<br>
	逆に、適応度の低い個体（及びその子孫）の数が減少すると考えられる。（＝自然選択、自然淘汰）<br>
- このような自然淘汰の効果により、集団を構成する各表現型をもつ個体の割合は、時間とおもに動的に変化する。<br>
	その際、長期的な時間経過で、どのような個体の割合の分布が、定常状態となるかを解析することが、<br>
	このダイナミクスの性質を知る上で、重要となる。<br>
- より詳細には、全ての個体が同じ行動を選択しており、定常状態にある系において、<br>
	外部から、突然変異によって生じた、異なる行動をもつ個体が侵入してきた時に、<br>
	集団内での個体の分布がどのように変化するか？<br>
	とりわけ、侵入してきた異種個体が集団内で増加し続けるか否か？という問題が重要となる。<br>
- このような観点から、定常状態にある系において、<br>
	集団に僅かな比率で突然変異が生じても、それが増加せず元の定常状態が維持される時、<br>
	この定常状態は、**”進化的に安定 [evolutionarily stable]”** であるという。<br>

<br>

<!------------------------------------------------------------------------->

この生物学における生物進化の考えを、ゲーム理論に適用することを考える。<br>
この際、以下のようなポイントが重要となる。<br>

- 生物進化における個体は、合理的に選択を行う意思決定主体ではないものの、<br>
	適応度の低い個体は、自然淘汰により淘汰されるため、<br>
	形式的に、親から遺伝される行動様式（＝表現型）をゲームのプレイヤーとみなし、<br>
	合理的選択（＝利得最大化）を自然淘汰に置き換えることにより、<br>
	ゲーム理論における戦略形２人ゲームのモデルが、生物進化ゲームにも適用可能となる。（＝進化ゲーム）<br>
- このような進化ゲームにおいて、ナッシュ均衡点の概念より強い均衡点の概念となる、<br>
	突然変異が侵入出来ない進化的に安定した状態を表す、**”進化的に安定な戦略 [ESS : evolutionarity stable strategy]”** <br>
	を定義出来る。（後述）<br>
- 又、この進化ゲームの観点から、意思決定主体の合理的行動を規定する概念であるナッシュ均衡点を、<br>
	合理性の前提を必要としない、**集団均衡 [population equilibrium]** として再解釈でき、<br>
	更に、その動学的基礎を与えるモデルが与えられる。<br>
	
	- この集団均衡の概念は、より詳細には、以下のようになる。<br>
		生物進化と同様に、大規模集団内でランダムに遭遇したプレイヤーによってゲームがプレイされ、<br>
		長期間同じゲームが繰り返されるようなゲーム的状況を想定する。<br>
		又、各プレイヤーはゲームのルールに関して、完全な共有知識をもつことを前提としない。<br>
		（＝必ずしも完全な共有知識をもつとは限らない）<br>
		そして、集団の中で、より大きな利得を得た戦略の比率が増加するような戦略の選択の力が作用しているものとする。<br>
		このような集団内での安定状態では、集団内で正の割合で存在する戦略の利得は等しくなるはずであり、<br>
		更に、これらの戦略より成功的（高い利得の）他の戦略は存在しないと考えられる。<br>
		（定常状態なので、ある一定の安定した状態となっていると考えられるため）<br>
        この性質は、まさにナッシュ均衡点の性質である。<br>

<br>

---

<a id="ID_1-10-1"></a>

### ◎ 進化的に安定な戦略 [ESS : evolutionaly stable strategy]

先の生物進化ゲームの進化ゲームへの適用で見たように、進化ゲームの基本的なモデルは、戦略形２人対称ゲームとなる。<br>
（対称ゲームである理由は、進化ゲームでは大規模母集団からランダムに選ばれたプレイヤーを想定するが、<br>
これらのプレイヤーが同じ母集団から選ばれたプレイヤーであり、それらの相互作用を考えるためである。）<br>

- ![image](https://user-images.githubusercontent.com/25688193/38610700-9aaf54dc-3dbc-11e8-9b21-2941fccfa308.png) : 戦略形２人ゲーム<br>
    - この戦略形２人ゲームが対称である（対称ゲーム）とは、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38610780-d5b19fe0-3dbc-11e8-924a-53aea9eb63c9.png) であり、全ての ![image](https://user-images.githubusercontent.com/25688193/38610801-e70fbbf0-3dbc-11e8-83af-395649e986a7.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38610855-0f159c0a-3dbd-11e8-9947-0049b6457a78.png)<br>
    が成り立つときのことを言う。<br>

- ![image](https://user-images.githubusercontent.com/25688193/38610880-27e69522-3dbd-11e8-8ef3-76a8c9234a9f.png) : プレイヤー i(=1,2) の純戦略の集合 {1,2,...,n}

- ![image](https://user-images.githubusercontent.com/25688193/38610919-45ce53ea-3dbd-11e8-91bf-f72e30aaf52e.png) : プレイヤー i の利得関数で、![image](https://user-images.githubusercontent.com/25688193/38610974-6f3920d4-3dbd-11e8-85ab-383f948b215b.png) 上の実数値関数。<br>
    対称ゲームでは、利得の対称性が故に、プレイヤー番号は意味を持たなくなるので、<br>
    インデックス i を除外した ![image](https://user-images.githubusercontent.com/25688193/38611229-1720c284-3dbe-11e8-9b8e-6129f96f4e98.png) で表記する。<br>

- ![image](https://user-images.githubusercontent.com/25688193/38612844-eb23688a-3dc2-11e8-94e9-1f84bd7086f7.png) : プレイヤーの混合戦略。<br>
    このプレイヤーの混合戦略 p は、純戦略の集合 S 上の確率分布であり、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38612872-fc1d4d22-3dc2-11e8-9163-c9f6237a8d0f.png)<br>
    又、プレイヤー全体の混合戦略 p の集合を ![image](https://user-images.githubusercontent.com/25688193/38612911-1b4e117c-3dc3-11e8-9bbb-eb434de0195b.png)（ n−1 の意味？）とする。<br>

    ここで、進化ゲームにおける混合戦略は、以下の２つの解釈が可能となる。<br>

    1. １つ目の解釈は、これまでと同様にして、<br>
		混合戦略を、純戦略（の組み合わせ）を確率的に選択する「１つの確率的な戦略」としてみなす。<br>
		この場合、母集団は単一の戦略から構成されるとみなせ、これを**単型 [monomorphic] 集団**という。<br>

    2. ２つ目の解釈は、１つの混合戦略は、母集団内で各純戦略 i (=1,2,...,n) を採用するプレイヤーが、<br>
		割合（確率分布）![image](https://user-images.githubusercontent.com/25688193/38613018-73ff9dfe-3dc3-11e8-933e-4cae9377db8e.png)で分布している状態を表しているとみなす。<br>
		この場合、母集団は複数の戦略から構成され、これを**多型 [polymorphic] 集団**という。<br>

- ![image](https://user-images.githubusercontent.com/25688193/38613067-a607526a-3dc3-11e8-9269-da54af140934.png) : ２つの混合戦略 p と q が対戦したときの、混合戦略 p の期待利得。<br>
	これは、任意の ![image](https://user-images.githubusercontent.com/25688193/38613087-b6334bee-3dc3-11e8-8af2-010e735df7bf.png) と ![image](https://user-images.githubusercontent.com/25688193/38613112-c9a116b6-3dc3-11e8-885d-0871887abfbd.png) に対して、<br>
	![image](https://user-images.githubusercontent.com/25688193/38613136-dfe5bf12-3dc3-11e8-8875-75359ce39aa7.png)<br>
    と書ける。<br>

<br>

<!------------------------------------------------------------------------->

混合戦略 p のみからなる単型集団を考える。<br>
今、混合戦略 p とは異なる混合戦略 q が、集団内に僅かな割合で侵入した結果、<br>
集団内における混合戦略 p, q の比が、1−ε :ε （ ε はゼロに十分近い正の値）になったとする。<br>

集団内で２人の戦略がランダムに出会って対戦する時、<br>
戦略 p は、確率 1−ε で同じ戦略 p と対戦することになり、確率 ε で戦略 q と対戦することになる。 <br>
従って、戦略 p の期待利得 F(p,q)  は、![image](https://user-images.githubusercontent.com/25688193/38619331-e667d84e-3dd6-11e8-9f64-703365766af5.png) で記述でき、<br>
戦略 q の期待利得 F(q,p)  は、![image](https://user-images.githubusercontent.com/25688193/38620640-ef266b0a-3dd9-11e8-9f01-8516282beab2.png) で記述できる。<br>
そして、（戦略 p の期待利得）≧（戦略 q の期待利得）の関係が成り立つならば、<br>
戦略 p のほうが、戦略 q よりも集団に適応しており、侵入した戦略 q の割合が、集団内で増加することはない挙動となる。<br>
この意味で、混合戦略 p からなる集団は、（異なる戦略の侵入に対して、）安定な集団である。<br>

以上の概念を、進化的に安定な戦略（ESS）として、以下のように定義する。<br>
![image](https://user-images.githubusercontent.com/25688193/38623154-dd7af44c-3ddf-11e8-8d3b-49c5b293f5f4.png)<br>

この進化的に安定な戦略（ESS）に対して、以下の定理が成り立つ。<br>
![image](https://user-images.githubusercontent.com/25688193/38629879-391ce11a-3df0-11e8-8a17-d7ce7870ad33.png)<br>

以下、この進化的に安定な戦略（ESS）を、進化生物学での基本的なゲームを例に、実際に解いてみる。<br>

（例）タカ-ハトゲーム [Hawk-Dove game]<br>
![image](https://user-images.githubusercontent.com/25688193/38630340-99d89c5a-3df1-11e8-9cb6-491add28352a.png)<br>

- 同じ集団からランダムに選ばれた２つの生物個体が、縄張りや餌などをめぐり対立するゲーム的状況を考える。<br>
- ２つの生物個体が、選択可能な純戦略は、タカ戦略（H）とハト戦略（D）である。<br>
- タカ戦略（H）は攻撃的な戦略であり、（この問題においては）相手が負傷するまで戦うような戦略である。<br>
- 一方、ハト戦略（D）は穏健な戦略であり、（この問題においては）双方が負傷するまでは戦わないような戦略である。<br>
- それぞれの生物個体が勝つ確率はランダムな 1/2 である。<br>
- 勝者は、資源の価値 V を独占することが出来る。<br>
- 敗者は、負傷し、負傷コスト C を支払うことになる。<br>

このようなタカハトゲームにおいて、進化的に安定な戦略（ESS）を探す。<br>

1. ![image](https://user-images.githubusercontent.com/25688193/38631322-63d1e3e8-3df4-11e8-8615-d9081f415670.png) のとき、タカ戦略 H は ESS であることを示す。<br>
	![image](https://user-images.githubusercontent.com/25688193/38631322-63d1e3e8-3df4-11e8-8615-d9081f415670.png) のとき、タカ戦略（H）がハト戦略（D）を弱く支配する。<br>
	従って、任意の ![image](https://user-images.githubusercontent.com/25688193/38657442-338b3132-3e5b-11e8-80ab-0c2e88b45dbc.png) に対して、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38657461-43bc2674-3e5b-11e8-825d-1df751e1eab5.png)<br>
	
	ESS の定義より、タカ戦略（H）は ESS であると言える。<br>

2. ![image](https://user-images.githubusercontent.com/25688193/38657480-6609ba20-3e5b-11e8-8670-80c744361a7e.png) のとき、<br>
	確率 ![image](https://user-images.githubusercontent.com/25688193/38657498-7c2bb650-3e5b-11e8-88b1-dba4b8b88994.png) でタカ戦略（H）をとり、確率 ![image](https://user-images.githubusercontent.com/25688193/38657509-8ea6095c-3e5b-11e8-9088-2f48c3989b81.png) でハト戦略（D）をとる混合戦略は、ESS であることを示す。<br>

	定理（ESSと進化の均衡条件、進化の安定条件）より、ESS はナッシュ均衡点でもある。<br>
	純戦略の組 (H,H) と (D,D) は、その利得行列よりナッシュ均衡点ではないので、<br>
	ある混合戦略 p がナッシュ均衡点となり、又、ESS でもあることになる。<br>
	今、この混合戦略 p を、<br>
    ![image](https://user-images.githubusercontent.com/25688193/38659264-c4f825a0-3e63-11e8-84f0-144047087efd.png)<br>
    とすると、（ ![image](https://user-images.githubusercontent.com/25688193/38659252-b2bdbd8c-3e63-11e8-983c-f3f2d605b880.png) : タカ戦略が選択される確率）<br>
    混合戦略のナッシュ均衡点の性質より、<br>
    <br>
	この ![image](https://user-images.githubusercontent.com/25688193/38659252-b2bdbd8c-3e63-11e8-983c-f3f2d605b880.png) は、V<C の関係より、![image](https://user-images.githubusercontent.com/25688193/38659300-ee09504a-3e63-11e8-9942-026ad66caf4f.png) となる。<br>
	従って、混合戦略 ![image](https://user-images.githubusercontent.com/25688193/38659352-2226ad00-3e64-11e8-8b1c-047d8ca377a2.png) は存在し、ESS である。<br>

<br>

<!----------------------------------------------------------------->

ESS と各均衡点の関係性に関する定理は、以下のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/38668353-ce5124e2-3e7e-11e8-8a6c-83309a731290.png)<br>

ESS の存在性に関する定理は、以下のようになる。<br>
![image](https://user-images.githubusercontent.com/25688193/38668423-e0e7cec6-3e7e-11e8-9cc4-d33efad1d8cd.png)<br>

先のタカハトゲームでは、ESS は存在したが、<br>
戦略形２人対称ゲーム（進化ゲーム）において、ESS は必ずしも存在するとは限らない。<br>
そのことを以下の例で示す。<br>

（例）じゃんけんゲーム<br>
![image](https://user-images.githubusercontent.com/25688193/38668509-0cf2491a-3e7f-11e8-8b10-3e7d0d038cd3.png)<br>

このゲームは、ただ１つのナッシュ均衡点 ![image](https://user-images.githubusercontent.com/25688193/38675601-44079036-3e93-11e8-9a9c-fd79d888d2c1.png) を持つ。<br>
この ![image](https://user-images.githubusercontent.com/25688193/38675668-6e3f46be-3e93-11e8-9473-c2c803b90248.png) と任意の ε に対して、<br>
![image](https://user-images.githubusercontent.com/25688193/38675702-8f91adfc-3e93-11e8-9f88-b3315c376e5d.png)<br>
つまり、ESS であるための条件 ![image](https://user-images.githubusercontent.com/25688193/38675760-cc701f9c-3e93-11e8-8dfa-a189f354840d.png) が成り立たないので、<br>
このゲームの ESS は存在しない。<br>

<br>

---

<a id="ID_1-10-2"></a>

### ◎ レプリケータ動学
先の ESS の概念は、母集団が単一の混合戦略から構成される単型集団から導入した。<br>
次に、各純戦略を採用するプレイヤーが、ある確率分布に従って分布しているような状態、<br>
即ち、母集団が複数の戦略から構成される多型集団から考える。<br>

今、各プレイヤーが、それぞれ１つの純戦略を採用している大規模集団（母集団）があったとする。<br>

- ![image](https://user-images.githubusercontent.com/25688193/38722580-4aab12c2-3f39-11e8-9838-88cbc170b5b7.png) : 集団内の純戦略 i の割合（確率）<br>

- ![image](https://user-images.githubusercontent.com/25688193/38722614-653d2c10-3f39-11e8-9063-97433fa61b9f.png) : 純戦略の確率分布<br>
    ![image](https://user-images.githubusercontent.com/25688193/38723429-00376aa8-3f3c-11e8-95e8-71c989b10874.png)<br>

- ![image](https://user-images.githubusercontent.com/25688193/38723487-360af73a-3f3c-11e8-90ce-6640c73b18e6.png) : 純戦略 i を採用するプレイヤーと、純戦略 j を採用するプレイヤーが対戦する時の利得。<br>
    A は成分 ![image](https://user-images.githubusercontent.com/25688193/38723514-49bb06e4-3f3c-11e8-9c3e-fe4023ebc17f.png) からなる n×n の利得行列<br>
    ![image](https://user-images.githubusercontent.com/25688193/38723555-653078aa-3f3c-11e8-909b-3302dfc49636.png)<br>

このときの、純戦略 i を採用するプレイヤーの期待利得は、<br>
![image](https://user-images.githubusercontent.com/25688193/38723584-8326f578-3f3c-11e8-861f-634dff9efc87.png)<br>

又、この集団での平均利得は、<br>
![image](https://user-images.githubusercontent.com/25688193/38726125-4605b62c-3f44-11e8-8b72-7654ad565ad8.png)<br>

プレイヤーの利得（適応度）は、（生物学からの観点に従うと）親の個体が次世代に残せる子の期待値とみなせる。<br>
すると、次世代で純戦略 i を採用するプレイヤーの個体数は、<br>
![image](https://user-images.githubusercontent.com/25688193/38726209-80c8c286-3f44-11e8-9f9e-2834299c5606.png)<br>

又、次世代での総個体数は、<br>
![image](https://user-images.githubusercontent.com/25688193/38726231-8e31d73c-3f44-11e8-8d83-e5f4be4a86ee.png)<br>

従って、次世代において純戦略 i を採用するプレイヤーの割合 ![image](https://user-images.githubusercontent.com/25688193/38726945-963dd9d8-3f46-11e8-9068-66cab20d6582.png) は、<br>
![image](https://user-images.githubusercontent.com/25688193/38726974-abf8c0bc-3f46-11e8-958c-bc07943c7f96.png)<br>
となる。<br>

よって、（集団が親世代から子世代に推移するときの）割合の変化は、<br>
![image](https://user-images.githubusercontent.com/25688193/38726996-bec67d38-3f46-11e8-8524-bcd170759ef9.png)<br>
であり、時間を連続的にして、上式の差分方程式を微分方程式に書き換えると、<br>
![image](https://user-images.githubusercontent.com/25688193/38727024-d214edac-3f46-11e8-8442-6487fe17c397.png)<br>

ここで、この微分方程式の動学的な性質は、分母の項を除外した式<br>
![image](https://user-images.githubusercontent.com/25688193/38727049-e3068ad0-3f46-11e8-826b-b9414fba1a7a.png)<br>

と変わらないので、この分母項を除外した式が、進化ゲームの基本的なモデルとして提案されている。<br>

これらの議論をまとめると、以下のような定義となる。<br>
![image](https://user-images.githubusercontent.com/25688193/38727098-06e09da6-3f47-11e8-8c49-82a13fe04834.png)<br>

<br>

<a id="ID_1-10-2-1"></a>

#### ☆ レプリケーターダイナミクスの解の性質
レプリケーターダイナミクスの解 x(t) の性質として、まず初めに、<br>
「ある世代で存在した純戦略は、将来に世代で完全に消滅することはない。<br>
（但し、時間の経過と共に、その割合が限りなく０に近づくことはありうる。）」<br>
ことを示す。<br>
![image](https://user-images.githubusercontent.com/25688193/38734904-2718bc64-3f62-11e8-9c82-997b57a1d561.png)<br>

次に、戦略形ゲーム２人対称ゲームにおけるナッシュ均衡点、ESS と、<br>
レプリケーター動学の定常状態（平衡点）の関係性に関する基本的な定理を見ていく。<br>
![image](https://user-images.githubusercontent.com/25688193/38734952-4c8bcab8-3f62-11e8-95cb-ea3c756ba647.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38734990-6bce8bd6-3f62-11e8-9c59-ce7683111a09.png)<br>

又、全ての純戦略 i に対して、<br>
戦略分布 ![image](https://user-images.githubusercontent.com/25688193/38735770-c6414bec-3f64-11e8-8fab-a5532d5e56b7.png) は、レプリケーター動学の平衡点でもある。<br>
そして、集団の全てのプレイヤーが同じ純戦略を選択するとき、異なる戦略の侵入がない限り、戦略分布は変化しない。<br>

<br>

<!-------------------------------------------------------------------------------->

レプリケーター動学の平衡点（定常状態）は、<br>
戦略形ゲーム２人対称ゲームにおけるナッシュ均衡点より弱く均衡点の概念となるが、<br>
以下の定理は、漸近安定な平衡点（平衡点が安定かつ t→∞で０に近づくような平衡点）は、<br>
ナッシュ均衡点より強い概念であることを示す。<br>
![image](https://user-images.githubusercontent.com/25688193/38736027-9c1d82f8-3f65-11e8-8c4a-d6acecb14fdd.png)<br>

レプリケーターダイナミクスにおける漸近安定な平衡点では、<br>
集団に外部から新しいプレイヤーが侵入し、集団の戦略分布が平衡点から僅かに変化しても、<br>
時間が経過すれば（t → ∞）、定常状態が復元される。<br>
上記定理は、このような漸近安定な平衡点が、ナッシュ均衡点であることを示している。<br>

<br>

<!-------------------------------------------------------------------------------->

更に、次の定理は、ESS のほうが漸近安定な平衡点よりも強い概念（より広義の概念）であることを示している。<br>
![image](https://user-images.githubusercontent.com/25688193/38757751-233436ae-3fa9-11e8-8907-1ba57ae86a8f.png)<br>

<br>

<a id="ID_1-10-2-2"></a>

#### ☆ レプリケーター・ダイナミクスの例

（例）タカ - ハトゲームのレプリケーター・ダイナミクス<br>
![image](https://user-images.githubusercontent.com/25688193/38765725-e94af762-4001-11e8-8df1-df5f59c6a6ad.png)<br>

先にも見たように、![image](https://user-images.githubusercontent.com/25688193/38765734-01d23e58-4002-11e8-8d01-68865aa103d3.png) のとき、<br>
確率 ![image](https://user-images.githubusercontent.com/25688193/38765742-2027bd9c-4002-11e8-89b0-7f56ebc6e2ed.png) でタカ戦略（H）をとり、確率 ![image](https://user-images.githubusercontent.com/25688193/38765749-30398454-4002-11e8-9c23-8147856b7d1d.png) でハト戦略（D）をとる混合戦略は、ESS である。<br>

今、集団内でタカ戦略（H）をとるプレイヤーの割合を ![image](https://user-images.githubusercontent.com/25688193/38765755-572108da-4002-11e8-83bb-b7a73fb76bde.png) とし、<br>
その戦略分布を ![image](https://user-images.githubusercontent.com/25688193/38769044-8c0fd744-4037-11e8-809c-566750598e0f.png) とすると、<br>
このゲームのレプリケーター・ダイナミクスは、以下の微分方程式で記述される。<br>
![image](https://user-images.githubusercontent.com/25688193/38765767-7ab0637c-4002-11e8-88a5-9923b8313272.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38766314-4781b330-400b-11e8-93d9-feab2a6fa238.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38766318-5b74f1d6-400b-11e8-865b-0372efcb7f17.png)<br>

従って、このレプリケーター・ダイナミクスは、<br>
３つの平衡点 ![image](https://user-images.githubusercontent.com/25688193/38766327-73ab0b50-400b-11e8-9f1b-b0628606f8f2.png) を持つことが分かる。<br>
ここで、![image](https://user-images.githubusercontent.com/25688193/38767234-a8af1af0-4018-11e8-892e-f62dcb5f68d7.png) のときは、![image](https://user-images.githubusercontent.com/25688193/38767238-bed95fca-4018-11e8-8ad3-f48a29913a86.png) であり、![image](https://user-images.githubusercontent.com/25688193/38767246-dfdf3032-4018-11e8-9da5-ee6a8c3d8115.png) のときは、![image](https://user-images.githubusercontent.com/25688193/38767262-0addc9c4-4019-11e8-9b76-42b4b47e0a3e.png) なので、<br>
３つの平衡点の内、![image](https://user-images.githubusercontent.com/25688193/38767272-217d684c-4019-11e8-9142-128c470070e2.png) のみが漸近安定な平衡点である。<br>

![image](https://user-images.githubusercontent.com/25688193/38769068-f09c76b8-4037-11e8-875c-a6e044552062.png)<br>

<br>

<!-------------------------------------------------------------------->

（例）じゃんけんゲームのレプリケーター・ダイナミクス<br>
![image](https://user-images.githubusercontent.com/25688193/38769034-5defbbea-4037-11e8-9477-4aead37df5ba.png)<br>

先に見たように、このゲームの唯一のナッシュ均衡点は、![image](https://user-images.githubusercontent.com/25688193/38769031-49354026-4037-11e8-8735-b002a78b8c3b.png) であり、ESS は存在しない。<br>

集団の戦略分布を ![image](https://user-images.githubusercontent.com/25688193/38769078-1a8e9afa-4038-11e8-811c-b2ee3c5c6c9e.png) とすると、<br>
レプリケーター・ダイナミクスの微分方程式<br>
![image](https://user-images.githubusercontent.com/25688193/38769083-3384b396-4038-11e8-9ee1-97ee212bfe62.png)<br>
の各項は、<br>
![image](https://user-images.githubusercontent.com/25688193/38769089-46ec9ee4-4038-11e8-9e59-651d2a25dcb2.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38769095-5773d958-4038-11e8-9b7e-445f6362a83b.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38769110-7aedd794-4038-11e8-8fef-fb18a3446c81.png)<br>
![image](https://user-images.githubusercontent.com/25688193/38769114-892f6958-4038-11e8-9aaf-e39bae41bace.png)<br>

よって、このゲームのレプリケーター・ダイナミクスは、以下の微分方程式になる。<br>
![image](https://user-images.githubusercontent.com/25688193/38769119-a092a510-4038-11e8-8c97-793e8bc56ea7.png)<br>

> 記載中...

<br>

---

<a name="参考文献"></a>

## 参考文献

- ゲーム理論入門 (日経文庫―経済学入門シリーズ)<br>
    - [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%B2%E3%83%BC%E3%83%A0%E7%90%86%E8%AB%96%E5%85%A5%E9%96%80-%E6%97%A5%E7%B5%8C%E6%96%87%E5%BA%AB%E2%80%95%E7%B5%8C%E6%B8%88%E5%AD%A6%E5%85%A5%E9%96%80%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-%E6%AD%A6%E8%97%A4-%E6%BB%8B%E5%A4%AB/dp/4532108292?SubscriptionId=AKIAIAVGBNTUU4E5P2DA&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4532108292)


---

以下、同様の文献（はてなブログ形式）

<!-- ゲーム理論入門 (日経文庫―経済学入門シリーズ) -->
[]
