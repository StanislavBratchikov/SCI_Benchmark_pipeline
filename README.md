# SCI_Benchmark_pipeline
A pipeline to provide benchmarking for Single Cell data integration tools
## Intro
This pipeline was inspired by  [this paper](./Papers_and_refs/SCBIP_paper.pdf)
that   
> benchmarked 16 popular data integration tools on 13 data integration tasks... using14 metrics to evaluate 
the integration methods on their ability to remove batch effects while conserving biological variation

The actual implementation of it could be found [here](https://github.com/theislab/scib-reproducibility).
## Updates and challenges 
### Updates
### Challenges 
- [ ] Try-test Experiment implementation
        To see whether SCIBP works a negative/positive controls need to be benchmarked.  
        1. As one option it was proposed to introduce it to 2 lab samples of SC data: integrated and non-integrated.Both of them could be from some labeled dataset. Non-integrated data could be simulated by artificially corrupting subset of 
         one sample expression data introducing the batch effect. Then these two samples could be compared using the SCIBP metrics. The former sample is expected to have higher score and ranking then the latter.
         The Positive control could be manufactured the same way. Integrated data could be randomly assigned batch labels. The score of this control should be higher than the negative one.
        2. As second option, take some open-source integrated and non-integrated data and compare them.

