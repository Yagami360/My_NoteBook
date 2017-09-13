# グラフ理論 [graph theory]

グラフ理論に関してのまとめたマイノートです。随時更新予定です。

This is my notebook that summarizes about "graph theory". I will add contents as needed.

> Twitterモーメント：https://twitter.com/i/moments/880663424799318016
![default](https://user-images.githubusercontent.com/25688193/30402306-4370f5de-9918-11e7-8e6d-5259edcd66d4.png)

## 項目 [Contents]

1. [概要、全体 MAP [Overview]](#ID_1)
1. [グラフ [Graph]](#ID_2)
    1. [グラフ [Graph] の概要](#ID_2-1)
    1. [グラフと頂点、辺、隣接関係](#ID_2-2)
        1. [（単純無向）グラフ [Undirected graph]](#ID_2-2-1)
        1. [頂点の隣接関係、頂点の次数](#ID_2-2-2)
    1. [グラフの幾何学的表現、概念](#ID_2-3)
        1. [グラフの同型 [isomorphic]](#ID_2-3-1)
        1. [有向グラフ [directed graph]](#ID_2-3-2)
        1. [多重グラフと有向多重グラフ](#ID_2-3-3)
        1. [ネットワーク](#ID_2-3-4)
    1. [グラフと隣接行列](#ID_2-4)
    1. [グラフ上のウォーク、パス、サイクルと連結グラフ](#ID_2-5)
        1. [ウォーク](#ID_2-5-1)
        1. [パス（道）](#ID_2-5-2)
        1. [サイクル](#ID_2-5-3)
        1. [連結、連結グラフ](#ID_2-5-4)
        1. [頂点間の距離](#ID_2-5-5)
        1. [ウォークの個数](#ID_2-5-6)
    1. [木構造](#ID_2-6)
        1. [根付き木](#ID_2-6-1)
        1. [２分木 [binary tree]](#ID_2-6-2)
1. [確率過程 [stochastic process]](#ID_3)
    1. [マルコフ連鎖 [markov chain]](#ID_3-1)
        1. [マルコフ連鎖の初期分布と定常分布](#ID_3-1-1)
        1. [マルコフ連鎖の定常性](#ID_3-1-2)
        1. [マルコフ連鎖の規約性](#ID_3-1-3)
        1. [マルコフ連鎖の過渡現象 [transient phenomena] の分類（再帰性、周期性）](#ID_3-1-4)
            1. [再帰性](#ID_3-1-4-1)
            1. [周期性 [cyclic, periodic]](#ID_3-1-4-2)
1. [グラフのスペクトル [spectral]（スペクトルグラフ理論）](#ID_4)
    1. [グラフの特性方程式 [characteristic equation]](#ID_4-1)
    1. [グラフのスペクトル　[Spectrum]](#ID_4-2)
        1. [グラフの同型とスペクトルの関係（スペクトルの同型問題）](#ID_4-2-1)
1. [参考文献](#参考文献)

- 追記予定項目
    - 確率過程
        - ボルツマンマシン [Boltzmann machine]
        - 確率微分方程式への展開
    - 巡回セールスマン問題
    - A* アルゴリズム
    - PageRank アルゴリズム

<a id="ID_1"></a>

## 概要、全体 MAP [Overview]
> 記載中...

<a id="ID_2"></a>

## グラフ [Graph]

<a id="ID_2-1"></a>

### グラフ [Graph] の概要
![twitter_ _ _1-1_170602](https://user-images.githubusercontent.com/25688193/29314190-ea3a24cc-81f7-11e7-943a-82614a44d551.png)

<a id="ID_2-2"></a>

### グラフと頂点、辺、隣接関係

<a id="ID_2-2-1"></a>

#### （単純無向）グラフ [Undirected graph]
![twitter_ _ _1-2_170602](https://user-images.githubusercontent.com/25688193/29314193-ea4e339a-81f7-11e7-9e38-fda3564e1a07.png)

<a id="ID_2-2-2"></a>

#### 頂点の隣接関係、頂点の次数
![twitter_ _ _1-3_170602](https://user-images.githubusercontent.com/25688193/29314191-ea3d593a-81f7-11e7-96bf-902241ec95f8.png)

<a id="ID_2-3"></a>

### グラフの幾何学的表現、概念

<a id="ID_2-3-1"></a>

#### グラフの同型 [isomorphic]
![twitter_ _ _1-4_170602](https://user-images.githubusercontent.com/25688193/29314194-ea4ebc34-81f7-11e7-8a75-2c5d7225f27a.png)

<a id="ID_2-3-2"></a>

#### 有向グラフ [directed graph]
![twitter_ _ _1-5_170603](https://user-images.githubusercontent.com/25688193/29314195-ea4f6b3e-81f7-11e7-85ab-62e112013a0b.png)

<a id="ID_2-3-3"></a>

#### 多重グラフと有向多重グラフ
![twitter_ _ _1-6_170603](https://user-images.githubusercontent.com/25688193/29314196-ea522932-81f7-11e7-991d-887205242540.png)

<a id="ID_2-3-4"></a>

#### ネットワーク
![twitter_ _ _1-7_170603](https://user-images.githubusercontent.com/25688193/29314197-ea5c6abe-81f7-11e7-86e6-e0a3d3cce1ee.png)

<a id="ID_2-4"></a>

### グラフと隣接行列
![twitter_ _ _1-8_170603](https://user-images.githubusercontent.com/25688193/29314198-ea608c8e-81f7-11e7-97fb-7dd56d797b40.png)
![twitter_ _ _1-9_170603](https://user-images.githubusercontent.com/25688193/29314199-ea70c6bc-81f7-11e7-991d-194728cbf613.png)

<a id="ID_2-5"></a>

### グラフ上のウォーク、パス、サイクルと連結グラフ
![image](https://user-images.githubusercontent.com/25688193/30403092-13c57d98-991b-11e7-977e-9734b94a181c.png)

<a id="ID_2-5-1"></a>

#### ウォーク
![image](https://user-images.githubusercontent.com/25688193/30403118-2c35ca72-991b-11e7-931d-bc0aec8d1bcd.png)

<a id="ID_2-5-2"></a>

#### パス（道）
![image](https://user-images.githubusercontent.com/25688193/30403161-523c8d0a-991b-11e7-86a2-f8b4ac356b40.png)

<a id="ID_2-5-3"></a>

#### サイクル
![image](https://user-images.githubusercontent.com/25688193/30403186-68b0e8c4-991b-11e7-91da-30f6ec17b5e3.png)

<a id="ID_2-5-4"></a>

#### 連結、連結グラフ
![twitter_ _ _2-2_170603](https://user-images.githubusercontent.com/25688193/29314201-ea75b5fa-81f7-11e7-9a2c-5d2d21140c88.png)

<a id="ID_2-5-5"></a>

#### 頂点間の距離
![twitter_ _ _2-3_170603](https://user-images.githubusercontent.com/25688193/29314202-ea760dac-81f7-11e7-8d39-2efc627b9f75.png)

<a id="ID_2-5-6"></a>

#### ウォークの個数
![twitter_ _ _2-4_170603](https://user-images.githubusercontent.com/25688193/29314203-ea813fb0-81f7-11e7-8f04-d9561b36b487.png)

<a id="ID_2-6"></a>

### 木構造
![twitter_ _ _3-1_170603](https://user-images.githubusercontent.com/25688193/29314204-ea83889c-81f7-11e7-91cc-09dd08ee09b1.png)

<a id="ID_2-6-1"></a>

#### 根付き木
![image](https://user-images.githubusercontent.com/25688193/30403506-ea202a5e-991c-11e7-9b88-63849ef0be25.png)

<a id="ID_2-6-2"></a>

#### ２分木 [binary tree]
![image](https://user-images.githubusercontent.com/25688193/30403538-1e56a730-991d-11e7-8469-dd632e38229d.png)



<a id="ID_3"></a>

## 確率過程 [stochastic process]
![twitter_ _ _4-1_170604](https://user-images.githubusercontent.com/25688193/29314206-ea9889ea-81f7-11e7-93ab-89e441c467b6.png)

<a id="ID_3-1"></a>

### マルコフ連鎖 [markov chain]
![twitter_ _ _4-2_170604](https://user-images.githubusercontent.com/25688193/29314208-ea9fe6fe-81f7-11e7-9340-70a03692766b.png)

<a id="ID_3-1-1"></a>

#### マルコフ連鎖の初期分布と定常分布
![twitter_ _ _4-3_170604](https://user-images.githubusercontent.com/25688193/29314207-ea9a505e-81f7-11e7-9175-94875928dcca.png)

<a id="ID_3-1-2"></a>

#### マルコフ連鎖の定常性
![twitter_ _ _4-4_170604](https://user-images.githubusercontent.com/25688193/29314209-eaa59e0a-81f7-11e7-9897-f23b11a5becf.png)
![twitter_ _ _4-5_170604](https://user-images.githubusercontent.com/25688193/29314210-eaa5ba98-81f7-11e7-97d1-cc22b231c1fb.png)

<a id="ID_3-1-3"></a>

#### マルコフ連鎖の規約性
![twitter_ _ _4-7_170605](https://user-images.githubusercontent.com/25688193/29314211-eab83790-81f7-11e7-9a1c-b0d437fff7b4.png)
![twitter_ _ _4-8_170605](https://user-images.githubusercontent.com/25688193/29314212-eab9fa9e-81f7-11e7-81b0-000d8f29dc4d.png)
![twitter_ _ _4-9_170606](https://user-images.githubusercontent.com/25688193/29314213-eabeda32-81f7-11e7-85ce-0f26113d15ca.png)

<a id="ID_3-1-4"></a>

#### マルコフ連鎖の過渡現象 [transient phenomena] の分類（再帰性、周期性）

<a id="ID_3-1-4-1"></a>

##### 再帰性
![twitter_ _ _4-10_170607](https://user-images.githubusercontent.com/25688193/29314214-eac70d7e-81f7-11e7-8999-5340e5751803.png)
![twitter_ _ _4-11_170607](https://user-images.githubusercontent.com/25688193/29314215-eac96128-81f7-11e7-9ba5-38031e41842e.png)

<a id="ID_3-1-4-2"></a>

##### 周期性 [cyclic, periodic]
![twitter_ _ _4-12_170607](https://user-images.githubusercontent.com/25688193/29314216-eaceafe8-81f7-11e7-9b78-cad7178720b1.png)


<a id="ID_4"></a>

## グラフのスペクトル [spectral]（スペクトルグラフ理論）
![image](https://user-images.githubusercontent.com/25688193/30403837-77e2c1c0-991e-11e7-9879-bd41fd0dc32e.png)

<a id="ID_4-1"></a>

### グラフの特性方程式 [characteristic equation]
![twitter_ _ _5-1_170607](https://user-images.githubusercontent.com/25688193/29314217-eadc1da4-81f7-11e7-9cd3-09e3cff5895e.png)
![twitter_ _ _5-2_170609](https://user-images.githubusercontent.com/25688193/29314218-eadc765a-81f7-11e7-8e24-e1ef6a30a8fb.png)
![image](https://user-images.githubusercontent.com/25688193/30403987-4a2bf110-991f-11e7-886f-f6e73a370b60.png)
![image](https://user-images.githubusercontent.com/25688193/30404009-60dc4c02-991f-11e7-9c4f-46f5d19074ec.png)

<a id="ID_4-2"></a>

### グラフのスペクトル　[Spectrum]
![twitter_ _ _5-3_170609](https://user-images.githubusercontent.com/25688193/29314219-eae2fe62-81f7-11e7-9290-b17a78cf93dd.png)
![twitter_ _ _5-4_170609](https://user-images.githubusercontent.com/25688193/29314220-eaeaceee-81f7-11e7-8694-9f8eef21b885.png)

<a id="ID_4-2-1"></a>

#### グラフの同型とスペクトルの関係（スペクトルの同型問題）
![image](https://user-images.githubusercontent.com/25688193/30404061-a7b40c5a-991f-11e7-8632-291ab3b15c56.png)






<a name="参考文献"></a>

## 参考文献
> 情報数理の基礎と応用 (ライブラリ情報学コア・テキスト) </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%83%85%E5%A0%B1%E6%95%B0%E7%90%86%E3%81%AE%E5%9F%BA%E7%A4%8E%E3%81%A8%E5%BF%9C%E7%94%A8-%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA%E6%83%85%E5%A0%B1%E5%AD%A6%E3%82%B3%E3%82%A2%E3%83%BB%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88-%E5%B0%BE%E7%95%91-%E4%BC%B8%E6%98%8E/dp/4781912109?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4781912109)</br>