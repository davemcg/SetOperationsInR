# SetOperationsInR

# Intersect Bed (equivalent of bedtools intersectBed)
# modified lightly from Dave Tang
# https://rdrr.io/github/davetang/bedr/man/intersect_bed.html
library(GenomicRanges)
# a and b are GRanges objects
intersect_bed <- function(a, b){
  hits <- findOverlaps(a, b)
  cbind(as.data.frame(a[queryHits(hits)]),
                  as.data.frame(b[subjectHits(hits)]))
    
}
