# Kickstart Project Work

### Overview {-}

#### Purpose {-}

#### Learning Objectives {-}

#### Introduction {-}

In this lab we will kickstart your project work by analyzing one of the first BioDIGS long-read datasets from Baltimore soil sequenced using PacBio HiFi technology.
Afterwards, you will be ready to analyze additional publicly available datasets and compare the results with other datasets of interest (e.g. managed vs wetland soil, corn soy vs cowpea diet).

| Title      | Technology | Source           |
| ---------- | ---------- | ---------------- |
| [BioDIGS Pilot](http://biodigs.gdscn.org){target="_blank"} | PacBio | [Galaxy History](https://usegalaxy.org/u/cutsort/h/biodigs-pacbio-pilot-data){target="_blank"} |
| [Wetland](https://pubmed.gov/38926353){target="_blank"} | Nanopore | [PRJNA1119519](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1119519){target="_blank"} (e.g. SRR29366187) |
| [Habitats](https://www.exeter.ac.uk/research/groups/geography/casper){target="_blank"} | Nanopore | [PRJNA1112790](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1112790){target="_blank"} (e.g. SRR29081438) |
| | |
| [Zymo Gut Standard](https://www.zymoresearch.com/products/zymobiomics-gut-microbiome-standard){target="_blank"} | PacBio | [Galaxy History](https://usegalaxy.org/u/cutsort/h/zymo-gut-data){target="_blank"} (e.g. SRR13128014) |
| [Zymo Fecal Reference](https://www.zymoresearch.com/collections/zymobiomics-microbial-community-standards/products/zymobiomics-fecal-reference-with-trumatrix-technology){target="_blank"} | PacBio | [Galaxy History](https://usegalaxy.org/u/cutsort/h/zymo-fecal-data){target="_blank"} |
| Diet | PacBio & Nanopore | [PRJNA1139951](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1139951){target="_blank"} (e.g. SRR29980925) |

### **Activity 1** -- Get Data {-}

The BioDIGS PacBio pilot dataset is available as a Galaxy History.
You can quickly import this dataset and any other dataset available as a Galaxy History by clicking on the link in the table above, clicking on `Import this history`, and then `Copy History` as you did in [Taxonomy Profiling].

Additional datasets can be obtained from the NCBI [Sequence Read Archive](https://www.ncbi.nlm.nih.gov/sra){target="_blank"} which is the "largest publicly available repository of high throughput sequencing data".
After identifying an `SRR` number (see examples in the table above) you can import the dataset using the Galaxy tool named `Faster Download and Extract Reads in FASTQ`.

::: {.notice}
`Faster Download and Extract Reads in FASTQ` will add three Collections to your history (Pair end, Single end, and Other).
You can simplify this so that your dataset of interest appears as a new history entry by using the `Extract dataset` tool and selecting `The first dataset` from the `Single-end data` Collection.
Learn more about Collections in [Troubleshooting]
:::

Shown here is an example of importing [SRR13128014](https://www.ncbi.nlm.nih.gov/sra/?term=SRR13128014) which is a PacBio HiFi dataset of the ZymoBIOMICS [Gut Microbiome Standard](https://www.zymoresearch.com/products/zymobiomics-gut-microbiome-standard) that contains "21 different strains to mimic the human gut microbiome".

<img src="kickstart-project-work_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f0aedcb71c_0_0.png"  />

### **Activity 2** -- Adjust for PacBio HiFi {-}

PacBio [HiFi](https://www.pacb.com/technology/hifi-sequencing) technology provides "highly accurate long-read sequencing".
The higher accuracy (99.9% on par with short reads and Sanger sequencing) allows for some simplification of the workflows in [Taxonomy Profiling] and [Finding AMRs] which were developed for Oxford Nanopore technology.
These adjustments include:

- Skip the `Trim and QC Reads` workflow as `Porechop` adapter removal and `fastqp` quality trimming may be unnecessary/incorrect
- Run the `NanoPlot` tool directly to calculate summary statistics
- Run `ABRicate` directly on `flye_consensus_fasta` rather than on `sample_all_contigs` (produced by `medaka` which is designed to polish nanopore sequencing data)

::: {.notice}
Datasets close to and larger than 10 GB require increasingly more computational resources to analyze.
In addition to taking longer to process, some tools such as `flye` may fail with errors such as `ERROR: Looks like the system ran out of memory`.
For these situations, try using the `Split file` tool to create smaller subsets of data to analyze.
See note above about extracting a dataset from a Collection.
:::

<img src="kickstart-project-work_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f0aedcb71c_0_19.png"  />

<img src="kickstart-project-work_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f0aedcb71c_0_54.png"  />

<img src="kickstart-project-work_files/figure-html//1fH9s5OLcRF5meZtFWTJe89RFvJSh125kdjhdqp5smqA_g2f0aedcb71c_0_59.png"  />

### **Activity 3** -- Interpret Results {-}

### Footnotes {-}

#### Resources {-}

- Google Doc

#### Contributions and Affiliations {-}

- Jennifer Kerr, Notre Dame of Maryland University
- Rosa Alcazar, Clovis Community College
- Frederick Tan, Johns Hopkins University

Last Revised: September 2024
