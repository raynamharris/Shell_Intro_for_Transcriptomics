# Lesson 02. Navigating the Unix File System



The part of the operating system responsible for managing files and directories is called the file system. It organizes our data into files, which hold information, and directories (also called "folders"), which hold files or other directories. Several commands are frequently used to create, inspect, rename, and delete files and directories. To start exploring them, let's open a shell window:

The dollar sign is a **prompt**, which shows us that the shell is waiting for input. When typing commands from these lessons, do not type the prompt($); only type the commands that follow it.

~~~ {.bash}
$
~~~

### whoami

We can type the command `whoami` and hit the return key to execute the command. The output returned should be the name of your computer. More specifically, when we type `whoami` the shell:
1.  finds a program called `whoami`,
2.  runs that program,
3.  displays that program's output, then
4.  displays a new prompt to tell us that it's ready for more commands.

For example: 

~~~ {.bash}
$ whoami
~~~
~~~ {.output}
raynamharris
$ 
~~~

### pwd

Next, let’s find out where we are by running a command called `pwd` which stands for **print working directory**. At any moment, our current working directory is our current default directory, i.e., the directory that the computer assumes we want to run commands in unless we explicitly specify otherwise. 

~~~ {.bash}
$ pwd
~~~
~~~ {.output}
/Users/raynamharris
~~~

Note: The home directory path will look different on different operating systems. On Linux it may look like /Users/raynamharris but on Windows it will look more like C:\Users\raynamharris. In future examples, we’ve used Mac output as the default.

### ls

If we want to see the contents of our own filesystem, we cannot simply double click a folder on our desktop. From the command line, we the command `ls`, which stands for “listing”, to explore our file system. `ls` prints the names of the files and directories in the current directory in alphabetical order, arranged neatly into columns.

~~~ {.bash}
$ ls
~~~
~~~ {.output}
Applications	Downloads             
Desktop			Github 
Dropbox			Movies    
Documents		Music           
~~~

This is cool, but we can view a lot more information about our files by using **flags** or **arguments**. Let's explore the following: `ls -t`, and `ls -tlh`. The -t flag will sort things in order by the time last edited. We can combine flags to do multiple things at a time, like sort by time (-t), list all the details (-l), and display the file size in human readable format (-h).

~~~ {.bash}
ls -t
~~~
~~~ {.output}
Desktop		Applications  
Downloads	Documents	
Dropbox		Movies	
Github		Pictures
~~~

~~~ {.bash}
ls -tlh
~~~
~~~ {.output}
drwx------+ 24 raynamharris  staff   816B Feb 16 18:42 Desktop
drwx------@ 36 raynamharris  staff   1.2K Feb 16 18:42 Dropbox
drwx------+ 38 raynamharris  staff   1.3K Feb 16 18:39 Downloads
drwx------+ 63 raynamharris  staff   2.1K Feb 16 16:36 Documents
drwxr-xr-x  19 raynamharris  staff   646B Feb 16 02:16 Github
drwx------+ 15 raynamharris  staff   510B Feb 15 11:28 Pictures
drwx------   6 raynamharris  staff   204B Feb  3 16:58 Applications
drwx------+  5 raynamharris  staff   170B Feb  3 15:32 Music
~~~

We can also list contents of other directories by providing the path to that directory. 

~~~ {.bash}
$ ls -tlh Pictures
~~~
~~~ {.output}
-rw-r--r--@  1 raynamharris  staff   595K Feb 15 11:28 1000x300BDiB2016.png
-rw-r--r--@  1 raynamharris  staff   237K Feb 13 13:23 BDiBMugExample2016-2.jpg
drwxr-xr-x   2 raynamharris  staff    68B Feb  8 16:55 GoPro
~~~

~~~ {.bash}
$ ls -tlh Dropbox/GoPro
~~~
~~~ {.output}
-rw-------@ 1 raynamharris  staff   1.5G Feb  9 07:52 GOPR0009.MP4
-rw-------@ 1 raynamharris  staff    18M Feb  8 22:13 GOPR0008.MP4
~~~

### cd

We can also move around in the file system or *change directories*. The command to change locations is `cd` followed by the name of the directory or perhps the name and full path to the directory. 

~~~ {.bash}
$ cd Desktop
~~~

This command `cd ..` will take you up one directory. The command `cd ../..` will take you up two directories. The command `cd ../<other_directory_name` will take you up one directory level and into another directory. 

The .. is a relative path, because its relative to where you are now. We can also specify the absolute path to move around without respect to our current directory. For example:

~~~ {.bash}
$ cd ../Pictures
$ cd /Users/raynamharris/Pictures
~~~

In UNIX all the following commands (and others too) will take you to your home directory. 

~~~ {.bash}
$ cd 
$ cd ~
$ cd /Users/raynamharris
~~~

### Socrative Unix-Directories-Exercise
Login to [Socrative](https://b.socrative.com/login/student/) as a Student.
Enter the Room Number AKV8EK5UQ
Record your answers
