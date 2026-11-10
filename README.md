About this notebook:

This single notebook reproduces, step by step, the entire analysis of the manuscript: from the raw hourly IQAir export to the final tables and figures. It combines what were previously two notebooks (the main analysis and the supplementary analysis) into a single continuous workflow, so the data are uploaded and prepared once, and every subsequent step reuses the same objects. It is released alongside the processed hourly series to support the Data and Code Availability statement.

Scientific goal. Explain why PM1, PM2.5, and PM10 respond differently to time of day, season, and local weather in Pontianak, by training one model per particle size and comparing their SHAP feature attributions, while testing how robust each conclusion is.

Workflow at a glance
Part	Section	Step	Reviewer comment addressed

A. Data	

1	Setup and parameters	
2	Data ingestion (upload, column mapping, time-zone check)	
3	Pre-processing, record-count reconciliation, temperature QC, Table 1	R3.6, R3.7

B. Exploration	

4	Exploratory data analysis (time series, distributions, cycles, correlations)	
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

