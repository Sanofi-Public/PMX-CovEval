# PMX-CovEval: A framework for covariate model model building benchmarking

This repository contains all five components of PMX-CovEval:
- 127 simulated datasets corresponding to 127 model scenarios (see folder `datasets`)
- Their corresponding NONMEM and Monolix base* model (BM) files (see folders `BM_Monolix`, `BM_NONMEM`)
- The empirical Bayes estimates (EBEs) of the random effects of all base models (see folder `EBEs`)
- A scenario table `scenari_table.csv` summarizing all scenarios included in the framework
- The benchmarking of covariate model building methods under `benchmark.csv`

Base model = underlying structural + statistical model, without the covariate model

Quality checks of all scenarios are stored under the `appendix` folder.

### Contributing to the Benchmark

To add your covariate model building method's results, please send a `.csv` file to [Pharmacometrics-MP@sanofi.com](mailto:Pharmacometrics-MP@sanofi.com) with the following columns:

| Column               | Description                                                                         |
| -------------------- | ----------------------------------------------------------------------------------- |
| `scenario`           | Scenario identifier (must match an entry in `scenario_table.csv`)                   |
| `method`             | Name of the covariate model building method                                         |
| `rMPE`               | Relative mean prediction error (MPE) on population concentration predictions (%)    |
| `rRMSE`              | Relative root mean squared error (RMSE) on population concentration predictions (%) |
| `BIC`                | Bayesian Information Criterion of the final model                                   |
| `iRSE50`             | Whether all individual RSEs are below 50% (`TRUE`/`FALSE`)                          |
| `AUC_ss_rMPE`        | Relative MPE on steady-state AUC (%)                                                |
| `AUC_ss_rRMSE`       | Relative RMSE on steady-state AUC (%)                                               |
| `TPR_pair`           | True positive rate (sensitivity) for covariate–parameter pairs                      |
| `TNR_pair`           | True negative rate (specificity) for covariate–parameter pairs                      |
| `PPV_pair`           | Positive predictive value (precision) for covariate–parameter pairs                 |
| `correct_model`      | Whether the correct full covariate model was identified (`TRUE`/`FALSE`)            |
| `time`               | Total runtime in seconds                                                            |
| `hardware_processor` | Processor description                                                               |
| `hardware_ram`       | Available RAM                                                                       |
| `software_os`        | Operating system                                                                    |
| `software_kernel`    | OS kernel version                                                                   |

Therefore, if you submit results for a single method, your submitted .csv file should contain 127 rows (for the 127 scenarios).

`hardware_x` and `software_x` are here to inform on the computational environment used, enabling fair runtime comparisons across methods.

If you submit results generated on a new {`hardware_processor`, `hardware_ram`, `software_os`, `software_kernel`} quartet, you should also submit results of a CMB method already present in the benchmark on that new quartet. This provides a common reference point for normalizing runtime comparisons across different computational environments.

## Components utility

Providing users with the collection of simulated datasets and scenario summary table enables the investigation of any covariate model selection technique. In particular, users can assess how varying model components (e.g., covariate effect size) across scenarios impacts the performance metrics of their chosen method.
Providing additional base model files for NONMEM and Monolix enables direct execution of any existing or future Perl speaks NONMEM (PsN) or Monolix internal covariate model selection technique, two of the most widely used pharmacometrics tools.
Providing additional EBEs estimated under the BMs allows for direct EBEs-regression based methods evaluation (including machine and deep learning ones).




This work was done as part of Mélanie Karlsen's PhD project between Sanofi and the LIRMM (Laboratory of Informatics, Robotics and Microelectronics in Montpellier), with academic supervisors Pascal Poncelet, Sandra Bringay and Jérôme Azé, and industrial supervisor Elisa Calvier.