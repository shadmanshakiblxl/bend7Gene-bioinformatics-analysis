Markdown
# BEND7 Bioinformatics Analysis & Recombinant Cloning Strategy


[![NCBI RefSeq](https://img.shields.io/badge/NCBI-RefSeq--NM__001291464.2-green.svg)](https://www.ncbi.nlm.nih.gov)
[![PDB Structure](https://img.shields.io/badge/PDB-7YUN-orange.svg)](https://www.rcsb.org/structure/7YUN)

A comprehensive bioinformatics and computational biology portfolio investigating **BEND7** (BEN Domain-Containing Protein 7) across vertebrate evolution, detailing a recombinant gene amplification and cloning pipeline in **pET-28a**, and analyzing structural homology with DNA ligand interactions.

---

##  Project Overview

This project integrates three core computational and molecular biology modules:

1. **Phylogenetic Inference & Molecular Evolution:** Cross-lineage comparison of BEND7 across 12 vertebrate taxa spanning 5 classes (*Mammalia*, *Aves*, *Reptilia*, *Amphibia*, *Actinopterygii*) using Neighbor-Joining (NJ), UPGMA, and Maximum Parsimony (MP) models[cite: 2].
2. **Recombinant Amplification & Directional Cloning Strategy:** Complete wet-lab cloning protocol designed for *Anas georgica* BEND7 CDS (~1,647 bp) into the `pET-28a` expression vector using `BamHI` and `XhoI` restriction sites[cite: 13, 15, 17].
3. **Protein Structure & Ligand Interaction Analysis:** Structural homology modeling and atomic interaction profiling using human BEND6 (PDB: **7YUN**) as a 3D template to map α5 helix major groove reading and Loop 1 minor groove contacts.



Key Research Findings1. Phylogenetic Analysis & Lineage DivergenceTaxonomic Coverage: Evaluated 12 RefSeq entries across Primates, Rodentia, Laurasiatheria, Afrotheria, Aves, Reptilia, Amphibia, and Actinopterygii.   Methodological Comparison:Neighbor-Joining (NJ): Most accurate topology; accounts for variable substitution rates without enforcing a strict molecular clock.   UPGMA: Preserves major clade memberships but distorts relative branch lengths for fast-evolving lineages like Mus musculus due to molecular clock constraints.   Maximum Parsimony (MP): Highly congruent topology; slight artifact in Bos taurus positioning due to homoplasy in the BEN domain.   mRNA vs. Protein Signal: Nucleotide sequences provide useful resolution for short evolutionary distances ($<200 \text{ Mya}$), whereas protein alignments prevent saturation and transition bias across deep vertebrate divergences ($>400 \text{ Mya}$).   

2. Recombinant Cloning Strategy (Anas georgica BEND7)Target Insert: Anas georgica BEND7 Coding Sequence (CDS) (~1,647 bp, ~548 aa).   Vector Backbone: pET-28a (Addgene #42634) with Kanamycin selection ($50 \ \mu\text{g/mL}$).   Restriction Strategy: Directional dual-digest using BamHI ($5'$) and XhoI ($3'$).   Primers Engineered:Forward: 5'-CGCGCG-GGATCC-[ATG + BEND7 CDS 5' Start]-3'   Reverse: 5'-CGCGCG-CTCGAG-[Reverse Complement Stop Codon]-3'   Host Strain: E. coli DH5α (endA1 recA1) for stable plasmid propagation without background T7 expression.   Verification Protocol: 3-tier validation comprising Colony PCR (~1,900 bp band), Diagnostic BamHI/XhoI double digest (~5.3 kb + ~1.65 kb bands), and full-length Sanger sequencing.

 Structural Homology & DNA Ligand BindingHomolog Template: Human BEND6 BEN domain (PDB: 7YUN, 2.13 Å resolution).   Fold Architecture: 5-helix bundle inserting into methylated DNA.   Key Interacting Residues:Arg254 (α5 helix): Direct major-groove hydrogen bonding to Guanine 7'.   Asn261 (α5 helix): Major-groove amide contact with Guanine 5' and water-mediated interaction with Cytosine 3.   Lys265 (α5 helix C-term): Direct hydrogen bonds to Guanine 3' and Adenine 4'.   Ser217 / Thr218 (Loop 1): Minor-groove insertion and hydrogen bonding to Guanines 7'/8.   Lys191 & Gln258 (α2/α5 helices): Electrostatic salt bridges and backbone phosphate interaction

To reproduce the structural binding interface for PDB 7YUN in PyMOL:

fetch 7yun, type=pdb
hide everything; show cartoon, polymer.protein; show cartoon, polymer.nucleic
color skyblue, polymer.protein; color orange, polymer.nucleic
show sticks, resi 254+261+265+217+218+191+258 and polymer.protein
distance hb1, resi 254 and polymer.protein, resi 7 and polymer.nucleic, mode=2
zoom resi 254+261+265+217+218 and polymer.protein, 8
ray 1600, 1200
png interaction_view.png, dpi=300
