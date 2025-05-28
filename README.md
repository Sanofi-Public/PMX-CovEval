# PMX-CovEval: A framework for robust evaluation of covariate model selection techniques

This repository contains all four components of PMX-CovEval:
- 99 simulated datasets corresponding to 99 model scenarios (see folder `datasets`)
- Their corresponding NONMEM and Monolix pharmaco-statistical model files (see folders `PSM_Monolix`, `PSM_NONMEM`)
- The empirical Bayes estimates (EBEs) of the random effects of pharmaco-statistical models that achieved successful minimization (see folder `EBEs`)
- A scenario table "`scenari_table.csv`" summarizing all scenarios included in the framework


Quality checks were performed on all scenarios. We intend to later publish the quality checks in an `appendix` folder, along with the source code of the framework generation. 


Providing users with the collection of simulated datasets and scenario summary table enables the investigation of any covariate model selection technique. In particular, users can assess how varying model components (e.g., covariate effect size) across scenarios impacts the performance metrics of their chosen method.
Providing additional PSM files for NONMEM and Monolix enables direct execution of any existing or future Perl speaks NONMEM (PsN) or Monolix internal covariate model selection technique, two of the most widely used pharmacometrics tools.
Providing additional EBEs estimated under the PSMs allows for direct EBEs-regression based methods evaluation (including machine and deep learning ones), supporting the development and assessment of AI-driven covariate modeling approaches.



This work was done as part of Mélanie Karlsen's PhD project between Sanofi and the LIRMM (Laboratory of Informatics, Robotics and Microelectronics in Montpellier), with academic supervisors Pascal Poncelet, Sandra Bringay and Jérôme Azé, and industrial supervisor Elisa Calvier.