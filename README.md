# Interactive Genetic Code Analyzer

This interactive web tool is designed for visualizing, exploring, and analyzing structural and mathematical symmetries inherent in the genetic code. It particularly focuses on the concepts related to Rumer's transformations and extends this analysis to the group symmetries formed by codogram orbits.

*   **[v1.0](https://ruslankhafizov.github.io/genetic-code-by-khafizov/)**
*   **[v2.0](https://ruslankhafizov.github.io/genetic-code-by-khafizov/beta.html)**
*   **[v3.0](https://ruslankhafizov.github.io/genetic-code-by-khafizov/v3.0.html)**
*   **[v4.0](https://ruslankhafizov.github.io/genetic-code-by-khafizov/v4.0.html)**

## Core Features

The application is divided into two main interactive panels:

### 1. Rumer Orbit Explorer (Left Panel)

This panel focuses on the group-theoretic properties of the genetic code:

*   **Codogram Orbit Visualization:**
    *   It has been established by the program's author that the 24 homogeneous codogram representations of the genetic code are partitioned into 6 disjoint "orbits" under the action of the {E, R, R1, R2} transformation group. This tool displays these 6 orbits.
    *   Users can select any of the 6 orbits for detailed inspection.
*   **Mini-Matrix Display (Codograms):**
    *   For the selected orbit, 4 mini-matrices (4x4 codograms) are displayed, corresponding to the application of the E (identity), R1, R2, and R transformations to the orbit's representative nucleotide order.
    *   Cells (XY-boxes) within each mini-matrix are colored:
        *   **Black:** Belongs to Octet I (all 4 codons XYN code for the same amino acid in the *currently selected genetic code*).
        *   **White:** Belongs to Octet II.
    *   **Molecular Mass Display:** Each of the 16 XY-boxes in a mini-matrix displays the sum of atomic weights of the four amino acids it codes for (using the active genetic code). Stop codons are assigned a conventional weight of 74 Da, and unknown codons ('?') a weight of 0 Da.
    *   **Row/Column/Grand Total Masses:** Sums of molecular masses are displayed for each row, each column, and the grand total for each mini-matrix.
*   **Interactive Rumer-related Transformations:**
    *   Buttons allow users to apply R (U↔G, C↔A), R1 (U↔G), or R2 (C↔A) transformations to the nucleotide orders of the currently displayed orbit.
    *   This dynamically changes the displayed codograms, allowing observation of how these transformations affect code structure and nucleotide arrangements.
    *   Nucleotides affected by an active transformation are highlighted on the axes and titles of the mini-matrices.
*   **Genetic Code Selection for Analysis:**
    *   Allows selection from a comprehensive list of genetic codes (Standard Code, specific alternative codes, and grouped lists of other nuclear, mitochondrial, and bacterial/plastid codes sourced from NCBI).
    *   The Octet I/II assignments and molecular masses in the mini-matrices update dynamically based on the selected code.
*   **Symmetry Analysis Panel:**
    *   For any selected alternative genetic code, this panel provides an analysis comparing its structure to the Standard Code:
        *   **Changes in Octet I:** Lists XY-pairs that have left or joined Octet I. Mini-matrix cells visually indicate these changes with colored borders.
        *   **R-Symmetry Check:** Evaluates whether Rumer's R-symmetry (Octet I ↔ Octet II) is preserved or violated for the octets defined by the *selected alternative code*.
*   **Information Button:**
    *   Opens a modal window with detailed scientific background on Rumer's Octets, transformations, codograms, and orbits (available in English and Russian).

### 2. Detailed Genetic Code Matrix (Right Panel)

This panel provides a detailed, configurable 16x4 matrix representation of the genetic code:

*   **Full Codon Display:** Each of the 16 main cells (XY-boxes) displays information for all 4 corresponding codons (XYU, XYC, XYA, XYG).
*   **Customizable Axis Orders:**
    *   Independent selection of nucleotide order for the 1st (vertical), 2nd (horizontal), and 3rd codon positions.
    *   A toggle allows synchronization of the 1st and 2nd axis orders or independent settings. The order selection for the 1st/2nd axes is based on the 6 Rumer orbits.
*   **Multiple Coloring Modes:** Users can choose various modes to color the matrix cells or individual codons, revealing different properties:
    *   **By Rumer Octets:** Reflects Octet I/II assignments based on the genetic code selected in the Rumer Orbit Explorer.
    *   **By Amino Acids:** Unique background color for each amino acid; Start/Stop codons are specially highlighted.
    *   **By AA Hydrophobicity:** Colors codons based on the hydrophobicity category of the encoded amino acid.
    *   **By AA Charge:** Colors codons based on the charge category of the encoded amino acid.
    *   **By Synonym Count:** Colors codons based on the number of synonymous codons for the encoded amino acid.
    *   **By H-bond Strength:** Colors XY-boxes based on the H-bond strength of the 1st and 2nd codon positions.
    *   **By Nucleotide Type:** Colors XY-boxes based on the purine/pyrimidine type of the 1st and 2nd codon positions.
    *   **By A+U / C+G Content:** Colors codons based on AU-richness or CG-richness.
    *   **By Pu/Py Code:** Colors codons based on their 3-position Purine/Pyrimidine code.
    *   **By Amino/Keto Type (1,2):** Colors XY-boxes based on the amino/keto nature of the 1st and 2nd codon positions.
    *   **By Synthetase Classes (Std. Code):** Colors codons based on the class of aminoacyl-tRNA synthetase associated with the amino acid (determined by the Standard Code).
*   **Dynamic Data Integration:**
    *   Amino acid assignments, Octet I/II coloring (in "By Rumer Octets" mode), hydrophobicity, charge, and synonym counts dynamically update to reflect the genetic code selected in the Rumer Orbit Explorer panel.
*   **Interactive Mass Summation:**
    *   Users can click on individual codons (the smallest cells within the 16x4 matrix) to select them.
    *   A running sum of the molecular masses of the selected codons is displayed below the matrix.
    *   The equation shows each selected amino acid (or STOP) and its mass, culminating in the total sum.
    *   The total sum is highlighted in green if it is divisible by 37.
    *   A "Reset Selection" button clears all selected codons.
*   **Dynamic Legend:** A comprehensive legend explains the current coloring mode and provides additional relevant information (e.g., the genetic code being analyzed).

## Scientific Background & Key Concepts

**1. Rumer's Octets:**
Y.B. Rumer was the first to note that the 16 "columns" (XY-boxes, defined by the first two nucleotides of a codon) in the standard genetic code table can be divided into two groups of eight columns each – the Octets.
*   **Octet I:** Includes XY-boxes where all four codons (XYN, where N is any of the four nucleotides) code for the same amino acid (complete 4-fold degeneracy).
*   **Octet II:** Includes the remaining XY-boxes where such complete degeneracy is not observed.
In this tool, assignment to Octet I or II is determined dynamically for the standard genetic code based on this principle of 4-fold degeneracy.

**2. Rumer's R-Transformation:**
Y.B. Rumer also discovered that Octets I and II are related by a simple symmetry transformation **R = (T↔G, C↔A)** (in RNA nucleotides: U↔G, C↔A). This transformation mutually converts XY-boxes from Octet I to Octet II and vice versa.

**3. Codograms and Code Representations:**
The concept of a **codogram** was introduced by Vladimir I. Shcherbak and Maxim A. Makukov (see <a href="https://arxiv.org/pdf/1707.03382" target="_blank" rel="noopener noreferrer" target="_blank" rel="noopener noreferrer">publication</a>) to visualize the structure of the genetic code. A codogram is a 4x4 square whose cells are colored based on whether the corresponding XY-box belongs to Octet I or Octet II.
There are 24 possible ways to order the nucleotides (U, C, A, G) on the axes of a codogram if the order on both axes is synchronous ("homogeneous representations").

**4. Simply-Connected Codograms and the {E, R, R1, R2} Transformation Group:**
Alexander D. Panov (see <a href="http://dec1.sinp.msu.ru/~panov" target="_blank" rel="noopener noreferrer">personal page</a>, <a href="https://www.sociostudies.org/almanac/articles/are_the_strange_information_structures_of_the_genetic_code_an_accident_or_an_artifact" target="_blank" rel="noopener noreferrer">publication</a>) and Felix P. Filatov analyzed all 24 codograms and found that among them, four "simply-connected" codograms stand out. In such codograms, the regions corresponding to Octets I and II are continuous.
They also showed that these four simply-connected codograms form a closed group under the transformations:
*   **R** (full Rumer): U↔G, C↔A
*   **R1** ("purine" Rumer transformation): U↔G (A and C unchanged)
*   **R2** ("pyrimidine" Rumer transformation): C↔A (U and G unchanged)
*   **E** (identity transformation)
These four transformations {E, R, R1, R2} form a mathematical group (the Klein four-group V₄).

**5. Codogram Orbits:**
Further analysis by the author of this tool (Ruslan Khafizov) has shown that all 24 homogeneous codograms are partitioned into 6 disjoint "orbits" under the action of the {E, R, R1, R2} transformation group. Each such orbit contains 4 codograms, and this tool demonstrates these orbital structures:
*   {TCAG, GACT, GCAT, TACG}
*   {TCGA, GATC, GCTA, TAGC}
*   {CTAG, AGCT, CGAT, ATCG}
*   {CTGA, AGTC, CGTA, ATGC}
*   {TGCA, GTAC, TGAC, GTCA}
*   {ACGT, CATG, ACTG, CAGT}

**Physico-Chemical and Structural Consequences of Rumer-related Transformations:**
*   **Conservation of Amino/Keto Type of XY-boxes:** All transformations in the {E, R, R1, R2} group preserve the amino-group (A, C) or keto-group (U, G) nature of each nucleotide.
*   **Purine ↔ Pyrimidine Transformations (Transversions):** The full R-transformation always acts as a transversion for both nucleotides in an XY-box. The "half" transformations R1 and R2 also perform transversions for their target nucleotides.
*   **Regular Changes in Nucleotide Bonding "Strength":** These transformations lead to predictable changes in nucleotide "strength" (H-bonds: Weak W – A/U; Strong S – G/C).

## How to Run Locally
1.  Download or clone this repository.
2.  Ensure the main HTML file is named `index.html`.
3.  Open the `index.html` file in a modern web browser (e.g., Chrome, Firefox, Edge, Safari).

## Technologies Used
*   **React 18** (via CDN)
*   **ReactDOM 18** (via CDN)
*   **Babel Standalone** (via CDN for in-browser JSX transformation)
*   **Tailwind CSS** (via CDN for styling)
*   **TinyColor** (via CDN for color manipulation)
*   HTML5, CSS3, JavaScript (ES6+)

## New Features in the v2.0

The [v2.0](https://ruslankhafizov.github.io/genetic-code-by-khafizov/beta.html) includes all stable features plus the following additions:

*   **New Visualization Mode - "By Side Chain Mass":**
    *   Colors codons based on the mass of their unique side chains (R-groups), categorized into four groups.
    *   The legend provides a detailed breakdown of R-group masses for each amino acid.
*   **Dual Mass Summation:**
    *   The interactive summation tool now calculates and displays both the **Total Mass** and the **Side Chain Mass** of selected codons. Both sums are independently checked for divisibility by 37.
*   **Enhanced Synthetase Analysis:**
    *   The "By Synthetase Classes" mode has been upgraded to **"By Synthetase Subtypes"**, providing a more granular analysis with a unique color for each subtype.
*   **Mini-Matrix Metric Control:**
    *   A new control panel in the Rumer Orbit Explorer allows users to switch the metric displayed in the mini-matrices between:
        1.  **Sum of Masses**
        2.  **Sum of H-Bonds** (a new physical metric)
        3.  **Hide Numbers** (now the default in Beta).

## New Features in the v3.0

The [v3.0](https://ruslankhafizov.github.io/genetic-code-by-khafizov/v3.0.html) includes all stable features plus the following additions:

*   **Advanced Mass Calculator:**
    *   Select any number of codons in the matrix to calculate their combined properties.
    *   **Biochemically Correct Polymer Masses:** Calculates the true mass of polypeptide chains, DNA/RNA strands, and DNA double helices, accounting for water loss during polymerization.
    *   **Dual Mass Display:** Shows both the final polymer mass and the sum of its free components in parentheses for clarity (e.g., `polymer_mass (sum_of_components)`).
    *   **Atomic Composition & Chemical Formula:** Automatically calculates the total atomic count (C, H, N, O, S) and displays the gross chemical formula of the selected peptide in real-time.
    *   Highlights sums divisible by 37 in green.

*   **Markov Stability Analysis:**
    *   A dedicated visualization mode to color codons by their evolutionary stability.
    *   Calculates the probabilities of synonymous, non-synonymous, and STOP mutations.
    *   Supports two models: a simple (equal probability) model and the Kimura K2P model.

*   **Expanded Genetic Code Library:**
    *   Includes all official genetic codes from NCBI (up to Table 33).
    *   Features four recently discovered (unofficial) genetic codes for cutting-edge research.
    *   A reorganized UI with quick access to standard/nuclear codes and logical dropdowns for other categories.

## New Features in the v4.0

The [v4.0](https://ruslankhafizov.github.io/genetic-code-by-khafizov/v4.0.html) is a major update focusing on a streamlined user interface, new deep-level analytical modes based on the Supersymmetry Genetic Code (SSyGC), and a significantly enhanced interactive calculator.

*   **Major UI Overhaul & Usability:**
    *   The application has been completely redesigned into a **single-screen experience**, removing the previous dual-panel layout to maximize focus on the interactive matrix.
    *   Controls are now organized into three dedicated columns: **Genetic Code Selection** (left), **Matrix Axes Configuration** (middle), and **Visualization Modes** (right) for a more intuitive workflow.

*   **Advanced Symmetry Visualization Modes:**
    *   **Restored R-Partner Highlighting:** Hovering over any XY-box in the main matrix now highlights its complementary R-partner with an orange dashed border, a feature that works across all visualization modes.
    *   **New SSyGC Modes:** Three new visualization modes based on the Supersymmetry Genetic Code model have been added:
        1.  **By SSyGC Quadrants:** Colors the matrix into four major blocks as defined in the SSyGC table.
        2.  **By SSyGC Box Type:** Differentiates between "Direct" and "Complement" XY-boxes.
        3.  **By SSyGC Box Class:** A detailed 4-color scheme that classifies boxes by both their Direct/Complement status and their Split/No-Split property.
    *   **Canonical Order Presets:** A new control panel allows one-click switching of all matrix axes to either the "Standard (UCAG)" or the **"SSyGC (AUGC)"** order, enabling instant analysis from different theoretical perspectives.

*   **Expanded Calculator Capabilities & Data Accuracy:**
    *   **Proton & Neutron Counting:** The calculator's "Atomic Composition" section now also sums the total number of **protons** and **neutrons** for the selected amino acids, based on the precise data from the Shcherbak-Makukov articles.
    *   **Multi-Divisor Highlighting:** The divisibility check is now far more powerful. Users can input up to **three different numbers** simultaneously. Any calculated mass divisible by **any** of these numbers will be highlighted in green.
    *   **Critical Logic Fix:** The calculator's logic has been corrected to ensure **STOP codons** are handled properly. They no longer incorrectly affect the calculation of polypeptide mass or the peptide's chemical formula, making the results biochemically accurate.

*   **Data and Color Scheme Updates:**
    *   **Corrected Synthetase Data:** The classification for aminoacyl-tRNA synthetases has been updated to align with the latest scientific consensus.
    *   **New Synthetase Color Scheme:** The visualization for synthetase classes has been improved with an intuitive new palette: shades of **blue for Class I** and shades of **red/orange for Class II**.

## Author
Ruslan Khafizov
*   **Email:** <a href="mailto:jhgf10@gmail.com">jhgf10@gmail.com</a>
*   **YouTube:** <a href="https://www.youtube.com/@ruslankhafizov251">@ruslankhafizov251</a>
*   **Facebook:** <a href="https://www.facebook.com/russopirato/">Profile</a>

## License
MIT License
