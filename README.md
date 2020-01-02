# Set Operations In R

A small set of commands which, in R, do some set operations.


## Intersect Bed (rough equivalent of bedtools intersectBed)
```
# modified lightly from Dave Tang
# https://rdrr.io/github/davetang/bedr/man/intersect_bed.html

# a and b are GRanges objects
intersect_bed <- function(a, b){
  hits <- findOverlaps(a, b)
  cbind(as.data.frame(a[queryHits(hits)]),
                  as.data.frame(b[subjectHits(hits)]))
    
}
```
