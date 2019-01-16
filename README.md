# pedigree_data_simulator

Requirements for parental_haplotypes and f1_haplotypes:
```
Python2.7
pysam
pyfasta
argparse
numpy
```


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

```
usage: sim_short_reads [-h] -o OUTPUT_DIRECTORY -f FASTAS [FASTAS ...] -c
                       COVERAGE -l READ_LENGTH [--tenx TENX]
                       [--DNA_input DNA_INPUT]
                       [--molecule_length MOLECULE_LENGTH]
                       [--subset_partitions SUBSET_PARTITIONS]

simulate short reads from pedigree fastas

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT_DIRECTORY, --output_directory OUTPUT_DIRECTORY
                        output prefix
  -f FASTAS [FASTAS ...], --fastas FASTAS [FASTAS ...]
                        reads will be generated equally from each fasta file
  -c COVERAGE, --coverage COVERAGE
                        coverage to generate
  -l READ_LENGTH, --read_length READ_LENGTH
                        short read length
  --tenx TENX           generate linked reads using LR-SIM
  --DNA_input DNA_INPUT
                        input DNA amount in ng. Ignored if --tenx not set.
                        Lower numbers improves links per molecule. Reasonable
                        values are 0.25-2.0
  --molecule_length MOLECULE_LENGTH
                        average long molecule length for linked reads
  --subset_partitions SUBSET_PARTITIONS
                        simulate library prep on subset of partitions
                        separated prior to breaking emulsion. Improves links
                        per molecule
```
