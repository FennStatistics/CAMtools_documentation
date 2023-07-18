Cognitive-Affective Map extended logic
=====

The application Cognitive-Affective Map extended logic, C.A.M.E.L. is a software package that supports CAM drawing. It can be applied if you aim to draw your single CAM on any topic. Yet, it is constructed to support large-scale online-studies to gather CAM data of many participants (several hundred participants would be no problem for C.A.M.E.L.) . 

Asking participants to draw CAMs from scratch may be an ambitious task and participants may not even draw a CAM regarding your intended issue (like your intended topic). Here it might help to predefine concepts to help your participants to draw the intended CAM. Moreover, it may be that researchers would like to control what is being displayed or even possible to do while drawing CAMs. To this end, a "researcher view" of the CAM board was implemented. There, it is possible to create, position and fix (i.e., impossibility to move a concept) elements (the section define your config file list parameters that you can change for your CAM study). Once the structure is ready, click on “export” to create a CAM.json including all the different elements as well as the configuration of the project (see in detail [Set up study](Set up study.md)).


***
Define your config file
------------

Within the administrative panel after you have logged in you can click on "Design a CAM" (blue botton top right). After you have drawn your default CAM, which should be presented to the participants (see details in [Set up study](Set up study.md)) you can click on the "gear symbol" (top left) to define the configuration of your CAM study. 


**Parameter you can change using the user interface:** 

| Parameter   |      Meaning      |  Possible values |
|----------|:-------------|:------:|
| #ConNumNodes    | Number of nodes a participant needs to draw before <br> she / he is can save the CAM. | 1-50<sup>1</sup> |
| #MaxLengthWords | Maximum number of words allowed for each concept.   |  1-5<sup>2</sup> |
| #MaxLengthChars | Maximum number of characters for each concept allowed. | 30-300 |
| #hideArrows | If ON possible to draw draw arrows / directed connections. | ON / OFF |
| #showOnlyPosSlid | If ON possible to draw supporting connections. | ON / OFF |
| #hideAmbivalent | If ON possible to draw ambivalent concepts. | ON / OFF |
| #cameraFeature | If ON  an splotlight feature is included to move the drawing <br> screen. If participants move their mouse to the edges the <br> drawing screen is moved to the respective side. | ON / OFF |
| #fullScreen | If ON study is set to fullscreen mode and paradata is <br> collected (defocus, focus events). | ON / OFF |
| #setLanguage | Set the language of the C.A.M.E.L. interface: | English, <br> German, <br> Spanish |


<sup>1</sup>Maxmimum number is restricted, because the drawing space is limited. In the future 3D environments will be implemented.

<sup>2</sup>It is **highly recommened to set this value to 1-3** if you are aiming to summarize / aggregate the CAM data. Instruct participants to avoid writing sentences and to draw instead multiple concepts. 

*Remark: It is no recommended to write directly into the config file. Certain configurations are set to default values and should not be changed.*

***
Data-structure of CAMs
----------------

blabla


***
Implemented features
----------------

blabla


***
Future features
----------------

blabla