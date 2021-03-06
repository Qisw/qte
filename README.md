README
================
Brantly Callaway
2017-02-01

<!-- README.md is generated from README.Rmd. Please edit that file -->
The R `qte` package implements many methods used, especially in economics, to estimate quantile treatment effects. These include the case where treatment is randomly assigned, under selection on observables, under a Difference in Differences Assumtpion.

The package is available on CRAN and can be loaded as follows

``` r
  library(qte)
```

The following example shows how to use the `ci.qte` method in the `qte` package using data about an experimental job training program.

``` r
data(lalonde)
 jt.cia <- ci.qte(re78 ~ treat,
   xformla=~age + education + black + hispanic + married + nodegree,
   data=lalonde.psid,
   probs=seq(0.05,0.95,0.05), se=T)
 summary(jt.cia)
```
