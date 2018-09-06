# bioinfoRef
Repository for keeping useful bioinformatics references

### One-line bash commands

Print original filenames and filenames without the specified file extension:
```Bash
ls | xargs -n1 sh -c 'echo $0 $(basename $0 <file-extension>)'
```
