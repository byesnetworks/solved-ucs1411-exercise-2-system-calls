Download Link: https://assignmentchef.com/product/solved-ucs1411-exercise-2-system-calls
<br>
To develop a C program to implement the cp, ls, grep commands (with some options) using system calls.

<strong>Sample Learning Outcome:</strong>

<ol>

 <li>Implement the various system commands like cp, grep, ls, head, tail, wc using system calls</li>

 <li>Learn to process command line arguments and error handling mechanism</li>

 <li>Understand the relation between the system calls and commands</li>

</ol>

<strong>Best Practices:</strong>

<ol>

 <li>Algorithm design</li>

 <li>Naming convention – for file names, variables</li>

 <li>Comment usage at proper places</li>

 <li>Prompt messages during reading input and displaying output</li>

 <li>Error handling mechanisms for failures in system calls</li>

 <li>Incremental program development</li>

 <li>Modularity</li>

 <li>All possible test cases in output</li>

</ol>

<strong>AIM:</strong>

To develop a C program to implement the cp, ls, grep commands (with some options) using system calls.

<strong>cp command: basic cp, -i </strong>To copy a file into another <strong>ls command: basic ls, -1, -R</strong>

To list all files in the directory

<strong>grep command: basic grep, -c, -v, -n</strong>

To search the given pattern in the file

<strong>Procedure for cp:</strong>

<ol>

 <li>The arguments should be obtained in command line and error messages should be printed if they are not sufficient.</li>

 <li>Use open, read, write, creat ,close system calls to do the following.</li>

</ol>

mycp sourcefilename destinationfilename

-copies source file to destination file

<ol start="3">

 <li>The failure messages for opening a file, creating a file should be intimated.Note: mycp is the user programs implementing cp.</li>

</ol>

<strong>Procedure for ls:</strong>

<ol>

 <li>To view the files in a directory include dirent.h that helps for opening, reading, closing a directory.</li>

 <li>Open the user named directory giving specific path using opendir system call. This returnsa pointer to a DIR data structure that represents a directory. 3. Can even use “.” to represent the current working directory.</li>

 <li>Traverse the directory entries using readdir system call. readdir () returns a pointer to a</li>

</ol>

dirent structure whose member d_name contains the name of the current file.

<ol start="5">

 <li>Output the entries of directory.</li>

 <li>Close the directory pointer</li>

</ol>

NOTE: Use open, read, write, creat ,close, opendir, readdir, closedir system calls wherever necessary.

<strong>Procedure for grep:</strong>

<ol>

 <li>Open the command line specified file using the required system call.</li>

 <li>Read the contents iteratively till the end of the file and compare it with the pattern you aresearching for.</li>

 <li>If word found print the line on to the display.</li>

 <li>Count the number of occurrences and display it finally.</li>

 <li>Close the file descriptor.</li>

</ol>

NOTE: Use open, read, write, creat ,close system calls wherever necessary.

<strong>SAMPLE INPUT/OUTPUT: <u>cp:</u></strong>

Source.txt:

SSN COLLEGE OF ENGINEERING

target.txt:

SSN NAGAR

KALAVAKKAM

$ ./mycp source.txt target.txt

FILE COPIED!

<strong><u>ls: </u></strong>$ ./myls lab

OUTPUT:

.

..

diros diros.zip Ex-3-cp-cat.doc

Ex-3-cp-cat.pdf Ex-4-ls-grep.doc fork.pdf grep.doc prgs.doc sys-call prgs.doc <strong><u>grep:</u></strong>

$ ./mygrep pattern filename

OUTPUT:

Display the contents of the file that has the pattern in it