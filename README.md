# pedigree_data_simulator

Requirements: 

Python2.7
pysam
pyfasta
argparse
numpy

```
parental_haplotypes -h
usage: parental_haplotypes [-h] -f FASTA -b BCF -o OUT_DIR
                           [--het_rate HET_RATE]

Create parental haplotypes for pedigree given fasta and population bcf

optional arguments:
  -h, --help            show this help message and exit
  -f FASTA, --fasta FASTA
                        base fasta file
  -b BCF, --bcf BCF     population bcf from which to pull variants
  -o OUT_DIR, --out_dir OUT_DIR
                        output directory (not yet created)
  --het_rate HET_RATE   override heterozygous variant rate from population bcf
```
  
```
f1_haplotypes -h
usage: f1_haplotypes [-h] -f FASTA -d PARENTAL_DIRECTORY
                     [-r RECOMBINATION_RATE] [-n NUM_OFFSPRING]

Build f1 haplotype-pairs given parental haplotypes and recombination rate

optional arguments:
  -h, --help            show this help message and exit
  -f FASTA, --fasta FASTA
                        base fasta file
  -d PARENTAL_DIRECTORY, --parental_directory PARENTAL_DIRECTORY
                        parental haplotype directory (from
                        parental_haplotypes)
  -r RECOMBINATION_RATE, --recombination_rate RECOMBINATION_RATE
                        recombination rate eg 1.0/10000000.0
  -n NUM_OFFSPRING, --num_offspring NUM_OFFSPRING
                        number haplotype-pairs to generage
```
