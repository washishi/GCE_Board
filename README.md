# GCE_Board
A board for growing cat ear LED

## M5Stack Core に [NekomimiLED](https://washishi.booth.pm/items/6764996)を取り付ける為？の基板です  
- CORE2の裏蓋をつけたままこの基板を取り付けることができます  
  (他のCOREやモジュール取り付け時はM-BUSのピンヘッダを切断して長さを短くすることで対応)
- PortB,PortCはコネクタ同士の間隔も含めてGoBottom互換のためNekomimiLEDが取り付けれます
- CORE2に取り付ける場合は取り外したCORE2 Ext.(MIC,IMU)をこの基板上に取り付けて利用することができます
- オプションでRGB LED(左右各5個,合計10個)が取り付け可能  
  (利用するGPIOについてはGoBottom互換)
- [タカオさん版ｽﾀｯｸﾁｬﾝｹｰｽ](https://mongonta.booth.pm/)に取り付けたまま使うことができます  
  (サーボ接続機能はないのでTakaoBaseを併用してください)

<img src="docs/images/IMG_20250702_212411.jpg" width="300px" height="280px">
<img src="docs/images/IMG_20250702_212422.jpg" width="300px" height="280px"><br>  
<img src="docs/images/IMG20250702211959.jpg" width="300px" height="280px">  
<img src="docs/images/IMG20250702213122.jpg" width="300px" height="280px"><br>  
<br>  

## 各部の説明
<img src="docs/images/GCE_Board1.png" width="300px" height="280px">
<img src="docs/images//GCE_Board2.png" width="300px" height="280px"><br>  
  1. M-BUSピンヘッダ M5Coreへ接続します<br>
　Core2の裏蓋の上に取り付ける場合はそのまま<br>
　Core2の裏蓋を外す場合や他のCoreやLLM等のモジュールの裏につける場合は<br>
　付属の治具を使いピンヘッダを丁度よい長さに切断します<br>
　<img src="docs/images//CUT.png" width="200px" >
<br>
<br>
<br>
  2. PortB GoBotom互換のPortBです<br>

  |種類||||<br>
  | :--- | :--- | :--- | :--- | :--- |
  |Basic系    |GND|5V|GPIO-26|GPIO-36|
  |Core2      |GND|5V|GPIO-26|GPIO-36|
  |CoreS3/S3SE|GND|5V|GPIO-9 |GPIO-8 |
<br>

  3.PortC GoBotom互換のPortCです  
  |種類|||TX|RX<br>
  | :--- | :--- | :--- | :--- | :--- |
  |Basic系    |GND|5V|GPIO-17|GPIO-16|
  |Core2      |GND|5V|GPIO-17|GPIO-16|
  |CoreS3/S3SE|GND|5V|GPIO-17|GPIO-18|
<br>

  4.PortA(BASIC系)/Int I2C(Core2,S3) (縦)  
  |種類|||SCL|DAT|<br>
  | :--- | :--- | :--- | :--- | :--- | :-- |
  |Basic系    |GND|5V|GPIO-21|GPIO-22|PortA|
  |Core2      |GND|5V|GPIO-21|GPIO-22|Int I2C|
  |CoreS3/S3SE|GND|5V|GPIO-12|GPIO-11|Int I2C| 
<br>

  5.GPIO(BASIC系)/PortA(Core2,S3) (横)
  |種類|||SCL|DAT|<br>
  | :--- | :--- | :--- | :--- | :--- | :-- |
  |Basic系    |GND|5V|GPIO-2|GPIO-5|GPIO|
  |Core2      |GND|5V|GPIO-32|GPIO-33|PortA|
  |CoreS3/S3SE|GND|5V|GPIO-2|GPIO-1|PortA| 
<br>

  6.GPIO (縦)
  |種類||||<br>
  | :--- | :--- | :--- | :--- | :--- |
  |Basic系    |GND|5V|GPIO-12|GPIO-13|
  |Core2      |GND|5V|GPIO-27|GPIO-19|
  |CoreS3/S3SE|GND|5V|GPIO-6|GPIO-7| 
<br>
  
  7.PortA(BASIC系)/Int I2C(Core2,S3) (横)<br> 
　接続は「4.PortA(BASIC系)/Int I2C(Core2,S3) (縦)」と同じです<br>
　ここに刺せるIMUのオプションを開発中です<br>
　Greoveコネクタも一応刺せますが刺しにくいです<br>
<br>

  8.NanoMIC(PDMマイク)専用コネクタ<br>
　NanoMICやM5のPDMマイク専用のGroveコネクタです<br>
  |種類|||I2S DAT|I2S CLK<br>
  | :--- | :--- | :--- | :--- | :--- |
  |Basic系    |GND|5V|GPIO-34|GPIO-0|
  |Core2      |GND|5V|GPIO-34|GPIO-0|
  |CoreS3/S3SE|GND|5V|GPIO-14|GPIO-0| 
<br>

  9.Core2 Ext. 専用ピンソケット<br>
　  Core2付属の Core2 Ext. をここに刺すことにより使えます<br>
　  注：Core2 Ext.で使用するピンしか接続されていません

  10.LED用ピンソケット(Core2,S3用)<br>
　オプションのRGB LEDを取り付けるピンソケットです<br>
　 Core2,CoreS3/S3SE用 GoBottom互換<br>
  |種類|RGB LED(WS2812B)<br>
  | :--- | :--- |
  |Core2      |GPIO-25|
  |CoreS3/S3SE|GPIO-5| 
<br>

  11.LED用ピンソケット(BASIC系用)
　オプションのRGB LEDを取り付けるピンソケットです<br>
　 BASIC系用 GoBottom互換<br>
  |種類|RGB LED(WS2812B)<br>
  | :--- | :--- |
  |BASIC系|GPIO-15|

<br>
  8. バッテリーコネクタ(小)<br>
  9. バッテリーコネクタ(大)<br>
  10. バッテリースイッチ<br>
<br>
こちらにバッテリーを繋げるとバッテリースイッチにより
物理的にバッテリーを切り離せるようになります<br>
利用する場合はバッテリーコネクタ(小)/(大)のいずれかのコネクタに3.7Vのリチウムポリマーバッテリーを<br>+､-があっていることを確認して繋いでください (市販の物で+,-が逆の物があるようです)<br>
またこちらを利用する場合はCore2の場合は内蔵バッテリーのコネクタは取り外してください<br> (バッテリーが1つしか繋がっていない状態にしてください)<br>Core2で裏蓋なしで利用する場合は取り外したバッテリーコネクタをこちらに繋ぐこともできます