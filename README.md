
<!-- README.md is generated from README.Rmd. Please edit that file -->

# pip-fake-data

The goal of pip-fake-data is to enable end-users to more easily explore
the computations that generates the poverty and inequality statistics
published on [PIP](https://pip.worldbank.org/home)

Since most data used in PIP are confidential microdata, this fake
dataset has been created to match the exact format expected by the
[pipapi](https://github.com/PIP-Technical-Team/pipapi) package.

# Getting started

Make sure the `pipapi` package is installed on your machine.

``` r
library(pipapi)
#> Warning: package 'pipapi' was built under R version 4.1.2
#> Info: Disk based caching is enabled.
lkups <- create_versioned_lkups(data_dir = ".")
lkups$versions
#> [1] "20211212_2011_01_01_PROD" "20200101_2011_01_01_PROD"
lkup <- lkups$versions_paths$`20211212_2011_01_01_PROD`
```

## Run main `pip` function

``` r
pip(country = "all", year = "all", povline = 1.9, lkup = lkup)
#>                         region_name region_code       country_name country_code
#>  1:           East Asia and Pacific         EAP              China          CHN
#>  2:           East Asia and Pacific         EAP              China          CHN
#>  3:           East Asia and Pacific         EAP              China          CHN
#>  4:           East Asia and Pacific         EAP              China          CHN
#>  5:           East Asia and Pacific         EAP               Fiji          FJI
#>  6:           East Asia and Pacific         EAP          Indonesia          IDN
#>  7:           East Asia and Pacific         EAP          Indonesia          IDN
#>  8:           East Asia and Pacific         EAP          Indonesia          IDN
#>  9:           East Asia and Pacific         EAP          Indonesia          IDN
#> 10:           East Asia and Pacific         EAP           Mongolia          MNG
#> 11:           East Asia and Pacific         EAP           Malaysia          MYS
#> 12:           East Asia and Pacific         EAP           Malaysia          MYS
#> 13:           East Asia and Pacific         EAP           Thailand          THA
#> 14: Latin America and the Caribbean         LAC          Argentina          ARG
#> 15: Latin America and the Caribbean         LAC Dominican Republic          DOM
#> 16:    Middle East and North Africa         MNA   Egypt, Arab Rep.          EGY
#> 17:                      South Asia         SAS              Nepal          NPL
#> 18:              Sub-Saharan Africa         SSA            Nigeria          NGA
#> 19:           East Asia and Pacific         EAP              China          CHN
#> 20:           East Asia and Pacific         EAP          Indonesia          IDN
#> 21:           East Asia and Pacific         EAP              China          CHN
#> 22:           East Asia and Pacific         EAP          Indonesia          IDN
#>                         region_name region_code       country_name country_code
#>     reporting_year reporting_level survey_acronym survey_coverage survey_year
#>  1:           1981           rural      CRHS-CUHS        national     1981.00
#>  2:           1981           urban      CRHS-CUHS        national     1981.00
#>  3:           1990           rural      CRHS-CUHS        national     1990.00
#>  4:           1990           urban      CRHS-CUHS        national     1990.00
#>  5:           2002        national           HIES        national     2002.50
#>  6:           1984           rural        SUSENAS        national     1984.00
#>  7:           1984           urban        SUSENAS        national     1984.00
#>  8:           1993           rural        SUSENAS        national     1993.00
#>  9:           1993           urban        SUSENAS        national     1993.00
#> 10:           1995        national           LSMS        national     1995.00
#> 11:           1984        national            HIS        national     1984.00
#> 12:           2003        national            HIS        national     2003.00
#> 13:           1981        national            SES        national     1981.00
#> 14:           1980           urban            EPH           urban     1980.00
#> 15:           1989        national         ENGSLF        national     1989.00
#> 16:           1995        national          HIECS        national     1995.75
#> 17:           1984        national           MHBS        national     1984.50
#> 18:           2010        national        GHSP-W1        national     2010.50
#> 19:           1981        national      CRHS-CUHS        national     1981.00
#> 20:           1984        national        SUSENAS        national     1984.00
#> 21:           1990        national      CRHS-CUHS        national     1990.00
#> 22:           1993        national        SUSENAS        national     1993.00
#>     reporting_year reporting_level survey_acronym survey_coverage survey_year
#>     welfare_type survey_comparability comparable_spell poverty_line   headcount
#>  1:       income                    0      1981 - 1987          1.9 0.953728174
#>  2:       income                    0      1981 - 1987          1.9 0.591778516
#>  3:  consumption                    1      1990 - 2012          1.9 0.785831245
#>  4:  consumption                    1      1990 - 2012          1.9 0.320104346
#>  5:  consumption                    0      2002 - 2013          1.9 0.024834375
#>  6:  consumption                    0      1984 - 1990          1.9 0.764868616
#>  7:  consumption                    0      1984 - 1990          1.9 0.448618677
#>  8:  consumption                    1      1993 - 1999          1.9 0.634093212
#>  9:  consumption                    1      1993 - 1999          1.9 0.345521862
#> 10:  consumption                    0      1995 - 1998          1.9 0.121169531
#> 11:       income                    0      1984 - 1997          1.9 0.028902832
#> 12:       income                    1      2003 - 2015          1.9 0.012401566
#> 13:  consumption                    0      1981 - 1988          1.9 0.193176611
#> 14:       income                    0      1980 - 1987          1.9 0.004798767
#> 15:       income                    1             1989          1.9 0.140940967
#> 16:  consumption                    0      1990 - 1995          1.9 0.056119067
#> 17:       income                    0             1984          1.9 0.782268999
#> 18:  consumption                    4      2010 - 2018          1.9 0.435084800
#> 19:       income                    0      1981 - 1987          1.9 0.880911142
#> 20:  consumption                    0      1984 - 1990          1.9 0.685034482
#> 21:  consumption                    1      1990 - 2012          1.9 0.662683738
#> 22:  consumption                    1      1993 - 1999          1.9 0.536533011
#>     welfare_type survey_comparability comparable_spell poverty_line   headcount
#>     poverty_gap poverty_severity       watts       mean     median        mld
#>  1: 0.499128342     0.2926001485 0.789583970  0.9722847  0.8873515 0.10195806
#>  2: 0.140982812     0.0479212354 0.175500543  1.8524267  1.7638123 0.05896937
#>  3: 0.300782879     0.1441421794 0.430011422  1.5776966  1.3174263 0.16093750
#>  4: 0.076042943     0.0267393518 0.096004403  2.6198905  2.3601091 0.10811732
#>  5: 0.004870228     0.0014288158 0.005840094  8.1902373  6.2004183 0.24010268
#>  6: 0.293501926     0.1417482206 0.421115090  1.5674467  1.3408207 0.14055442
#>  7: 0.137366715     0.0579608703 0.183953112  2.5011236  2.0434828 0.18371649
#>  8: 0.192555631     0.0745708629 0.247705048  1.8705042  1.6220437 0.11014091
#>  9: 0.090597539     0.0324860127 0.114215044  2.9837413  2.2996335 0.20336434
#> 10: 0.025429759     0.0079026534 0.030903468  4.7929111  4.0011078 0.18345788
#> 11: 0.005870994     0.0020480934 0.007713040 12.4366432  8.0224457 0.41196667
#> 12: 0.002244861     0.0007865853 0.002855670 15.5845263 10.4589669 0.37429382
#> 13: 0.049192439     0.0168261018 0.060853604  5.4965896  3.6856019 0.34412662
#> 14: 0.002215663     0.0020544611 0.000904391 22.9432465 17.5438111 0.29184721
#> 15: 0.036276342     0.0127716850 0.045307997  7.7738552  4.8357551 0.44731241
#> 16: 0.007614276     0.0019144534 0.008926023  4.3082955  3.5221410 0.15464102
#> 17: 0.312209906     0.1528863446 0.447943381  1.5326358  1.2747035 0.14717741
#> 18: 0.148951474     0.0688673206 0.206486772  2.6790194  2.1123517 0.20893157
#> 19: 0.427076625     0.2433756448 0.666042667  1.1493516         NA 0.12836289
#> 20: 0.254087153     0.1205969420 0.361245921  1.8031441         NA 0.17058920
#> 21: 0.241357145     0.1130985237 0.341693286  1.8532735         NA 0.16944443
#> 22: 0.158085639     0.0603428168 0.202574747  2.2468674         NA 0.16711364
#>     poverty_gap poverty_severity       watts       mean     median        mld
#>          gini polarization    decile1    decile2    decile3    decile4
#>  1: 0.2472923    0.2028512 0.04132991 0.05658410 0.06790506 0.07756826
#>  2: 0.1846186    0.1513719 0.05231606 0.06764996 0.07631176 0.08395676
#>  3: 0.3057347    0.2277171 0.03868118 0.05096246 0.06098069 0.07003742
#>  4: 0.2559464    0.2129191 0.04114640 0.05526574 0.06630447 0.07601143
#>  5: 0.3810205    0.3324702 0.02717484 0.03972235 0.04984532 0.05985534
#>  6: 0.2921472    0.2385572 0.03871003 0.05106256 0.06146780 0.07106190
#>  7: 0.3329345    0.2753216 0.03350620 0.04542587 0.05598468 0.06605534
#>  8: 0.2600183    0.2095176 0.04443495 0.05775549 0.06612447 0.07396967
#>  9: 0.3535324    0.2962118 0.03317168 0.04497871 0.05368715 0.06247691
#> 10: 0.3319534    0.3002709 0.03058394 0.04308235 0.05455941 0.06576576
#> 11: 0.4862481    0.4284957 0.01833118 0.02741841 0.03682924 0.04693669
#> 12: 0.4641620    0.4397759 0.01765557 0.02869426 0.03851743 0.04877163
#> 13: 0.4521682    0.4113264 0.02292256 0.03125336 0.04010132 0.04980821
#> 14: 0.4083086    0.3728986 0.02009856 0.03286435 0.04492988 0.05697859
#> 15: 0.5045787    0.4566968 0.01663330 0.02528777 0.03444576 0.04446244
#> 16: 0.3012696    0.2295591 0.04184216 0.05322220 0.06116103 0.06894943
#> 17: 0.3005754    0.2474645 0.04045139 0.05065805 0.05993790 0.06894979
#> 18: 0.3565021    0.3311554 0.02888311 0.04168837 0.05159117 0.06161321
#> 19: 0.2816410    0.2521087 0.03673302 0.05168220 0.06264423 0.07208088
#> 20: 0.3247122    0.2683615 0.03536700 0.04741074 0.05732037 0.06667543
#> 21: 0.3222662    0.2711864 0.03493718 0.04785257 0.05764625 0.06681384
#> 22: 0.3201759    0.2530064 0.03862412 0.05063052 0.05866377 0.06655801
#>          gini polarization    decile1    decile2    decile3    decile4
#>        decile5    decile6    decile7   decile8   decile9  decile10       cpi
#>  1: 0.08668369 0.09607455 0.10670273 0.1202979 0.1416627 0.2051911 0.1769007
#>  2: 0.09142351 0.09917575 0.10770156 0.1178366 0.1318140 0.1718141 0.1730074
#>  3: 0.07893317 0.08839688 0.09942541 0.1139969 0.1380894 0.2604965 0.3340487
#>  4: 0.08534709 0.09509631 0.10624070 0.1206032 0.1432949 0.2106897 0.3424323
#>  5: 0.06999336 0.08235578 0.09768087 0.1191872 0.1579468 0.2962382 0.7013082
#>  6: 0.08060765 0.09084800 0.10283689 0.1186818 0.1446517 0.2400716 0.0799932
#>  7: 0.07632444 0.08755159 0.10090155 0.1187918 0.1485605 0.2668980 0.0799932
#>  8: 0.08228591 0.09157481 0.10269387 0.1173520 0.1401631 0.2236457 0.1549582
#>  9: 0.07184630 0.08301873 0.09736926 0.1171385 0.1502486 0.2860642 0.1549582
#> 10: 0.07736554 0.09015035 0.10536490 0.1255516 0.1579586 0.2496176 0.1454805
#> 11: 0.05825849 0.07162403 0.08857860 0.1126264 0.1548939 0.3845030 0.5019929
#> 12: 0.06050350 0.07511985 0.09349207 0.1205147 0.1654941 0.3512368 0.8162558
#> 13: 0.06087926 0.07415141 0.09120834 0.1156598 0.1589376 0.3550781 0.3514981
#> 14: 0.06968903 0.08394564 0.10122463 0.1246800 0.1638356 0.3017537 0.2656343
#> 15: 0.05585893 0.06949580 0.08700087 0.1120922 0.1566172 0.3981057 0.0741348
#> 16: 0.07727279 0.08672370 0.09819697 0.1135747 0.1386164 0.2604406 0.3500285
#> 17: 0.07826070 0.08854055 0.10085366 0.1174372 0.1450764 0.2498343 0.1265234
#> 18: 0.07272528 0.08588638 0.10255760 0.1255131 0.1618781 0.2676637 2.3368803
#> 19: 0.08150734 0.09219440 0.10592925 0.1255740 0.1543050 0.2173497 0.1769007
#> 20: 0.07628085 0.08699862 0.10012207 0.1182253 0.1486184 0.2629812 0.0799932
#> 21: 0.07636234 0.08730839 0.10109270 0.1200873 0.1499470 0.2579524 0.3340487
#> 22: 0.07503145 0.08488446 0.09709165 0.1141724 0.1441468 0.2701968 0.1549582
#>        decile5    decile6    decile7   decile8   decile9  decile10       cpi
#>             ppp reporting_pop reporting_gdp reporting_pce is_interpolated
#>  1:    3.039222     793935216      447.1190            NA           FALSE
#>  2:    3.905400     199949784      447.1190            NA           FALSE
#>  3:    3.039222     835019382      905.0309            NA           FALSE
#>  4:    3.905400     300165618      905.0309            NA           FALSE
#>  5:    1.016247        815257     4300.6413            NA           FALSE
#>  6: 3498.875839     120748398     1204.3367      732.4907           FALSE
#>  7: 4140.299249      40774955     1204.3367      732.4907           FALSE
#>  8: 3498.875839     126328216     1714.8776      918.0250           FALSE
#>  9: 4140.299249      64522968     1714.8776      918.0250           FALSE
#> 10:  580.637634       2298017     1451.5915            NA           FALSE
#> 11:    1.586355      15192300     3565.6801     1770.9094           FALSE
#> 12:    1.586355      24698821     6727.6710     2835.6954           FALSE
#> 13:   12.758684      48326269     1482.7089      921.2160           FALSE
#> 14:    3.161164      23122598    10318.1830            NA           FALSE
#> 15:   20.764965       6997877     3020.0648     2461.6157           FALSE
#> 16:    2.871648      62334025     2216.9482     1851.0317           FALSE
#> 17:   25.743326      16477488      384.8504            NA           FALSE
#> 18:   83.583336     158503203     2403.6453     2014.2442           FALSE
#> 19:          NA     993885000      447.1190            NA           FALSE
#> 20:          NA     161523353     1204.3367      732.4907           FALSE
#> 21:          NA    1135185000      905.0309            NA           FALSE
#> 22:          NA     190851184     1714.8776      918.0250           FALSE
#>             ppp reporting_pop reporting_gdp reporting_pce is_interpolated
#>     distribution_type estimation_type
#>  1:         aggregate          survey
#>  2:         aggregate          survey
#>  3:         aggregate          survey
#>  4:         aggregate          survey
#>  5:             micro          survey
#>  6:         aggregate          survey
#>  7:         aggregate          survey
#>  8:             micro          survey
#>  9:             micro          survey
#> 10:             group          survey
#> 11:             group          survey
#> 12:             micro          survey
#> 13:             group          survey
#> 14:             group          survey
#> 15:             group          survey
#> 16:             group          survey
#> 17:             group          survey
#> 18:           imputed          survey
#> 19:         aggregate          survey
#> 20:         aggregate          survey
#> 21:         aggregate          survey
#> 22:             micro          survey
#>     distribution_type estimation_type
```

# Launch the API

``` r
# pipapi::start_api(
#   api_version = 'v1',
#   port = 80, 
#   host = '0.0.0.0')
```
