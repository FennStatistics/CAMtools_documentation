<style>
.centerImg{
    display: block;
    margin: 0 auto;
}
</style>

Set up study
=====

General procedure
------------

If you want to set up a C.A.M.E.L. study using the interface you need to do the following steps: 

1. If you do not have an account please <a href="https://camel-host.herokuapp.com/apply-account" target="_blank"> apply here </a>
2. After we have provided you with an account, please <a href="https://camel-host.herokuapp.com/register" target="_blank"> log in </a> (Remark: currently we using a free version soltuion and there could be a delay up to 30 seconds)
3. Click on the button "Design a CAM" at the top right to get redirect to our C.A.M.E.L. software (Remark: if you do not see this button, please refresh your browser page):

    * first step: draw your default CAM: Start with changing the central predefined concept. It is **highly recommended to set the predefined concepts to not deletable, changeable and movable**, using the black researcher buttons at the botton of the concept dialog (pops up if you double click on a drawn concept)<sup>1</sup>  
    * second step step: after you have drawn your default CAM click on the "gear symbol" (top left) to define the configuration of your CAM study (see details in [Cognitive-Affective Map extended logic](Cognitive-Affective Map extended logic.md))

4. when you are happy with your default CAM and the configuration please copy the generated configuration file<sup>2</sup> to the administrative panel in the middle text box where is written "Paste your cam model here"<sup>3</sup>
5. Finally, give your CAM study a name and provide a link (if necessary) to which participants should be redirected<sup>3</sup>
6. To check if everything went well, you should try out once your defined C.A.M.E.L. study, just click on "Copy link" and add a random participant ID after the URL parameter like "11111": `&participantID=11111`. For your participants you need to add an participantID within your first study using for example simple java script functions (see study examples and code snippets in next section) and if you redirect your particpants to a subsequent study you also need to save again the participantID.

<sup>1</sup>**researcher functionalities:**
Use the black researcher buttons at the botton of the concept or connector dialog page to set defined concepts or connectors to not deletable, movable (concept cannot be moved) or changeable (content of concept cannot be changed):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/researcher_functionalities_concepts.jpg" alt="researcher functionalities picture missing" style="height:300px;" class="centerImg">

<sup>2</sup>**generated configuration file:**
After you have drawn your default CAM and configured your C.A.M.E.L. study, you can copy the text by using the button "Copy text" (red circle), or if this is not working copy the text manually from the textbox (blue arrow):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/generated_configfile.jpg" alt="generated config file picture missing" style="height:300px;" class="centerImg">

<sup>3</sup>**Add CAM study (within administrative panel):**
Copy the generated configuration file to the administrative panel within the cental textbox (red arrow). It is important to not change this file. The title of your study can be added under Name (first blue arrow) and if you want to redirect your particpants to a further study you can provide the redirect link (second blue arrow):

<img src="https://raw.githubusercontent.com/FennStatistics/CAMtools_documentation/master/docs/media/adminPanel_addExperiment.jpg" alt="admin panel add experiment picture missing" style="height:300px;" class="centerImg">



Example studies
------------

blabla

***
Possible Cognitive-Affective Map study designs
------------

blabla

***
Instructions
------------

blabla

***
Register
------------

blabla