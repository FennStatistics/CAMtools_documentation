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
### Suffix notation
---
Internally the CAM-App attaches a suffix to summarized words (see below), whereby a suffix is placed after the end of a word. For example after summarizing the word "Cost", which was drawn by multiple participants, some participants rated the word as negative, neutral, ambivalent or even positive and the word would be internally represented as follows:  

```r
Cost_negative
Cost_neutral
Cost_ambivalent
Cost_positive
```

It is a source of confusion, but it is of most importance to distinguish between the semantics and the valence of a word. It is highly probable that a participant who rated the drawn concept "Cost" positive has something different in mind than a participant who rated in negatively.


***
Implemented features overview
----------------


In our experience it is necessary to guide the researcher (or assistent) through the analysis process, because the analysis of CAM data is relatively difficult and the individual modules build on each other logically. The following figure visualizing all the implemented features seperated for the (a) pre-processing and (b) analysis part: 

<p style="color:red;">!!! add picture</p>

As visible in the picture the researcher needs always to upload the raw CAM data (and the protocol) and to draw all the CAMs. 


***
Import, draw CAMs part
----------------

When starting the CAM-App in the first module "upload data" the researcher can import the raw CAM data (and the protocol). After uploading the files the researcher can click on one of the following buttons:

* **Preprocessing Part:** using multiple modules it is possible to summarize the CAM data semi-automatically
* **Analysis Part:** the summarized data can be subsequently analyzed and visualized using multiple implemented functions

*See for details the single sections.*

***
### Import CAM data
---

**Core-functions module**:
After starting the CAM-App by clicking on "2) Upload a raw CAM data set" the researcher can upload a raw CAM data set. Internally the data set is checked multiple times if it is a valid CAM data set. If a **protocol already exists** it is mandatory to upload the protocol before uploading the raw CAM data.

**Module options**: 

* "> Descriptive:" after a valid CAM dataset has been uploaded, several descriptive statistics can be looked at. Within the dynamic tables it is possible to sort the data according to single variables of search within the nodes and connectors data set.
* "> Protocol stats:" after a valid protocol has been uploaded, several statistics for the protocol can be looked at, e.g., how often certain summary functions had been used
* "> Clean Valence:" by clicking on the button "clean Valence data" the R function "fix_ValenceData()" tries to automatically remove known problems within data sets of the previous CAM software <a href="https://osf.io/9tza2/" target="_blank">Valence</a>. Only needed if you have uploaded Valence data



<br>
**Internal the following R functions are applied**:

```r
create_CAMfiles(datCAM = raw_CAM, reDeleted = TRUE, verbose = FALSE)

create_ValenceFiles(datBlocks = blocks, datLinks = links)

fix_ValenceData(dat_nodes, dat_connectors, dat_merged, verbose = FALSE)
```

* create_CAMfiles(): takes raw CAM data as input, removes all the deleted concepts / connectors (<code>reDeleted</code>), not printing this process to the console (<code>verbose</code>)
* create_ValenceFiles(): takes raw CAM data from Valence software as input; Valences files are seperate <code>.csv</code> files for blocks (concepts) and links (connectors)
* fix_ValenceData(): takes raw CAM data from Valence software as input and tries to automatically remove known problems within data sets of the Valence software, for example in Valence it is technically possible to draw multiple connections between concepts


***
### Import protocol: remarks
---

After starting the CAM-App by clicking on "1) Upload your protocol" the researcher can upload a protocol generated by the CAM-App. Each time a researcher engages with the CAM-App, an automatic protocol is generated in the background, documenting all data pre-processing and analysis steps. By uploading the protocol and then the raw CAM data, all previously performed summary steps are reiterated and a researcher could continue pre-processing the CAM data. The protocol makes the summary process of the CAM data fully transparent for other researchers.

**Example of protocol**: The protocol is internally JavaScript Object Notation (JSON) file and in the example it could be seen that the data was collected using the C.A.M.E.L. software, no CAMs had been deleted and only the summary function "Searching terms" (see below) has been used, whereby the researcher searched for the word "cost" and found three terms. 

```json
{
    "sessionID": [
        "6634852443"
    ],
    "software": [
        {
            "software": [
                "CAMEL"
            ],
            "time": [
                "2023-07-22 11:58:16"
            ]
        }
    ],
    "cleanValence": [
        false
    ],
    "deletedCAMs": {},
    "currentCAMs": [
        "5d7ebf9e93902b0001965912",
        "5f50e3d60305bb088998b766",
        "5c17c149f596b100011ca8b8",
        "61112576c81c42b0409bd52a",
        "56b4b530b2de2a000632cc5f"
    ],
    "approximateMatching": {},
    "searchTerms": {},
    "findSynonyms": [
        {
            "time": [
                "2023-07-22 11:58:24"
            ],
            "wordsFound": [
                "Cost_positive",
                "damage_negative",
                "Cost_ambivalent"
            ],
            "superordinateWord": [
                "Cost"
            ],
            "noneSearchArgumentSynonyms": [
                "none"
            ]
        }
    ],
    "modelwordVec": {}
}
```

<br>
**Internal the following R functions are applied**: if any summarize terms module functions had been applied the function "overwriteTextNodes()" overwrites the texts of the drawn nodes to superordinate terms:

```r
overwriteTextNodes(protocolDat, nodesDat)
```

***
### Draw CAMs
---

blabla

***
***
Pre-processing part
----------------

using multiple modules it is possible to summarize the CAM data semi-automatically


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

the summarized data can be subsequently analyzed and visualized using multiple implemented functions


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