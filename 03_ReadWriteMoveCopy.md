# Lesson 03. Reading, Writing, Moving, Copying, Removing, Gunzipping 

In this part of the course, we will download some RNAseq data and practice reading, writing, moving, and copying files and directories

## Getting Ready: Download the Practice Data
For this lesson, you will need to download some files in order to follow along.
Let's save this directory to our desktop

~~~ {.bash}
$ cd
$ cd Desktop
$ git clone https://github.com/raynamharris/DataForUnixCourse.git
$ cd DataForUnixCourse

~~~

## mkdir

Let's create a new directory in here called *practice* using the command `mkdir` which stands for *make directory*. You can check to see that it was made with `ls` then change into that directory with `cd`

~~~ {.bash}
$ mkdir practice
$ ls 
$ cd practice
~~~

## echo, >, and >> 

`echo` is a command we can use to print something to the screen, like "Hello, World." 

~~~ {.bash}
$ echo Hello, World.
~~~
~~~ {.output}
Hello, World.
~~~

Here, the standard output is to your screen, which is why you can see it. But, we can also redirect the output elsewhere, like to a text file with `>` or `>>`. The `>` will send the output to a file, overriding anything that may have already been there. The  `>>` will append the input to a new line of the file. Let's take a look

~~~ {.bash}
$ echo hello > hello.txt
$ echo hello > hello.txt
$ echo hello >> hellohello.txt
$ echo hello >> hellohello.txt
$ ls
~~~

## Looking at files with cat, head, tail, and less

### cat
We just made two files, but how do we look at them? Let's explore a few of the many ways.

`cat <filename>` file name print the context to the screen. We can even print multiple files to the screen at once like this `cat <filename> <filename>`

~~~ {.bash}
$ cat hello.txt
$ cat hellohello.txt
$ cat hello.txt hellohello.txt
$ 
~~~

### head and tail
`head <filename>` and `tail <filename>` are two commands that print a select number of lines of the file to the screen. The default is to print 10 lines. We can use the flag `-n 4` to print the first 4 lines

~~~ {.bash}
$ head -n 4 SRR534005_01_R1.fastq
~~~
~~~ {.output}
@SRR534005.201 HWI-ST945:93:c02g4acxx:3:1101:11521:2210/1
GAAAAGTTCAGCTTCAATACTGCATGGAACTTCGAGAAGAAAAAGCTCATGGATTTTCTTTATTCATAAACCTCCTGCCAAATAAATGAATTAATTGAAA
+
BBCFFFDFHHHHHJJJJIJJJJJJJJJJJJJJJJGJGJJIJJJJJJIJJJJJHIJJJJIJJJJJJJJJJJJJIJHHHHHFFFFFEEEEDEEEDDEEDDDD
~~~

~~~ {.bash}
$ tail -n 4 SRR534005_01_R1.fastq
~~~
~~~ {.output}
@SRR534005.300 HWI-ST945:93:c02g4acxx:3:1101:16320:2026/1
CAGGTCCAAAATAATAGTCTGAGTAAAGCANAACACTCACATGAGACCTGAGGTTAGCAGGCTGTATTTAACAGGTGCCTAATTTTTGGGTAATGCTGCC
+
CCCFDFFFHGHHHIJIJFHIIHJFHIIJII#2?FHIIJJJJJJJJJJJIJJJJFEBFGAFFG;F;@EHHHGGCHG>=@CCDCEEEECDDB;@?>>C3>C<
~~~

You might want to view a few more lines. This examples will show the first 100 and then the last 200 lines. But, its not very easy to see the whole file this way. 

~~~ {.bash}
$ head -n 100 SRR534005_01_R1.fastq
$ tail -n 200 SRR534005_01_R1.fastq
~~~

### less
`less <filename>` will open up a program called less so that you can view and scroll through the contents. This is nice for looking at larger files. Let's move out of the practice file and look at a fasta file.


~~~ {.bash}
$ cd ..
$ less SRR534005_01_R1.fastq
~~~

This is a nice way to view this fairly large file using the up and down arrows. 
Hit the `q` key to quit the program less. 


## cp
We use the `cp` command to make a copy files. If you want to copy a file into the same directory then used something like `cp <oringinal_filename.txt> <new_filename>`. For example:

~~~ {.bash}
$ cp yeast_01_R1.fastq.gz  copy_yeast_01_R1.fastq.gz
$ ls
~~~

You can also make a copy of the file but store it in a new location. Here's are two examples. One will keep the file name the same but the other command will change the name. We can use less to see that the copied files are in the new directory

~~~ {.bash}
$ mkdir fastq_copies
$ cp yeast_01_R2.fastq.gz fastq_copies/
$ cp yeast_02_R2.fastq.gz  fastq_copies/copy-yeast_02_R2.fastq.gz
$ ls fastq_copies/
~~~

## mv
If we don't want to keep an original copy, we use the `mv` command **to move** or **to rename** files. We use the syntax `mv <origingalfilename> <newfilename>

~~~ {.bash}
$ mv copy_yeast_01_R1.fastq.gz fastq_copies/
$ cd fastq_copies
$ ls	
$ mv yeast_01_R2.fastq.gz copy-yeast_01_R2.fastq.gz
$ ls
~~~

## rm 
We can use the `rm` command to remove files. 

~~~ {.bash}
$ rm copy-yeast_01_R2.fastq.gz
~~~

To remove a non-empty directory we must add the flag ` -r`. The `-r `means recursive or, in this case, remove the directory and everything inside it.

~~~ {.bash}
$ cd ..
$ rm -r fastq_copies/
~~~

If you want to remove an empty directory, you can use `rm -r` or `rmdir`.

# FIXME
# Socrative Unix-Files-Exercise
Login to Socrative as a Student.
Enter the Room Number AKV8EK5UQ

## Proceed to the Next or Previous lesson
**Next Lesson:** [04 Pipes and Filters](https://github.com/raynamharris/Shell_Intro_for_Transcriptomics/blob/master/04_PipesFilters.md)  
**Previous Lesson** [02 Navigating Directories](https://github.com/raynamharris/Shell_Intro_for_Transcriptomics/blob/master/02_Navigating_Dirs.md)