Welcome to the online documentation of our software package "Cognitive-Affective Maps extended logic"!
===============================================

<!-- 
[![Documentation Status](https://readthedocs.org/projects/example-mkdocs-basic/badge/?version=latest)](https://example-mkdocs-basic.readthedocs.io/en/latest/?badge=latest)
 -->

 > This is the documentation for our developed Cognitive-Affective Map (CAM) tools. Please visit the central website <a href="https://drawyourminds.de/" target="_blank">https://drawyourminds.de/</a>, for further information or to set up your first CAM study.


# Table of Contents of Developed Tools

- [Data Collection Tool](#data-collection-tool)
- [Data Analysis Tool](#data-analysis-tool)
- [Administrative Panel](#administrative-panel)


## Data Collection Tool

The data collection tool is an open-source software to draw CAMs. It aims to offer people an easy and intuitive interface on which they could draw their own mind map within online studies. There is a participant view and a researcher view to set up studies. Currently it is possible to change over 10 parameters of the tool (e.g. force to full screen, or change language to Chinese).


## Data Analysis Tool

Using multiple modules you can summarize your CAM data omputer-assisted (e.g. sophisticated language models are implemented) and the so summarized data can subsequently be analyzed using multiple implemented functions, e.g. aggregating CAMs or compute over 30 network indicators. 

## Administrative Panel

The administrative panel allows you to set up and configure CAM studies easily without the need of coding and guarantee the highest privacy standards. Simply register an account at our webpage <a href="https://drawyourminds.de/" target="_blank">https://drawyourminds.de/</a>.



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