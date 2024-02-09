
### After fetching 
We will have a samplesheet.tsv stored under the output directory of fetching. We will then modify the samplesheet so it will be the input of the next step which is rnaseq.      

```shell
DIR=/cluster/tufts/xli37/test_run/nfcore/2024-02-08/
rnaseqDIR=/cluster/tufts/xli37/test_run/nfcore/rnaseq/
awk -F"," 'OFS=","{print $29,$2,$3,"auto"}' $DIR/samplesheet/samplesheet.csv  |sed 's/"//g'  |
sed 's/sample_description,fastq_1,fastq_2,auto/sample,fastq_1,fastq_2,strandedness/' \
> $rnaseqDIR/samplesheet.csv
```


### Progress file can be found here
```shell
/cluster/tufts/xli37/test_run/nfcore/rnaseq/pipeline_info/execution_trace_*
```

* Example of the progress file. The pipeline involves many steps, each is with one task_id. When a task is finished, that task will be logged here in this file, with other information like name of the task, status, duration, %cpu, and peak_vmem.      
* %cpu and peak_vmem are important information because we will know how much memory we should ask next time we run the pipelien.      
```
task_id	hash	native_id	name	status	exit	submit	duration	realtime	%cpu	peak_rss	peak_vmem	rchar	wchar
1	d6/4a9080	303711	NFCORE_RNASEQ:RNASEQ:PREPARE_GENOME:GUNZIP_GTF (hg38.ncbiRefSeq.gtf.gz)	COMPLETED	0	2024-02-09 14:44:43.053	4.9s	4s	72.6%	2.4 MB	7.2 MB	40 MB	792 MB
2	65/1b01a6	303701	NFCORE_RNASEQ:RNASEQ:PREPARE_GENOME:GUNZIP_FASTA (hg38.fa.gz)	COMPLETED	0	2024-02-09 14:44:43.039	23.7s	22.9s	86.9%	2.4 MB	7.2 MB	938.2 MB	3 GB
21	0e/5755be	305721	NFCORE_RNASEQ:RNASEQ:PREPARE_GENOME:CUSTOM_GETCHROMSIZES (hg38.fa)	COMPLETED	0	2024-02-09 14:45:07.819	11s	10s	99.7%	2.9 MB	11.9 MB	3 GB	35.2 KB
22	1f/69cfd0	305711	NFCORE_RNASEQ:RNASEQ:PREPARE_GENOME:GTF_FILTER (hg38.fa)	COMPLETED	0	2024-02-09 14:45:07.803	16s	15s	94.8%	16.3 MB	25.1 MB	3.8 GB	778.5 MB
24	68/002402	307408	NFCORE_RNASEQ:RNASEQ:PREPARE_GENOME:GTF2BED (hg38.filtered.gtf)	COMPLETED	0	2024-02-09 14:45:24.814	26.5s	25s	99.6%	4 GB	4 GB	778.7 MB	32.3 MB

```


### Remember to set `-resume` button if you run the pipeline adding additional samples.       
For example, if you initial run only have two samples A549_GFPkd_1 and A549_PRMT5kd_1 and the job finishes running successfully.         
After a few days, you have new data generated, which is A549_GFPkd_2 and A549_PRMT5kd_2.         
You can run the same pipeline by editing the samplesheets.tsv and run the pipeline in the same directory. The pipeline won't repeat the QC and ailgnment step for the first two samples.      
```
sample,fastq_1,fastq_2,strandedness
A549_GFPkd_1,SRR3362661_1.fastq.gz,SRR3362661_2.fastq.gz,auto
A549_GFPkd_2,SRR3362662_1.fastq.gz,SRR3362662_2.fastq.gz,auto
A549_PRMT5kd_1,SRR3362664_1.fastq.gz,SRR3362664_2.fastq.gz,auto
A549_PRMT5kd_2,SRR3362665_1.fastq.gz,SRR3362665_2.fastq.gz,auto
```
