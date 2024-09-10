# Taxonomy Profiling

### Overview {-}

#### Purpose {-}

#### Learning Objectives {-}

#### Introduction {-}

<img src="taxonomy-profiling_files/figure-html//1fN-efiepolGfj50pPk7DQ7yu-batzIRP6HZ2SSnxp-k_g35f391192_00.png"  />

[[slides](https://docs.google.com/presentation/d/1fN-efiepolGfj50pPk7DQ7yu-batzIRP6HZ2SSnxp-k){target="_blank"}]
[[video](https://drive.google.com/file/d/1C6iAjCESmyhvzjaH0txyBNYJ5ZiD5ys0){target="_blank"}]

### **Activity 1** -- Trim and QC Reads {-}

*Estimated time: 40 min (~25 min computing)*

#### Instructions {-}

##### 1. Import dataset {-}

- Open the [GTN Pathogen Detection from Nanopore](https://usegalaxy.org/u/cutsort/h/gtn-pathogen-data){target="_blank"} public history
- Click on `Import this history` and then `Copy History`

<img src="taxonomy-profiling_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f6b21b1164_0_15.png"  />

Confirm `Barcode10_Spike2.fastq.gz` exists in your history by clicking on the Home button in the top menu

<img src="taxonomy-profiling_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f6b21b1164_0_25.png"  />

##### 2. Run workflow {-}

- Open the [Trim and QC Reads](https://usegalaxy.org/u/cutsort/w/qc-reads){target="_blank"} public workflow
- Click on `Run` and then `Run Workflow` on the `Barcode10_Spike2.fastq.gz` dataset

<img src="taxonomy-profiling_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f6b21b1164_0_35.png"  />

Wait ~25 minutes as the NanoPlot, Porechop, and fastp jobs are scheduled, run, and complete

<img src="taxonomy-profiling_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f6b21b1164_0_39.png"  />

##### 3. View results {-}

- Click on the Display icon (eyeball) next to the dataset tagged `NanoPlot-Original`
- Compare the number of reads, length, quality, etc. with the report tagged `NanoPlot-QCed`

<img src="taxonomy-profiling_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f6b21b1164_0_50.png"  />

#### Questions {-}

You can refer to [this completed history](https://usegalaxy.org/u/cutsort/h/finding-amrs-complete){target="_blank"} to answer these questions while you wait for your jobs to complete.

| 1A. How many megabases were sequenced?  What percentage was removed by the trimming step? |
|:-|
| <br> |

| 1B. What are the median and mean read lengths?  Why is the mean is longer than the median? |
|:-|
| <br> |

### **Activity 2** -- Taxonomy Profiling {-}

*Estimated time: 50 min (~25-35 min computing)*

#### Instructions {-}

##### 1. Run workflow {-}

- Open the [Taxonomy Profiling](https://usegalaxy.org/u/cutsort/w/taxonomy-profiling){target="_blank"} public workflow
- Click on `Run` and then `Run Workflow` with the following parameters
  - Dataset: `fastp on data 5: Read 1 output`
  - kraken_database: `Prebuilt Refseq indexes: PlusPF`
- Wait ~35 minutes as the Kraken2, KrakenTools, and Krona jobs are scheduled, run, and complete

<img src="taxonomy-profiling_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f6b21b1164_0_57.png"  />

##### 2. View results {-}

- Click on the Display icon (eyeball) next to the dataset tagged `taxonomy_profiling_visualization_krona_pie_chart`
- Examine how many reads were classified as Salmonella, Escherichia coli, Homo sapiens, and Unclassified

<img src="taxonomy-profiling_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f6b21b1164_0_67.png"  />

#### Questions {-}

| 2A. What is the percentage of unclassified for the sample? |
|:-|
| <br> |

<br>

| 2B. What are the kindgoms found for the sample? |
|:-|
| <br> |

<br>

| 2C. Where might the eukaryotic DNA come from? |
|:-|
| <br> |

<br>

| 2D. How is the diversity of *Proteobacteria* versus *Firmicutes* Phylum? |
|:-|
| <br> |

<br>

| 2E. How much *E. coli* and *Salmonella* are present in the sample? |
|:-|
| <br> |

### Footnotes {-}

#### Resources {-}

- [Google Doc](https://docs.google.com/document/d/1r4Pr4f_An8A5sB4NGMG4sYU4vWVMQE-q)

#### Contributions and Affiliations {-}

- Jennifer Kerr, Notre Dame of Maryland University
- Rosa Alcazar, Clovis Community College
- Frederick Tan, Johns Hopkins University
- Based on "Pathogen detection from (direct Nanopore) sequencing data using Galaxy - Foodborne Edition" ([GTN](https://gxy.io/GTN:T00393))

Last Revised: September 2024
