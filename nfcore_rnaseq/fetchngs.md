## Reference paper
In this workshop, we will use the RNAseq data from a paper studying the epigenetic regulator `PRMT5` and its obligate cofactor `MEP50` in human.   
![PRMT5 Paper](images/PRMT5_paper.png)
From the paper, we learn that the raw data is available in in Gene Expression Omnibus at `GSE80182`.
<img src="images/accession.png" alt="accession" width="50%">

## Fetchngs
To run the `fetchngs` pipeline, we can first create a working directory where the pipeline will run inside. 
In my case, I will use `/cluster/tufts/yzhang85/rt/yzhang85/nf-core_workshp`. You can use your group's project directory as the working directory. **Please do not use your `$HOME`**.
```
mkdir -p /cluster/tufts/yzhang85/rt/yzhang85/nf-core_workshp/fetchngs
cd /cluster/tufts/yzhang85/rt/yzhang85/nf-core_workshp/fetchngs
```

### Create a sampleet.csv as input
```
echo GSE80182 > samplesheet.csv
```

## Open OnDemand
In the demo, we will run the pipeline using the `fetchngs` pipeline deployed on [Tufts Open OnDemand server](https://ondemand.pax.tufts.edu/)

Under `Bioinformatcis Apps`, you can find `fetchngs` within the `nf-core pipelines` subcategory. 

This pipeline is pretty simple. We can leave most parameters as default. 

Below are the arguments we will use:
- Number of hours: 2
- Select cpu partition: batch
- Resveration for class, training, workshop: default
- Version: 1.11.0
- Working Directory: The direcotry your created above. For me, it is `/cluster/tufts/yzhang85/rt/yzhang85/nf-core_workshp/fetchngs`
- Output directory Name: fetchngsOut
- Input: samplesheet.csv
- nf_core_pipeline: rnaseq
- force_sratools_download: true

![fetchngs](images/fetchngs.png)

After you fill in these fields, we can launch now. 

When the job starts, you can click the link after `Session ID: `. If you `view` `outpupt.log`, you can check the running processes of nextflow. 
```

------------------------------------------------------
                                        ,--./,-.
        ___     __   __   __   ___     /,-._.--~'
  |\ | |__  __ /  ` /  \ |__) |__         }  {
  | \| |       \__, \__/ |  \ |___     \`-._,-`-,
                                        `._,._,'
  nf-core/fetchngs v1.11.0
------------------------------------------------------
Core Nextflow options
  runName                   : wise_keller
  containerEngine           : singularity
  launchDir                 : /cluster/tufts/yzhang85/rt/yzhang85/nf-core_workshp/fetchngs
  workDir                   : /cluster/tufts/yzhang85/rt/yzhang85/nf-core_workshp/fetchngs/work
  projectDir                : /cluster/tufts/biocontainers/nf-core/pipelines/nf-core-fetchngs/1.11.0/1_11_0
  userName                  : yzhang85
  profile                   : tufts
  configFiles               : 

Input/output options
  input                     : samplesheet.csv
  nf_core_pipeline          : rnaseq
  outdir                    : fetchngsOut

Institutional config options
  custom_config_base        : /cluster/tufts/biocontainers/nf-core/pipelines/nf-core-fetchngs/1.11.0/1_11_0/../configs/
  config_profile_description: The Tufts University HPC cluster profile provided by nf-core/configs.
  config_profile_contact    : Yucheng Zhang
  config_profile_url        : https://it.tufts.edu/high-performance-computing

Max job request options
  max_cpus                  : 72
  max_memory                : 120 GB
  max_time                  : 7d

!! Only displaying parameters that differ from the pipeline defaults !!
------------------------------------------------------
If you use nf-core/fetchngs for your analysis please cite:

* The pipeline
  https://doi.org/10.5281/zenodo.5070524

* The nf-core framework
  https://doi.org/10.1038/s41587-020-0439-x

* Software dependencies
  https://github.com/nf-core/fetchngs/blob/master/CITATIONS.md
------------------------------------------------------
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_IDS... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_RUN... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_FAS... -

[-        ] process > NFCORE_FETCHNGS:SRA:SRA_IDS... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_RUN... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_FAS... -
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_TO_... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_MER... -
[-        ] process > NFCORE_FETCHNGS:SRA:MULTIQC... -

[-        ] process > NFCORE_FETCHNGS:SRA:SRA_IDS... [  0%] 0 of 1
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_RUN... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_FAS... -
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... [  0%] 0 of 1
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_TO_... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_MER... -
[-        ] process > NFCORE_FETCHNGS:SRA:MULTIQC... -

executor >  slurm (1)
[cb/bb53b0] process > NFCORE_FETCHNGS:SRA:SRA_IDS... [  0%] 0 of 1
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_RUN... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_FAS... -
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... [  0%] 0 of 1
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_TO_... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_MER... -
[-        ] process > NFCORE_FETCHNGS:SRA:MULTIQC... -

executor >  slurm (2)
[cb/bb53b0] process > NFCORE_FETCHNGS:SRA:SRA_IDS... [  0%] 0 of 1
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_RUN... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_FAS... -
[90/989701] process > NFCORE_FETCHNGS:SRA:FASTQ_D... [  0%] 0 of 1
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:FASTQ_D... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_TO_... -
[-        ] process > NFCORE_FETCHNGS:SRA:SRA_MER... -
[-        ] process > NFCORE_FETCHNGS:SRA:MULTIQC... -
```