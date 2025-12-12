# PMX-CovEval: A framework for robust evaluation of covariate model selection techniques

This repository contains all four components of PMX-CovEval:
- 106 simulated datasets corresponding to 106 model scenarios (see folder `datasets`)
- Their corresponding NONMEM and Monolix base* model (BM) files (see folders `BM_Monolix`, `BM_NONMEM`)
- The empirical Bayes estimates (EBEs) of the random effects of all base models (see folder `EBEs`)
- A scenario table `scenari_table.csv` summarizing all scenarios included in the framework

Base model = underlying structural + statistical model, without the covariate model

Quality checks of all scenarios are stored under the `appendix` folder.


Providing users with the collection of simulated datasets and scenario summary table enables the investigation of any covariate model selection technique. In particular, users can assess how varying model components (e.g., covariate effect size) across scenarios impacts the performance metrics of their chosen method.
Providing additional base model files for NONMEM and Monolix enables direct execution of any existing or future Perl speaks NONMEM (PsN) or Monolix internal covariate model selection technique, two of the most widely used pharmacometrics tools.
Providing additional EBEs estimated under the BMs allows for direct EBEs-regression based methods evaluation (including machine and deep learning ones).


This work was done as part of Mélanie Karlsen's PhD project between Sanofi and the LIRMM (Laboratory of Informatics, Robotics and Microelectronics in Montpellier), with academic supervisors Pascal Poncelet, Sandra Bringay and Jérôme Azé, and industrial supervisor Elisa Calvier.