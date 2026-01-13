# Phylogenetics
# MCMC Tree on map


```
library(phytools)
library(randomcoloR)
library(mapdata)
library(viridis)
library(randomcoloR)



tree <- read.nexus("coi.tre")
class(tree)
plot(tree)
tree$tip.label
Ntip(tree)


south_africa <- as.matrix(read.table(file ="coordinates.txt",header=T, sep="\t",row.names = 1)) 

head(south_africa)
tail(south_africa)


cols<-setNames(sample(viridis(n=Ntip(tree))),
               tree$tip.label)



obj<-phylo.to.map(tree,south_africa,database="worldHires",plot=FALSE,direction="rightwards")


plot(obj,xlim=c(0,50),ylim=c(-38,-8), colors=cols,ftype="i",fsize=0.9,cex.points=c(0.8,1.4),map.fill="lightblue")

```
#plot(obj,xlim=c(0,50),ylim=c(-38,-18),fsize=0.9,ftype="i",asp=0.8,lty="solid",map.bg="darkgreen",map.fill="lightblue",lwd=3,pts=FALSE,colors="orange",cex.points=1.4,delimit_map=TRUE)

