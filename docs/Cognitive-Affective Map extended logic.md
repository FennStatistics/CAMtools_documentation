Cognitive-Affective Map extended logic
=====

The application Cognitive-Affective Map extended logic, C.A.M.E.L. is a software package that supports CAM drawing. It can be applied if you aim to draw your single CAM on any topic. Yet, it is constructed to support large-scale online-studies to gather CAM data of many participants (several hundred participants would be no problem for C.A.M.E.L.) . 

Asking participants to draw CAMs from scratch may be an ambitious task and participants may not even draw a CAM regarding your intended issue (like your intended topic). Here it might help to predefine concepts to help your participants to draw the intended CAM. Moreover, it may be that researchers would like to control what is being displayed or even possible to do (i.e., draw ambivalent concepts) while drawing CAMs. To this end, a "researcher view" of the CAM board was implemented. There, it is possible to create, position and fix (i.e., impossibility to move a concept) elements. Once the structure is ready, click on “export” to create a CAM.json including all the different elements as well as the configuration of the project (see in detail [Set up study](Set up study.md)).


***
Define your config file
------------

Within the administrative panel after you have logged in you can click on "C.A.M.E.L. (researcher view)" (botton at the top). After you have drawn your default CAM, which should be presented to the participants (see details in [Set up study](Set up study.md)) you can click on the "gear symbol" (top left) to define the configuration of your CAM study. 


**Parameter you can change using the user interface:** 

| Parameter   |      Meaning      |  Possible values |
|----------|:-------------|:------:|
| #ConNumNodes    | Number of nodes a participant needs to draw before <br> she / he is can save the CAM. | 1-50<sup>1</sup> |
| #MaxLengthWords | Maximum number of words allowed for each concept.   |  1-5<sup>2</sup> |
| #MaxLengthChars | Maximum number of characters for each concept allowed. | 30-300 |
| #hideArrows | If ON possible to draw arrows / directed connections. | ON / OFF |
| #BidirectionalDefault | Only makes sense if #hideArrows is set to ON, <br> as default the drawn connection is bidirectional. | ON / OFF |
| #showOnlyPosSlid | If ON possible to draw supporting connections. | ON / OFF |
| #hideAmbivalent | If ON possible to draw ambivalent concepts. | ON / OFF |
| #cameraFeature | If ON  an splotlight feature is included to move the drawing <br> screen. If participants move their mouse to the edges the <br> drawing screen is moved to the respective side. | ON / OFF |
| #fullScreen | If ON study is set to fullscreen mode and paradata is <br> collected (defocus, focus events). | ON / OFF |
| #setLanguage | Set the language of the C.A.M.E.L. interface: | English, <br> German, <br> Spanish, <br> Chinese |


<sup>1</sup>Maxmimum number is restricted, because the drawing space is limited. In the future 3D environments will be implemented.

<sup>2</sup>It is **highly recommened to set this value to 1-3** if you are aiming to summarize / aggregate the CAM data. Instruct participants to avoid writing sentences and to draw instead multiple concepts. 

*Remark: It is no recommended to write directly into the config file, except you know what you are doing. Certain configurations are set to default values and should not be changed. By programming your CAM <a href="https://camtools-documentation.readthedocs.io/en/master/Set%20up%20study/#program-on-scratch" target="_blank">on scratch</a> you are able to set reminders to program even adaptive designs.*

***
Data-structure of CAMs
----------------

The CAM itself is a Java Script object, 
client side programming
Java Script classes...


**Concepts** (nodes) drawn in CAM have the following data structure, whereby the single parameters are explained below:


```js
    constructor(value, text, position, isDraggable = true, isDeletable = true, isTextChangeable = true) {
        this.id = uuid.v4();
        this.value = value;
        this.text = text;
        this.comment = "";
        this.position = position;
        this.isActive = true;
        this.date = (new Date).getTime();
        this.kind = "Node";
        this.isSelected = false;
        this.isConnectorSelected = false;
        this.isDraggable = isDraggable;
        this.isDeletable = isDeletable;
        this.hasElementMoved = false;
        this.eventLog = [];
        this.isTextChangeable = isTextChangeable;

        this.enterLog({
            type: "create node",
            value: value
        });
    }
```
* "id:" ...

<br>

**Connectors** (edges) drawn in CAM have the following data structure, whereby the single parameters are explained below:

```js
    constructor(isDeletable = true) {
        this.id = uuid.v4();
        this.value = null;
        this.source = null;
        this.target = null;
        this.agreement = null; 
        this.isActive = null;
        this.date = (new Date).getTime();
        this.kind = "Connector";
        this.isSelected = false;
        this.intensity = IncreaseSliderIntensity;
        this.isDeletable = isDeletable;
        this.isOver = false;
        this.isBidirectional = true;
        this.eventLog = [];
    }
```

* "id:" ...


***
Implemented features
----------------

blabla


***
Future features
----------------



<br>
If you are missing a feature for your study and do not know how to implement it, we are happy to hear from you: <cam.contact@drawyourminds.de>