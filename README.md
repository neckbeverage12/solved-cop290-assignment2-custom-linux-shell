Download Link: https://assignmentchef.com/product/solved-cop290-assignment2-custom-linux-shell
<br>
<strong>Writing a basic shell </strong>

Write a program in C to act as a command interpreter (Shell). The shell will give a prompt for the user to type in a command (from a set of commands), take the command, execute it, and then give the prompt back for the next command (i.e., actually give the functionality of a shell). Your program should do the following:

<ul>

 <li>Give a prompt “shell&gt;” for the user to type in a command</li>

 <li>Implement the following <em>builtin </em>commands:</li>

 <li><strong>cd “dir” </strong>: changes the directory to “dir”</li>

 <li><strong>pwd </strong>: prints the current directory</li>

 <li><strong>mkdir “dir” </strong>: creates a directory called “dir”</li>

 <li><strong>rmdir “dir” </strong>: removes the directory called “dir”</li>

 <li><strong>exit </strong>: exits the shell</li>

</ul>

The commands are the same as the corresponding Linux commands by the same name. Do “man” to see the descriptions. You can use the standard system calls chdir, getcwd, mkdir, rmdir etc. to implement the calls (standard C library functions are available for these; look them up). These commands are called <em>builtin </em>commands since your shell program will have a function corresponding to each of these commands to execute them; no new process will be created to execute them.

<ul>

 <li>Any other command typed at the prompt should be executed as if it is the name of an executable file. For example, typing “a.out” should execute the file <em>out </em>. The file can be in the current directory or in any of the directories specified by the PATH environment variable. The file should be executed after creating a new process and then exec’ing the file onto it. The parent process should wait for the file to finish execution and then go on to read the next command from the user.</li>

 <li>Should be able to redirect the output of a program to a file using “&gt;” and read the input of a program from a file using “&lt;“. For example, typing “a.out &gt; outfile” should send whatever was supposed to be displayed on the screen by a.out to the file <em>outfile </em>. Similarly, typing “a.out &lt; infile” should make a.out take the inputs from the file <em>infile </em>instead of the keyboard.</li>

 <li>Should be able to redirect the output of one command to the input of another by using the “|” symbol. For example, if there is a program <em>out </em>that writes a string “abcde” to the display, and there is a program <em>b.out </em>that takes as input a string typed from the keyboard, counts the number of characters in the string, an displays it, then typing “a.out | b.out” at your shell prompt should display 5 (the output “abcde” from <em>a.out </em>was fed as input to <em>b.out </em>, and 5, the number of characters in “abcde”, is printed). Use the pipe command.</li>

</ul>

To run your shell, write another C program that will create a child process and call an appropriate form of exec to run the program above. The parent process simply waits for the child to finish (execute the “exit” command), after which it also exits.

Name the file containing your C code for the shell &lt;your roll no&gt;_sh.c (for example, 06CS1004_sh.c). Submit only this C file.