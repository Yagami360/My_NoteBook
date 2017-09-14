# 最適化問題 [optimization problem]（数理計画問題 [mathematical programming] ）

最適化問題、数理計画法に関してまとめたマイノートです。今後も随時追加予定です。

This is my notebook that summarizes about "Optimization problem". I will add contents as needed.

Twitterモーメント：https://twitter.com/i/moments/781974495905009664
![default](https://user-images.githubusercontent.com/25688193/29314342-9624ec36-81f8-11e7-91ed-aaa5eea15629.jpg)

## 項目 [Contents]
1. [概要 [Overview]、全体MAP図](#ID_1)
1. [凸最適化問題 [convex programing problem]](#ID_2)
    1. [凸集合 [convex set]](#ID_2-1)
    1. [凸関数 [convex function]](#ID_2-2)
        1. [（下に凸な）凸関数 [downward-convex function]](#ID_2-2-1)
        1. [（上に凸な）凸関数 [upward-convex function] 又は、凹関数[concave function]](#ID_2-2-2)
        1. [凸関数であることの条件、判定](#ID_2-2-3)
            1. [１次の条件 [first-order convexity condition]](#ID_2-2-3-1)
            1. [２次の条件 [second-order convexity condition]（凸関数が１変数の関数の場合）](#ID_2-2-3-2)
            1. [２次の条件 [second-order convexity condition]（凸関数が多変数の関数の場合）](#ID_2-2-3-3)
    1. [凸最適化問題（より詳細な説明）](#ID_2-3)
    1. [制約条件なしの 凸最適化問題 [unconstrained convex optimization]](#ID_2-4)
    1. [【補足】ラグランジュの未定乗数法 [the method of Largrange multipliers]](#ID_2-5)
        1. [ラグランジュの未定乗数法の直感的な意味](#ID_2-5-1)
        1. [ラグランジュの未定乗数法の意味（数式変換）](#ID_2-5-2)
    1. [等式制約付き 凸最適化問題 [constrained convex optimization]](#ID_2-6)
    1. [不等式制約付き 凸最適化問題 [unconstrained convex optimization]](#ID_2-7)
        1. [（ラグランジュ関数の）鞍点 [saddle point]](#ID_2-7-1)
        1. [最適解問題の主問題 [primal problem] と双方問題 [dual problem]](#ID_2-7-2)        
1. [参考文献](#参考文献)

- 追記予定項目
    - ２次最適化問題 [quadratic programming]
        - 凸二次最適化問題
    - 線型計画問題 [linear programming problem]
        - シンプレックス法 [simplex method]
    - 非線形計画法 [NLP : nonlinear programming]
    

<a id="ID_1"></a>

## 概要 [Overview]、全体MAP図
![twitter_ 1-1_160908](https://user-images.githubusercontent.com/25688193/29314346-99fdcfb2-81f8-11e7-9feb-901dc7c791f1.png)

全体MAP図
> 記載中...

<a id="ID_2"></a>

## 凸最適化問題 [convex programing problem]
![image](https://user-images.githubusercontent.com/25688193/30413506-5ec493b8-9959-11e7-94e6-b53a4b82f183.png)

<a id="ID_2-1"></a>

### 凸集合 [convex set]
![image](https://user-images.githubusercontent.com/25688193/30413527-8f0bfb92-9959-11e7-83d4-888d505b262a.png)

<a id="ID_2-2"></a>

### 凸関数 [convex function]
![image](https://user-images.githubusercontent.com/25688193/30413556-bb7c373c-9959-11e7-8939-49332cefa399.png)

<a id="ID_2-2-1"></a>

#### （下に凸な）凸関数 [downward-convex function]
![image](https://user-images.githubusercontent.com/25688193/30413588-e218c770-9959-11e7-9a12-f29f770ad0f5.png)

<a id="ID_2-2-2"></a>

#### （上に凸な）凸関数 [upward-convex function] 又は、凹関数[concave function]
![image](https://user-images.githubusercontent.com/25688193/30413606-f8273fa6-9959-11e7-8101-021b42342082.png)

<a id="ID_2-2-3"></a>

#### 凸関数であることの条件、判定

<a id="ID_2-2-3-1"></a>

##### １次の条件 [first-order convexity condition]
![image](https://user-images.githubusercontent.com/25688193/30413624-169eddfe-995a-11e7-9e97-fd3e99e58980.png)

<a id="ID_2-2-3-2"></a>

##### ２次の条件 [second-order convexity condition]（凸関数が１変数の関数の場合）
![image](https://user-images.githubusercontent.com/25688193/30413663-5a98204c-995a-11e7-9c6f-5d51b8b8fb28.png)
![image](https://user-images.githubusercontent.com/25688193/30413683-7b2e77ac-995a-11e7-8002-6fad3e733dd7.png)

<a id="ID_2-2-3-3"></a>

##### ２次の条件 [second-order convexity condition]（凸関数が多変数の関数の場合）
![twitter_ 4-1_160910](https://user-images.githubusercontent.com/25688193/29314351-9a3be82e-81f8-11e7-82db-6e113874b4ae.png)
![twitter_ 4-2_160910](https://user-images.githubusercontent.com/25688193/29314350-9a28b5c4-81f8-11e7-8cc4-7e2a368ca411.png)

<a id="ID_2-3"></a>

### 凸最適化問題（より詳細な説明）
![twitter_ 5-1_160910](https://user-images.githubusercontent.com/25688193/29314352-9a3c6772-81f8-11e7-8f17-434effd522a4.png)

<a id="ID_2-4"></a>

### 制約条件なしの 凸最適化問題 [unconstrained convex optimization]
![twitter_ 5-2_160910](https://user-images.githubusercontent.com/25688193/29314353-9a43aa0a-81f8-11e7-94d3-730a0efdec37.png)

<a id="ID_2-5"></a>

### 【補足】ラグランジュの未定乗数法 [the method of Largrange multipliers]
![twitter_ 6-1_160912](https://user-images.githubusercontent.com/25688193/29314356-9a4d9fce-81f8-11e7-9c2d-27ec34a70aff.png)

<a id="ID_2-5-1"></a>

#### ラグランジュの未定乗数法の直感的な意味
![twitter_ 6-2_160912](https://user-images.githubusercontent.com/25688193/29314354-9a4aeafe-81f8-11e7-9ac4-5866a3030b5f.png)

<a id="ID_2-5-2"></a>

#### ラグランジュの未定乗数法の意味（数式変換）
![twitter_ 6-3_160913](https://user-images.githubusercontent.com/25688193/29314355-9a4bda5e-81f8-11e7-9785-4f1d1b6be7fa.png)

<a id="ID_2-6"></a>

### 等式制約付き 凸最適化問題 [constrained convex optimization]
![twitter_ 7-1_160913](https://user-images.githubusercontent.com/25688193/29314358-9a612724-81f8-11e7-9875-36df68267f46.png)

<a id="ID_2-7"></a>

### 不等式制約付き 凸最適化問題 [unconstrained convex optimization]
![twitter_ 8-1_160914](https://user-images.githubusercontent.com/25688193/29314357-9a5fbdf8-81f8-11e7-8231-e7476731036d.png)

<a id="ID_2-7-1"></a>

#### （ラグランジュ関数の）鞍点 [saddle point]
![image](https://user-images.githubusercontent.com/25688193/30413821-6ba395fa-995b-11e7-8ff2-c93fcee7c316.png)

<a id="ID_2-7-2"></a>

#### 最適解問題の主問題 [primal problem] と双方問題 [dual problem]
![image](https://user-images.githubusercontent.com/25688193/30414028-83b1ca94-995c-11e7-8b56-c742a8911ec4.png)



<a name=参考文献></a>

## 参考文献

> はじめてのパターン認識 </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%81%AF%E3%81%98%E3%82%81%E3%81%A6%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E8%AA%8D%E8%AD%98-%E5%B9%B3%E4%BA%95-%E6%9C%89%E4%B8%89/dp/4627849710?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4627849710)</br>
