# bwacycle
BWAcycle - a simple cross-platform pipeline for Influenza virus NGS data analysis. 

Description of files and folders:
 - map_all.py - main script file
 - Reference - folder with reference sequences for all Influenza A and B virus genes in FASTA format
 - stuff - folder with required binaries (both Linux and Windows)
 
Requirements:
 - Python version 3.6 or higher. (Original installer from Python website (https://www.python.org/downloads/) or Miniconda (https://docs.conda.io/en/latest/miniconda.html))
 - Matplotlib library (Can be installed via pip: ```pip3 install matplotlib```)
 - FastQC quality assessment tool (https://www.bioinformatics.babraham.ac.uk/projects/fastqc/). Jar files are provided in stuff folder.
 - Trimmomatic data trimming tool (http://www.usadellab.org/cms/?page=trimmomatic). Jar files are provided in stuff folder
 - BWA sequence aligner (https://github.com/lh3/bwa). Linux and Windows binaries are provided in stuff folder
 - Samtools and Bcftools - software for SAM and BAM files manipulating (https://github.com/samtools/). Linux and Windows binaries are provided in stuff folder
 - Bam-readcount tool (https://github.com/genome/bam-readcount). Linux and Windows binaries are provided in stuff folder
 - FastQC and Trimmomatic reqiure Java to be installed
 - Windows binaries were built using Cygwin (https://cygwin.com/). All necessary Cygwin dlls are provided in stuff folder

Installation:
 - Clone repository using git: ```git clone https://github.com/Molecular-virology-lab/bwacycle.git``` or download ZIP-archive to your computer.
 - The following folder structure is prefered:<br/>
      - root data analysis folder/ <br/>
                                 - Reference<br/>
                                 - stuff<br/>
                                 - map_all.py<br/>
                                 - folders with FASTQ files from your sequencer<br/>
     
 Usage:
  - mount to folder with your FASTQ files
  - prepare sample list in tab-delimited text file with 3 columns: sample id used in Illumina sample sheet, sample name, sample number in Illumina sample sheet and save it in the same directory with FASTQ files.<br/>
  Example sample list:<br/><br/>
  36[tab]A/Example/01/2000[tab]45<br/><br/>
  (In this example script will use files 36_S45_L001_R1_001.fastq.gz and 36_S45_L001_R2_001.fastq.gz and will generate FASTA files with strain name A/Example/01/2000)
  
  - To run BWAcycle on Windows:<br/> ```python3 ..\map_all.py -list <provide your sample list> -mode <select one avaliable>```<br/>
  - To run BWAcycle on Linux:<br/> ```python3 ../map_all.py -list <provide your sample list> -mode <select one avaliable>```
  
  Avaliable modes:<br/>
   - A (search for H1-H16, N1-N9, PB2, PB1, PA, NP, M, NS)<br/>
   - B (search for BHAvic, BHAyam, BNAvic, BNAyam, BPB2, BPB1, BPA, BNP, BM, BNS)<br/>
   - A_seasonal (search for H1, H3, N1, N2, PB2, PB1, PA, NP, M, NS)<br/>
   - H1 (search for H1, N1, PB2, PB1, PA, NP, M, NS)<br/>
   - H3 (search for H3, N2, PB2, PB1, PA, NP, M, NS)<br/>
   - default (combined A + B)

Contact: Artem Fadeev (afadeewATgmail.com)
 
##To be completed soon...
Resulting files description
