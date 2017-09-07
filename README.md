# 慶應義塾大学SFC 特別講座　データドリブンアート 2017
###### Keio University SFC Data Driven Art 2017 Course
### 講師：真鍋大度、筧康明、and more.
###### Professors: Daito Manabe , Yasuaki Kakehi, and more.

Team HUGHITO
=====
* 森田健人 Kento Morita (@kentoids)
* 小林颯 Hayate Kobayashi (@hytk)
* 清水快　Kye Shimizu (@kkshmz)


What we did
----
![dda-example](https://raw.github.com/hughito/datadrivenart-2017/master/docs/dda-example.jpg)

本作品では、脳波の計測と分析ができるハードとソフトのオープンソフトプラットフォーム、OpenBCIを用い、ハグ度の計測と視覚化を行った。
私たちは何もしていない状態と人とハグしている状態の脳波を測定し、それらの波形データを機械学習させ、波形が何もしていない状態に近ければ0、ハグしているときに近ければ1となるようなモデルを作成した。このモデルが表す「人をハグした時の脳波との近似度」をハグ度とし、様々な無機物とハグした時の脳波を分析し、視覚化した。
これにより私たちは、人がどのようなものにハグした時に人と似たような感情を抱いているのか、その差異やパターンについて考えることによって、人と無機物との感情的な距離を算出することを目指した。

How we did it
----
![dda-setup](https://raw.github.com/hughito/datadrivenart-2017/master/docs/dda-setup.png)


私たちは
* TOP RIGHT : Openframeworks - OpenBCIによって獲得されたデータをoscで受け取り、ノイズ処理するとともに、各チャンネルの近似値を出すために使用し、その処理されたデータをまたoscでWekinatorに送る。また、最終的にMaxから来たデータをArduinoへ信号をおくるために、映像へビジュアライズされるために使用。
* * [ofxOpenBCI](http://github.com/kentoids/ofxOpenBCI)を開発。
* BOTTOM RIGHT : Max 7 - OpenBCIから来たデータを確認するためと、Wekinatorから来たデータの処理をするために使用。
* TOP LEFT : Wekinator - OpenBCIのデータを使用して、モデルを作成するためのツールとして使用。
* Arduino - 人間バルーンを制御するために使用し、値をOpenframeworksから獲得する。


Our setup consisted of 
* TOP RIGHT : Openframeworks - To visualize the incoming data via OpenBCI through osc and remove some of the noise created by creating an average of the overall data throughout time. This data is then sent to Max 7 to filter again before sending to Wekinator. OF was also used to visualize video playback and also for sending accurate numbers to arduino IDE.
* * Creation of [ofxOpenBCI](http://github.com/kentoids/ofxOpenBCI) through this.
* BOTTOM RIGHT: Max 7 - To filter the incoming data via OpenBCI to readable 126 data and also slice the incoming channel number from the data
* TOP LEFT : Wekinator - To create a machine learning model of the data and also be able to test the model against other various hugs. This data is then sent to OpenFrameworks again to be able to use the output int for video playback and arduino controlling.
* BOTTOM LEFT : OpenBCI Control Panel
* Arduino - Arduino IDE and board was used for the inflating the human baloon, which was used to visualize how relatable the "hugness" was.

