<style>
.centerImg{
    display: block;
    margin: 0 auto;
}
</style>

Set up study
============



Register
--------

You first apply (if you do not already have) for an account, log in with your credential and create an experiment using our dashboard. 


General procedure
-----------------


<p style="color:red;">!!! change links</p>

If you want to set up a C.A.M.E.L. study using the interface you need to do the following steps:

1. If you do not have an account please `<a href="https://camel-host.herokuapp.com/apply-account" target="_blank">` apply here `</a>`
2. After we have provided you with an account, please `<a href="https://camel-host.herokuapp.com/register" target="_blank">` log in `</a>`
3. After logged in you will see the dashboard, here it is possible to: 
    - Add experiment: create a CAM experiment by defining the desired parameters of your CAM study
    - Copy link: send the link of your experiment directly to participants or use the link within an online-experiment (add a unique participant ID to your CAMs)
    - Status: set the status of your experiment (it is only possible to participate in active experiments)
4. ............................ <p style="color:red;">!!! change general procedure after adjustements</p>
3. Click on the button "Design a CAM" at the top right to get redirect to our C.A.M.E.L. software (Remark: if you do not see this button, please refresh your browser page):

   * first step: draw your default CAM: Start with changing the central predefined concept. It is **highly recommended to set the predefined concepts to not deletable, changeable and movable**, using the black researcher buttons at the botton of the concept dialog (pops up if you double click on a drawn concept)`<sup>`1`</sup>`
   * second step step: after you have drawn your default CAM click on the "gear symbol" (top left) to define the configuration of your CAM study (see details in   `<a href="https://camtools-documentation.readthedocs.io/en/master/Cognitive-Affective%20Map%20extended%20logic/#define-your-config-file" target="_blank">` config file`</a>`)
4. when you are happy with your default CAM and the configuration please copy the generated configuration file`<sup>`2`</sup>` to the administrative panel in the middle text box where is written "Paste your cam model here"`<sup>`3`</sup>`
5. Finally, give your CAM study a name and provide a link (if necessary) to which participants should be redirected`<sup>`3`</sup>`
6. To check if everything went well, you should try out once your defined C.A.M.E.L. study, just click on "Copy link" and add a random participant ID after the URL parameter like "11111": `&participantID=11111`. For your participants you need to add an participantID within your first study using for example simple java script functions (see study examples and code snippets in next section) and if you redirect your particpants to a subsequent study you also need to save again the participantID to match all your data.

`<sup>`1`</sup>`**researcher functionalities:**
Use the black researcher buttons at the botton of the concept or connector dialog page to set defined concepts or connectors to not deletable, movable (concept cannot be moved) or changeable (content of concept cannot be changed):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/researcher_functionalities_concepts.jpg" alt="researcher functionalities picture missing" style="height:300px;" class="centerImg">

`<sup>`2`</sup>`**generated configuration file:**
After you have drawn your default CAM and configured your C.A.M.E.L. study, you can copy the text by using the button "Copy text" (red circle), or if this is not working copy the text manually from the textbox (blue arrow):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/generated_configfile.jpg" alt="generated config file picture missing" style="height:300px;" class="centerImg">

`<sup>`3`</sup>`**Add CAM study (within administrative panel):**
Copy the generated configuration file to the administrative panel within the cental textbox (red arrow). It is important to not change this file. The title of your study can be added under Name (first blue arrow) and if you want to redirect your particpants to a further study you can provide the redirect link (second blue arrow):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/adminPanel_addExperiment.jpg" alt="admin panel add experiment picture missing" style="height:300px;" class="centerImg">



---

Instructions
------------

All the text instructions can be downloaded from GitHub (currently in German and English): `<a href="https://github.com/FennStatistics/CAMtools_documentation/tree/master/docs/media/CAM%20instructions" target="_blank">`https://github.com/FennStatistics/CAMtools_documentation/tree/master/docs/media/CAM%20instructions`</a>`

---

Possible Cognitive-Affective Map study designs
----------------------------------------------

CAMs can be used in a multitude of study designs, ranging from a one time elicitation to multiple times of measurement, from letting participants freely associate with no pre-defined concepts to having participants build a network with-, and ascribe affective value to predetermining concepts only[@livanec_whos_2022]. How the initial nodes are placed also has an influence on the resulting arrangement of nodes and graphs in subjects CAMs, which can be used to evoke different network topologies (Julius Metaanalyse?). From the vast amount of possible CAM study designs, the following are just an example to showcase the many different possibilities CAMs offer in research.

<h3>Different (experimental) designs:</h3>

CAMs can be used in multiple ways and during multiple stages of the research process, the following options can give an idea of the diverse opportunities CAMs can offer in research:

* CAMs as a `<b>`one time elicitation`</b>` of the cognitive-affective representation a person has about a certain concept`<sup>`e.g`</sup>` [@mansell_measuring_2021]
* CAMs as a `<b>`dependent variable in a pre-post intervention design`</b>`, where participants either draw two separate CAMs before and after an intervention or have the chance to adjust the first CAM at a later point in time`<sup>`e.g`</sup>` [@reuter_leisure_2021]
* Using `<b>`CAMs themselves as an intervention`</b>`, where participants are shown a CAM that is not their own and the influence of this exposure to somebody elses representation is assessed`<sup>`e.g`</sup>` [@gros_camediaid_2021]
* CAMs in a `<b>`mixed method design`</b>` to augment questionnaire data with rich information about cognitive-affective representations and the possibility of freely associating, away from prespecified answer options`<sup>`e.g`</sup>` [@fennIdentifyingKeypsychologicalFactors2023]

- CAMs in an `<b>`adaptive design`</b>`, where participants receive an adaptive intervention based on an automated real time analysis of the CAM they have just drawn (e.g. specific intervention depending on mean valence of the CAM).

<h3>Different network topologies:</h3>

Analyzing network parameters of CAMs is a promising way of gaining quantitative insight into participants cognitive-affective representations of a concept. When setting up a CAM study, it is possible to predefine (or choose to not predefine) central nodes as a “starting CAM” which every participant will receive as a basis to build their own CAM around. Preliminary results show that the layout and connections (referred to as the topology of a network in telecommunication science) of this starting CAM has an influence on the type of layout participants are most inclined to draw when constructing their CAM (source: computed Metaanalyse). In telecommunication technology, different network designs have specific properties and different X-ities like evolvability, scalability and adaptability of a network in a future stage (~ the finished CAM of a participant) depend on the initial network design (~ the predefined CAM given to every participant as a starting point). Knowing this, the `<b>`design of the “starting CAM” should be consciously chosen`</b>` as it might have an influence on the network parameters of participants CAMs. Multiple `<b>`initial network topologies`</b>` are possible to specify with a staring CAM:

* `<b>`Single node in the middle`</b>`: this design likely evokes a network which is equivalent to a physical `<i>`star topology`</i>`, where all concepts are connected to a central node. This often results in high local and global density.
* `<b>`Two contradictory concepts`</b>`: specifying two contradictory concepts as a starting point is an interesting way of analyzing the perception of opposite poles or concepts. The two sub-networks of the resulting CAMs can be analyzed and compared separately in a future analyzing step (see module “slice CAMs” within [CAM-App](CAM-App.md)).
* `<b>`Tree Topology`</b>`: an initial hierarchical arrangement of nodes supposably nudges participants towards “adding leaves to a predefined tree” in a hierarchical manner, differentiating and diversifying the initial network hierarchically. In contrast to star networks, tree networks typically have low overall and local density.
* `<b>`No predefined concepts`</b>`: letting participants start off with clean slate typically results in a partially connected `<i>`mesh topologies`</i>`.

`<b>`Single node in the middle`</b>`:
`<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/networkTopology_star.jpg" alt="star missing" style="height:300px;" class="centerImg">`

`<b>`Two contradictory concepts`</b>`:
`<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/networkTopology_ClusteredBus.jpg" alt="clustered bus missing" style="height:300px;" class="centerImg">`

`<b>`Tree Topology`</b>`:
`<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/networkTopology_tree.jpg" alt="tree missing" style="height:300px;" class="centerImg">`

Example studies
---------------

- complete study (here included instructions CAM, scenario text, preview CAM, CAMEL, technical feedbackquestions after drawing): `<a href="https://studien.psychologie.uni-freiburg.de/publix/qDU7aBJyuQz?PROLIFIC_PID=testerID" target="_blank">` complete study `</a>`
- adaptive study design: `<a href="https://studien.psychologie.uni-freiburg.de/publix/gv3Q8UvdRLu" target="_blank">` adaptive study design `</a>`
  - simply draw 2 concepts with pos. / neg. valence and connect them and click on disk symbol to save. By adaptive designs any query you can imagine (like query for the most central concept, certain neighbourhoods of given nodes, the re-presentation of the drawn CAM etc.) are possible. We also have no data limitation here as it can use functions of JATOS internally (so-called "multi-component study"), which is a server hosted in the Psychology departement within the University of Freiburg.


References
----------
