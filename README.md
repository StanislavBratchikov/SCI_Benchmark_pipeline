# SCI_Benchmark_pipeline
A pipeline to provide benchmarking for Single Cell data integration tools
## Intro
This pipeline was inspired by  [this paper](./Papers_and_refs/SCBIP_paper.pdf)
that   
> benchmarked 16 popular data integration tools on 13 data integration tasks... using 14 metrics to evaluate 
the integration methods on their ability to remove batch effects while conserving biological variation

The actual implementation of it could be found [here](https://github.com/theislab/scib-reproducibility).
## Motivation 
Extensive need of validating and comparing different integration tools as well as their hyper parameters in the lab makes this
project highly up-to-date.This pipeline would allow researchers perform analysis of their integration tools performance.
## Usage 
The pipeline expects an anndata object with normalised and log-transformed counts in ```adata.X``` and counts in ```adata.layers['counts']```.
Data should include different batches and cell types.The output should be ```.h5ad``` with integrated batch data. Using ```scib.metrics.metrics()``` funtion ```scib``` provides 
pandas dataframe with all the parameters for the different metrics.
## Validation
To see whether SCIBP works and does so efficiently unit tests need to be developed.   

| Case study                |    Data    |   Result | Samples |
|:--------------------------:|:----------:|:--:|
| integrated samples don't need integration | 1 sample split into 2 batches artificially | dataset should rank higher than those with batch effect (i.e un-integrated 3' and 5' samples)  | SC334 |
| same biosamples should perform similarly |  technical replicate samples  | samples have the same scib performance |SC311, SC312|
| 3' and 5' chemistry samples integration|  same samples prepared with different chemistry (Karolina’s 3' vs 5' project)  | un-integrated samples produce batch effect. Integration should increase scib scores| SC486, SC612|
| CRISPRclean depletion samples produce batch which vanishes after integration |  same samples prepared normally and with jumpcode (JC) processing step | JC and SC samples are scored higher after integration | SC334, JC334|
|  |  Reyfman data: unintegrated vs integrated   | Integrated datasets are ranked higher than un-integrated | ??? |
| scib handles overintergrated samples|  overinegration of biologically different samples  | scib doesn't break when analysing large data| ???|

