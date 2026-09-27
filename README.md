# Bioinformatics Roadmap — Biotech → Cancer Genomics → CRISPR

My learning plan for moving from biotechnology into bioinformatics, computational biology, cancer genomics, and CRISPR/Cas9 analysis. It lists the tools I'm studying, with a link to each tool's source and the paper to cite, and connects to my own projects as I build them.

> Compiled with help from Claude Code (an AI assistant). Every repository link was checked on GitHub and every paper DOI was checked against Crossref when this list was written.

## Where this is going

```text
Cancer gene → sequence → candidate sgRNAs → off-target analysis → sequencing data → editing outcome
```

```text
FASTQ → QC → alignment → BAM → variant calling → VCF → annotation → cancer interpretation
```

## Learning order

| # | Topic | Status |
|---|---|---|
| 1 | Git / GitHub | in progress |
| 2 | Python | starting |
| 3 | Biopython + sequence analysis | planned |
| 4 | R + Bioconductor | planned |
| 5 | Cancer genomics / TCGA | planned |
| 6 | Linux / Bash | planned |
| 7 | FASTQ / BAM / VCF formats | planned |
| 8 | Nextflow | planned |
| 9 | CRISPR guide + off-target analysis | planned |
| 10 | ML / AI for computational biology | planned |

## My projects

| Project | What it covers | Status |
|---|---|---|
| `crispr-guide-design` | Fetch a gene, find SpCas9 sites, filter sgRNAs, off-target search | planned |
| `cancer-crispr-targets` | TCGA mutation data → pick a gene → design and compare guides | planned |
| `variant-calling-pipeline` | Small Nextflow pipeline: FASTQ → QC → alignment → VCF | planned |

Links will be added here once each project has working, documented results.

---

## Tools by layer

### 1. CRISPR / guide-RNA design

| Tool | Source | Cite |
|---|---|---|
| Cas-OFFinder | [snugel/cas-offinder](https://github.com/snugel/cas-offinder) · successor: [pnucolab/cas-offinder-2](https://github.com/pnucolab/cas-offinder-2) | Bae et al. 2014 [¹](#ref-1) |
| CRISPResso2 | [pinellolab/CRISPResso2](https://github.com/pinellolab/CRISPResso2) | Clement et al. 2019 [²](#ref-2) |
| CRISPick | Broad Institute **web tool** (not a GitHub repo): [portals.broadinstitute.org/gppx/crispick](https://portals.broadinstitute.org/gppx/crispick/public) | Doench et al. 2016 [³](#ref-3); Sanson et al. 2018 [⁴](#ref-4) |

### 2. Cancer genomics

| Tool | Source | Cite |
|---|---|---|
| maftools | [PoisonAlien/maftools](https://github.com/PoisonAlien/maftools) | Mayakonda et al. 2018 [⁵](#ref-5) |
| TCGA MC3 somatic mutations (data) | via [PoisonAlien/TCGAmutations](https://github.com/PoisonAlien/TCGAmutations) | Ellrott et al. 2018 [⁶](#ref-6) |
| nf-core/oncoanalyser | [nf-core/oncoanalyser](https://github.com/nf-core/oncoanalyser) | cite the repo + nf-core [¹¹](#ref-11) |
| nf-core/sarek | [nf-core/sarek](https://github.com/nf-core/sarek) | Garcia et al. 2020 [¹⁶](#ref-16); Hanssen et al. 2024 [¹⁷](#ref-17) |

### 3. Sequencing / variant analysis

| Tool | Source | Cite |
|---|---|---|
| FastQC | [s-andrews/FastQC](https://github.com/s-andrews/FastQC) | [Babraham Bioinformatics project page](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) (no paper) |
| BWA | aligner used in my pipeline | Li & Durbin 2009 [¹³](#ref-13) |
| samtools / bcftools | [samtools/samtools](https://github.com/samtools/samtools) · [samtools/bcftools](https://github.com/samtools/bcftools) | Danecek et al. 2021 [⁸](#ref-8) |
| GATK | [broadinstitute/gatk](https://github.com/broadinstitute/gatk) | McKenna et al. 2010 [¹⁴](#ref-14) |
| MultiQC | [MultiQC/MultiQC](https://github.com/MultiQC/MultiQC) | Ewels et al. 2016 [⁹](#ref-9) |

### 4. Computational biology / proteins

| Tool | Source | Cite |
|---|---|---|
| Biopython | [biopython/biopython](https://github.com/biopython/biopython) | Cock et al. 2009 [⁷](#ref-7) |
| AlphaFold | [google-deepmind/alphafold](https://github.com/google-deepmind/alphafold) | Jumper et al. 2021 [¹²](#ref-12) |
| AutoDock Vina | [ccsb-scripps/AutoDock-Vina](https://github.com/ccsb-scripps/AutoDock-Vina) | Trott & Olson 2010 [¹⁵](#ref-15); Eberhardt et al. 2021 [¹⁸](#ref-18) |
| RDKit | [rdkit/rdkit](https://github.com/rdkit/rdkit) | [rdkit.org](https://www.rdkit.org/) (no single paper) |
| PyTorch | [pytorch/pytorch](https://github.com/pytorch/pytorch) | Paszke et al. 2019 [¹⁹](#ref-19) |

### 5. Workflow engineering

| Tool | Source | Cite |
|---|---|---|
| Nextflow | [nextflow-io/nextflow](https://github.com/nextflow-io/nextflow) | Di Tommaso et al. 2017 [¹⁰](#ref-10) |
| nf-core | [github.com/nf-core](https://github.com/nf-core) | Ewels et al. 2020 [¹¹](#ref-11) |
| Docker | [github.com/docker](https://github.com/docker) | [docs.docker.com](https://docs.docker.com/) |

---

## References

1. <a id="ref-1"></a>Bae, S., Park, J. & Kim, J.-S. (2014). Cas-OFFinder: a fast and versatile algorithm that searches for potential off-target sites of Cas9 RNA-guided endonucleases. *Bioinformatics*. https://doi.org/10.1093/bioinformatics/btu048
2. <a id="ref-2"></a>Clement, K. et al. (2019). CRISPResso2 provides accurate and rapid genome editing sequence analysis. *Nature Biotechnology*. https://doi.org/10.1038/s41587-019-0032-3
3. <a id="ref-3"></a>Doench, J. G. et al. (2016). Optimized sgRNA design to maximize activity and minimize off-target effects of CRISPR-Cas9. *Nature Biotechnology*. https://doi.org/10.1038/nbt.3437
4. <a id="ref-4"></a>Sanson, K. R. et al. (2018). Optimized libraries for CRISPR-Cas9 genetic screens with multiple modalities. *Nature Communications*. https://doi.org/10.1038/s41467-018-07901-8
5. <a id="ref-5"></a>Mayakonda, A. et al. (2018). Maftools: efficient and comprehensive analysis of somatic variants in cancer. *Genome Research*. https://doi.org/10.1101/gr.239244.118
6. <a id="ref-6"></a>Ellrott, K. et al. (2018). Scalable Open Science Approach for Mutation Calling of Tumor Exomes Using Multiple Genomic Pipelines. *Cell Systems*. https://doi.org/10.1016/j.cels.2018.03.002
7. <a id="ref-7"></a>Cock, P. J. A. et al. (2009). Biopython: freely available Python tools for computational molecular biology and bioinformatics. *Bioinformatics*. https://doi.org/10.1093/bioinformatics/btp163
8. <a id="ref-8"></a>Danecek, P. et al. (2021). Twelve years of SAMtools and BCFtools. *GigaScience*. https://doi.org/10.1093/gigascience/giab008
9. <a id="ref-9"></a>Ewels, P. et al. (2016). MultiQC: summarize analysis results for multiple tools and samples in a single report. *Bioinformatics*. https://doi.org/10.1093/bioinformatics/btw354
10. <a id="ref-10"></a>Di Tommaso, P. et al. (2017). Nextflow enables reproducible computational workflows. *Nature Biotechnology*. https://doi.org/10.1038/nbt.3820
11. <a id="ref-11"></a>Ewels, P. A. et al. (2020). The nf-core framework for community-curated bioinformatics pipelines. *Nature Biotechnology*. https://doi.org/10.1038/s41587-020-0439-x
12. <a id="ref-12"></a>Jumper, J. et al. (2021). Highly accurate protein structure prediction with AlphaFold. *Nature*. https://doi.org/10.1038/s41586-021-03819-2
13. <a id="ref-13"></a>Li, H. & Durbin, R. (2009). Fast and accurate short read alignment with Burrows–Wheeler transform. *Bioinformatics*. https://doi.org/10.1093/bioinformatics/btp324
14. <a id="ref-14"></a>McKenna, A. et al. (2010). The Genome Analysis Toolkit: A MapReduce framework for analyzing next-generation DNA sequencing data. *Genome Research*. https://doi.org/10.1101/gr.107524.110
15. <a id="ref-15"></a>Trott, O. & Olson, A. J. (2010). AutoDock Vina: Improving the speed and accuracy of docking with a new scoring function, efficient optimization, and multithreading. *Journal of Computational Chemistry*. https://doi.org/10.1002/jcc.21334
16. <a id="ref-16"></a>Garcia, M. et al. (2020). Sarek: A portable workflow for whole-genome sequencing analysis of germline and somatic variants. *F1000Research*. https://doi.org/10.12688/f1000research.16665.2
17. <a id="ref-17"></a>Hanssen, F. et al. (2024). Scalable and efficient DNA sequencing analysis on different compute infrastructures aiding variant discovery. *NAR Genomics and Bioinformatics*. https://doi.org/10.1093/nargab/lqae031
18. <a id="ref-18"></a>Eberhardt, J. et al. (2021). AutoDock Vina 1.2.0: New Docking Methods, Expanded Force Field, and Python Bindings. *Journal of Chemical Information and Modeling*. https://doi.org/10.1021/acs.jcim.1c00203
19. <a id="ref-19"></a>Paszke, A. et al. (2019). PyTorch: An Imperative Style, High-Performance Deep Learning Library. *arXiv:1912.01703*. https://arxiv.org/abs/1912.01703
