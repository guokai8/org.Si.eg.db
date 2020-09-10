# org.Si.eg.db
__Anntation database for Setaria italica__
## Install
```
#Download the annoation package org.Si.eg.db.7z and uncompress it
git clone https://github.com/guokai8/org.Si.eg.db/
cd org.Si.eg.db
tar -xzf org.Si.eg.db.7z
install.packages("org.Si.eg.db",repos=NULL,type="source")
```
## How to use it 
```
library(org.Si.eg.db)
```
## Enrichment analysis
```
# install_github("guokai8/richR")
library(richR)
sigo<-buildOwn(dbname="org.Si.eg.db",anntype="GO")  
siko<-buildOwn(dbname="org.Si.eg.db",anntype="KEGG") 
genes<-sample(keys(org.Si.eg.db),200)
resgo<-richGO(genes,godata=sigo)
resko<-richKEGG(genes,kodata=siko,,builtin=FALSE)
head(resgo)
head(resko)
#make figures
ggbar(resgo)
ggdot(resko)
ggnetplot(resgo)
```
## Use the annotation database
```
#check the id type
columns(org.Si.eg.db)
# show annotation of gene
## use AnnotationDbi::select to avoid function overwrite
select(org.Si.eg.db,keys=genes,columns='GENENAME')
# show mapped rice id
select(org.Si.eg.db,keys=genes,columns='Os')
# show mapped TAIR id
select(org.Si.eg.db,keys=genes,columns='TAIR')
#KO brite
select(org.Si.eg.db,keys=genes,columns='KO')
#
```
## Contact information
For any questions please contact guokai8@gmail.com
