# RgeneticMap
A R function to draw genetic maps (linkage map), and can be used with R/qtl directly.  
You can export the maps as svg format and edit them with any svg editor (Inkscape is a good FREE svg editor).

# Example

```r
library(qtl)
data("hyper")
summary(hyper)

source("linkmap.R")
linkmap(hyper,chr=c(1,2,3))

pdf(file="geneticMap.pdf",paper="USr")
linkmap(hyper,chr=c(1,2))
linkmap(hyper,chr=c(1,2,3))
linkmap(hyper,chr=c(1,2,3,4))
dev.off()
```
**PNG format output**
![map](https://github.com/pinbo/RgeneticMap/blob/master/GeneticMap.png)

**SVG format output**
<img src="https://github.com/pinbo/RgeneticMap/blob/master/gmap.svg" width="100%" >
# Parameters
**linkmap <- function(object, chr, chr.space = 2, m.cex = 0.6, ...){...}**

Input of this function:
- **object**:
  + a "cross" object from R/qtl
  + a "map" class from the output of "pull.map" in R/qtl
  + a data frame with marker column, chromosme column and position column named as "mar", "chr" and "pos", respectively
- **chr**: a vector of chromosome names that need to be drawn.
- **chr.space**: space between each chromosomes
- **m.cex**: font size
- **...**: other plot parameters

# Credits
This script is a modification of function "link.map.cross" in R package "wgaim" (https://cran.r-project.org/web/packages/wgaim/index.html). I added marker positions on the left side of the chromosomes and make it look better.

# Other genetic map packages in R
- **LinkageMapView: Plot Linkage Group Maps with Quantitative Trait Loci** (https://cran.r-project.org/web/packages/LinkageMapView/index.html) [Right now it can only export pdf format]
