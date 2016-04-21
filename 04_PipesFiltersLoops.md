# Lesson 04: Pipes, Filters, and Loops

Rather than creating complex programs that do many different things, Unix programmers focus on creating simple tools that each do one job well. The simple tools can then be combined with one another to carry out more complex processes. This programming model is called “pipes and filters”. The key is that any program that reads lines of text from standard input and writes lines of text to standard output can be combined with every other program that behaves this way as well. 

To illustrate this concept, lets learn a few new commands and then learn how to string them together.

## wc

The **word count** command  `wc <filename>` counts the number of lines, words, and characters in the specified file.

To count the number of lines, words, and characters in our fastq.gz files, let's run the  command `wc Sample_Yeast_L005_R1.cat.fastq`.
`wc` is the "word count" command:
it counts the number of lines, words, and characters in files.

~~~ {.bash}
$ wc human_rnaseq.fastq
~~~
~~~ {.output}
  400000  400000 24624835 human_rnaseq.fastq
~~~


The `*` in `*.pdb` matches zero or more characters,
so the shell turns `*.pdb` into a list of all `.pdb` files in the current directory:


## Proceed to the Next and Previous lessons
**Next Lesson:** [05 Finding Things: Grep and History](https://github.com/raynamharris/Shell_Intro_for_Transcriptomics/blob/master/05_FindingThings.md)     
**Previous Lesson:** [03 Read Write Move Copy](https://github.com/raynamharris/Shell_Intro_for_Transcriptomics/blob/master/03_ReadWriteMoveCopy.md)