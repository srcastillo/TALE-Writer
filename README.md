**INTRODUCTION**<br><br>
Welcome to TALE Writer! A Python-based design tool for the efficient design of TALE repeat arrays. This script was made for the FusX TALE Base Editor (FusXTBE) project in the Precision Gene Editing Laboratory of Dr. Stephen C. Ekker at the Mayo Clinic by Ph.D candidate Santiago Restrepo-Castillo. The FusXTBE technology is based on the FusX assembly system, and on the first-ever mitochondrial base editor, DdCBE, which was developed by the Liu Group.<br><br>
Broadly, TALE Writer can be used to design TALENs or FusXTBEs against a specific target sequence. In particular, FusXTBE design allows mapping all potential 5'-TC-3' target sites for C-to-T base editing in a given sequence. Additionally, FusXTBEs can be specifically designed for premature termination codon (PTC) induction (a DNA edit resulting in the generation of a non-functional gene product due to the premature termination of translation). For this end, the script looks for the following target motifs within any given sequence:<br>
* The 5’-TGA-3’ motif (TGA in -frame), in which a G-to-A edit results in the stop codon UAA.<br>
* The 5’-TCAA-3’ motif (CAA in-frame), in which a C-to-T edit results in the stop codon UAA.<br>
* The 5’-TCAG-3’ motif (CAG in-frame), in which a C-to-T edit results in the stop codon UAG.<br>

**USER-DEFINED INPUT:**<br>
* **TALENs:**<br>
  * **Use default design parameters?** Type 'no' to define custom design parameters or 'yes' to proceed.<br>
    * All default minima and maxima are 14 and 16 bp, respectively. Custom limits are between 10 and 25 bp.<br>
  * **Sequence (5'-to-3'):** Input sequence containing the cut site region.<br>
  * **Target coordinate:** The coordinate within the input sequence that corresponds to the desired cut site.<br>
  * **Save results as CSV file?** Type 'yes' to save the results or 'no' to proceed.<br>
    * **Alphanumeric filename:** Type an alphanumeric filename to save the results<br>
  * **New sequence?** Type 'yes' to try another sequence or 'no' to exit.<br><br>
* **FusXTBEs:**<br>
  * **5'-TC-3' or PTC induction?** Choose whether to design base editors against all 5'-TC-3' motifs within a given sequence or for PTC induction.
  * **Use default design parameters?** Type 'no' to define custom design parameters or 'yes' to proceed.<br>
    * Default parameters and limits for custom parameters regarding arms and spacer length are the same as for TALEN design.
    * **Target window**: The script looks for all potential target sites within the protospacer region at least 'x' bp from the target sequence of either TALE repeat array, where 'x' is the target window. For example, if the length of the spacer is 16 bp and the target window is 4 bp, target Cs/Gs are searched from the fifth to the twelfth bp within the protospacer. The default target window is 4 bp. Custom target windows cannot be less than 0 or greater than half the length of the spacer minus 1 bp if spacer length is even or minus 1/2 bp if spacer length is odd.
  * **Sequence (5'-to-3'):** Input sequence containing the target(s) for base editing.<br>
  * **Save results as CSV file?** Type 'yes' to save the results or 'no' to proceed.<br>
    * **Alphanumeric filename:** Type an alphanumeric filename to save the results<br>
  * **New sequence?** Type 'yes' to try another sequence or 'no' to exit.<br>
 
**UNDERSTANDING THE OUTPUT:**<br>
* **Output sequence:** <br>
  * For TALEN design, the output sequence is the input sequence with the sequence of the target coordinate capitalized and highlighted in blue.
  * For FusXTBE design, the output sequence corresponds to the input sequence with all the potentially editable TC or GA motifs capitalized and highlighted in blue. Alternatively, for PTC induction, the output sequence consists of the input sequence with all targets amenable to PTC induction capitalized and highlighted in blue.<br><br>
* **Output table:**<br>
  * For TALEN design, the output table summarizes all the possible TALEN design permutations around the specified target, constrained by the design parameters. The table contains the design index of each design permutation, the target sequence of the left arm (plus a 5'T), the complementary sequence of the target sequence of the right arm (plus a 3'A), and the sequence of the spacer with the desired cut site capitalized and highlighted in blue.
  * For FusXTBE design, the output table summarizes all the possible FusXTBE design permutations around all the C-to-T base editing targets identified within the input sequence, constrained by the design parameters. The table contains the target indices, their local coordinates within the input sequence, their sequence motifs (TC or GA, or TGA, TCAA, or TCAG), the design indices, the target sequence of the left arm (plus a 3'A), the complementary sequence of the target sequence of the right arm (plus a 3'A), an exclamation mark (!) indicating potential off-target editing sites within the spacer, and the sequence of the spacer with the potential off-target sites highlighted in red and the on-target site capitalized and highlighted in blue.<br> 

**NOTES:**<br>
* In FusXTBE design, there can be dozens of design permutations per target. One way to decrease output size is to define constrained custom design parameters. For example, by making the minimum and maximum lengths of all left arms, right arms, and spacers the same (e.g., using a 15-15-15 design rule), output size can be significantly decreased. It is up to the user to select the design permutation that best fits their specific application.<br>
* For FusXTBE design, the program may ask to add nucleotides to either the 5' end, the 3' end, or both ends of the input sequence. In that case, it is possible that by adding the suggested number of nucleotides, new potential targets for C-to-T base editing are detected. One possible way around this issue is to add 'junk' extra nucleotides whenever required, such as a consecutive strecht of Ts. The user needs to consider extra targets or junk sequences when analyzing any design permutations.<br>
* Color highglights in the output may only be visible on Jupyter Notebook.<br>

**Relevant links:**
* The FusX TALE base editor (https://www.biorxiv.org/content/10.1101/2021.05.18.444740v1)
* FusX: A rapid one-step TALE assembly system (https://www.liebertpub.com/doi/10.1089/hum.2015.172)
* CRISPR-free mitochondrial base editing (https://www.nature.com/articles/s41586-020-2477-4)

**Author information:**<br>
Santiago Restrepo-Castillo<br>
RestrepoCastillo.Santiago@mayo.edu<br>
Ph.D. Candidate | Virology and Gene Therapy<br>
Mayo Clinic Graduate School of Biomedical Sciences
