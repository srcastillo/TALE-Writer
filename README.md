# TALE-Writer

The TALE Writer is a Python-based computational design tool for the efficient design ot TALE-based technologies: TALENs (https://pubmed.ncbi.nlm.nih.gov/26854857/) and DdCBEs (https://www.nature.com/articles/s41586-020-2477-4). It is recommended to run the TALE Writer in the Jupypter Notebook.

**TALE Writer can be used to:**

(I) Design TALENs around user-specified target sequences.

(II) Design C-to-T base editors against 5’-TC-3’ loci.

(III) Design C-to-T base editors specifically for premature termination codon (PTC) induction. 

The main input of the script is a sequence of target genes, and the output is the top-ranked design permutation (for TALEN design) or a list of the top-ranked design permutations for each target within the input sequence (for C-to-T base editor design). In general, a user-specified sequence is analyzed considering three design parameters: (I) Obligatory 5’-T0 for all TALE repeat arrays, (II) desired cut site or edit site at least four base pairs from the target sequence of either TALE repeat array, and (III) target and spacer sequences between 14 and 16 base pairs long (these lengths can be modified within the code). Based on these design parameters, a scoring system was developed; each possible design permutation is given a score, which consists of the sum of four Gaussian functions that depend on the length of the target and spacer sequences, and the position of the desired cut site or edit site within the spacer region. In brief, permutations that follow a 15-15-15 design format (TALE-gap-TALE) and that possess the desired cut site or edit site in the middle of the spacer sequence are favored. For PTC induction, herein defined as a DNA edit that results in the generation of a non-functional gene product due to the premature termination of translation, three types of edits were identified. First, the in-frame 5’-TGA-3’ motif, in which a G-to-A edit (equivalent to a C-to-T edit on the opposite strand) results in the stop codon UAA. Second, the 5’-TCAA-3’ motif (CAA in-frame), in which a C-to-T edit also results in the stop codon UAA. Lastly, the 5’-TCAG-3’ motif (CAG in-frame), in which a C-to-T edit results in the stop codon UAG. Noteworthy, PTC induction is possible both in nuclear DNA and mtDNA through any of these edits. Moreover, the availability of types of edits is currently limited by the strong 5’-TC-3’ context preference of the first generation of DdCBEs.

**Disclaimer:** This is the first release of this script. There may be errors and functionality may be improved. Please contact author Santiago Restrepo-Castillo at RestrepoCastillo.Santiago@mayo.edu for any inquires or suggestions.
