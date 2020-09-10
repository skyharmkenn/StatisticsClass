---
title: "Good Template"
author: "Ken Harmon"
date: "2020 September 10"
output:
  html_document:
    keep_md: yes
    code_folding: hide
    fig_height: 6
    fig_width: 12
    fig_align: center
  pdf_document: default
editor_options:
  chunk_output_type: console
---

# {.tabset .tabset-fade}







## Categorical Data


```r
pon <- read.csv("201709-CAH_PulseOfTheNation.csv")

# Pivot Table

pon_pivot <- table(pon$Gender,pon$Political.Affiliation)

# Simple side by side

barplot(pon_pivot, beside = T)
```

![](Graphics_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

```r
# Prettier

barplot(pon_pivot, ylab="Frequency", xlab="Party", main="Side-By-Side Bar Chart", col=c("blue", "pink", "purple" , "green" ), beside=T, width=.3)

legend("topright", title="Gender", legend= sort(unique(pon$Gender)), fill =c("blue", "pink", "purple" , "green" ), box.lty=0)
```

![](Graphics_files/figure-html/unnamed-chunk-2-2.png)<!-- -->

```r
# Pie

pon_pie <- table(pon$Political.Affiliation)

pie(pon_pie)
```

![](Graphics_files/figure-html/unnamed-chunk-2-3.png)<!-- -->

## Dotplot


```r
ggplot(pon, aes(x = Age)) + geom_dotplot(binwidth = .5)
```

![](Graphics_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

```r
ggplot(pon, aes(x = Age, fill = factor(Political.Affiliation))) + geom_dotplot(binwidth = .8)
```

![](Graphics_files/figure-html/unnamed-chunk-3-2.png)<!-- -->


