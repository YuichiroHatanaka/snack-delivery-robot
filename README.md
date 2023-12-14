# snack-delivery-robot
2023年度　設計製作特論　Aチーム

どんなロボット？

お菓子を配るロボット


環境

Ubuntu22.04

ROS2：Humble


2DLiDAR：RPLIDAR A2M8

https://www.seeedstudio.com/RPLiDAR-A2M8-360-Degree-Laser-Scanner-Kit-12M-Range-p-3074.html

パッケージ：https://github.com/Slamtec/sllidar_ros2#compile--install-sllidar_ros2-package

SDK(software development kit)：https://github.com/Slamtec/rplidar_sdk


動かし方(別の方法もある。コレが最適解ではない)

必要なもの

Ubuntuの入ったノートPC、ラズパイ

ノートPC側のUbuntuでの作業

１．ラズパイの電源を入れる。このとき有線LANでwifiにつながっているかを確認する。

２．以下のコマンドでwifiのIPアドレスの範囲を確認

　　`ip a`

３．同じWifiに接続されたノートPCから以下のコマンドを使ってラズパイのIPアドレスを見つける。

　　`sudo nmap -sn IPアドレスの範囲`
  
  0/24の０は変えないでください。

　　ラズパイの起動に数分かかるので気長に待つこと

４．sshで接続する。

　　`ssh ubuntu@IPアドレス`

　　ここでもsshで接続するのに起動してから5分ほどかかるので気長に待つ

ラズパイ側のUbuntuでの作業

モータの動かし方

1．以下のコマンドでデーモンを起動させる。

　　`sudo pigpiod`
  
２．以下のコマンドでモータが動く

　　`python3 test.py`
