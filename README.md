# project1-sequence-analysis
This task simulates part of a next-generation sequencing (NGS) data analysis workflow, in which sequencing reads are compared with a known reference sequence to identify nucleotide differences, or mismatches. These mismatches can then be used to identify and characterise mutations within the sequenced DNA.
# DNA Read Mismatch Analysis
# Title and Purpose
This program takes DNA sequencing reads and compares them to a reference sequence, identifying mismatches. It investigates whether a genotoxic agent causes more mutations in treated samples than in control samples.
# How to run the program
Open the .ipynb notebook in Google Colab by clicking Files -> Open notebook -> GitHub. Then choose Runtime and Run all to run the program. Run the cells in order.
# Inputs and Outputs
Inputs: A reference DNA sequence and a list of sequencing reads. Each read has an ID, sample name, group and DNA sequence.
Outputs: Summary tables showing valid and invalid reads, mismatch percentages and the most common mismatch positions. The program also lists the types of substitution and uses a Welch's t-test to compare treated and control samples
# Code Design
1. Separate functions- I separated calculations from printing. For example, summarise_one_sample will calculate the results, while print_summary_table displays them. This makes the code easier to test and understand
2. Reusable functions- I used get_top_positions to identify the most common mismatch positions. This way, the same code is not repeated and tied positions are handled consistently.
3. Handling invalid reads- Instead of removing invalid reads, I kept them in the results with an empty mutation list. This allows the program to count invalid reads without raising errors when analysing sequences of the wrong length
# Testing
- I tested lowercase DNA sequences to check they are converted to uppercase before mismatches are identified
- I tested samples with only invalid reads to ensure the program can handle them without a division by zero error
- I tested an additional group so that the comparison would only include treated and control samples. 
