# 線形代数学 [linear algebra]

線形代数学に関してのマイノートです。今後も随時追加予定です。</br>
あまり厳密でないので数学科or出身者の方から見たら天下り的説明に見えるかと思いますがご了承ください。

This is my notebook that summarizes about "linear algebra". I will add contents as needed.

> Twitterモーメント ： https://twitter.com/i/moments/867746637526876162</br>
![_](https://user-images.githubusercontent.com/25688193/30373543-a1127a20-98bc-11e7-822d-351aeb6b131d.gif)

## 項目 [Contents]

1. [概要、全体 MAP [Overview]](#ID_1)
1. [ベクトル [vector]](#ID_2)
    1. [ベクトル空間 [vector space]](#ID_2-1)
        1. [ベクトル空間とベクトルの性質](#ID_2-1-1)
            1. [張る（生成する）](#ID_2-1-1-1)
            1. [線形独立（一次独立）と線形従属（一次従属）](#ID_2-1-1-2)
                1. [線形独立（１次独立）[linearly independent] と線形従属（１次従属）[linearly dependent] のイメージ](#ID_2-1-1-2-1)            
        1. [基底ベクトル [basis vector]](#ID_2-1-2)
        1. [ベクトルの次元](#ID_2-1-3)
1. [行列 [Matrix]](#ID_3)
    1. [ガウスの消去法 [Gaussian elimination]](#ID_3-1)
    1. [行列式 [determinant]](#ID_3-2)
    1. [行列式の性質](#ID_3-3)
    1. [ガウスの消去法を利用した行列式の計算](#ID_3-4)
    1. [余因子展開 [cofactor expansion]](#ID_3-5)
    1. [行列式の積](#ID_3-6)
    1. [置換による行列式の表現](#ID_3-7)
        1. [置換の符号](#ID_3-7-1)
        1. [置換による行列式の定義](#ID_3-7-2)
    1. [逆行列 [inverse matrix]](#ID_3-8)
        1. [逆行列の公式](#ID_3-8-1)
        1. [逆行列の公式を用いての逆行列の算出](#ID_3-8-2)
        1. [ガウスの消去法を用いての逆行列の算出](#ID_3-8-3)
    1. [行列のランク（階級）[rank]](#ID_3-9)
        1. [行列のランクの意味](#ID_3-9-1)
            1. [小行列式によるランクの定義](#ID_3-9-1-1)
        1. [連立１次方程式と行列のランクの関係](#ID_3-9-2)
    1. [転置行列 [transposed matrix]、対称行列 [symmetric matrix]](#ID_3-10)
    1. [複素行列と複素共役、共役転置行列（随伴行列） [adjugate matrix]](#ID_3-11)
1. [線形写像 [linear mapping]](#ID_4)
    1. [線形変換 [linear transformation]](#ID_4-1)
        1. [線形変換の幾何学的イメージ](#ID_4-1-1)
        1. [アファイン変換 [affine transformation]](#ID_4-1-1-1)
        1. [線形変換の逆変換](#ID_4-1-2)
    1. [線形写像 [linear mapping]](#ID_4-2)
        1. [線形写像の核 [kernel] と像 [image]](#ID_4-2-1)
        1. [商空間 [quotient space]](#ID_4-2-2)
        1. [線形代数学の基本定理</br>（線形写像の商空間と像の関係＋カーネルと像の次元の関係、準同型定理の特殊なケース）](#ID_4-2-3)
        1. [連立１次方程式への線形代数学の基本定理の応用](#ID_4-2-4)
1. [固有値 [eigenvalue]、固有ベクトル [eigenvector]](#ID_5)
    1. [固有方程式](#ID_5-1)
    1. [特性方程式](#ID_5-2)
1. [行列の対角化 [diagonalization]](#ID_6)
    1. [対角化可能な条件](#ID_6-1)
    1. [なぜ対角化するのか？](#ID_6-2)
        1. [２次形式の標準化への応用](#ID_6-2-1)
    1. [直行行列 [orthogonal matrix] と実対称行列 [symmetric matrix]](#ID_6-3)
    1. [エルミート行列 [Hermitian matrix] とユニタリー行列 [Unitary matrix] の対角化](#ID_6-4)
        1. [エルミート行列 [Hermitian matrix]](#ID_6-4-1)
        1. [ユニタリー行列 [Unitary matrix]](#ID_6-4-2)
        1. [エルミート行列のユニタリー行列での対角化](#ID_6-4-3)
1. [ジョルダン標準形 [Jordan normal form]](#ID_7)
    1. [２×２行列でのジョルダン標準形](#ID_7-1)
    1. [ジョルダン標準形の微分方程式への応用](#ID_7-2)
1. [ベクトル解析 [vector calculus]](#ID_8)
    1. [内積 [inner product]](#ID_8-1)
    1. [外積 [cross product]](#ID_8-2)
    1. [勾配 [gradient] : grad f = ∇ f ](#ID_8-3)
    1. [発散 [divergence] : div A = ∇・A](#ID_8-4)
    1. [回転 [rotation] : rot A = ∇ × A](#ID_8-5)
1. [参考文献](#参考文献)

- 追記予定項目
    - グラム・シュミットの正規直交化法 [Gram–Schmidt orthonormalization]
    - 行列の QR 分解 [QR decomposition]
    - 行列の特異値分解 [SVD : single value decomposition]
    - ３×３行列でのジョルダン標準形

<a id="ID_1"></a>

## 概要 [Overview]
![twitter_ _1-1_170525](https://user-images.githubusercontent.com/25688193/29313679-4536cada-81f6-11e7-91d3-60484150ed15.png)


<a id="ID_2"></a>

## ベクトル [vector]

<a id="ID_2-1"></a>

### ベクトル空間 [vector space]
![twitter_ _2-1_170525](https://user-images.githubusercontent.com/25688193/29313678-452ed686-81f6-11e7-8114-56f516ad806a.png)
![twitter_ _2-2_170525](https://user-images.githubusercontent.com/25688193/29313682-45583314-81f6-11e7-86d0-cb72ac49bb97.png)

<a id="ID_2-1-1"></a>

### ベクトル空間とベクトルの性質

<a id="ID_2-1-1-1"></a>

#### 張る（生成する）
![twitter_ _2-3_170525](https://user-images.githubusercontent.com/25688193/29313680-4556590e-81f6-11e7-87bf-9ca0c1191ace.png)

<a id="ID_2-1-1-2"></a>

#### 線形独立（一次独立）と線形従属（一次従属）
![twitter_ _2-4_170525](https://user-images.githubusercontent.com/25688193/29313681-4558390e-81f6-11e7-96e0-c7631e404cfa.png)

<a id="ID_2-1-1-2-1"></a>

##### 線形独立（１次独立）[linearly independent] と線形従属（１次従属）[linearly dependent] のイメージ
![twitter_ _2-5_170525](https://user-images.githubusercontent.com/25688193/29313684-4559e0b0-81f6-11e7-818d-bb0fe61655d1.png)

![twitter_ _2-6_170525](https://user-images.githubusercontent.com/25688193/29313683-4559c828-81f6-11e7-951d-731e825f82a6.png)
![twitter_ _2-7_170525](https://user-images.githubusercontent.com/25688193/29313685-455a00d6-81f6-11e7-8a73-0df9221bbb51.png)

<a id="ID_2-1-2"></a>

### 基底ベクトル [basis vector]
![twitter_ _2-8_170525](https://user-images.githubusercontent.com/25688193/29313686-45789a46-81f6-11e7-92e3-1a660b038c2e.png)

<a id="ID_2-1-3"></a>

### ベクトルの次元
![twitter_ _2-9_170525](https://user-images.githubusercontent.com/25688193/29313687-457d48c0-81f6-11e7-9f60-a28e9729c91f.png)

<a id="ID_3"></a>

## 行列 [Matrix]

<a id="ID_3-1"></a>

### ガウスの消去法 [Gaussian elimination]
![twitter_ _4-1_170526](https://user-images.githubusercontent.com/25688193/29313688-457d4640-81f6-11e7-9bb0-e8264a7e9083.png)
![twitter_ _4-2_170526](https://user-images.githubusercontent.com/25688193/29313689-457e2aec-81f6-11e7-99f0-b936a01b5702.png)
![twitter_ _4-3_170526](https://user-images.githubusercontent.com/25688193/29313691-45816d1a-81f6-11e7-8ea6-2e7dfb3f1013.png)

<a id="ID_3-2"></a>

### 行列式 [determinant]
![twitter_ _5-1_170526](https://user-images.githubusercontent.com/25688193/29313690-457f0138-81f6-11e7-9e6b-9246fdbe0576.png)
![twitter_ _5-2_170526](https://user-images.githubusercontent.com/25688193/29313693-45a24d46-81f6-11e7-9db1-789ba7ebd6f8.png)
![twitter_ _5-3_170526](https://user-images.githubusercontent.com/25688193/29313696-45a3f92a-81f6-11e7-9347-83aa1c01b360.png)

<a id="ID_3-3"></a>

### 行列式の性質
![twitter_ _5-4_170526](https://user-images.githubusercontent.com/25688193/29313692-45a22316-81f6-11e7-8744-c0c65f35517b.png)
![twitter_ _5-5_170526](https://user-images.githubusercontent.com/25688193/29313694-45a2fb92-81f6-11e7-86f4-f8e83e1024c2.png)

<a id="ID_3-4"></a>

### ガウスの消去法を利用した行列式の計算
![twitter_ _5-6_170526](https://user-images.githubusercontent.com/25688193/29313695-45a37e14-81f6-11e7-88ef-afcf7aef4618.png)

<a id="ID_3-5"></a>

### 余因子展開 [cofactor expansion]
![twitter_ _5-7_170526](https://user-images.githubusercontent.com/25688193/29313697-45a5f7b6-81f6-11e7-9124-b3e82f5a4faf.png)
![twitter_ _5-8_170526](https://user-images.githubusercontent.com/25688193/29313699-45c7ca1c-81f6-11e7-992d-b51c8b2605c8.png)

<a id="ID_3-6"></a>

### 行列式の積
![twitter_ _5-9_170526](https://user-images.githubusercontent.com/25688193/29313698-45c5a264-81f6-11e7-9e69-fe65562aac55.png)

<a id="ID_3-7"></a>

### 置換による行列式の表現
![image](https://user-images.githubusercontent.com/25688193/30404778-28362dce-9923-11e7-8acf-9e352ccc957a.png)

<a id="ID_3-7-1"></a>

#### 置換の符号
![image](https://user-images.githubusercontent.com/25688193/30404797-3f653706-9923-11e7-9e69-66141c789f58.png)

<a id="ID_3-7-2"></a>

#### 置換による行列式の定義
![twitter_ _5-11_170526](https://user-images.githubusercontent.com/25688193/29313701-45c98898-81f6-11e7-9b05-5e949c7daa26.png)

<a id="ID_3-8"></a>

### 逆行列 [inverse matrix]

<a id="ID_3-8-1"></a>

#### 逆行列の公式
![twitter_ _6-1_170526](https://user-images.githubusercontent.com/25688193/29313700-45c8ae8c-81f6-11e7-99a4-dd69e4fdd18b.png)
![twitter_ _6-2_170526](https://user-images.githubusercontent.com/25688193/29313702-45d0f5ce-81f6-11e7-8b4d-9c5883534bc9.png)
![twitter_ _6-3_170526](https://user-images.githubusercontent.com/25688193/29313707-45edb8ee-81f6-11e7-936e-6190968688d0.png)

<a id="ID_3-8-2"></a>

#### 逆行列の公式を用いての逆行列の算出
![twitter_ _6-4_170526](https://user-images.githubusercontent.com/25688193/29313704-45ea8552-81f6-11e7-8924-7d4b4f6a97f2.png)

<a id="ID_3-8-3"></a>

#### ガウスの消去法を用いての逆行列の算出
![twitter_ _6-5_170526](https://user-images.githubusercontent.com/25688193/29313706-45ed9904-81f6-11e7-9467-9d7ba7bc5a2f.png)

<a id="ID_3-9"></a>

### 行列のランク（階級）[rank]
![twitter_ _7-1_170526](https://user-images.githubusercontent.com/25688193/29313705-45edac50-81f6-11e7-81ca-71b40430438c.png)
![twitter_ _7-2_170526](https://user-images.githubusercontent.com/25688193/29313708-45f4dd40-81f6-11e7-9df0-73c9082307c1.png)

<a id="ID_3-9-1"></a>

#### 行列のランクの意味
![twitter_ _7-3_170526](https://user-images.githubusercontent.com/25688193/29313709-45ff6f1c-81f6-11e7-8d69-a06a87ac7620.png)
![twitter_ _7-4_170526](https://user-images.githubusercontent.com/25688193/29313711-461179be-81f6-11e7-93f9-1fe859b41cd6.png)

<a id="ID_3-9-1-1"></a>

##### 小行列式によるランクの定義
> 記載中...

<a id="ID_3-9-2"></a>

#### 連立１次方程式と行列のランクの関係
![twitter_ _7-5_170526](https://user-images.githubusercontent.com/25688193/29313710-461128f6-81f6-11e7-8c80-43a3f9af1ffe.png)
![twitter_ _7-6_170526](https://user-images.githubusercontent.com/25688193/29313712-46123822-81f6-11e7-88db-8dde81368015.png)


<a id="ID_3-10"></a>

### 転置行列 [transposed matrix]、対称行列 [symmetric matrix]
![image](https://user-images.githubusercontent.com/25688193/30404841-9cc59dbe-9923-11e7-9f1b-4b0a3136961b.png)

<a id="ID_3-11"></a>

### 複素行列と複素共役、共役転置行列（随伴行列） [adjugate matrix]
![image](https://user-images.githubusercontent.com/25688193/30404923-051693be-9924-11e7-882b-e35a9ce8ef6e.png)


<a id="ID_4"></a>

## 線形写像 [linear mapping]

<a id="ID_4-1"></a>

### 線形変換 [linear transformation]
![image](https://user-images.githubusercontent.com/25688193/30404587-4c394482-9922-11e7-812a-28bd943a539f.png)
![twitter_ _8-2_170526](https://user-images.githubusercontent.com/25688193/29313714-461fc7e4-81f6-11e7-8813-1fd469af3f42.png)
![twitter_ _8-3_170526](https://user-images.githubusercontent.com/25688193/29313715-462aee9e-81f6-11e7-9d58-4654824c2fdf.png)

<a id="ID_4-1-1"></a>

#### 線形変換の幾何学的イメージ
![twitter_ _8-4_170526](https://user-images.githubusercontent.com/25688193/29313719-463c7c7c-81f6-11e7-917d-0e77da16cc97.png)
![twitter_ _8-5_170526](https://user-images.githubusercontent.com/25688193/29313717-463637b8-81f6-11e7-8d0b-d7f80bc03ab6.png)
![twitter_ _8-6_170526](https://user-images.githubusercontent.com/25688193/29313716-46360b1c-81f6-11e7-88b8-63c3e903185f.png)

<a id="ID_4-1-1-1"></a>

#### アファイン変換 [affine transformation]
![twitter_ _8-7_170526](https://user-images.githubusercontent.com/25688193/29313718-46371d9a-81f6-11e7-832a-a5b55d12a496.png)

<a id="ID_4-1-2"></a>

#### 線形変換の逆変換
![twitter_ _8-8_170526](https://user-images.githubusercontent.com/25688193/29313720-4643b0be-81f6-11e7-97f9-88efefe6203b.png)

<a id="ID_4-2"></a>

### 線形写像 [linear mapping]
![twitter_ _9-1_170526](https://user-images.githubusercontent.com/25688193/29313721-464e596a-81f6-11e7-814b-5026a14c68b6.png)

<a id="ID_4-2-1"></a>

#### 線形写像の核 [kernel] と像 [image]
![twitter_ _9-2_170526](https://user-images.githubusercontent.com/25688193/29313722-4658b892-81f6-11e7-9cdb-8e0b9033e20c.png)
![twitter_ _9-4_170526](https://user-images.githubusercontent.com/25688193/29313723-465b2424-81f6-11e7-95aa-7890f145745e.png)

<a id="ID_4-2-2"></a>

#### 商空間 [quotient space]
![twitter_ _9-5_170526](https://user-images.githubusercontent.com/25688193/29313724-4673137c-81f6-11e7-9970-90eb0d528a7e.png)
![twitter_ _9-6_170526](https://user-images.githubusercontent.com/25688193/29313725-467ed34c-81f6-11e7-966d-4243bf20be4d.png)
![twitter_ _9-7_170526](https://user-images.githubusercontent.com/25688193/29313726-468330f4-81f6-11e7-9478-4bf528f24e74.png)

<a id="ID_4-2-3"></a>

#### 線形代数学の基本定理（線形写像の商空間と像の関係＋カーネルと像の次元の関係、準同型定理の特殊なケース）
![twitter_ _9-8_170527](https://user-images.githubusercontent.com/25688193/29313727-468a7a4e-81f6-11e7-9d75-e376fa28943a.png)
![twitter_ _9-9_170527](https://user-images.githubusercontent.com/25688193/29313728-4690cb4c-81f6-11e7-9c06-8e9fdfbc2ffd.png)

<a id="ID_4-2-4"></a>

#### 連立１次方程式への線形代数学の基本定理の応用
![twitter_ _9-10_170527](https://user-images.githubusercontent.com/25688193/29313729-4694f49c-81f6-11e7-9bea-098e25986c46.png)
![twitter_ _9-11_170527](https://user-images.githubusercontent.com/25688193/29313730-46972e74-81f6-11e7-8ed7-ead736bad135.png)

<a id="ID_5"></a>

## 固有値 [eigenvalue]、固有ベクトル [eigenvector]
![twitter_ _10-1_170527](https://user-images.githubusercontent.com/25688193/29313731-46a66db2-81f6-11e7-91d9-73f582d179a9.png)
![twitter_ _10-2_170527](https://user-images.githubusercontent.com/25688193/29313732-46a7754a-81f6-11e7-9af3-22e45cc7b9b0.png)
![twitter_ _10-3_170527](https://user-images.githubusercontent.com/25688193/29313733-46b0fe44-81f6-11e7-8232-fd23f1aaef63.png)
![twitter_ _10-4_170528](https://user-images.githubusercontent.com/25688193/29313734-46b4aee0-81f6-11e7-868d-0d1eddf44e56.png)
![twitter_ _10-5_170528](https://user-images.githubusercontent.com/25688193/29313735-46bb9ca0-81f6-11e7-963e-8e4f1700b6f9.png)
![twitter_ _10-6_170528](https://user-images.githubusercontent.com/25688193/29313736-46c0603c-81f6-11e7-94a7-f2a568d222a4.png)

<a id="ID_6"></a>

## 行列の対角化 [diagonalization]
![twitter_ _11-1_170529](https://user-images.githubusercontent.com/25688193/29313737-46cc04a0-81f6-11e7-84d5-564097bf600f.png)
![twitter_ _11-2_170529](https://user-images.githubusercontent.com/25688193/29313738-46d0740e-81f6-11e7-9d4f-8e0954b18ada.png)
![twitter_ _11-3_170529](https://user-images.githubusercontent.com/25688193/29313739-46d84b2a-81f6-11e7-8a00-4a2d5e7b220c.png)

<a id="ID_6-1"></a>

### 対角化可能な条件

![twitter_ _11-4_170529](https://user-images.githubusercontent.com/25688193/29313740-46df8868-81f6-11e7-8388-d93c06087098.png)
![twitter_ _11-5_170529](https://user-images.githubusercontent.com/25688193/29313741-46eb28a8-81f6-11e7-918b-15d0202bf7f5.png)
![twitter_ _11-6_170529](https://user-images.githubusercontent.com/25688193/29313742-46eb986a-81f6-11e7-9674-63dc93b5356c.png)
![twitter_ _11-7_170530](https://user-images.githubusercontent.com/25688193/29313743-46f7e07a-81f6-11e7-9480-975fc3f9be89.png)
![twitter_ _11-8_170530](https://user-images.githubusercontent.com/25688193/29313745-46ff69c6-81f6-11e7-93af-c578a9461745.png)

<a id="ID_6-2"></a>

### なぜ対角化するのか？
![twitter_ _11-9_170530](https://user-images.githubusercontent.com/25688193/29313746-470210fe-81f6-11e7-804d-7b66ba3a3891.png)

<a id="ID_6-2-1"></a>

#### ２次形式の標準化への応用
![twitter_ _11-10_170530](https://user-images.githubusercontent.com/25688193/29313747-470736f6-81f6-11e7-8efa-2661979fddaa.png)
![twitter_ _11-11_170530](https://user-images.githubusercontent.com/25688193/29313748-4713ed56-81f6-11e7-8f09-837fe9fa0ced.png)
![twitter_ _11-12_170530](https://user-images.githubusercontent.com/25688193/29313749-47195354-81f6-11e7-8674-9108d383ef9a.png)

<a id="ID_6-3"></a>

### 直行行列 [orthogonal matrix] と実対称行列 [symmetric matrix]
![twitter_ _12-1_170531](https://user-images.githubusercontent.com/25688193/29313750-47246fe6-81f6-11e7-9850-4866e523aeeb.png)
![twitter_ _12-2_170531](https://user-images.githubusercontent.com/25688193/29313751-472889dc-81f6-11e7-88ab-b47b72343841.png)
![twitter_ _12-3_170531](https://user-images.githubusercontent.com/25688193/29313752-4729c8ba-81f6-11e7-8973-f67f65aa41ab.png)

<a id="ID_6-4"></a>

### エルミート行列 [Hermitian matrix] とユニタリー行列 [Unitary matrix] の対角化

<a id="ID_6-4-1"></a>

#### エルミート行列 [Hermitian matrix]
![twitter_ _12-4_170531](https://user-images.githubusercontent.com/25688193/29313753-472e05e2-81f6-11e7-8ce8-04bee1068456.png)

<a id="ID_6-4-2"></a>

#### ユニタリー行列 [Unitary matrix]
![twitter_ _12-5_170531](https://user-images.githubusercontent.com/25688193/29313754-4738fa42-81f6-11e7-9ad7-79e712e5fb21.png)

<a id="ID_6-4-3"></a>

#### エルミート行列のユニタリー行列での対角化
![twitter_ _12-6_170531](https://user-images.githubusercontent.com/25688193/29313760-477a1838-81f6-11e7-9fcb-c0bac861babd.png)

<a id="ID_7"></a>

### ジョルダン標準形 [Jordan normal form]

<a id="ID_7-1"></a>

#### ２×２行列でのジョルダン標準形
![twitter_ _13-1_170531](https://user-images.githubusercontent.com/25688193/29313755-4749179c-81f6-11e7-9c8d-bf36cb817423.png)
![twitter_ _13-2_170601](https://user-images.githubusercontent.com/25688193/29313757-4756137a-81f6-11e7-8363-6605a872b47c.png)
![twitter_ _13-3_170601](https://user-images.githubusercontent.com/25688193/29313756-47551e70-81f6-11e7-8edc-9612ec9b8ea8.png)

<a id="ID_7-2"></a>

#### ジョルダン標準形の微分方程式への応用
![twitter_ _13-10_170602](https://user-images.githubusercontent.com/25688193/29313758-475897c6-81f6-11e7-9fac-9833342599fc.png)
![twitter_ _13-11_170602](https://user-images.githubusercontent.com/25688193/29313759-4767cd2c-81f6-11e7-9514-f44784a8f04e.png)

<a id="ID_8"></a>

### ベクトル解析 [vector calculus]

<a id="ID_8-1"></a>

#### 内積 [inner product]
![_ _1-1_170913](https://user-images.githubusercontent.com/25688193/30376898-e915c7c6-98c8-11e7-8f68-8d6c8b5d2740.png)

<a id="ID_8-2"></a>

#### 外積 [cross product]
![_ _1-2_170913](https://user-images.githubusercontent.com/25688193/30376902-e95acbfa-98c8-11e7-9548-98d9a5a1a431.png)

<a id="ID_8-3"></a>

#### 勾配 [gradient] : grad f = ∇ f
![_ _2-1_170913](https://user-images.githubusercontent.com/25688193/30376899-e9501ad4-98c8-11e7-8f21-4f5bd2d34f6e.png)

<a id="ID_8-4"></a>

#### 発散 [divergence] : div A = ∇・A
![_ _2-2_170913](https://user-images.githubusercontent.com/25688193/30376900-e9522f72-98c8-11e7-9c03-e37c51c34211.png)

<a id="ID_8-5"></a>

#### 回転 [rotation] : rot A = ∇ × A
![_ _2-3_170913](https://user-images.githubusercontent.com/25688193/30376901-e9532e68-98c8-11e7-98c8-93f875d71680.png)


<a name="参考文献"></a>

## 参考文献

> 情報数理の基礎と応用 (ライブラリ情報学コア・テキスト) </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E6%83%85%E5%A0%B1%E6%95%B0%E7%90%86%E3%81%AE%E5%9F%BA%E7%A4%8E%E3%81%A8%E5%BF%9C%E7%94%A8-%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA%E6%83%85%E5%A0%B1%E5%AD%A6%E3%82%B3%E3%82%A2%E3%83%BB%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88-%E5%B0%BE%E7%95%91-%E4%BC%B8%E6%98%8E/dp/4781912109?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4781912109)</br>

> キーポイント線形代数 (理工系数学のキーポイント 2) </br>
> [amazonで詳細を見る](https://www.amazon.co.jp/%E3%82%AD%E3%83%BC%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E7%B7%9A%E5%BD%A2%E4%BB%A3%E6%95%B0-%E7%90%86%E5%B7%A5%E7%B3%BB%E6%95%B0%E5%AD%A6%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88-2-%E8%96%A9%E6%91%A9-%E9%A0%86%E5%90%89/dp/4000078623?SubscriptionId=AKIAI4N75A3H7VG7SKUQ&amp;tag=cloudstudy09-22&amp;linkCode=xm2&amp;camp=2025&amp;creative=165953&amp;creativeASIN=4000078623)</br>
