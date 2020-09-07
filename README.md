# org.Si.eg.db
Anntation database for Setaria italica
## Install
```
#Download the annoation package org.Si.eg.db.7z and uncompress it
install.package("org.Si.eg.db",repos=NULL,type="source")
```
## How to use it 
```
library(org.Si.eg.db)
##enrichment analysis
# install_github("guokai8/richR")
library(richR)
sigo<-buildOwn(dbname="org.Si.eg.db",anntype="GO")  
siko<-buildOwn(dbname="org.Si.eg.db",anntype="KEGG") 
genes<-sample(keys(org.Si.eg.db),200)
resgo<-richGO(genes,godata=sigo)
resko<-richKEGG(genes,kodata=siko)
head(resgo)
head(resko)
#make figures
ggbar(resgo)
ggdot(resko)
ggnetplot(resgo)
```
## Contact information
For any questions please contact guokai8@gmail.com
