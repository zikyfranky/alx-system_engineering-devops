# Shell Scripting Basics Exercises

## [0-current_working_directory](./0-current_working_directory)

    pwd -> print working directory

## [1-listit](./1-listit)

    ls -> list directory contents

## [2-bring_me_home](./2-bring_me_home)

    cd -> change directory

## [2-bring_me_home](./2-bring_me_home)

    cd ~ -> Return to home directory

## [3-listfiles](./3-listfiles)

    ls -l -> list directory contents in long form

## [4-listmorefiles](./4-listmorefiles)

    ls -al -> list directory contents in long form, including hidden files

## [5-listfilesdigitonly](./5-listfilesdigitonly)

    ls -an -> Order ls output by digits first

## [6-firstdirectory](./6-firstdirectory)

    mkdir /tmp/my_first_directory -> Create a my_first_directory inside the tmp directory

## [7-movethatfile](./7-movethatfile)

    mv /tmp/betty /tmp/my_first_directory/betty -> Move file betty, which is located inside the tmp directory, to the my_first_directory directory, which is also located inside the tmp directory.

## [8-firstdelete](./8-firstdelete)

    rm /tmp/my_first_directory/betty -> Remove file betty located in tmp/my_first_directory directory.

## [9-firstdirdeletion](./9-firstdirdeletion)

    rmdir /tmp/my_first_directory OR rm -r /tmp/my_first_directory -> Remove directory my_first_directory located in directory tmp.

## [10-back](./10-back)

    cd - -> Change directory to the previous directory you were in.

## [11-lists](./11-lists)

     ls -al . .. /boot -> List all files/directories, including hidden files/directories, from 3 separate directories: current directory, parent of working directory, and /boot directory. The ls command allows multiple directories to be listed separated by spaces.

## [12-file_type](./12-file_type)

    file /tmp/iamafile -> Prints the type of file iamafile.

## [13-symbolink_link](./13-symbolink_link)

    ln -s /bin/ls ./__ls__ -> Create a symbolic link named __ls__ for /bin/ls in working directory

## [14-copy_html](./14-copy_html)

    cp ./*.html ../ -u -> Copy all html files from the current directory to the parent directory, but only copy files that didn't exist in the parent directory or are newer versions than the ones that already exist in the parent directory. The -u flag copies the file into the directory if its a newer version OR If the file doesn't exist in the directory unlike the -n flag that works for copying files that don't exist in the parent directory, but doesn't check if the file is a newer version or not.

## [100-lets_move](./100-lets_move)

    mv [A-Z]* /tmp/u/ -> Move all files that begin with a capital letter to /tmp/u

## [101-clean_emacs](./101-clean_emacs)

     rm *~ Deletes all files in the current directory that end with a ~

## [102-tree](./102-tree)

    mkdir -p welcome/to/school -> Create nexted directories, The -p flag creates any intermediate directories in the path argument.

## [103-commas](./103-commas)

    ls -amvp -> List all files and directories of the current directory, separated by commas. Directory names should end with a /. The listing should be alph ordered, except for dot (.) or dot dot (..), which should be listed at the beginning. The -a flag is to show any hidden files. The -p flag writes a / at the end of directory names. The -m flag streams the output, separating each listing with commas. The -v flag lets out printed if not in a terminal

## [school.mgc](./school.mgc)

    0 string SCHOOL School data !:mime School -> Create a magic file called school.mgc that can be used with the command file to detect School data files. School data files always contain "SCHOOL" at offset 0.

    This much different from the previous exercises. From what I understand, the magic file is used to detect patterns in files and will give a specified output depending on a matching pattern. The first argument is a number representing the offset. The second argument is the data type you are searching for. In our case, it is a string. The third argument is the data you are searching for. In our case, "SCHOOL", which we specified as a string in the second argument. The fourth argument is the message you want to output on match. If the search matches, it will output this message. The last argument is separated by a line. Since the fourth argument can be long and contain multiple strings, we separate the fourth and fifth arguments with this new line. This last argument can be multiple different things. In this case, a MIME type. According to bash manual, a "MIME type is given on a separate line, which must be the next non-blank or comment line after the magic line that identifies the file type". I knew to search for a MIME type because the example provided: $ file --mime-type -m school.mgc _ The above returns message "Holberton" when matching a MIME ?? Not exactly sure, but this is what I can tell from what I've tested out and can see from the output and examples. $ file -m school.mgc _ The above will return message "Holberton data" for any offset 0 "SCHOOL" matches. A cool thing to note is that the file command is compiling and running the magic file. So there is no need to compile to magic "permanently". NOTE: Compiling a magic source file: $ file -C -m .mgc This produces the compiled magic file. $ file -i -m .mgc \* This allows you to use the compiled file by specifying its name using the -m switch again.
