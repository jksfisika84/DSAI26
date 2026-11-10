Decoding Size-Resolved Particulate Matter Dynamics under Tropical Riverine Conditions
An Interpretable Machine Learning Analysis of Hourly PM1, PM2.5, and PM10 Variability in Pontianak, Indonesia
Complete analysis notebook (main analysis + supplementary analyses)

Joko Sampurno and Irfana Diah Faryuni, Department of Physics, Faculty of Mathematics and Natural Sciences, Universitas Tanjungpura, Pontianak, Indonesia

About this notebook
This single notebook reproduces, step by step, the entire analysis of the manuscript: from the raw hourly IQAir export to the final tables and figures. It combines what was previously two notebooks (the main analysis and the supplementary analysis) into one continuous workflow, so the data are uploaded and prepared once and every later step reuses the same objects. It is released together with the processed hourly series in support of the Data and Code Availability statement.

Scientific goal. Explain why PM1, PM2.5, and PM10 respond differently to time of day, season, and local weather in Pontianak, by training one model per particle size and comparing their SHAP feature attributions, while testing how robust each conclusion is.

Workflow at a glance
Part	Section	Step	Reviewer comment addressed
A. Data	1	Setup and parameters	
2	Data ingestion (upload, column mapping, time-zone check)	
3	Pre-processing, record-count reconciliation, temperature QC, Table 1	R3.6, R3.7
B. Exploration	4	Exploratory data analysis (time series, distributions, cycles, correlations)	
5	Feature construction and the season_dry check	R4.2
C. Models	6	Modeling design and baseline (as-submitted) models	R1.1, R3.2, R4.1
7	Hyper-parameter search on an equal footing	R3.3
8	Table 2: hold-out performance (both R² conventions)	R1.1, R3.2, R4.1
9	Rolling-origin cross-validation, paired contrasts	R1.1, R3.3
10	Sensitivity to screening of radiatively affected hours	R3.7
D. Interpretation	11	Out-of-fold SHAP, Table 3, bootstrap intervals, beeswarm figures	R3.4, R3.5, R3.10, R4.2
12	κ-Köhler test of the 88–90 % humidity feature	R1.3, R3.9
13	Permutation control for the dow attribution	R3.11
E. Output	14	Results summary and export of manuscript-ready tables	
How to run
Execute the cells in order (Run All). Each section states its purpose, what it produces, and what to check before moving on.
Section 2 opens a dialog to select the data file directly from your computer (Google Colab upload button, or a file-selection window when run locally). The column names are mapped automatically, and the time-zone convention is verified before any analysis proceeds.
All figures (PNG), tables (CSV) and the selected hyper-parameters (JSON) are written to the outputs/ folder. In Colab the folder is also zipped for download at the end.
Runtime
Runtime is dominated by Section 9 (450 models) and Section 11 (SHAP attribution); together they take roughly 30 to 60 minutes on a Colab CPU runtime. For a first pass, set N_SEEDS = 3 in Section 1 and restore it to 10 for the values reported in the manuscript. If Section 11 is slow or the session runs out of memory, lower SHAP_MAX_ROWS.
