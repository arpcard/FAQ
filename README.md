# FAQ
Frequently Asked Questions pertaining to CARD usage, CARD website navigation and RGI webtool usage.

---

**TABLE OF CONTENTS**

1. [Key Documentation](#key-documentation)
2. [CARD FAQs](#card-faqs)
3. [RGI FAQs](#rgi-faqs)
4. [ARO DOWNLOAD FAQs](#aro-download-faqs)

---

# **KEY DOCUMENTTION**

* Alcock et al. 2023. CARD 2023: Expanded Curation, Support for Machine Learning, and Resistome Prediction at the Comprehensive Antibiotic Resistance Database. Nucleic Acids Research, 51, D690-D699. [PMID 36263822](https://pubmed.ncbi.nlm.nih.gov/36263822/)
* [Resistome Gene Identifier software documentation](https://github.com/arpcard/rgi)
* [CARD Copyrights & Disclaimers](https://card.mcmaster.ca/about)
* [YouTube Video Lecture: Canadian Bioinformatics Workshops 2023 - Infectious Disease Genomic Epidemiology - Antimicrobial Resistant Gene (AMR) Analysis using CARD & RGI](https://www.youtube.com/watch?v=FvOCDlcYaTo&list=PL3izGL6oi0S8RG8vnwLXFznzJnKh8OR8F&index=6)
* [State of the CARD 2021 Presentations & Demonstrations](https://github.com/arpcard/state-of-the-card-2021)

---

# **CARD FAQs**
<details closed>
<summary>Q1: How do I cite CARD?</summary>
<br>
A: Alcock et al. 2023. CARD 2023: Expanded Curation, Support for Machine Learning, and Resistome Prediction at the Comprehensive Antibiotic Resistance Database. Nucleic Acids Research, 51, D690-D699. [PMID 36263822](https://pubmed.ncbi.nlm.nih.gov/36263822/)
</details>

<details closed>
<summary>Q2: How do I contact the CARD curators or developers?</summary> 
<br>
A: You can contact the CARD curators or developers directly at card@mcmaster.ca or at GitHub (https://github.com/arpcard/rgi).
</details>

<details closed>
<summary>Q3: How is the CARD curated?</summary>
<br>
A: The CARD is curated by a group of experts in the area of antimicrobial resistance (AMR) and bioinformatics, including consultation with outside experts where needed.
</details>

<details closed>
<summary>Q4: How often is CARD updated?</summary>
<br>
A: The CARD is updated approximately monthly.
</details>

<details closed>
<summary>Q5: What data is included in CARD? Can I add unpublished data?</summary>
<br>
A: Only published AMR genes and mutations, with subsequent submission of sequence to GenBank, with clear evidence of elevated MICs are curated into CARD.
The only exception is beta-lactamase genes, which are being named faster than they can be validated. Alcock et al. (2023) provided details on CARD's curation paradigm. We can additionally provide genome or whole-genome shotgun assembly bulk annotation for private data sets using the Resistance Gene Identifier, please contact card@mcmaster.ca.
</details>

<details closed>
<summary>Q6: What has changed since the first version of the CARD, as published in McArthur et al. 2013. The Comprehensive Antibiotic Resistance Database. Antimicrobial Agents and Chemotherapy, 57, 3348-3357?</summary>
<br>
A: The CARD is now more tightly focussed on antimicrobial resistance (AMR) reference sequences and associated detection models. Each sequence curated into the CARD is now associated with both the Antibiotic Resistance Ontology to provide classification and semantic context as well as defined detection models and parameters. The CARD has additionally abandoned use of internal accessions for sequences and now exclusively uses GenBank accessions.
</details>

<details closed>
<summary>Q7: What are CARD detection models and how are bitscore cut-offs determined?</summary>
<br>
A: CARD now organizes reference AMR gene sequences and mutations in the context of bioinformatics models, which are listed here: https://card.mcmaster.ca/ontology/40323. These model types are discussed in detail in Alcock et al. 2023. The most frequently used model type is the Protein Homolog Model for presence or absence of acquired resistance genes, such as beta-lactamases (see this thread on how CARD determines bitscore cutoffs: https://github.com/arpcard/rgi/issues/140). The second most frequently used model type is the Protein Variant Model for detection of intrinsic genes that have acquired mutations conferring resistance. The RGI Documentation gives detailed information on how CARD models are used: https://github.com/arpcard/rgi.
</details>

<details closed>
<summary>Q8: What are CARD Short Names?</summary>
<br>
A: A CARD-specific abbreviation for AMR gene names associated with Antibiotic Resistance
Ontology terms, often not based on the literature. This is used for programmatic and 
compatibility purposes and is not ontologically relevant. Each ontology term with an 
associated AMR detection model has a CARD Short Name that appears in CARD data files 
and output generated by RGI. If the original gene name is less than 15 characters, the 
CARD short name is identical; if the gene name is greater than 15 characters, the CARD 
Short Name has been abbreviated by CARD curators specifically to identify the proper 
gene or protein name. All CARD Short Names are unique and have whitespace characters 
replaced by underscore characters. The convention for pathogen names is capitalized 
first letter of the genus followed by the lowercase first three letters of the species 
name. The antibiotic abbreviations are from https://journals.asm.org/journal/aac/abbreviations
plus some custom abbreviations by the CARD curators. Simple CARD Short Names often do not
involve either, e.g. CTX-M-15, but where applicable the CARD Short Names follow pathogen_gene
or pathogen_gene_drug. The full lists of abbreviations can be found at:
https://card.mcmaster.ca/latest/data
</details>

<details closed>
<summary>Q9: How do I find a list of all resistance genes in a particular organism?</summary>
<br>
A: CARD now provides annotated genomes, plasmids, and whole-genome shotgun assemblies in the Resistomes, Variants, & Prevalence section.
</details>

<details closed>
<summary>Q10: For intrinsic resistance genes for which resistance is conferred by specific mutations, does CARD include all known mutant sequences?</summary>
<br>
A: The CARD does not contain complete sequences of resistant mutants, due to the fact the individual mutations are often reported in the literature without the complete mutant gene sequence being deposited in GenBank. Instead, the CARD maintains a complete list of all resistance SNPs relative to a reference sequence, which may either be a reported mutant sequence or a wild-type sequence. As such, it is important that SNP mapping be included in analysis of any genes that require mutation to confer resistance. This step is included in the Resistance Gene Identifier but not naive BLAST analyses. Computational predicted sequence variants are available in the Resistomes, Variants, & Prevalence section.
</details>

<details closed>
<summary>Q11: How are Minimum Inhibitory Concentration (MIC) data curated?</summary>
<br>
A: The CARD does not yet curate MIC data directly, but instead records the resistance profile of resistance genes. This is performed using the categorical confers_resistance_to_drug_class relationship within the Antibiotic Resistance Ontology, e.g. beta-lactamases confers_resistance_to_drug_class beta-lactams, as well as the specific confers_resistance_to_antibiotic relationship, e.g. AAC(1) confers_resistance_to_antibiotic apramycin. The latter requires constant curatorial effort and may have gaps - please let us know if find such missing data within the CARD.
</details>

<details closed>
<summary>Q12: How can I help with CARD?</summary>
<br>
A: Any problems you find in CARD, you can post an issue at https://github.com/arpcard/amr_curation/issue.
</details>

---

# **RGI FAQs**

<details closed>
<summary>Q1: I am having problems running RGI, what do I do?</summary>
<br>
A: Please ensure that you have all the necessary dependencies on your device. Dependencies are listed at https://github.com/arpcard/rgi. Also ensure that you've installed it correctly. If assistance is still required, please email us at card@mcmaster.ca. Be sure to include detailed information how your process, a snapshot of your input file, your error, and anything that you believe is important to know. The more you tell us, the better we can help you.
</details>

<details closed>
<summary>Q2: I have a windows PC. How do I run RGI?</summary>
<br>
A: Windows is not supported by RGI. Please use MacOS or Linux. Alternatively, if you have access to a remote virtual environment, you may use that instead.
</details>

<details closed>
<summary>Q3: Can I use the Resistance Gene Identifier offline?</summary>
<br>
A: Yes, the Resistance Gene Identifier can now be downloaded as command-line software.
</details>

<details closed>
<summary>Q4: How can I install RGI on my own device?</summary>
<br>
A: Please refer to https://github.com/arpcard/rgi for documentation on RGI functionality and installation processes.
</details>

<details closed>
<summary>Q5: How do I use the RGI tool on the CARD website?</summary>
<br>
A: The FAQ github repository contains a PDF explaining the step-by-step process of accessing the RGI webtool.
</details>

<details closed>
<summary>Q6: Can the SNP mapping data be downloaded?</summary>
<br>
A: Yes, the SNP mapping data is now available in the Downloads sections within the card.json and snps.txt files.
</details>

<details closed>
<summary>Q7: Can CARD and the RGI accurately predict antibiogram?</summary>
<br>
A: While the CARD systematically curates categorical confers_resistance_to_drug_class relationships within the Antibiotic Resistance Ontology, e.g. beta-lactamases confers_resistance_to_drug_class beta-lactams, curation of specific confers_resistance_to_antibiotic relationships, e.g. AAC(1) confers_resistance_to_antibiotic apramycin, is rarely complete due to the volume of literature to curate, variation in MICs for genes among pathogens, and changing clinical breakpoints. As such, curation of confers_resistance_to_antibiotic relationships for accurate prediction of antibiogram is currently inconsistent throughout the CARD and our RGI software is focussed primarily upon accurate prediction of resistome, not antibiogram.
</details>

<details closed>
<summary>Q8: Are both PERFECT and STRICT hits with the Resistance Gene Identifier (RGI) functional AMR genes?</summary>
<br>
A: If a hit is PERFECT, the predicted gene perfectly matches a known resistance gene curated in the CARD at the amino acid level (including SNPs if that is part of the detection model). Only published AMR genes, with subsequent submission of sequence to GenBank, with clear evidence of elevated MICs are curated into CARD. However, a PERFECT hit does not indicate if the AMR gene is expressed or if it results in elevated MIC in the pathogen of interest. Activity of AMR genes can be pathogen and strain specific. STRICT hits are not exact matches to a published AMR sequence, but are similar to CARD reference sequences within detection model cut-offs defined by the CARD curators (see this thread on how CARD determines bitscore cutoffs: https://github.com/arpcard/rgi/issues/140). STRICT hits are likely functional, but those with low percent similarity to the curated CARD reference sequence may require experimental verification. The RGI Documentation gives detailed information on Perfect / Strict / Loose paradigm: https://github.com/arpcard/rgi.
</details>

<details closed>
<summary>Q9: Does the Resistance Gene Identifier (RGI) work for metagenomics data?</summary>
<br>
A: Yes, the RGI can analyze metagenomics data at the command line. Full details are available at GitHub: https://github.com/arpcard/rgi.
</details>

<details closed>
<summary>Q10: What are Percent Identity, Bitscore, and E-value?</summary>
<br>
A: From the NCBI BLAST Glossary, percent identity is the extent to which two (nucleotide or amino acid) sequences have the same residues at the same positions in an alignment, often expressed as a percentage. The expectation value or expect value represents the number of different alignments with scores equivalent to or better that is expected to occur in a database search by chance. The lower the E value, the more significant the score and the alignment. The bitscore is derived from the raw alignment score, taking the statistical properties of the scoring system into account. Because bitscores are normalized with respect to the scoring system, they can be used to compare alignment scores from different searches. In addition, they provide finer resolution of differences among similar proteins than the expectation score.
</details>

<details closed>
<summary>Q11: Can you use Resistome & Variants <i>in silico</i> predictions in RGI <i>main</i> to annotate assembly contigs?</summary>
<br>
A: The alleles in CARD's Resistomes & Variants dataset are <i>in silico</i> prediction of AMR alleles by running RGI against genomic data available in GenBank. They are not experimentally characterized genes. While they can be used by <i>RGI bwt</i> as an additional reference set for short read alignment, they cannot be used by <i>RGI main</i> to annotate genome assemblies. <i>RGI main</i> uses hand-curated AMR gene detection models involving BLAST, bitscore cut-offs, reference sequences, and curated SNP lists, i.e. much more than read alignment to reference sequences. The underlying reference sequences in these detection models are from experimentally validated alleles reported in the scientific literature, e.g. Sser_gyrB_FLO, https://card.mcmaster.ca/ontology/39891. RGI's Perfect / Strict / Paradigm and BLAST ensures that all possible antibiotic resistance genes in CARD are annotated for genome assemblies. In contrast, short read alignment under <i>RGI bwt</i> requires close sequence similarity for annotation and the broader sequence variation in CARD's Resistomes & Variants can overcome this limitation if the canonical references in CARD's detection models are from a different organism that you have sequenced, albeit the annotation can be based upon unvalidated genes. See RGI's documentation: https://github.com/arpcard/rgi
</details>

<details closed>
<summary>Q12: What RGI settings are best for a Metagenome-Assembled Genome (MAG)?</summary>
<br>
A: If the MAG is long and of high quality assembly, default RGI analysis is more than sufficient to predict Perfect / Strict / Loose hits to the CARD AMR detection models. For shorter or fragmentary assemblies, we suggest using RGI <i>main</i> or the RGI web portal with the <i>Low Quality/Coverage</i> settings to allow RGI to include partial open reading frames (ORFs) and ORFs with errors. To additionally compensate for possible evolutionary distance between the MAGs and the organisms curated in CARD, we suggest examining Loose hits for possible new/divergent antimicrobial resistance genes. As there are often many Loose hits, sorting results by % identity or HSP length can help, but additional use of the <i>Include Nudge</i> option will convert Loose hits of any length with at least 95% identity to CARD reference sequences to Strict hits if you wish to use a broader Strict criteria. See https://github.com/arpcard/rgi to review the Perfect / Strict / Loose paradigm.
</details>

<details closed>
<summary>Q13: How do I submit a bug report for RGI?</summary>
<br>
A: Go to the https://github.com/arpcard/rgi/issues page and click new issue. On this page select the Bug Report Template. Follow the instructions on the template and input all information instructed or any that is deemed important. Click submit and wait until the CARD help-desk responds.
</details>

---

# **ARO DOWNLOAD FAQs**

<details closed>
<summary>Q1: What are the URLs for all the ontologies in CARD?</summary>
<br>
A: Antibiotic resistance Ontology (ARO):

/aro/accession e.g https://card.mcmaster.ca/aro/3003689 

Relationship Ontology (RO):

/ro/accession e.g https://card.mcmaster.ca/ro/is_a 

Model Ontology (MO): 

/mo/accession e.g https://card.mcmaster.ca/mo/0000009 

NCBI Taxonomy Ontology (NCBITaxon):

/ncbitaxon/accession e.g https://card.mcmaster.ca/ncbitaxon/570 

Gene Ontology (GO):

/go/accession e.g https://card.mcmaster.ca/go/0022804

</details>

<details closed>
<summary>Q2: How can I download the latest software or data without using the download page?</summary>
<br>
A: Download latest data:

/latest/data e.g https://card.mcmaster.ca/latest/data 

Download latest software:

/latest/software e.g https://card.mcmaster.ca/latest/software

</details>

<details closed>
<summary>Q3: I want the Resistomes and Variants. Where can I find it?</summary>
<br>
A: You can find the Resistomes and Variant at https://card.mcmaster.ca/resistomes.
</details>

