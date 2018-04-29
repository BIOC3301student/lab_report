# lab_report
Repository of batch scrips for BIOC3301 lab report

Scripts were used in the following order:
  1. joined_reads
  2. splitting_libraries
  3. OTU
  4. biom_summary
  5. core_diversity
  6. compare_categories
  7. summarize_taxa
  8. group_significance
  9. split_otu
 
Joined reads
  Uses join_paired_ends.py
  Joins paired-end illumina reads to be used in demultiplexing
  
Splitting libraries
    Uses split_libraries.py
    Splits libraries according to the barcodes in the mapping file
    The incomplete mapping file was used at this stage
    
OTU
  Uses pick_closed_reference_otus.py with the SILVA database for OTU identification
  
Biom summary
  Uses biom summarize-table to summarize the data in the BIOM file generated from OTU
  
Core diversity
  Uses core_diversity_analysis.py to run core QIIME divesity analysis
  The complete mapping file is used from this stage onwards
  
Compare categories
  Uses compare_categories.py
  Determine the statistical significance of sample groupings based on the categories in the mapping file
  This script was run multiple times and the category specified by -c was changed each time
  This was to determine the statistical significance of sample groupings based on: 
      pH, nitrogen, phosphorus, potassium, moisture and vegetation    
      
Summarize taxa
  Uses summarize_taxa
  Used to summarize the OTU table based on phyla groupings and class groupings for the following group_significance tests
  
Group significance
  Uses group_significance.py
  Used to identify which OTUs are differentially represented in the sample groups test previously.
  The OTU table determined by -i was changed to look at OTUs on the level of phlya and class
  The kruskal wallis method was chosen as it is non-parametric and can be used on more than two groups
  This script was run mutliple times and the category determined by -c was changed to test the significance 
  for several soil properties. 
  
Split otu
  Uses split_otu_table_by_taxonomy.py to obtain OTU tables for each phylum group to be used in summarize taxa
  
