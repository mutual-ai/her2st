# Spatial Deconvolution of HER2 positive Breast Tumors Reveals Novel Intercellular Relationships

## Description
All data, results and code related to the paper _Spatial Deconvolution of HER2 positive Breast Tumors Reveals Novel Intercellular Relationships_ can be found here within. For large sets of images and tables, we provide scripts that are self-contained within this repository (i.e., all you need to do is to run them to reproduce our images)


## Structure
* `data/`
    * `ST-cnts/` : contains data for the 36 breast cancer sections used in this study
    * `ST-imgs/` : contains the associated HE-images for the 36 sections used in this study
    * `ST-spotfiles/` : contains tables with selected spots under tissue used to subset the raw gene count matrices
    * `go-sets/` : GO gene sets. Named go-{GO-ID}.tsv
    * `public.yaml` : markdown file with links to the publicly available data sets that we've used
* `res/`
    * `ST-pat/`
        * `img/` : images showing the pathologist's annotations
        * `lbl/` : meta files (tsv) where each spot is labeled according to the pathologist's annotations
    * `ST-cluster/`
        * `lbl/` : meta files (tsv) where each spot is labeled by membership of the expression based clusters
        * `markers/` : marker genes for each cluster
        * `fea/` : functional enrichment analysis results for each cluster
        * `pat-enr/` : enrichment of clusters within the pathologist's regions
        * `core-sig/` : core signature for tumor and immune populations
        * `motivation.xlsx` : motivations regarding how the clusters were annotated
    * `ST-deconv/` 
        * `props/{major,minor,subset}.zip` : spot-wise proportion estimates for respective tier, obtained using Stereoscope 
        * `pat-enr/{major,minor,subset}.zip` : enrichment of cell types within the pathologist's regions
        * `cluster-enr/{major,minor,subset}.zip` : enrichment of cell types within the expression based clusters 
        * `corrs/{major,minor,subset}.zip` : correlation plots for all cell types within respective tier
    * `ST-SW-enr/`
        * `raw/` : spot-wise pathway enrichment; values are given for within spot each section 
        * `viz/` : visualization of the raw spot-wise pathway enrichment
    * `TLS-pred/`
        * `coef-full.tsv` : coefficient values (including intercept) for all genes in the model to predict TLS-score
        * `tls-signature.tsv` : the tls-signature presented in the paper
        * `tls-fea.tsv` : functional enrichment results for the tls-signature
* `scripts/`
    * FILL IN
    * `* corrplot.R` : script to use correlation plot. Uses bootstrapping to estimate confidence. (Figure 3 and 4)
    *  `* enriched-region.py` : estimates enrichment of types in defined regions by a permuation test (Figure 3 and 4). Produces palette-plots.
    * `* spw-enr.py` : calculates spot-wise enrichment of gene set using Fisher's exact test (Figure 4)
    * `* rank-plot.py` : generates a rank-plot where genes to highlight can be provided by a text file or as an argument.

    * `* viz-tls-score.py` : visualized, B-cell and T-cell proportions together with calculated TLS-score
    * `* tls.py` :  fits the TLS-model. Takes as input a set of count matices and associated proportion values for these. 
    * `* fea.py` :  conduct functional enrichment analysis using g:Profiler for a set of provided genes. Generates tsv file with all pathways and an image. (Figure 5)
    * `* predict.py` : predict TLS-score for a ST/Visium section. Takes count data for the section to apply the model to and a coefficient file (generated by tls.py)


`*` := with CLI (command line interface). Do ```./script.py -h``` to see all different options that can be selected/parameters to be configures.
