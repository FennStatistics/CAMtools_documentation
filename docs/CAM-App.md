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
| CAM    | Character string (ID) that is assigned by the C.A.M.E.L. software to <br> the CAM. |
| participantCAM   |  ID that is assigned by the researchers to the CAM <br> (usually ID is generated in previous study part). |
| id    | Random character string (ID) that is assigned by the C.A.M.E.L. software to <br> the single node. |
| text   |  Text written by the participant. |
| value    | Valence given by the participant ranging from [-3,3]. |
| comment   |  Comment given by the participant. |
| date   |  Date of creation. |
| x_pos   |  x-coordinate of the drawn concept. |
| y_pos   |  y-coordinate of the drawn concept. |
| predefinedConcept   |  If any of the following 3 variables are <code>TRUE</code>, the concept is predefined by <br> the researcher. |
| isDraggable   | If concept is moveable (set by researcher). |
| isDeletable   | If concept is deletable (set by researcher). |
| isTextChangeable   |  If text of concept is changeable (set by researcher). |
| isActive   |  <code>TRUE</code> if concept was not deleted by participant. |

Remark: By default all concepts deleted by the participants are removed from the nodes data set (isActive is a constant only containing <code>TRUE</code>).

<br>

**Connectors data set** contains all connectors drawn in the CAM and the following variables are considered in the CAM-App:

| Parameter   |      Meaning   | 
|----------|:----------------|
| CAM    | Character string (ID) that is assigned by the C.A.M.E.L. software to <br> the CAM. |
| participantCAM   |  ID that is assigned by the researchers to the CAM <br> (usually ID is generated in previous study part). |
| id     | Random character string (ID) that is assigned by the C.A.M.E.L. software to <br> the single connector. |
| date   |  Date of creation. |
| daughterID    | ID of the node to which the connection is pointing. |
| motherID   |  ID of the node from which the connection originates. |
| intensity   |  Thickness of line. |
| agreement   |  <code>TRUE</code> if it a strengthening connection (solid line), <code>FALSE</code> if it is a <br> inhibitory connection (dashed line). |
| isBidirectional   |  <code>TRUE</code> if connection is bidirectional. |
| isDeletable   | If concept is deletable (set by researcher). |
| isActive   |  <code>TRUE</code> if connector was not deleted by participant. |

Remark: By default all connectors deleted by the participants are removed from the connectors data set (isActive is a constant only containing <code>TRUE</code>).

***
Implemented features overview
----------------


In our experience it is necessary to guide the researcher (or assistent) through the analysis process, because the analysis of CAM data is relatively difficult and the individual modules build on each other logically. The following figure visualizing all the implemented features seperated for the (a) pre-processing and (b) analysis part: 

<p style="color:red;">!!! add picture</p>

As visible in the picture the researcher needs always to upload the raw CAM data (and the protocol) and to draw all the CAMs. 


***
Import, draw CAMs part
----------------

blabla


***
### Import CAM data
---

blabla

<br>

**Internal the following R functions are applied**:

```r
create_CAMfiles(datCAM = raw_CAM, reDeleted = TRUE, verbose = FALSE)

create_ValenceFiles(datBlocks = blocks, datLinks = links)
```

* create_CAMfiles(): takes raw CAM data as input, removes all the deleted concepts / connectors (<code>reDeleted</code>), not printing this process to the console (<code>verbose</code>)
* create_ValenceFiles(): takes raw CAM data from Valence software as input; Valences files are seperate <code>.csv</code> files for blocks (concepts) and links (connectors)


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