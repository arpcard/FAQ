# FAQ
Frequently Asked Questions pertaining to CARD usage, CARD website navigation and RGI webtool usage.
<p>
<details closed>
  <summary>CARD FAQ</summary>
  <br>
  <details closed>
    <summary>Q1: How do I cite CARD?</summary>
    <br>
    A: Alcock et al. 2020. CARD 2020: antibiotic resistome surveillance with the Comprehensive Antibiotic Resistance Database. Nucleic Acids Research, 48, D517-D525.
  </details>

  <details closed>
    <summary>Q2: How do I contact the CARD curators or developers?</summary> 
    <br>
    A: You can contact the CARD curators or developers directly at card@mcmaster.ca, Twitter at @arpcard, or at GitHub.
  </details>

  <details closed>
    <summary>Q3: How is the CARD curated?</summary>
    <br>
    A: The CARD is curated by a group of experts in the area of antimicrobial resistance (AMR) and bioinformatics, including consultation with outside experts where needed.
  </details>

  <details closed>
    <summary>Q4: How often is CARD updated?</summary>
    <br>
    A: The CARD is updated monthly.
  </details>


  <details closed>
    <summary>Q5: What data can be included? Can I add unpublished data?</summary>
    <br>
    A: Only peered reviewed, published data that is also associated with a GenBank accession can be included in the curated CARD data with the exception of beta-lactamases. We can additionally provide genome or whole-genome shotgun assembly bulk annotation for private data sets using the Resistance Gene Identifier, please contact card@mcmaster.ca.
  </details>


  <details closed>
    <summary>Q6: What has changed since the first version of the CARD, as published in McArthur et al. 2013. The Comprehensive Antibiotic Resistance Database. Antimicrobial Agents and Chemotherapy, 57, 3348-3357?</summary>
    <br>
    A: The CARD is now more tightly focussed on antimicrobial resistance (AMR) reference sequences and associated detection models. Each sequence curated into the CARD is now associated with both the Antibiotic Resistance Ontology to provide classification and semantic context as well as defined detection models and parameters. The CARD has additionally abandoned use of internal accessions for sequences and now exclusively uses GenBank accessions.
  </details>

  <details closed>
    <summary>Q7: How do I find a list of all resistance genes in a particular organism?</summary>
    <br>
    A: CARD now provides annotated genomes, plasmids, and whole-genome shotgun assemblies in the Genomes & Variants section.
  </details>
  <details closed>
    <summary>Q8: For intrinsic resistance genes for which resistance is conferred by specific mutations, does CARD include all known mutant sequences?</summary>
    <br>
    A: The CARD does not contain complete sequences of resistant mutants, due to the fact the individual mutations are often reported in the literature without the complete mutant gene sequence being deposited in GenBank. Instead, the CARD maintains a complete list of all resistance SNPs relative to a reference sequence, which may either be a reported mutant sequence or a wild-type sequence. As such, it is important that SNP mapping be included in analysis of any genes that require mutation to confer resistance. This step is included in the Resistance Gene Identifier but not naive BLAST analyses. Computational predicted sequence variants are available in the Genomes & Variants section.
 </details>

 <details closed>
  <summary>Q9: How are Minimum Inhibitory Concentration (MIC) data curated?</summary>
    <br>
    A: The CARD does not yet curate MIC data directly, but instead records the resistance profile of resistance genes. This is performed using the categorical confers_resistance_to relationship within the Antibiotic Resistance Ontology, e.g. beta-lactamases confers_resistance_to beta-lactams, as well as the specific confers_resistance_to_drug relationship, e.g. AAC(1) confers_resistance_to_drug apramycin. The latter requires constant curatorial effort and may have gaps - please let us know if find such missing data within the CARD.
 </details>
 <details closed>
   <summary>Q10: How can I help with CARD?</summary>
   <br>
   A: Any problems you find in CARD, you can post an issue at https://github.com/arpcard/amr_curation/issue.
 </details>
</details>
</p>
<p>
<details closed>
  <summary>RGI(Resistance Gene Identifier) FAQ</summary>
  <br>
  
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
    A: While the CARD systematically curates categorical confers_resistance_to relationships within the Antibiotic Resistance Ontology, e.g. beta-lactamases confers_resistance_to beta-lactams, curation of specific confers_resistance_to_drug relationships, e.g. AAC(1) confers_resistance_to_drug apramycin, is rarely complete due to the volume of literature to curate, variation in MICs for genes among pathogens, and changing clinical breakpoints. As such, curation of confers_resistance_to_drug relationships for accurate prediction of antibiogram is currently inconsistent throughout the CARD and our RGI software is focussed primarily upon accurate prediction of resistome, not antibiogram.
  </details>

  <details closed>
    <summary>Q8: Are both PERFECT and STRICT hits with the Resistance Gene Identifier (RGI) functional AMR genes?</summary>
    <br>
    A: If a hit is PERFECT, the predicted gene perfectly matches a known resistance gene curated in the CARD at the amino acid level (including SNPs if that is part of the detection model). Only published AMR genes, with subsequent submission of sequence to GenBank, with clear evidence of elevated MICs are curated into CARD. However, a PERFECT hit does not indicate if the AMR gene is expressed or if it results in elevated MIC in the pathogen of interest. Activity of AMR genes can be pathogen and strain specific. STRICT hits are not exact matches to a published AMR sequence, but are similar to CARD reference sequences within detection model cut-offs defined by the CARD curators. STRICT hits are likely functional, but those with low percent similarity to the curated CARD reference sequence may require experimental verification.
  </details>

  <details closed>
    <summary>Q9: Does the Resistance Gene Identifier (RGI) work for metagenomics data?</summary>
    <br>
    A: Yes, the RGI can analyze metagenomics data at the command line. Full details are available at GitHub.
  </details>

  <details closed>
    <summary>Q10: What are Percent Identity, Bitscore, and E-value?</summary>
    <br>
    A: From the NCBI BLAST Glossary, percent identity is the extent to which two (nucleotide or amino acid) sequences have the same residues at the same positions in an alignment, often expressed as a percentage. The expectation value or expect value represents the number of different alignments with scores equivalent to or better that is expected to occur in a database search by chance. The lower the E value, the more significant the score and the alignment. The bitscore is derived from the raw alignment score, taking the statistical properties of the scoring system into account. Because bitscores are normalized with respect to the scoring system, they can be used to compare alignment scores from different searches. In addition, they provide finer resolution of differences among similar proteins than the expectation score.
  </details>
</details>
</p>
<p>
<details closed>
  <summary>DOWNLOAD FAQ</summary>
  <br>
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
    <summary>Q3: I want the Resistomes and Varian. Where can I find it?</summary>
    <br>
    A: You can find the Resistomes and Variant at https://card.mcmaster.ca/resistomes.
  </details>
</details>
</p>

