# TALE Writer

This Colab notebook allows designing TALENs, DdCBEs, and TALEDs. 

TALENs can be designed against a specific target coordinate or against multiple targets within a given sequence. 

DdCBEs with the DddA/DddA6 or the DddA11 effector domain can be designed either against all potentially editable sites within a given sequence, for the introduction of nonsense mutations in protein-coding genes, or against a specific target site within a given sequence. 

Subsequently, the repeat variable diresidues (RVDs) of the left and right TALE binding sequences and their corresponding FusX recipes can be obtained of FusX-based assembly.

## General information

* There can be dozens of design permutations (pairs of TALE binding sequences) per target. One way to decrease output size is to define constrained custom design parameters. It is up to the user to select the design permutation that best fits their specific application.

* The [FusX recipe tool](http://www.talendesign.org/pFUXrecipeInput.php) referenced in this script works for TALE arrays targeting sequences 15- to 17-bp-long. To assemble TALE-based technologies with TALE arrays that target shorter or longer sequences, alternative assembly approaches or adaper kits must be used.

* Loss and gain of restriction sites for genotyping:
  * In TALEN design, TALE Writer identifies potential loss of restriction sites within the target region.
  * In base editor design, TALE Writer identifies both loss and gain of restriction sites within the target region.

* In general, for the introduction of nonsense mutations using DdCBEs, the following sequence motifs are identified:

  *   In-frame 5’-TGA-3’/5'-TGG-3'/5'-GGA-3'/5'-GGG-3' motifs, in which specific G-to-A edit could result in the stop codons UAA, UAG, AGA, or AGG, respectively.
  *   The 5’-HCAA-3’ motif (H: A, T, or C, CAA in-frame), in which a C-to-T edit results in the stop codon UAA.
  *   The 5’-HCAG-3’ motif (H: A, T, or C, CAG in-frame), in which a C-to-T edit results in the stop codon UAG.

* More information on TALENs, mitochondrial editors, the FusX assembly system, and TALE Writer here:

  * [CRISPR-free mitochondrial C-to-T base editing](https://www.nature.com/articles/s41586-020-2477-4)
  * [Targeted A-to-G base editing in human mitochondrial DNA](https://www.sciencedirect.com/science/article/pii/S0092867422003890?via%3Dihub)
  * [The FusX TALE base editor (FusXTBE) platform](https://www.liebertpub.com/doi/full/10.1089/crispr.2021.0061)
  * [The FusX system for rapid TALE assembly](https://www.liebertpub.com/doi/10.1089/hum.2015.172?url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org&rfr_dat=cr_pub++0pubmed)
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
