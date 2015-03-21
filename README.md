# 簡易HMDを使ったVRハンズオンセミナー
 
### ユニティちゃんCandy Rock Star をダウンロードしよう！
 
http://unity-chan.com

以下のファイルおダウンロード
- ユニティちゃんライブステージ！ -Candy Rock Star-
- ユニティちゃんシェーダー（修正パッチ）
- ユニティちゃんスクリプト（Unity 5 修正パッチ）
 
### ヘッドトラッキングアセットを持ってくる
 
Unity5でうまく動くアセット
 
##### Durovis Dive SDK
- https://www.durovis.com/sdk.html
- ドリフトあり、追従性良、iOS/Android
- 無料
 
##### Google Cardboard SDK for Unity
- https://developers.google.com/cardboard/unity/download
- ドリフトなし、追従性良、Android
- 無料
 
##### Head Tracking Camera for Smart Phone
- AssetStore
- ドリフトなし、追従性並、iOS/Android
- 有料
 
今回は「Durovis Dive SDK」を使用
 
#### 簡易HMDで見れるようにしよう
 
1. CRSプロジェクトを開く
1. 二つのパッチをあてる
1. Assets/UnityChan/Models/UnityChanShader/Shader　を
Assets/UnityChan/CandyRockStar/Shader　にExplorer/Finder上で上書きコピー
1. Mainを開く
1. UnityChan/Prefabs/CharacterLight の Intensity を0.6に
 
重い？
 
#### HMDで見る

1. Stage Directorの Main Camear Rig Prefabに Assets/Dive/Dive_Camera を D&D
1. プレイしてみる
1. 二眼で動くことを確認
1. Assets/Dive/Dive_Camera Prefabで場所を適当(0, 1.2, 1.2)に変更。Zoomを0.05 Znearを0.01
 
#### Durovis Dive SDKを修正

OpenDiveSensor.cs:L45

```
	AndroidJavaObject mConfig;
	AndroidJavaObject mWindowManager;
``` 

を以下のように変更 

```
#if UNITY_ANDROID
	AndroidJavaObject mConfig;
	AndroidJavaObject mWindowManager;
#endif
``` 
 
#### 軽量化
Stage Directorの設定を画像の通りに
プレイしてみる
 
#### Android設定
http://docs.unity3d.com/ja/current/Manual/android-sdksetup.html
を見ながらSDKダウンロード
 
#### iOS設定
http://docs.unity3d.com/ja/current/Manual/iphone-accountsetup.html
 
#### こちらを向いてもらおう
UnityChanLookAt.cs を D&D
IK設定
 
#### MMDを動かしてみよう
・MMD4Mecanimをインストール
http://stereoarts.jp
 
・MMDをDL
https://bowlroll.net
から
 
#### VMDを使って好きな動きを付けてみよう
VMDをDL
https://bowlroll.net
https://bowlroll.net/file/734 DIVA2nd メルトモーション
から
 
MMD4Mecanimに
 
#### ゆれものを付けてみよう
UnityChanを見てゆれものがどうなっているのか調べる
テラシュールの紹介
SprintBone.csをアタッチ
SpringBoneManager.csをルートにアタッチ
向きを設定
子をセット
Managerに登録
プレイしてゆれるか確認？
 
#### 音楽をDL
http://supercell.sc/music/3melt.zip
http://supercell.sc/music/wim.zip
 
#### 部屋やアセットをDLして豪華にしてみよう
