---
title: "Modelling scenarios for nutrient-sensitive fisheries management"
date: "Last compiled on 2022-03-07 18:57:00"
mainfont: Montserrat
geometry: "left=3cm,right=3cm,top=2cm,bottom=2cm"
output:
  bookdown::pdf_book:
    latex_engine: lualatex
    toc: yes
    toc_depth: 2
    number_sections: true
  bookdown::epub_book:
    number_sections: true
    toc: true
  bookdown::gitbook:
    lib_dir: assets
    split_by: section
    config:
      toolbar:
        position: static
      download: ["plots_report.pdf", "plots_report.epub"]
header-includes: 
  - \usepackage{float} 
  - \floatplacement{figure}{H}
  - \usepackage{leading}
  - \leading{16pt}
  - \definecolor{myblue}{RGB}{68,117,151}
  - \let\counterwithout\relax
  - \let\counterwithin\relax
  - \usepackage{chngcntr}
  - \usepackage{caption}
  - \captionsetup[figure]{font=footnotesize}
---





# Data pipeline

(ref:pipeline) The main steps of Peskas' data workflow (see <https://github.com/WorldFishCenter/peskas.timor.data.pipeline> for more details). The initial raw data consist of the KOBO landing surveys and GPS tracks provided by Pelagic Data Systems. The landing surveys undergo a preprocessing step in which we extract further information from the data, primarily the catches' weight and the nutritional yield for each catch. Both the landing surveys and the PDS data are subjected to a validation process involving the cleaning and removal of outliers. Validated data is modelled to return the national estimates of catch prices, weight and nutrient yield. Finally, data are organized to be shared.

<div class="figure" style="text-align: center">
<img src="/Users/lore/My Drive/WorldFish/Timor.nutrients/inst/pipeline.png" alt="(ref:pipeline)" width="2016" height="150px" />
<p class="caption">(\#fig:pipeline)(ref:pipeline)</p>
</div>

# Data summary

## Regions' temporal coverage

(ref:missing) Temporal coverage of each municipality on the aggregated daily scale.

<div class="figure">
<img src="/Users/lore/My Drive/WorldFish/Timor.nutrients/inst/plots_report_files/figure-html/missings-1.png" alt="(ref:missing)" width="576" />
<p class="caption">(\#fig:missings)(ref:missing)</p>
</div>

Atauro, Bobonaro, Bacau and Covalima are the most complete. I'll filter the following analyses on these 4 municipalities and consider the period Jun 2019 - Feb 2022.

# Nutrients seasonality

Let's start visualizing seasonal patterns in total weight and nutrients:

(ref:seasonal) Seasonal distribution of catch weight and nutrients. The values are normalized on the number of trips of each municipality highlighting the average monthly yield independently from the sample size.

<div class="figure">
<img src="/Users/lore/My Drive/WorldFish/Timor.nutrients/inst/plots_report_files/figure-html/seasonal-1.png" alt="(ref:seasonal)" width="576" />
<p class="caption">(\#fig:seasonal)(ref:seasonal)</p>
</div>

There is something strange with Baucau values. That something to focus on. At the moment leave it apart and continue with other municipalities.

(ref:seasonal-2) Seasonal distribution of catch weight and nutrients. The values are normalized on the number of trips of each municipality highlighting the average monthly yield independently from the sample size.

<div class="figure">
<img src="/Users/lore/My Drive/WorldFish/Timor.nutrients/inst/plots_report_files/figure-html/seasonal-2-1.png" alt="(ref:seasonal-2)" width="576" />
<p class="caption">(\#fig:seasonal-2)(ref:seasonal-2)</p>
</div>

What is (are) the driver (drivers ) of the seasonal differences we see between municipalities? One could be differences in taxa composition.

\pagebreak

# Catch composition

(ref:composition) Aggregated stock of the 10 most important species in each municipality.

<div class="figure">
<img src="/Users/lore/My Drive/WorldFish/Timor.nutrients/inst/plots_report_files/figure-html/composition-1.png" alt="(ref:composition)" width="1056" />
<p class="caption">(\#fig:composition)(ref:composition)</p>
</div>

The composition of the most representative taxa is heterogeneous among the municipalities. In particular, Atauro seems to be quite different from the others.

(ref:taxa) Interannual distribution of weekly aggregated values of the 10 most important species.

<div class="figure">
<img src="/Users/lore/My Drive/WorldFish/Timor.nutrients/inst/plots_report_files/figure-html/taxa-1.png" alt="(ref:taxa)" width="1056" />
<p class="caption">(\#fig:taxa)(ref:taxa)</p>
</div>
