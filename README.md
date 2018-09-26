# bioinfoRef
Repository for keeping useful bioinformatics references

## One-line bash commands

Check the [repo](https://github.com/stephenturner/oneliners) by [Stephen](https://github.com/stephenturner) first to see if he already has a one-line bash command that will work

- Print original filenames and filenames without the specified file extension:
```Bash
ls | xargs -n1 sh -c 'echo $0 $(basename $0 <file-extension>)'
```
## RNA-Seq

- "Guess" whether RNA-Seq data is stranded or not by using `infer_experiment.py` from RSeQC.
  - [RSeQC](http://rseqc.sourceforge.net/#infer-experiment-py)
  - Reference [BED file](https://sourceforge.net/projects/rseqc/files/BED/Human_Homo_sapiens/) (Human)
