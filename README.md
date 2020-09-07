# org.Si.eg.db
Anntation database for Setaria italica
## Install
```
library(devtools)
install_github("guokai8/org.Si.eg.db")
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
resgo<-richGO(gene,godata=sigo)
resko<-richKEGG(gene,kodata=siko)
head(resgo)
head(resko)
#make figures
ggbar(resgo)
ggdot(resko)
```
## Contact information
