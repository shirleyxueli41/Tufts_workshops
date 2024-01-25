Date: Feb 6, 2024   
Author: Shirley Li, xue.li37@tufts.edu     
Class ID: Sp24-IDGH-1001-1-Bioinformatics    
Canvas link: https://canvas.tufts.edu/courses/55751/files/folder/IDGH_1001_Bioinformatics_2024 
# Introduction to Metagenomics - Session 2
## Learning Objective
1.	NCBI Database Proficiency: Develop skills to efficiently locate and interpret data on the [NCBI database](https://www.ncbi.nlm.nih.gov/), including navigating to specific BioProject and SRA experiment pages.
2.	Data Retrieval from Published Papers: Gain the ability to identify and extract relevant raw data and metadata from published scientific papers.
3.	Metagenomic Sequencing Platforms: Learn about different sequencing platforms by analyzing their data characteristics, specifically focusing on [Illumina](https://www.sciencedirect.com/science/article/pii/S0198885921000628) and [Nanopore technologies](https://www.nature.com/articles/nbt.3423).
4.	Taxonomic Analysis: Acquire practical experience in assigning taxonomic labels to sequencing reads using Kraken2 on [Tufts Galaxy](https://galaxy.cluster.tufts.edu/), and in converting and visualizing these labels with Krona.
5.	Data Comparison and Interpretation: Enhance skills in comparing visualized data with NCBI SRA information and drawing conclusions about sample composition.

## Exercise 1
### Objecttive: 
In this section, you will learn to navigate the [NCBI database](https://www.ncbi.nlm.nih.gov/bioproject). Known for its comprehensive nature, the database hosts a variety of sections, each tailored to specific types of datasets. Your focus will be on mastering the ability to identify and navigate through BioProject pages, SRA experiment pages, and SRA Runs linked to published research papers. This proficiency is crucial in the field of bioinformatics, enabling us to effectively leverage previous research as a foundation for new discoveries and advancements in the study of biological data.

<img src="https://github.com/shirleyxueli41/Tufts_workshops/assets/88347911/32383594-b895-4f0b-9107-882313c69304" width="900" height="300">          

   <em>A screenshot of NCBI website</em>       
   
### Instructions:
Your task involves exploring the NCBI database to gather specific information:

1. Check the research paper ["Evaluation of full-length nanopore 16S sequencing for detection of pathogens in microbial keratitis"](https://peerj.com/articles/10778/) . Your goal is to identify the associated BioProject ID within the paper.
    * Hint: BioProject ID is [PRJEB37709](https://www.ncbi.nlm.nih.gov/bioproject/PRJEB37709/) in the "Data Availability" section of the paper.        
2. Answer the following queries regarding the BioProject, and keep a record of your findings:           
    a. What is the URL for this specific BioProject?        
    b. Total number of samples included in this BioProject.        
    c. Count of SRA runs associated with this BioProject.          
    d. Determine the sequencing platform used for SRA run [ERR4836970](https://www.ncbi.nlm.nih.gov/sra/?term=ERR4836970).          
3. Apply the same procedure as step 2 for a second research paper: ["Apply the same procedure as step 2 for a second research paper"](https://www.nature.com/articles/s41597-022-01762-z).
    * Hint: BioProject ID is in the "Data Records" section of the paper. 
   


## Exercise 2        
### Objective:
Engage in a hands-on exercise to explore the NCBI database using specific SRA run IDs. Your task will involve navigating various sections of the database and applying your understanding of sequencing technologies to hypothetical research scenarios.   

### Instructions:
Utilize the SRA run ID to search the NCBI website. Explore the corresponding SRA, BioSample, and BioProject sections related to this SRA run.             
1. Assignment Completion: Choose one SRA run and document your findings in the provided Google Spreadsheet: [Exercise Spreadsheet](https://docs.google.com/spreadsheets/d/1s_NVSPLABQtTmB-EXwY4gmNOzGJxr2RE7WVnbFz6djw/edit#gid=927665114).

<img src="https://github.com/shirleyxueli41/Tufts_workshops/assets/88347911/de1556b2-f038-451a-b4dc-a4f3d324aeae" width="900" height="300">   

<em>A screenshot of the spreadsheet</em>                 

2. Questions for Analysis         
    a. **Mars Soil Sample Analysis**: If you obtained a soil sample from Mars for identifying microorganisms and assembling their genomes, which sequencing technology would be optimal? Consider factors like the detection of novel organisms and the precision required for genome assembly. Discuss your choice, focusing on read length, accuracy, and cost implications.         
    b. **Gut Microbiome Study**: In researching the impact of dietary changes on the gut microbiome, what type of sample would you collect, and which sequencing technology would be most suitable? Provide your rationale for this choice.         

Additional Resources: Hints for these questions can be found [here](https://github.com/shirleyxueli41/Tufts_workshops/blob/main/IGDH-1001_2024Feb/Exercise%202_hints.pdf).        


## Exercise 3      
### Objective:
Use Kraken2 for taxonomy assignment and visualize the results with a Krona plot. Interpretate and present the result. 

### Exercise 3A: Taxonomy assignment and interpretation.
### Instructions:
1. Log in to your [Galaxy account](https://galaxy.cluster.tufts.edu/).
2. Name the history as "Session 2 Metagenomics-ERR12302112"
3. Now let's start the analysis:
    1. **Download and Extract Reads in FASTA/Q** format from NCBI SRA with the following parameters:       
            * **Accession:** ERR12302112      
![Screenshot 2024-01-25 at 16 09 58](https://github.com/shirleyxueli41/Tufts_workshops/assets/88347911/9cafa3e2-78ad-4040-9e7f-a3baae378512)
    2. **Kraken2** assign taxonomic labels to sequencing reads with the following parameters:       
            * **Single or paired end**: Single      
            * **Input Sequences**: the output from last step.     
            * Click Create Report, then set **Print a report with aggregrate counts/clade to file** to Yes       
            * **Select a Kraken2 database**: Minikraken2 v2
      ![Screenshot 2024-01-25 at 16 17 44](https://github.com/shirleyxueli41/Tufts_workshops/assets/88347911/26d7e312-a8a7-49c5-b3d5-39e9ce5893d9)

   

# Reference
https://bisonnet.bucknell.edu/files/2021/05/Kraken2-Help-Sheet.pdf
