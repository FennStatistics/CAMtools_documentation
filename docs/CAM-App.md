CAM-App
=====

There are two **possibilities to run the CAM-App**:

* locally: 
    * download the CAM-App from the GitHub repository: <a href="https://github.com/Camel-app/DataAnalysis" target="_blank">https://github.com/Camel-app/DataAnalysisR</a> (use <code>.git</code> or download it manutally -> green button "<>Code" -> "Download ZIP")
    * if not already installed, download <a href="https://cran.r-project.org/" target="_blank">R</a> and <a href="https://posit.co/download/rstudio-desktop/" target="_blank">RStudio</a>
    * open the file <code>app.R</code>, install packages if needed, click on "Run App"
* online (! disadvantage: App is slower): 
    * open the link: <a href="https://fennapps.shinyapps.io/CAMtools_CAMapp/" target="_blank">https://fennapps.shinyapps.io/CAMtools_CAMapp/</a>
    
<br>

Within the CAM app you are **guided and within every implemented module** (see below) you have module specific information ("> Information" button in the sidebar panel). The single modules / functionalities are explained in more detail below with specific examples. 
<br>
If you want **to change or extend single functions**, please check out the readme file of the folder "additional scripts" in the GitHub repository: <a href="https://github.com/Camel-app/DataAnalysis/tree/main/additional%20scripts" target="_blank">https://github.com/Camel-app/DataAnalysis/tree/main/additional%20scripts</a>



***
Data-structure of uploaded CAMs
----------------

After uploading your raw CAM data (see next section) you can click on the module specific option "> Descriptive" to get an overview over your uploaded data in the form of dynamic tables. Here you can see, that a CAM data set consists of a nodes (also called "concepts") and connectors data set (for details of the data structure within the C.A.M.E.L. software see <a href="https://camtools-documentation.readthedocs.io/en/master/Cognitive-Affective%20Map%20extended%20logic/#data-structure-of-cams" target="_blank">"Data-structure of CAMs"</a>
): 



**Nodes data set** contains all concepts drawn in the CAM and the following variables are considered in the CAM-App:

| Parameter   |      Meaning   | 
|----------|:----------------|
| CAM    | blub. |
| participantCAM   |  blub. |
| id    | blub. |
| text   |  blub. |
| value    | blub. |
| comment   |  blub. |
| date   |  blub. |
| x_pos   |  blub. |
| y_pos   |  blub. |
| predefinedConcept   |  blub. |
| isDraggable   |  blub. |
| isDeletable   |  blub. |
| isTextChangeable   |  blub. |
| isActive   |  blub. |

Remark: By default all concepts deleted by the participants are removed from the nodes data set (isActive is a constant only containing <code>TRUE</code>).

<br>

**Connectors data set** contains all connectors drawn in the CAM and the following variables are considered in the CAM-App:

| Parameter   |      Meaning   | 
|----------|:----------------|
| CAM    | blub. |
| participantCAM   |  blub. |
| id    | blub. |
| date   |  blub. |
| daughterID    | blub. |
| motherID   |  blub. |
| intensity   |  blub. |
| agreement   |  blub. |
| isBidirectional   |  blub. |
| isDeletable   |  blub. |
| isActive   |  blub. |

Remark: By default all concepts deleted by the participants are removed from the connectors data set (isActive is a constant only containing <code>TRUE</code>).

***
Implemented features overview
----------------

blabla


***
Import, draw CAMs part
----------------

blabla


***
### Import CAM data
---

blabla



***
### Import protocol
---

blabla


***
### Draw CAMs
---

blabla

***
***
Pre-processing part
----------------

blabla


***
### Approximate matching
---

blabla


***
### Searching terms
---

blabla


***
### Search for synonyms
---

blabla


***
### Apply word2vec model
---

blabla


***
### 5-step procedure to summarize CAM data
---

blabla



***
***
Reliability module
----------------

blabla



***
### Train raters for summarizing of concepts
---

blabla



***
### Compute inter-rater reliability
---

blabla


***
***
Analysis part
----------------

blabla


***
### Network Indicators
---

blabla


***
#### Compute network indicators
---

blabla


***
#### Compute neighborhood network indicators
---

blabla



***
### Word outputs overall
---

blabla


***
#### Create wordlist
---

blabla


***
#### Create wordcloud
---

blabla



***
### Word outputs single words
---

blabla


***
#### Get graphics and summary statistics for concept by concept
---

blabla

***
#### Get summary statistics for all concepts
---

blabla




***
### Aggregate CAMs
---

blabla




***
### Clustering CAMs
---

blabla


***
#### Concept co-occurrences
---

blabla


***
#### Valence co-occurrences
---

blabla



***
### Slice CAMs
---

blabla




***
### Get Report
---

blabla


***
***
Future features
----------------

blabla


<br>
If you are missing a specific feature for your study and do not know how to implement it, we are happy to hear from you: <cam.contact@drawyourminds.de>