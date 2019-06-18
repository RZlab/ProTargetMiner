ProTargetMiner R Shiny package
================


# System Requirements
## Hardware Requirements
The ProTargetMiner package requires a standard office computer.
Generation of the PLS-DA model will usually take less than 1min, however with increased data sets size this might be different. 

## Software Requirements
### OS Requirements
This package was develop under *Windows 7* and was tetsed also on *macOS: XXXX (XX)*.

### R Dependencies
The ProTargetMiner package depends on:
```
shiny
plotly
tidyverse
DT
shinycssloaders
shinydashboard
mixOmics
```

# Installation Guide
Please install all necessary packages from CRAN or Bioconductor:
    
    install.packages(c("shiny", "plotly", "tidyverse", "DT", "shinycssloaders", "shinydashboard"))
    BiocManager::install("mixOmics")    
Which should take less than 1min.   

Once all packages are installed, please start the ProTargetMiner R shiny with the following command:

    shiny::runGitHub("ProTargetMiner", "beuschc")
    
# Description
The ProTargetMiner R Shiny package is an automated online software for anticancer drug target/mechanism deconvolution. ProTargetMiner is the first publicly available expandable proteome signature library of anticancer molecules in cancer cell lines. Based on 55 compound signatures in A549 cells, the main resource contains data on 7,328 proteins and 1,307,859 refined protein-drug pairs. The drug targets/mechanisms can be deconvoluted by partial least square-discriminant analysis modeling (PLS-DA), where the proteome signature of a given compound is contrasted against a library of other signatures and specific proteins are revealed. For 9 molecules representing most diverse action mechanisms and common cancer cell lines MCF-7, RKO and A549, deep proteome datasets are made available. The database can be easily extended and merged with new compound signatures.

The shiny package provides a user interface for data integration and PLS-DA modeling for either a selected cell line or in the merged dataset as well as for extracting the PLS-DA loading rankings for top proteins (Fig. 1a). In short, the user obtains the proteome signature of the desired compound at LC50 concentration in 48h in any of the available cell lines (or all of them) in form of the gene names and fold changes in (preferably) three replicates, and feeds this information to the ProTargetMiner R Shiny according to the step-by-step procedure given in Fig. 1b. A template for the input .CSV file is shown in Fig. 1c. The package output will be a PLS-DA model contrasting the given compound against the 9 diverse proteome signatures in that cell line (or 54 the original dataset), from which a ranking of specificity for proteins can be extracted for target/mechanism deconvolution. The proteins with lowest rankings (on either side of the plot) are therefore the most likely drug target candidates or mechanistic proteins. Clicking on the interactive PLS-DA plot gives the attributes of the selected proteins, e.g. name, number of peptides and sequence coverage, and will show the specific regulation of that protein. For more information, please refer to the paper: <https://www.biorxiv.org/content/10.1101/421115v1>

<img src="www/shiny_workflow.jpg" width="100%" />

# License

This project is covered under the **Apache 2.0 License**.
