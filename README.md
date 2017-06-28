Armadillo Mapper (v0.1.0)
=========================

Armadillo Mapper (AM) is a web application that automatically updates
the potential distribution of the hairy long-nosed armadillo (*Dasypus
pilosus*), which is endemic to the cloud forest and subparamo habitats
of Peru. Users could upload new observations of *D. pilosus* and AM will
output the updated potential distribution made by [Maxent
algorithm](version%203.3.3k;%20https://biodiversityinformatics.amnh.org/open_source/maxent/).

There are three ways to use AM.

1.  User can direct use AM via this
    [link](http://armadillomapper.fengxiao.info).

2.  User can download this repository and deploy it on a Shiny server
    [(see more instructions)](https://shiny.rstudio.com/deploy/).

3.  If user wants to run AM locally (e.g., a personal Rstudio).

<!-- -->

1.  AM requires the following R packages *leaflet*, *shiny*, *dismo*,
    *raster*, *sp*, *rJava*, and *ggplot2* to be installed.

<!-- -->

    install.packages(c("leaflet","shiny","dismo","raster","sp","ggplot2","rgeos","rJava"))

1.  AM relies on Maxent algorithm, thus user must put a copy of
    **maxent.jar**
    [(download)](https://github.com/mrmaxent/Maxent/tree/master/ArchivedReleases/3.3.3k)
    in a specific folder. Put the file 'maxent.jar' in the 'java' folder
    of *dismo* package. The folder can found by running
    **system.file("java", package="dismo")**. Additional, R and Java
    must both be under 32-bit or 64-bit (e.g., 32-bit R & 32-bit Java).
    Please refer to more details of runing maxent in R by
    **?dismo::maxent**

<!-- -->

    library("leaflet")
    library("shiny")
    library("dismo")
    library("raster")
    library("sp")
    library("ggplot2")
    library("rgeos")
    library("rJava")
    runGitHub("ArmadilloMapper", "shandongfx")

Overview folders and files
------------------------------------------

ArmadilloMapper/  
├── ui.R `draws the interface`  
├── server.R `implements all analysis`  
├── global.R `defines languages & colors`  
├── internalFunctions.R            `defines functions for variable selection`   
├── raw\_data\_clean/ `stores data of Feng et al. (2017)`  
├── raw\_data\_clean/web translation\_v2.csv
`stores strings of the interface (English/Spanish)`  
├── www/ `stores html elements`  
├── www/google-analytics.js `Google Analytics script`  
├── maxent\_outputs/ `stores maxent output`  
└── userUpload/ `stores user uploaded data`