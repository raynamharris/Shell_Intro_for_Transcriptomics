# Lesson 03. Reading, Writing, Moving, Copying Files
## 3. Bash Commands

Now, let's begin exploring the Gapminder dataset. We are going to download some a directory and its contents to our desktop. Lines 1,2, and 4 should be familiar. We will learn more about the third line later. 

~~~ {.bash}
$ cd
$ cd Desktop 
$ git clone https://github.com/raynamharris/GapminderCourse.git
$ cd GapminderCourse
$ pwd GapminderCourse
~~~

### mkdir

Let's create a new directory in here called *practice* using the command `mkdir` which stands for *make directory*. You can check to see that it was made with `ls` then change into that directory with `cd`

~~~ {.bash}
$ mkdir practice
$ cd practice
~~~

### echo, >, and >> 

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

### cat, head, tail, and less

We made two files, but how do we look at them? Let's explore a few of the many ways.

`cat <filename>` file name print the context to the screen. We can even print multiple files to the screen at once like this `cat <filename> <filename>`

~~~ {.bash}
$ cat hello.txt
$ cat hellohello.txt
$ cat hello.txt hellohello.txt
$ 
~~~
  
`head <filename>` and `tail <filename>` are two commands that print the first or last, respectively, 5 lines of the file to the screen. Here, we have less that 5 lines, so you can see the whole file this way.

~~~ {.bash}
$ head hello.txt
$ tail hellohello.txt 
~~~

`less <filename>` will open up a program called less so that you can view and scroll through the contents. Hit the q key to quit the program less. 

### cp
We use the `cp` command to copy files from one location to another. You can be very verbose with the command, such by including the full path and file name to the orginal and new copy `cp <path/to/original/filename.txt> <path/to/new.filename>` or you can use some of the tricks we learned earlier. 

Let's practice this by copying some data from the data directory (which is one level up) into our current directory (`.`). Let's use `ls` to look at the filename and the current directory with `cp <path/to/file/file.txt> .` 

~~~ {.bash}
$ ls ..
$ ls ../data
$ cp ../data/gapminder-FiveYearData.csv .
$ ls
$ ls ../data
~~~

When we use `cp` function, we end up with two copies of the same file. 

### mv
We use the `mv` command to move or to rename files. We use the syntax `mv <origingalfilename> <newfilename>

~~~ {.bash}
$ mv gapminder-FiveYearData.csv gapminder.csv
$ ls
~~~

### rm 
We can use the `rm` command to remove files. The command `rm -r` is used when removing directories. The -r means recursive or, in this case, remove the directory and everything inside it.

~~~ {.bash}
$ rm gapminder.csv
$ cd ..
$ rm -r practice
~~~

## Socrative Unix-Files-Exercise
Login to Socrative as a Student.
Enter the Room Number AKV8EK5UQ