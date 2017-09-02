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


How we did it
----
!(dda-setup)[https://github.com/hughito/datadrivenart-2017/blob/master/docs/dda-setup.png]

私たちは
*
*
*
*


Our setup consisted of 
* Openframeworks - To visualize the incoming data via OpenBCI through osc and remove some of the noise created by creating an average of the overall data throughout time. This data is then sent to Max 7 to filter again before sending to Wekinator. OF was also used to visualize video playback and also for sending accurate numbers to arduino IDE.
* Max 7 - To filter the incoming data via OpenBCI to readable 126 data and also slice the incoming channel number from the data
* Wekinator - To create a machine learning model of the data and also be able to test the model against other various hugs. This data is then sent to OpenFrameworks again to be able to use the output int for video playback and arduino controlling.
* Aruduino - Arduino IDE and board was used for the inflating the human baloon, which was used to visualize how relatable the "hugness" was.

