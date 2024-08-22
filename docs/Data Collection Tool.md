Cognitive-Affective Map extended logic
=====

The application Cognitive-Affective Map extended logic (C.A.M.E.L.) is a software package that enable participants to draw CAMs. It is constructed to support large-scale online-studies to gather CAM data of many participants (several hundred participants would be no problem for C.A.M.E.L.). 

Asking participants to draw CAMs from scratch may be an ambitious task and participants may not even draw a CAM regarding your intended issue (like your intended topic). Here it might help to predefine concepts to help your participants to draw the intended CAM. Moreover, it may be that researchers would like to control what is being displayed or even possible to do (i.e., draw ambivalent concepts) while drawing CAMs. For example, it could be the case, that you fear that a large number of possible features would be too demanding (cognitively or from a time perspective) for your participants, you can easily disable certain features, like the ability to draw unidirectional relations or inhibiting connections. 

To this end, a "researcher view" of the CAM board was implemented. There, it is possible to create, position and fix (i.e., impossibility to move a concept) elements. Once the structure is ready, click on “export” to create a CAM.json including all the different elements as well as the configuration of the project (see in detail [Set up study](Set up study.md)).


***
Define your config file
------------

Within the administrative panel, after you have logged in, you can click on the "C.A.M.E.L. (researcher view)" button at the top. After you have drawn your default CAM, which should be presented to the participants (see details in [Set up study](Set up study.md)), you can click on the "gear symbol" (top left) to define the configuration of your CAM study. 


**Parameter you can change using the user interface:** 

| Parameter   |      Meaning      |  Possible values |
|----------|:-------------|:------:|
| #ConNumNodes    | Number of concepts a participant needs to draw before <br> she / he is can save the CAM. | 1-50<sup>1</sup> |
| #MaxLengthWords | Maximum number of words allowed for each concept.   |  1-5<sup>2</sup> |
| #MaxLengthChars | Maximum number of characters allowed for each concept. | 30-300 |
| #hideArrows | If ON possible to draw arrows / directed connections. | ON / OFF |
| #BidirectionalDefault | Only makes sense if #hideArrows is set to ON, <br> as default the drawn connection is bidirectional. | ON / OFF |
| #showOnlyPosSlid | If ON possible to draw supporting connections. | ON / OFF |
| #hideAmbivalent | If ON possible to draw ambivalent concepts. | ON / OFF |
| #cameraFeature | If ON a splotlight feature is included to move the drawing <br> screen. If participants move their mouse to the edges the <br> drawing screen is moved to the respective side. | ON / OFF |
| #fullScreen | If ON study is set to fullscreen mode and paradata is <br> collected (defocus, focus events). | ON / OFF |
| #setLanguage | Set the language of the C.A.M.E.L. interface: | English, <br> German, <br> Spanish, <br> Chinese |


<sup>1</sup>Maxmimum number is restricted because the drawing space is limited. In the future, 3D environments will be implemented.

<sup>2</sup>It is **highly recommened to set this value to 1-3** if you are aiming to summarize / aggregate the CAM data. Instruct participants to avoid writing sentences and to draw instead multiple concepts. 

*Remark: It is not recommended to write directly into the config file. Certain configurations are set to default values and should not be changed. By programming your CAM <a href="https://camtools-documentation.readthedocs.io/en/master/Set%20up%20study/#program-on-scratch" target="_blank">on scratch</a> you are able to set reminders to program even adaptive designs.*

***
Data-structure of CAMs
----------------



The CAM itself is a Java Script object which is temporarily stored on the client-side. Every CAM, concept or connector is a Java Script class, whereby the *constructer* is initializing a single instance of that respective class. Within the arrays <code>nodes</code> and <code>connectors</code>, all the drawn (or deleted) concepts (nodes) respective connectors (edges) are stored.


In the following, all the parameters of the *constructer* of the CAM, concept and connector is explained: 


**Cognitive-Affective Map** has the following data structure when initialized, whereby the single parameters are explained below:


```js
    constructor() {
        this.idCAM = uuid.v4();
        this.creator = uuid.v4();
        this.projectCAM = config.CAMproject;
        this.defocusCAM = null;
        this.date = (new Date).getTime();
        this.nodes = [];
        this.connectors = [];
        this.currentID = null;
        this.currentNode = null;
        this.hasSelectedNode = false;
        this.currentConnector = null;
        this.hasSelectedConnector = false;
        this.readyToMove = false;
        this.isIncoming = false;
    }
```

| Parameter   |      Meaning      |  Application |
|----------|:--------|:---------|
| idCAM    | Random character string (ID) that is assigned <br> by the C.A.M.E.L. software to the CAM. | Unique identifier. |
| creator   | Character string that is stored by the <br> researcher. | **Unique ID** to identify <br> participants between study <br> parts. |
| projectCAM  | Name of current project. | <i>internal</i> <br> (information not needed) |
| defocusCAM | Array which stores defocus events, <br> when <code>#fullScreen</code> is set to <code>TRUE</code> | Check if a participant left <br> fullscreen during the CAM <br> study part. |
| date  | Date of CAM initialization. | Starting point of drawing the <br> CAM. |
| nodes | Array which stores all concepts. | Array includes visible and <br> deleted concepts. |
| connectors | Array which stores all connectors. | Array includes visible and <br> deleted connectors. |
| currentID | Get currrent ID of  (open dialog) element. | <i>internal</i> |
| currentNode | Get focused concepts. | <i>internal</i> <br> <code>NULL</code> if no concept is clicked <br> on. |
| hasSelectedNode | <code>TRUE</code> if participant focused a concept. | <i>internal</i> |
| currentConnector | Get focused connectors. | <i>internal</i> <br> <code>NULL</code> if no connector is clicked on. |
| hasSelectedConnector | <code>TRUE</code> if participant focused a connector. | <i>internal</i> |
| readyToMove | <code>TRUE</code> if concept (single click) is ready to move. | <i>internal</i> <br> to validate the process <br> of moving concepts |
| isIncoming | <i>internal</i> (tried out WebSocket) | <i>internal</i> <br> to enable simultaneous <br> collaboration  |

<br>

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
    }
```

| Parameter   |      Meaning      |  Application |
|----------|:--------|:---------|
| id    | Random character string that is assigned by <br> the C.A.M.E.L. software for each drawn <br>concept. | Unique identifier. |
| value    | Valence given by the participant ranging <br>from [-3,3]. | To compute the average valence <br> of a CAM. |
| text    | Text written by the participant. | Get meaning of drawn <br> concept. |
| comment  | Comment given by the participant. | Support interpretation of drawn <br> concept. |
| position |  <code>{x:,y:}</code> coordinate of the concept. | To compute the distance <br> between concepts. |
| isActive |  <code>TRUE</code> statement if concept was not deleted. | All deleted concepts are not <br> visible and marked by a <code>FALSE</code> <br>statement. |
| date  | Date of creation. | Trace the sequence of the <br>drawing process. |
| kind    | Type of element. | <i>internal</i> |
| isSelected    | If current concept is selected. | <i>internal</i> |
| isConnectorSelected | If connector adjacent to concept is selected. | <i>internal</i> |
| isDraggable | If concept is moveable. | Defined by researcher in <br>advance. |
| isDeletable | If concept is deletable. | Defined by researcher in <br>advance. |
| hasElementMoved | Controls if the element has been moved or<br> just selected. | <i>internal</i> |
| eventLog | Every interaction with the concept is <br>recorded. | Create animated videos of <br>drawing process. |
| isTextChangeable | If text of concept is changeable. | Defined by researcher in <br>advance. |

<br>

**Connectors** (edges) drawn in CAMs have the following data structure, whereby the single parameters are explained below:

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

| Parameter   |      Meaning      |  Application |
|----------|:--------|:---------|
| id    | Random character string that is assigned by <br> the C.A.M.E.L. software for each drawn <br>connector. | Unique identifier. |
| value    | Strength of connector given by the participant <br>ranging from [-3,3]. | Compute network indicators <br>of weighted network and <br>check type of connection. |
| source | Outgoing connection of a concept to a target. | <i>internal</i> <br> (indicate a directional relationship) |
| target | Incoming connection of a concept from a source. | <i>internal</i> |
| agreement | Shape of connecting line (solid = strengthening <br>connections, dashed = inhibitory connections). | Solid lines have positive values [1,3], <br>dashed lines have negative values [-3,-1] |
| isActive |  <code>TRUE</code> statement if connector was not deleted. | All deleted connectors are not <br> visible and marked by a <code>FALSE</code> <br>statement. |
| date  | Date of creation. | Trace the sequence of the <br>drawing process. |
| kind    | Type of element. | <i>internal</i> |
| isSelected    | If current connector is selected. | <i>internal</i> |
| intensity    | Thickness of line. | <i>internal</i> <br> defined by global variable <br>"IncreaseSliderIntensity" |
| isDeletable | If concept is deletable. | Defined by researcher in <br>advance. |
| isOver | If mouse if hovering over connection. | <i>internal</i> to highlight connection |
| isBidirectional | <code>TRUE</code> if connection is bidirectional. | To differentiate between uni- and <br>bidirectional connections. |
| eventLog | Every interaction with the connector is <br>recorded. | Create animated videos of <br>drawing process. |




***
Implemented features
----------------

The following features are implemented to increase data quality: 

* a participant cannot save the CAM if any of the configurations regarding <code>#ConNumNodes</code>, <code>#MaxLengthWords</code> and <code>#MaxLengthChars</code> is violated
* by applying the breadth-first search algorithm it is prevented that participants can save CAMs with disconnected components (cluster of concepts)
* the predefined concepts cannot be moved if <code>isDraggable</code> is set to FALSE, cannot be deleted if <code>isDeletable</code> is set to FALSE and text cannot be changed if <code>isTextChangeable</code> is set to FALSE
* the predefined connectors cannot be deleted if <code>isDeletable</code> is set to FALSE


> => If a participant violates any of the configuration a pop-up informs the participants what she / he has done wrong.


Using the Java Script library Cytoscape all kinds of additional real-time pre- or post-processing analysis are possible in real-time and it is possible to implement adaptive study designs (see <a href="https://camtools-documentation.readthedocs.io/en/master/Set%20up%20study/#example-studies" target="_blank">example study section</a>).





***
Future features
----------------


Multiple extensions of the C.A.M.E.L. software are currently tested: currently we are implementing **simultaneous collaboration** in C.A.M.E.L., as such that more than one person can work on the identical CAM at the same time. Tweaking the software it was already possible to run **sequential collaboration studies**, whereby a CAM is consecutively changed. A **graphical database** (e.g. using Neo4j) was recently implemented. Using Neo4j queries can be made directly on summarized CAM data, e.g., “How often was the concept "own car" associated with "flexibility"?”. Finally **3D visualizations** for large CAMs are set up (e.g. using Unity also virtual reality experiment would be possible).

<br>
If you are missing a specific feature for your study and do not know how to implement it, we are happy to hear from you: <cam.contact@drawyourminds.de>