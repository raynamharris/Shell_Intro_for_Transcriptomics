# Lesson 07: Bash Scripts

Let's write a script that will execute Scott's one liner to find the most overrepresented sequence. But, let's go over some of the file structure.

## .sh and #!/bin/bash

Bash scripts are text files that end in `.sh`. Also, for cloud computing, they must start with a header that lets the computer know what type of file it is. When working on stampede, all your files will begin with `#!/bin/bash`.

So, let's start by making a file with that header.

~~~ {.bash}
$ echo '#!/bin/bash' >> overrepresented.sh
~~~

Now lets append the for loop we wrote earlier to find the most overrepresented sequence for all of our samples.

~~~ {.bash}
$ echo 'for file in *fastq; do echo $file; head -100000 $file | grep -A 1 '^@HWI' | grep -v '^@HWI' | sort | uniq -c | sort -n -r | head -n 2; done' >> overrepresented.sh 
~~~

## bash overrepresented.sh

To execute the command, type `bash overrepresented.sh`

~~~ {.bash}
$ bash overrepresented.sh 
~~~

The answer is the same, but now we don't have to keep typing the for loop everytime we need to call it!  

## Proceed Previous lesson
**Previous Lesson:** [06 For Loops](https://github.com/raynamharris/Shell_Intro_for_Transcriptomics/blob/master/06_ForLoops.md) 


