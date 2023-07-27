# **Deriving connectivity from relatedness: broad-scale isolation-by-distance in the shanny _Lipophrys pholis_**

**This repository contains code and data presented in the article**:

Jeannot, L.-L., Mouronvalle, C., Peyran, C., Olabarria, C., Beger, M., Blanco, A., Planes, S. Deriving connectivity from relatedness: broad-scale isolation-by-distance in the shanny *Lipophrys pholis*. Marine Ecology Progress Series (in rev).

[![Generic badge]((https://zenodo.org/badge/DOI/10.5281/zenodo.8190819.svg))](https://zenodo.org/record/8190819)


## 1. How to download this project?

On the project main page on GitHub, click on the green button `Code` and then click on `Download ZIP`.



## 2. Description of the project

### 2.1 Project organization

This project is organized in 4 folders:

* :file_folder:	`data` folder contains 7 datasets (see **2.2 Datasets description**).
* :file_folder:	`R` folder contains 1 _R_ code (see **2.3 Code description**).
* :file_folder:	`fig_data` folder contains 6 datasets for directly generating Fig. 3, Fig. 4, Fig. 5, and Fig. S6 (see **2.4 How to reproduce figures?**).
* :file_folder:	`figures` folder contains 4 PNG files of Fig. 3, Fig. 4, Fig. 5 and Fig. S6.


### 2.2 Datasets description

The dataset _BDD_Lpholis_Demerelate.txt_ corresponds to the genotypes of the 519 samples using 27 microsatellite markers, formatted for analysis with the R package _Demerelate_ (Kraemer & Gerlach, 2017), and contains the following variables:

- `Sample-ID` Sample ID
- `Population` Sampling site
- `AGC06.a ... AG20.a` Allele 1 fragment size (bp)
- `AGC06.b ... AG20.b` Allele 2 fragment size (bp)


The dataset _BDD_Lpholis_CKMRsim.csv_ corresponds to the genotypes of the 519 samples using 27 microsatellite markers, formatted for analysis with the R package _CKMRsim_ (Anderson, 2023), and contains the following variables:

- `ID` Sample ID
- `AGC06.1 ... AG20.1` Allele 1 fragment size (bp)
- `AGC06.2 ... AG20.2` Allele 2 fragment size (bp)


The dataset _FSTDistance.csv_ (16 var. and1 16 obs.) corresponds to _F<sub>ST</sub>_ values between sites calculated using the Robertson and Hill estimator implemented in GENETIX, with the Raufaste and Bonhomme correction (Robertson & Hill 1984, Raufaste & Bonhomme 2000).


The dataset _NeiDistance.csv_ (16 var. and1 16 obs.) corresponds to Nei's genetic distances values between sites calculated in GenAlex v. 6.503 (Peakall & Smouse 2006, 2012).


The dataset _GeosphereDistance.csv_ (16 var. and 16 obs.) corresponds to geographic distance (km) between sites using the Haversine method (Sinnott 1984, Hijmans 2021a).


The dataset _ShortestPathDistance.csv_ (16 var. and 16 obs.) corresponds to geographic distance (km) between sites using the costDistance function from the _gdistance_ package on rasterized maps of Spain and Portugal (van Etten, 2017; Van Wynsberge et al., 2017)).


The dataset _Demerelate_relatedness.csv_ corresponds to relative relatedness calculated using the _Demerelate_ package. This dataset can be computed in the code but is made available to save computation time. It contains the following variables: Lynch-Li (L-L; Li, Weeks & Chakravarti, 1993), Lynch-Ritland (L-R; Lynch & Ritland, 1999), Queller-Goodnight (Q-G; Queller & Goodnight, 1989) and Wang (W; Wang, 2002, 2007). 

- `rownames` Sample pair
- `wang` Relative relatedness computed with Wang's estimator (2002, 2007)
- `lynchli` Relative relatedness computed with Li, Weeks and Chakravarti's estimator (1993)
- `lxy` Relative relatedness computed with Lynch and Ritland's estimator (1999)
- `rxy` Relative relatedness computed with Queller and Goodnight's estimator (1989)


### 2.3 Code description

The _Lpholis_relatedness.Rmd_ code is formatted in Rmarkdown and contains all R-based analyses and code to reproduce data for Tables 3, 4 and S5 Figures 3, 4, 5 and S6. It is divided into three sections:

* I. Relative relatedness
* II. Relatedness based on relationship category
* III. MSR-Mantel tests
  

### 2.4 How to reproduce figures?

Load all packages, making sure that all required packages were previously installed. _Demerelate_ and its dependencies can be downloaded from the CRAN archive, but installation can be bypassed using the output file _Demerelate_relatedness.csv_. For each figure, data may be computed by running the code in sequence. To save computation time, data can also be loaded directly from the `fig_data` folder under _Import data (optional)_. Code sections and data to run each figure are as follows:

- **Figure 3**: II. Relatedness based on relationship category / _estimators_graph_1.csv_ & _estimators_graph_1.csv_
- **Figure 4**: II. Relatedness based on relationship category / _n_graph.csv_
- **Figure 5**: I. Relative relatedness / _estimators_graph_comp.csv_ & _stat_test.csv_
- **Figure S6**: II. Relatedness based on relationship category / _estimators.csv_


### 2.5 How to reproduce statistical results?

Load all packages, making sure that all required packages were previously installed. _Demeralate_ and its dependencies can be downloaded from the CRAN archive, but installation can be bypassed using the output file _Demerelate_relatedness.csv_. For each table, run the code in sequence. Code sections to reproduce data are as follows:

- **Table 3**: III. MSR-Mantel tests
- **Table 4**: II. Relatedness based on relationship category
- **Table S5**: II. Relatedness based on relationship category

Please note MSR-Mantel tests may return slightly different results than from the manuscript.


## 3. Reproducibility parameters


```R
R version 4.2.1 (2022-06-23 ucrt)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 10 x64 (build 19045)

Matrix products: default

locale:
[1] LC_COLLATE=English_United Kingdom.utf8  LC_CTYPE=English_United Kingdom.utf8    LC_MONETARY=English_United Kingdom.utf8
[4] LC_NUMERIC=C                            LC_TIME=English_United Kingdom.utf8    

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] glmmTMB_1.1.7     ggpubr_0.6.0      CKMRsim_0.1.2.999 ade4_1.7-22       adespatial_0.3-21 spdep_1.2-8      
 [7] sf_1.0-13         spData_2.2.2      ggh4x_0.2.4       lubridate_1.9.2   forcats_1.0.0     stringr_1.5.0    
[13] dplyr_1.1.2       purrr_1.0.1       readr_2.1.4       tidyr_1.3.0       tibble_3.2.1      tidyverse_2.0.0  
[19] ggpmisc_0.5.2     ggpp_0.5.2        ggplot2_3.4.2     plyr_1.8.8        reshape2_1.4.4    MuMIn_1.47.5     
[25] MASS_7.3-60       broom_1.0.5       Demerelate_0.9-3 

loaded via a namespace (and not attached):
  [1] uuid_1.1-0          backports_1.4.1     igraph_1.4.3        fts_0.9.9.2         sp_1.6-1            TMB_1.9.4          
  [7] splines_4.2.1       rncl_0.8.7          TH.data_1.1-2       digest_0.6.31       htmltools_0.5.5     fansi_1.0.4        
 [13] magrittr_2.0.3      cluster_2.1.4       sfsmisc_1.1-15      tzdb_0.4.0          sandwich_3.0-2      timechange_0.2.0   
 [19] prettyunits_1.1.1   jpeg_0.1-10         colorspace_2.1-0    mlogit_1.1-1        rbibutils_2.2.13    crayon_1.5.2       
 [25] lme4_1.1-33         phylobase_0.8.10    survival_3.5-5      zoo_1.8-12          ape_5.7-1           glue_1.6.2         
 [31] gtable_0.3.3        emmeans_1.8.6       MatrixModels_0.5-1  seqinr_4.2-30       car_3.1-2           adegraphics_1.0-18 
 [37] abind_1.4-5         SparseM_1.81        scales_1.2.1        mvtnorm_1.2-2       DBI_1.1.3           rstatix_0.7.2      
 [43] Rcpp_1.0.10         xtable_1.8-4        progress_1.2.2      units_0.8-2         proxy_0.4-27        Formula_1.2-5      
 [49] stats4_4.2.1        httr_1.4.6          RColorBrewer_1.1-3  wk_0.7.3            ellipsis_0.3.2      pkgconfig_2.0.3    
 [55] XML_3.99-0.14       deldir_1.0-9        utf8_1.2.3          tidyselect_1.2.0    rlang_1.1.1         later_1.3.1        
 [61] polynom_1.4-1       munsell_0.5.0       adephylo_1.1-13     tools_4.2.1         cli_3.6.1           generics_0.1.3     
 [67] fastmap_1.1.1       s2_1.1.4            nlme_3.1-162        mime_0.12           quantreg_5.95       adegenet_2.1.10    
 [73] dfidx_0.0-5         xml2_1.3.4          compiler_4.2.1      rstudioapi_0.14     png_0.1-8           e1071_1.7-13       
 [79] ggsignif_0.6.4      statmod_1.5.0       RNeXML_2.4.11       stringi_1.7.12      lattice_0.21-8      Matrix_1.5-4.1     
 [85] classInt_0.4-9      nloptr_2.0.3        vegan_2.6-4         permute_0.9-7       vctrs_0.6.2         pillar_1.9.0       
 [91] lifecycle_1.0.3     Rdpack_2.4          lmtest_0.9-40       estimability_1.4.1  httpuv_1.6.11       R6_2.5.1           
 [97] latticeExtra_0.6-30 promises_1.2.0.1    KernSmooth_2.23-21  codetools_0.2-19    boot_1.3-28.1       withr_2.5.0        
[103] multcomp_1.4-24     mgcv_1.8-42         parallel_4.2.1      hms_1.1.3           grid_4.2.1          coda_0.19-4        
[109] class_7.3-22        minqa_1.2.5         carData_3.0-5       numDeriv_2016.8-1.1 shiny_1.7.4         interp_1.1-4     
```
