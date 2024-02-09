awk -F"," 'OFS=","{print $29,$2,$3,"auto"}' /cluster/tufts/xli37/test_run/nfcore/2024-02-08/samplesheet/samplesheet.csv  |sed 's/"//g'  > /cluster/tufts/xli37/test_run/nfcore/rnaseq/samplesheet.csv
