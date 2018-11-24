# CAN通信 [Controller Area Network]

車両用ネットワーク規格であるCAN通信に関してのマイノートです。

## 内容
1. CAN通信規格
1. 通信プロトコル
1. BASIC CAN と FULL CAN
1. CANバスネットワーク（レセッシブ、ドミナント）
1. CANメッセージ
1. CANメッセージのビットタイミングと同期、セグメント
1. 受信処理
1. 送信処理
1. 通信遅延
1. 通信エラー、バスオフ
1. 電圧異常時の動作
1. 電源系の違いによる動作
1. 故障診断
    1. 故障診断通信規格
    1. 故障診断メッセージ


<!--
## ◎ CAN通信規格
-->

![can_1_170703](https://user-images.githubusercontent.com/25688193/29316048-54c1416e-8201-11e7-931e-eba9e7465aac.jpg)
![can_2_170703](https://user-images.githubusercontent.com/25688193/29316049-54d59682-8201-11e7-9542-dc91ed941a50.jpg)
![can_3_170703](https://user-images.githubusercontent.com/25688193/29316050-54e30f10-8201-11e7-9b4b-de614ac219e2.jpg)
![can_4_170703](https://user-images.githubusercontent.com/25688193/29316051-54ea6940-8201-11e7-97cf-714eb2819f5c.jpg)
![can_5_170707](https://user-images.githubusercontent.com/25688193/29316052-54ed7ab8-8201-11e7-85e9-4d449a7b8229.jpg)
![can_6_170707](https://user-images.githubusercontent.com/25688193/29316053-54ee1b9e-8201-11e7-89f6-83518c33a20c.jpg)
![can_7_170707](https://user-images.githubusercontent.com/25688193/29316056-5504b35e-8201-11e7-9eb9-7892e239dde4.jpg)
![can_8_170711](https://user-images.githubusercontent.com/25688193/29316054-54f98056-8201-11e7-9f43-990995f7ec14.jpg)