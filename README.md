Welcome to the online documentation of our software package "Cognitive-Affective Maps extended logic"!
===============================================

<!-- 
[![Documentation Status](https://readthedocs.org/projects/example-mkdocs-basic/badge/?version=latest)](https://example-mkdocs-basic.readthedocs.io/en/latest/?badge=latest)
 -->

 > This is the documentation for our developed Cognitive-Affective Map (CAM) tools. Please visit the central website <a href="https://drawyourminds.de/" target="_blank">https://drawyourminds.de/</a>, for further information or to set up your first CAM study.


# Table of Contents

- [What are Cognitive-Affective Maps?](#what-are-cognitive-affective-maps)
- [Data Collection Tool](#data-collection-tool)
- [Set up a study](#set-up-a-study)
- [Data Analysis Tool](#data-analysis-tool)
- [Administrative Panel](#administrative-panel)
- [Support](#support)
- [Additional Resources](#additional-resources)
- [How to Cite](#how-to-cite)
- [Serving the Documentation Locally](#serving-the-documentation-locally)


## What are Cognitive-Affective Maps?

Cognitive-Affective Maps (CAMs) are a qualitative and quantitative research method, first introduced by Thagard (2010), for identifying, visually representing and analyzing belief structures. A CAM is a weighted, directional network of concepts (nodes) connected by supporting or inhibiting connections (edges), where each concept also carries an affective valence (positive, negative, neutral or ambivalent). See the <a href="https://camtools-documentation.readthedocs.io/en/master/Cognitive-Affective%20Maps/" target="_blank">Cognitive-Affective Maps</a> page for the theoretical background, example CAMs, and an overview of research questions currently being investigated.


## Data Collection Tool

The Data Collection Tool lets participants draw CAMs in large-scale online (or offline) studies. A "researcher view" allows you to predefine, position and lock concepts/connections, disable specific features (e.g. arrows, ambivalent concepts), and export a configuration used to run the study. See the <a href="https://camtools-documentation.readthedocs.io/en/master/Data%20Collection%20Tool/" target="_blank">Data Collection Tool</a> page for the full configuration reference and the underlying CAM/concept/connector data structures.


## Set up a study

Studies are configured through the administrative panel at <a href="https://drawyourminds.de/" target="_blank">https://drawyourminds.de/</a>: register an account, draw a default CAM in the researcher view, generate its configuration file, and create an experiment with that configuration and a participant redirect link. The <a href="https://camtools-documentation.readthedocs.io/en/master/Set%20up%20study/" target="_blank">Set up study</a> page walks through this process step by step, lists example study designs and network topologies (star, tree, mesh, two contradictory concepts), and explains how to run the tool "on scratch" on your own server.


## Data Analysis Tool

Using multiple modules you can summarize your CAM data computer-assisted (e.g. approximate string matching, synonym search, word2vec) and analyze the resulting data — aggregating CAMs, computing over 30 network indicators, clustering on concept level, or generating an APA7-formatted report. It runs locally as an R Shiny app (via RStudio) or online at <a href="https://fennapps.shinyapps.io/DataAnalysis/" target="_blank">https://fennapps.shinyapps.io/DataAnalysis/</a>. See the <a href="https://camtools-documentation.readthedocs.io/en/master/Data%20Analysis%20Tool/" target="_blank">Data Analysis Tool</a> page for the data structure, the full pre-processing/analysis workflow, and a reliability module for multi-rater coding.


## Administrative Panel

The administrative panel allows you to set up and configure CAM studies easily without the need of coding and guarantee the highest privacy standards. Simply register an account at our webpage <a href="https://drawyourminds.de/" target="_blank">https://drawyourminds.de/</a>.


## Support

Join our user community for questions, issues or feature requests via Matrix (<a href="https://matrix.to/#/#cognitive-affective-maps:matrix.uni-freiburg.de" target="_blank">invite link</a>, using an app such as <a href="https://element.io/" target="_blank">Element</a>), or email us directly at <cam.contact@drawyourminds.de>. See the <a href="https://camtools-documentation.readthedocs.io/en/master/Support/" target="_blank">Support</a> page for details.


## Additional Resources

The <a href="https://camtools-documentation.readthedocs.io/en/master/Additional%20Resources/" target="_blank">Additional Resources</a> page collects the central CAM publications and thematically sorted literature (conflict resolution, political ideologies, applied ethics, qualitative and quantitative CAM studies), plus links to further CAM research.


## How to Cite

If you use these tools in your research, please cite our publication:

> Fenn, J., Gouret, F., Gorki, M., Reuter, L., Gros, W., Hüttner, P., & Kiesel, A. (2025). Cognitive-affective maps extended logic: Proposing tools to collect and analyze attitudes and belief systems. *Behavior Research Methods*, *57*(6), 174. <a href="https://doi.org/10.3758/s13428-025-02699-y" target="_blank">https://doi.org/10.3758/s13428-025-02699-y</a>

Citation metadata is also available in machine-readable form in <a href="https://github.com/FennStatistics/CAMtools_documentation/blob/master/CITATION.cff" target="_blank">CITATION.cff</a>.


# Developed Cognitive-Affective Map tools

Our developed software package "Cognitive-Affective Maps <i>extended logic</i>" can be found on GitHub: <a href="https://github.com/CAM-E-L" target="_blank">https://github.com/CAM-E-L</a>


# Serving the Documentation Locally

This site is built with [MkDocs](https://www.mkdocs.org/). To preview it on your machine before pushing changes:

```bash
# 1. create and activate a virtual environment (once)
python3 -m venv .venv
source .venv/bin/activate      # on Windows: .venv\Scripts\activate

# 2. install the pinned dependencies
pip install -r docs/requirements.txt

# 3. start the live-reloading dev server
mkdocs serve
```

Then open <a href="http://127.0.0.1:8000" target="_blank">http://127.0.0.1:8000</a> in your browser. The page reloads automatically as you edit files under `docs/`.

> **Note (Python 3.13+):** `docs/requirements.txt` was locked against Python 3.10 (the version [Read the Docs](https://readthedocs.org) builds with, per `.readthedocs.yaml`). On newer local Python versions, `mkdocs-bibtex` may fail to load with `ModuleNotFoundError: No module named 'pkg_resources'` because recent `setuptools` releases dropped that module. If so, run:
> ```bash
> pip install "setuptools<81"
> ```
> This only affects local previews — published builds on Read the Docs use Python 3.10 and are unaffected.
