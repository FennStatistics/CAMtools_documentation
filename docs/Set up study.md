<style>
.centerImg{
    display: block;
    margin: 0 auto;
}
</style>

Set up study
============

You first apply (if you do not already have) for an account, log in with your credentials and create an experiment using our dashboard. It is highly recommended to read the complete "General procedure" and "Possible CAM study designs" parts before starting collecting data. It is also possible set up your study "on scratch" and use your own server, see final section.


General procedure
-----------------

If you want to set up a CAM study using the administrative panel you need to do the following steps on our webpage <a style="font-size: 18px;" href="https://drawyourminds.de/" target="_blank">https://drawyourminds.de/</a>

1. If you do not have an account please go to the register page and create yourself an account
2. After we have provided you with an account, please go to the log in page
3. After logging in, you will see the dashboard on which it is possible to: 
    - ADD EXPERIMENT: create a CAM experiment by defining the desired parameters of your CAM study
    - Link Participants: send the link of your experiment directly to participants or use the link within an online-experiment (it is <b>important to add a unique participant ID to your CAMs</b>, see last step)
    - Enter Experiment: enter your CAM experiment to get real-time statistics of your collected data
4. Click on the button "ADD EXPERIMENT" at the lower center of the page, in the pop-up you can change the following:
    - Provide a name for the CAM study: name of your CAM study
    - Paste JSON File Content: paste the JSON file of your CAM study, including the pre-defined concepts / connectors and the configuration (see step 5.)
    - Provide a redirect link for your participants (mandatory): link to redirect participants after they have drawn their CAM
5. To configure your CAM, please close the pop-up and click on the button "C.A.M.E.L." at the top left (check out the [Cognitive-Affective Map *extended logic*](Cognitive-Affective Map extended logic.md) page for details); two steps are needed: 
    * first step: draw your default CAM: start with changing the central pre-defined concept. It is **highly recommended to set the pre-defined concepts to not deletable, changeable and movable**, using the black researcher buttons at the bottom of the concept dialog (pops up if you double click on a drawn concept)<sup>1</sup>. Further you can drawn connections and set them to not deletable.
    * second step: after you have drawn your default CAM, click on the "gear symbol" (top left) to define the configuration of your CAM study (see details in <a href="https://camtools-documentation.readthedocs.io/en/master/Cognitive-Affective%20Map%20extended%20logic/#define-your-config-file" target="_blank"> Define your config file</a>)

    => when you are happy with your default CAM and the configuration please copy the generated configuration file<sup>2</sup> to the pop-up of the administrative panel in the middle text box where is written "Paste the JSON content here"<sup>3</sup>

6. Finally, give your CAM study a name and provide a link to which participants should be redirected<sup>3</sup>
7. To check if everything went well, you should try out once your defined C.A.M.E.L. study: (a) if your participants are redirected from a previous study part (e.g., where you describe your participants how to draw a CAM) you need to pass the unique ID of the participant to the **URL parameter "participantID"**, (b) if you present the participants a study part after they have drawn a CAM (e.g., socio-demographic questions) make sure to save the URL parameter participantID in your study
    * you could check the (b) step by just clicking "Copy link" and add a random participant ID after the URL parameter like "&participantID=11111", make sure to save the ID "11111" in your data set

<sup>1</sup>**researcher functionalities:**
Use the black researcher buttons at the bottom of the concept or connector dialog page to set defined concepts or connectors to not deletable, movable (concept cannot be moved) or changeable (content of concept cannot be changed):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/researcher_functionalities_concepts_new.jpg" alt="researcher functionalities picture missing" style="height:300px;" class="centerImg">

<sup>2</sup>**generated configuration file:**
After you have drawn your default CAM and configured your C.A.M.E.L. study, you can copy the text by using the button "Copy text" (red rectangle), or if this is not working copy the text manually from the textbox (blue arrow):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/generated_configfile.jpg" alt="generated config file picture missing" style="height:300px;" class="centerImg">

<sup>3</sup>**Add CAM study (within administrative panel):**
Copy the generated configuration file to the administrative panel within the cental textbox (yellow arrow). It is important to not change this file. The title of your study can be added under Name (red arrow) and if you want to redirect your particpants to a further study you can provide the redirect link (green arrow):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/adminPanel_addExperiment_new.jpg" alt="admin panel add experiment picture missing" style="height:300px;" class="centerImg">



---

Instructions
------------

If you want to explain your participants how to draw a CAM you could use our text instructions, which can be downloaded from GitHub (currently in German and English): <a href="https://github.com/Camel-app/DataCollection/tree/main/CAM%20instructions" target="_blank">https://github.com/Camel-app/DataCollection/tree/main/CAM%20instructions</a>

> Please read the readme file on the GitHub page for detailed explenations of the instructions.

---

Possible CAM study designs
----------------------------------------------

CAMs can be used in a multitude of study designs, ranging from a one time elicitation to multiple times of measurement, from letting participants freely associate with no pre-defined concepts to having participants build a network with-, and ascribe affective value to predefined concepts only[@livanec_whos_2022]. How the initial concepts are placed also has an influence on the resulting arrangement of concepts and graphs in subjects CAMs, which can be used to evoke different network topologies.

By independently adjusting, for example, whether participants can add, adjust or delete concepts, you are able to give participants a predefined set of concepts that cannot be altered and ask them to connect the concepts to best represent their own cognitive representation of these concepts. This would provide you with a standardized set of concepts which allows for easy interpretation and comparison of how different participants / groups decide to structure and connect them. On the other end of the spectrum, a completely open or explorative design is possible, too. If you are more interested in eliciting an unbiased cognitive-affective representation about a certain concept, you can provide participants with a limited amount of / one initial concept(s) (or even none at all!) and ask them to freely add concepts to the CAM as they see fit.

From the vast amount of possible CAM study designs, the following are just an example to showcase the many different possibilities CAMs offer in research:

<h3>Different (experimental) designs:</h3>

CAMs can be used in multiple ways and during multiple stages of the research process. The following options can give an idea of the diverse opportunities CAMs can offer in research:


**CAM as graphical representation:**

*  CAMs as a <b>one time elicitation</b> of the cognitive-affective representation a person/a group has about a certain concept / topic<sup>e.g</sup> [@mansell_measuring_2021]


**quantitative/network parameters and qualitative analyses of CAMs as measurements ("dependent variables") in empirical/experimental studies:**

* CAMs as a <b>dependent variable in a pre-post intervention design</b>, where participants either draw two separate CAMs before and after an intervention or have the chance to adjust the first CAM at a later point in time<sup>e.g</sup> [@reuter_leisure_2021]
* CAMs in a <b>mixed method design</b> to augment questionnaire data with rich information about cognitive-affective representations and the possibility of freely associating, away from prespecified answer options<sup>e.g</sup> [@fennIdentifyingKeypsychologicalFactors2023]

**CAM as independent variable to influence/inform participants:**

* Using <b>CAMs themselves as an intervention</b>, where participants are shown a CAM that is not their own and the influence of this exposure to somebody elses representation is assessed<sup>e.g</sup> [@gros_camediaid_2021]
* CAMs in an <b>adaptive design</b>, where participants receive an adaptive intervention based on an automated real time analysis of the CAM they have just drawn (e.g. specific intervention depending on mean valence of the CAM).


<br>
<h3>Different network topologies:</h3>


Analyzing network parameters of CAMs is a promising way of gaining quantitative insight into participants cognitive-affective representations of a concept. When setting up a CAM study, it is possible to predefine (or choose to not predefine) central concepts as a “starting CAM” which every participant will receive as a basis to build their own CAM around. Preliminary results show that the layout and connections (referred to as the **topology of a network** in telecommunication science) of this starting CAM has an influence on the type of layout participants are most inclined to draw when constructing their CAM. In telecommunication technology, different network designs have specific properties and different X-ities like evolvability, scalability and adaptability of a network in a future stage (~ the finished CAM of a participant) depend on the initial network design (~ the predefined CAM given to every participant as a starting point). Knowing this, the <b>design of the “starting CAM” should be consciously chosen</b> as it might have an influence on the network parameters of participants CAMs. Multiple <b>initial network topologies</b> are possible to specify with a staring CAM:


* <b>Single concept in the middle</b>: this design likely evokes a network which is equivalent to a physical <i>star topology</i>, where all concepts are connected to a central concept. This often results in high local and global density.
* <b>Two contradictory concepts</b>: specifying two contradictory concepts as a starting point is an interesting way of analyzing the perception of opposite poles or concepts. The two sub-networks of the resulting CAMs can be analyzed and compared separately in a future analyzing step (see module “slice CAMs” within [CAM-App](CAM-App.md)).
* <b>Tree Topology</b>: an initial hierarchical arrangement of concepts supposably nudges participants towards “adding leaves to a predefined tree” in a hierarchical manner, differentiating and diversifying the initial network hierarchically. In contrast to star networks, tree networks typically have low overall and local density.
* <b>No predefined concepts</b>: letting participants start off with clean slate typically results in a partially connected <i>mesh topologies</i>.


<b>Single concept in the middle</b>:
<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/networkTopology_star.jpg" alt="star missing" style="height:300px; width: 500px;" class="centerImg">

<b>Two contradictory concepts</b>:
<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/networkTopology_ClusteredBus.jpg" alt="clustered bus missing" style="height:300px; width: 500px;" class="centerImg">

<b>Tree Topology</b>:
<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/networkTopology_tree.jpg" alt="tree missing" style="height:300px; width: 500px;" class="centerImg">

Example studies
---------------

- complete study regarding relatively unknown topic "Stratospheric Aerosol Injection"; here included instructions CAM, scenario text, preview CAM, C.A.M.E.L., technical feedbackquestions after drawing: <a href="https://studien.psychologie.uni-freiburg.de/publix/qDU7aBJyuQz?PROLIFIC_PID=testerID" target="_blank"> complete study "Stratospheric Aerosol Injection"</a>
- complete study regarding well known topic "Covid-19 pandemic"; here included instructions CAM, preview CAM, C.A.M.E.L. (reminder, initial pop-up included), technical feedbackquestions and one adaptive question after drawing: <a href="https://studien.psychologie.uni-freiburg.de/publix/JiWZUbeXjfo?PROLIFIC_PID=testerID" target="_blank"> complete study "Covid-19 pandemic"</a>
- adaptive study design: <a href="https://studien.psychologie.uni-freiburg.de/publix/gv3Q8UvdRLu" target="_blank"> adaptive study design </a>
    - simply draw 2 concepts with pos. / neg. valence and connect them and click on disk symbol to save. By adaptive designs any query you can imagine (like query for the most central concept, certain neighbourhoods of given concepts, the re-presentation of the drawn CAM etc.) are possible. We also have no data limitation here as it can use functions of JATOS internally (so-called "multi-component study"), which is a server hosted in the Psychology departement within the University of Freiburg.


Program "on scratch"
---------------

Before reading this section, please read the documentation of the [Cognitive-Affective Map *extended logic*](Cognitive-Affective Map extended logic.md) data collection tool.

**Pre-defined elements:**

The visible content of the CAM resides within an SVG container, which is initially constructed by the Java Script function "defaultCAM()". This function can be dynamically modified to display any desired set of pre-defined concepts:

* to **add concepts** within the function defaultCAM(), you can write 
 
```js
    CAM.addElement(new NodeCAM(0, "central concept", {
        x: 600,
        y: 400
    }, false, false, false));
```

, which would create a concept which is not moveable (first false statement), deletable and the text is not changeable. By setting the "false" statements to "true" you could allow participants to move the concept and so on.

* to **add connectors** within the function defaultCAM, you can write 

```js
    var connector = new ConnectorCAM();
    connector.establishConnection(CAM.nodes[0], CAM.nodes[1], IncreaseSliderIntensity, true);
    CAM.addElement(connector);
    CAM.connectors[0].isDeletable = false;
```
, which creates a connection between the first and second drawn concept. The "true" statement represents a strengthening / agreeing connection ("false" a inhibitory / disagreeing connection). The attribute "isDeletable" can be set to "false" if you do not want participants to delete the pre-defined connectors.



**Configuration:**

The configuration of the CAM study is specified in the "configfile", a simple Java Script object that can be freely modified (also in real-time or by URL parameters):

```js
var config = {
    CAMproject: "projectName", // "proj_" + uuid.v4(), // necessary for server (see ERM) !!!
    ConNumNodes: 10, // number of nodes necessary to draw
    
    hideArrows: false, // if false = possible to draw arrows
    BidirectionalDefault: false, // if true the default connection is bidirectional

    hideAmbivalent: true, // if false = possible to draw ambivalent node
    showOnlyPosSlid: false, // if true = show only slider for agreement (+1 - +3), only works if hideArrows is set to true
    
    MaxLengthWords: 3, // maximum number of words for each concept
    MaxLengthChars: 40, // maximum number of characters for each concept
    LengthSentence: 14, // include breaklines if >= X characters
    LengthWords: 8, // include breaklines after each word with cumsum >= X characters

    ShowResearcherButtons: false, // if true = show researcher functionalities

    cameraFeature: false, // include camera / splotlight feature to move screen

    setLanguage: "English", // set language of your CAM study, e.g. French 

    fullScreen: false, // if true = study in fullscreen mode + paradata
    showNotPopupStart: true, // true = no pop up shown; only working if fullScreen is set to true

    AdaptiveStudy: true, // run as adaptive study 
    ADAPTIVESTUDYurl: "http://example.org/", // URL the CAM data should be append to !!!

    setReminder: false, // if true = after X ms 2 reminder pop up

    surpressSaveCAMpopup: false // if set to true no popup is shown when downloading a vector graphic of the CAM (for automation via the CAM2Image tool)
}

// global variable
var usingSupabase = true;
var usingJATOS = false;
```

In the following, only parameters are explained which are not described in the <a href="https://camtools-documentation.readthedocs.io/en/master/Cognitive-Affective%20Map%20extended%20logic/#define-your-config-file" target="_blank"> Define your config file</a> section of the documentation:


* "CAMproject:" simply choose a name, which is stored in your CAM data
* "setReminder:" if set to true two reminders pop up after X ms, please adjust the content and time for your reminder in the .js file "setReminder"
* "surpressSaveCAMpopup:" if set to true no pop-up is show if CAM is saved as an .svg file

If you are using a <a href="https://www.jatos.org/" target="_blank">JATOS</a> server (or others), you are able to set up "adaptive" studies, which pre-process the CAM data in real-time, whereby you should adjust the following parameters (see simple example in the "Example studies" section):

* "AdaptiveStudy:" set to "true" (default)
* "ADAPTIVESTUDYurl:" provide the link to redirect your participants
* set the global variable "usingJATOS" to true and "usingSupabase" to false.


Feel free to  <a href="https://github.com/Camel-app/DataCollection" target="_blank">download the C.A.M.E.L. software</a> and adjust it according to your needs (MIT licence: use software without any liability or warranty).


References
----------
