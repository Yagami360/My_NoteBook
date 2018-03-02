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
    1. 展開形ゲーム [game in extensive form]
    1. 繰り返しゲーム
        1. 繰り返し囚人のジレンマ
        1. 繰り返しゲームのナッシュ均衡点に関する基本的な定理
    1. 進化ゲーム
        1. 進化的に安定な戦略 [ESS : evolutionaly stable strategy]
        1. 中立的に安定な戦略 [NSS : neutrally stable strategy]
    1. [xxx](#ID_1-x)
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

![image](https://user-images.githubusercontent.com/25688193/36353823-8491514a-150e-11e8-8287-ff63fc97d581.png)

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

![image](https://user-images.githubusercontent.com/25688193/36824205-8c83b1e8-1d44-11e8-9b88-c0ae6e27ed9c.png)

![image](https://user-images.githubusercontent.com/25688193/36824457-b96518a4-1d45-11e8-9d9a-ab66d1b45ef2.png)

![image](https://user-images.githubusercontent.com/25688193/36826790-221d1286-1d53-11e8-91a1-7739bfd70585.png)

![image](https://user-images.githubusercontent.com/25688193/36827068-9d5ee9c8-1d54-11e8-95c8-53daf731607d.png)

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

<!------------------------------------------------------------------>

<a id="ID_1-3-5-2"></a>

#### ☆ maxmin戦略, minmax戦略からのナッシュ均衡点の計算方法
次に、このゼロ和２人ゲームのナッシュ均衡点を maxmin戦略, minmax戦略から計算する。


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
