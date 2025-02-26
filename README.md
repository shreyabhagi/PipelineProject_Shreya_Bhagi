# PipelineProject_Shreya_Bhagi
Problem 1:
 retrieve and convert SA data
1. downloaded the transcriptomes from NCBI SRA
- **Donor 1 (2dpi)**: SRR6109134
- **Donor 1 (6dpi)**: SRR6109137
2. downloaded the files using wget
3. converted SRA to FASTQ files using split-files and fasterq-dumo
-fasterq-dump SRR6109134 --split-files -O .
-fasterq-dump SRR6109137 --split-files -O .
4. renamed the files for consistency purposes later on
-mv SRR6109134_1.fastq donor1_2dpi_R1.fastq
-mv SRR6109134_2.fastq donor1_2dpi_R2.fastq
-mv SRR6109137_1.fastq donor1_6dpi_R1.fastq
-mv SRR6109137_2.fastq donor1_6dpi_R2.fastq
5. done a quick test on the sample dataset
-head -n 40000 donor1_2dpi_R1.fastq > donor1_2dpi_sample_R1.fastq
-head -n 40000 donor1_2dpi_R2.fastq > donor1_2dpi_sample_R2.fastq
-head -n 40000 donor1_6dpi_R1.fastq > donor1_6dpi_sample_R1.fastq
-head -n 40000 donor1_6dpi_R2.fastq > donor1_6dpi_sample_R2.fastq
6. logged that output by using echo:
-echo "Downloaded and converted FASTQ files from SRA" > ../logs/PipelineProject.log
-echo "Donor 1 (2dpi) - FASTQ Files: donor1_2dpi_R1.fastq, donor1_2dpi_R2.fastq" >> ../logs/PipelineProject.log
-echo "Donor 1 (6dpi) - FASTQ Files: donor1_6dpi_R1.fastq, donor1_6dpi_R2.fastq" >> ../logs/PipelineProject.log
-echo "Created sample dataset with first 40,000 lines" >> ../logs/PipelineProject.log


