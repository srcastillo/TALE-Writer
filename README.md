# TALE Writer

TALE Writer allows you to design TALE nucleases (TALENs) and FusX TALE Base Editors (FusXTBEs) for C-to-T editing. TALENs can be designed against a specific target coordinate or against multiple targets within a given sequence. FusXTBEs can be designed against all 5'-TC-3' target sites within a given sequence or for premature termination codon (PTC) induction in a protein-coding gene. Subsequently, the repeat variable diresidues (RVDs) corresponding to the left and right sequences of the designed technologies can be determined for FusX-based assembly.

For PTC induction with FusXTBEs, TALE Writer identifies the following sequence motifs:

* The 5’-TGA-3’ motif (TGA in -frame), in which a G-to-A edit results in the stop codon UAA.<br>
* The 5’-TCAA-3’ motif (CAA in-frame), in which a C-to-T edit results in the stop codon UAA.<br>
* The 5’-TCAG-3’ motif (CAG in-frame), in which a C-to-T edit results in the stop codon UAG.<br>

## Inputs & Outputs

### Inputs

#### TALEN design

  * **Use default design parameters?** Type 'no' to define custom design parameters or 'yes' to proceed.<br>
    * Default left/right arm length ranges between 15-16 bp.<br>
    * Default spacer length ranges are 14-16 bp.<br>
  * **Sequence (5'-to-3'):** Input sequence containing the cut site region.<br>
  * **Target coordinate:** The coordinate within the input sequence that corresponds to the desired cut site.<br>
  * **Save results as CSV file?** Type 'yes' to save the results or 'no' to proceed.<br>
    * **Alphanumeric filename:** Type an alphanumeric filename to save the results<br>
  * **New sequence?** Type 'yes' to try another sequence or 'no' to exit.
  * **New analysis?** Type 'yes' to perform a new analysis or 'no' to exit.

#### FusXTBE design

  * **5'-TC-3' or PTC induction?** Choose whether to design base editors against all 5'-TC-3' motifs within a given sequence or for PTC induction.
  * **Use default design parameters?** Type 'no' to define custom design parameters or 'yes' to proceed.<br>
    * Default parameters and limits for custom parameters regarding arms and spacer length are the same as for TALEN design.
    * **Target window**: The script looks for all potential target sites within the protospacer region at least 'n' bp from the target sequence of either TALE repeat array, where 'n' is the target window. For example, if the length of the spacer is 16 bp and the target window is 4 bp, target Cs/Gs are searched from the 5th to the 12th bp within the protospacer. The default target window is 4 bp. Custom target windows cannot be less than 0 or greater than half the length of the spacer minus 1 bp if spacer length is even or minus 1/2 bp if spacer length is odd.
  * **Sequence (5'-to-3'):** Input sequence containing the target(s) for base editing.<br>
  * **Save results as CSV file?** Type 'yes' to save the results or 'no' to proceed.<br>
    * **Alphanumeric filename:** Type an alphanumeric filename to save the results<br>
  * **New sequence?** Type 'yes' to try another sequence or 'no' to exit.
  * **New analysis?** Type 'yes' to perform a new analysis or 'no' to exit.
 
### Outputs

#### TALEN design

* **Output sequence:** The output sequence is the input sequence with the sequence of the target coordinate capitalized and highlighted in blue.<br>
* **Output table:** The output table summarizes all the possible TALEN design permutations around the specified target, constrained by the design parameters. From left to right, the table contains the target index (TGT), the design index of each design permutation (DSG), the enzymes which restriction sites may be lost after double-strand break (LOSS), the top strand 5'-to-3' left TALE binding sequence (LEFT SEQUENCE), the bottom strand 5'-to-3' right TALE binding sequence (RIGHT SEQUENCE), and the top strand 5'-to-3' protospacer sequence (SPACER) with the desired cut site capitalized and highlighted in blue.

#### FusXTBE design

* **Output sequence:** The output sequence corresponds to the input sequence with all the potentially editable TC or GA motifs capitalized and highlighted in blue. Alternatively, for PTC induction, the output sequence consists of the input sequence with all targets amenable to PTC induction capitalized and highlighted in blue.<br>
* **Output table:** The output table summarizes all the possible FusXTBE design permutations around all the C-to-T base editing targets identified within the input sequence, constrained by the design parameters. From left to right, the table contains the target index (TGT), the design index of each design permutation (DSG), the enzymes which restriction sites are lost after editing (LOSS), the enzymes which restriction sites are gained after editing (GAIN), the number of potential off-target edits within the protospacer (X), the top strand 5'-to-3' left TALE binding sequence (LEFT SEQUENCE), the bottom strand 5'-to-3' right TALE binding sequence (RIGHT SEQUENCE), and the top strand 5'-to-3' protospacer sequence (SPACER) with the desired cut site capitalized and highlighted in blue.<br><br>

## General information

* There can be dozens design permutations (pairs of TALE binding sequences) per target. One way to decrease output size is to define constrained custom design parameters. It is up to the user to select the design permutation that best fits their specific application.

* The [FusX recipe tool](http://www.talendesign.org/pFUXrecipeInput.php) referenced in this script works for TALE arrays targeting sequences 15- to 17-bp-long. To assemble TALE-based technologies with TALE arrays that target shorter or longer sequences, alternative assembly approaches or adaper kits must be used.

* Loss and gain of restriction sites for genotyping:
  * In TALEN design, TALE Writer identifies potential loss of restriction sites within the target region.
  * In FusXTBE design, TALE Writer identifies both loss and gain of restriction sites within the target region.

* For PTC induction with FusXTBEs, TALE Writer identifies the following sequence motifs:

  *   The 5’-TGA-3’ motif (TGA in -frame), in which a G-to-A edit results in the stop codon UAA.
  *   The 5’-TCAA-3’ motif (CAA in-frame), in which a C-to-T edit results in the stop codon UAA.
  *   The 5’-TCAG-3’ motif (CAG in-frame), in which a C-to-T edit results in the stop codon UAG.

* You can find more information about TALENs, mitochondrial base editors, the FusX assembly system, and TALE Writer here:

  * [CRISPR-free mitochondrial base editing paper](https://www.nature.com/articles/s41586-020-2477-4)
  * [FusX TALE base editor (FusXTBE) paper](https://www.liebertpub.com/doi/full/10.1089/crispr.2021.0061)
  * [FusX assembly system paper](https://www.liebertpub.com/doi/10.1089/hum.2015.172?url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org&rfr_dat=cr_pub++0pubmed)
  * [TALE Writer on GitHub](https://github.com/srcastillo/TALE-Writer)

## Citing this work

Any publication that discloses findings arising from using this notebook should cite the [FusXTBE paper](https://www.liebertpub.com/doi/full/10.1089/crispr.2021.0061), in which TALE Writer was first reported.<br>

## Acknowledgements

TALE Writer communicates with and/or references the following separate libraries and packages:

* [Colab](https://research.google.com/colaboratory/)<br>
* [Colorama](https://pypi.org/project/colorama/)
* [NumPy](https://numpy.org/)
* [pandas](https://pandas.pydata.org/)
* [sys](https://docs.python.org/3/library/sys.html)
* [tabulate](https://pypi.org/project/tabulate/)

We thank all their contributors and maintainers!

## License and Disclaimer

This is not an officially-supported Google product.

This Colab notebook and other information provided is for computer-aided design of TALENs and FusXTBEs only, caution should be exercised in its use. It is porivded 'as-is' without any warranty of any kind, whether expressed or implied. Information is not inteded to be a substitute for professional medical advice, diagnosis, or treatment, and does not constitute medial or other professional advice.

### TALE Writer Code License

Licensed under the GNU General Public License, Version 3.0 (the "License"). You may obtain a copy of the License at https://www.gnu.org/licenses/gpl-3.0.en.html.

### Third-party software

Use of the third-party software, libraries or code referred to in the [Acknowledgements](https://github.com/srcastillo/TALE-Writer/blob/main/README.md#acknowledgements) section in the TALE Writer README may be governed by separate terms and conditions or license provisions. Your use of the third-party software, libraries or code is subject to any such terms and you should check that you can comply with any applicable restrictions or terms and conditions before use.
