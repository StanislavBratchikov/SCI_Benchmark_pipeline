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
Input should be ```.h5ad``` files containing sc expression data including different batches. The output should be ```.h5ad``` with integrated batch data. 
## Validation
To see whether SCIBP works and does so efficiently unit tests need to be developed.   
- [ ] negative/positive controls
  1. Integrated lab single cell dataset is sampled in two subsets. Cells from one subset are randomly assigned to batch labels - this would be positive
     control. Remaining subset is artificially introduced to batch effect via any predefined manner of changing its expression data - this would be negative
     control. SCIBP is expected to rate better and rank higher the positive control compared to negative.
  2. Open-source integrated and non-integrated data as positive and negative controls. The SCIBP result should rank integrated data higher.
- [ ] efficacy controls 
    
    High throughput data either open source or lab source should not break the SCIBP. Dataset containing large amounts of 
    cells should be ranked better than negative controls.
- [ ] __WIP__

