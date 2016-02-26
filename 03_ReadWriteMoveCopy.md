# Lesson 03. Reading, Writing, Moving, Copying, Removing 


Now, let's practice reading, writing, moving, and copying files and directories. Let's go back to our Shell_Transcriptomics

~~~ {.bash}
cd ~/Desktop/Shell_Transcriptomics
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

### less
`less <filename>` will open up a program called less so that you can view and scroll through the contents. This is nice for looking at larger files. Let's move out of the practice file and look at a fasta file.


~~~ {.bash}
$ cd ..
$ less 01-tissue-S01_R1_001.fastq
~~~

This is a nice way to view this fairly large file. Hit the `q` key to quit the program less. 

### head and tail
`head <filename>` and `tail <filename>` are two commands that print the first or last, respectively, 5 lines of the file to the screen. 

~~~ {.bash}
$ head 01-tissue-S01_R1_001.fastq
$ tail 01-tissue-S01_R1_001.fastq
~~~

If you want to view more than 5 lines, we can modify the command. This examples will show the first 100 and then the last 200 lines

~~~ {.bash}
$ head -100 01-tissue-S01_R1_001.fastq
$ tail -200 01-tissue-S01_R1_001.fastq
~~~


## cp
We use the `cp` command to make a copy files. If you want to copy a file into the same directory then used something like `cp <oringinal_filename.txt> <new_filename>`. For example:

~~~ {.bash}
$ cp 01-tissue-S01_R1_001.fastq  Sample1_R1.fastq
$ ls
~~~

You can also make a copy of the file but store it in a new location. Here's are two examples. One will keep the file name the same but the other command will change the name. We can use less to see that the copied files are in the new directory

~~~ {.bash}
$ mkdir fastq_copies
$ cp 02-tissue-S02_R1_001.fastq  fastq_copies/Sample2_R1.fastq
$ cp 02-tissue-S02_R2_001.fastq  fastq_copies/
$ ls fastq_copies/
~~~

## mv
If we don't want to keep an original copy, we use the `mv` command **to move** or **to rename** files. We use the syntax `mv <origingalfilename> <newfilename>

~~~ {.bash}
$ mv Sample1_R1.fastq fastq_copies/
$ cd fastq_copies	
$ mv 02-tissue-S02_R2_001.fastq Sample2_R2.fastq
~~~

## rm 
We can use the `rm` command to remove files. 

~~~ {.bash}
$ rm Sample1_R1
~~~

To remove a non-empty directory we must add the flag ` -r`. The `-r `means recursive or, in this case, remove the directory and everything inside it.

~~~ {.bash}
$ cd ..
$ rm -r fastq_copies/
~~~

If you want to remove an empty directory, you can use `rm -r` or `rmdir`.

## Socrative Unix-Files-Exercise
Login to Socrative as a Student.
Enter the Room Number AKV8EK5UQ