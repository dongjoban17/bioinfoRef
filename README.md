# bioinfoRef
Repository for keeping useful bioinformatics references

## One-line bash commands

Check the [repo](https://github.com/stephenturner/oneliners) by [Stephen](https://github.com/stephenturner) first to see if he already has a one-line bash command that will work

- Print original filenames and filenames without the specified file extension:
```Bash
ls | xargs -n1 sh -c 'echo $0 $(basename $0 [file-extension])'
```
- Print read lengths and their counts in .fastq file. Originally from [Biostars](https://www.biostars.org/p/72433/)
```Bash
awk 'if (NR%4 == 2) {len[len($0)]++} END {for (l in len) {print l, len[l]}}' [input.fastq]
```
- Parse & print first column, followed by the remaining columns. Used to modify Salmon output for DESeq2
```Bash
awk '{split($1,a,"|"); print a[1], substr($0,length($1)+1);}' quant.sf | tr -d " "
```
- Print columns and its corresponding column number.
```Bash
awk '{for (i=1; i<=NF; i++) print i"\t"$i; exit}' [filename]
```
- Sort all but header (Below is for when header consists of only 1 line). Originally from [StackOverflow](https://stackoverflow.com/questions/14562423/is-there-a-way-to-ignore-header-lines-in-a-unix-sort)
```Bash
# Parenthesis collects stdout from commands within it
(head -n1 [filename] && tail -n+2 [filename] | sort) > [outname]
```

## RNA-Seq

- "Guess" whether RNA-Seq data is stranded or not by using `infer_experiment.py` from RSeQC.
  - [RSeQC](http://rseqc.sourceforge.net/#infer-experiment-py)
  - Reference [BED file](https://sourceforge.net/projects/rseqc/files/BED/Human_Homo_sapiens/) (Human)
