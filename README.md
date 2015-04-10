# CCQM MBWG Microbial Identity 2013  
Description: International interlaboratory study sequencing 16s rRNA from two genomic reference materials.   

This study compared 16S rRNA gene sequencing data from two single organism genomic DNA reference materials generated by 6 difference laborites each using different sequencing platforms and methods.  The data were compared on three levels, biologically conserved positions, biologically variable positions, and set of biological variants.  The manuscript is currently in prep and the pre-print will be made available shortly.   
Scripts and pipelines presented have been run on Mac OSX 10.8 and 10.9 and Ubuntu 12.04 LTS.  A vagrant box ([http://www.vagrantup.com/](http://www.vagrantup.com/)) is available as well as the results of the analysis presented in the publication ([data](https://drive.google.com/folderview?id=0B8fRaMByhphgflZPcGJFSnJNcWxsR2VQLXM2T1RUcks1enhYZngzMGtZNE4xT3NnenN6YUk&usp=sharing),[vagrant image](https://drive.google.com/folderview?id=0B8fRaMByhphgfjJxY1h4SThCVjNXLThNT2dwaVQzZzhDOWR1VS1JV0NaZlRGeUZuZ3BfV3M&usp=sharing)). Please note this link is currently broken, we are actively looking into alternatives for long term storage of the virtual image and data files.

### Requirements  
Unix based operating system is required for a number of the pipeline dependencies.  
  
## Procedure for reproducing sequence analysis
From the `ccqm_mbwg_16S` execute the command `bash pipe.sh`, then compile the Rnw files using knitr.

### General Notes
####Directory structure  
  
    ccqm_mbwg_16S/    
        stats/ 
           data/                   -- data files generated as part of statistical analysis
           
        pub/  						-- Rnw scripts for generating tables used in the publication and the supplemental results document
           
        bioinf/
            bin/                   -- executables for third party software
            fastq-data/            -- raw sequence data
            resources/             -- additional input files required to run pipelines
            results/               -- output from bioinformatic pipelines
            scripts/               -- scripts written for bioinformatic analysis
            src/                   -- source code for third party software
            trace-data/            -- trace data obtained from GenBank

####Dependencies
##### Third Party Software and Packages
**Software** see links below for installation procedures  

- sratoolkit [http://www.ncbi.nlm.nih.gov/Traces/sra/?view=software](http://www.ncbi.nlm.nih.gov/Traces/sra/?view=software)  
- BWA [http://bio-bwa.sourceforge.net/](http://bio-bwa.sourceforge.net/)  
- TMAP [https://github.com/nh13/TMAP](https://github.com/nh13/TMAP)  
- Picard [http://picard.sourceforge.net/](http://picard.sourceforge.net/)
- GATK [http://www.broadinstitute.org/gatk](http://www.broadinstitute.org/gatk) 
- mothur [http://www.mothur.org/wiki/Download_mothur](http://www.mothur.org/wiki/Download_mothur)
- prinseq [http://prinseq.sourceforge.net/](http://prinseq.sourceforge.net/)

**Programming languages and Packages**  

* Python  
  *  biopython  
* R  
  * ggplot2, reshape2, plyr, knitr, stringr, dply, gtools, xtable
* Bash 

Users need to obtain third party software from link listed above and move the required compiled binaries to the *bioinf/bin* directory or create links.

1. AddOrReplaceReadGroups.jar
2. bcftools
3. bwa
4. CreateSequenceDictionary.jar
5. GenomeAnalysisTK.jar
6. mothur
7. prinseq-lite.pl
8. SortSam.jar
9. tmap
