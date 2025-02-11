# DuplicateFinder
A java standalone application to find sequence duplicates in your dataset
Protein (or Nucleotide) Sequences downloaded from NCBI Taxonomy Browser or other similar databases for an organism contain sequences which are duplicates of each other. Sometimes, these sequence duplicates turn out to be duplicate GenPept records, as found during our analyses, which need to be removed from the dataset to remove bias.
Here, we provide a simple desktop application to extract the sets of duplicates from a dataset and also provide the list of unique sequences from the input dataset.

**How to use the program:**
1) Download the zip file DuplicateFinder.zip here. Extract contents to a desired location.
2) Click on the DuplicatesFinder.jar, the program starts and you are good to go. Since this is a java program, it is OS independent.
(NOTE: You need to have java runtime environment (JRE) installed in your system to run the program. To check if your system has java installed, refer to the end of this post.)

**Input Files accepted by the program:**
1) Comma separated values (*.csv)
   The data should contain two colums – Identifier number, Sequence.
   Identifier is a unique number to identify the sequence.
   Sequence is the set of sequences to be analyzed.

2) FASTA (*.fasta) or Tab delimited (*.txt)
   The sequences should be in fasta format as shown below
   ```
   >716349
   ACGTAGCATCGATCG
   >837468
   TGATGCATGCATCGT
   ```

**Output Files created by the program:**
The output files are created in the same directory and folder as the input file. Two output files are created:
1) Duplicates sequences File: A file containing the sets of duplicates (Duplicates.csv). The columns in the file are:
     a) Duplicate Set – the index of groups of duplicates;
     b) Count – the index of a duplicate sequence in the set of duplicates it belongs to. So each series of numbers from 1 to n represents a set of sequence duplicates with a total of n duplicate sequences in that set;
     c) Sequence – the duplicate sequences in ascending order (for easy visual checking).
     d) Identifier – the number from the identifier column in the .csv file or the identifier number after '>' in the .fas and .txt files.
     e) Remarks – remarks if any.

2) Unique sequences file: A file containing the unique sequences from the dataset in fasta format (Unique.fas). The file includes one representative from each set of duplicates.

NOTE: In both output files, the sequences are arranged in ascending order of the sequence.

**To check if your system has JRE:**
Go to command prompt and type java –version.
   If your system has java, you will see the version details
   If your system does not have java installed, you get the error:
   ‘java’ is not recognized as an internal or external command, operable program or batch file
    You can then download the JRE for your OS from Sun Microsystems: http://www.java.com/en/download/manual.jsp)
