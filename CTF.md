# OverTheWire CTF Solutions

## Bandit

### Level 0

![Bandit Level 0](images/image1.png)

### Level 0 &rarr; Level 1

 - `cat readme`

![Bandit Level 0 to 1 first](images/image2.png)
![Bandit Level 0 to 1 second](images/image3.png)

### Level 1 &rarr; Level 2

 - `cat ./-`

![Bandit Level 1 to 2 first](images/image4.png)

### Level 2 &rarr; Level 3

 - `cat "spaces in this filename"`

![Bandit Level 2 to 3 first](images/image5.png)
![Bandit Level 2 to 3 second](images/image6.png)

### Level 3 &rarr; Level 4

 - `ls -a`: a stands for all shows entries that starts with ‘.’ which are generally hidden.
 - `cat .hidden`

![Bandit Level 3 to 4 first](images/image7.png)
![Bandit Level 3 to 4 second](images/image8.png)

### Level 4 &rarr; Level 5

 - `cd inhere`
 - `ls`
 - `file ./-f*`. Note: `file *` lists the data types of all the files but since the file name starts with `-f`. `*` will give `ile00` instead of `-file00`  and so on therfore giving the wrong output. To overcome this we use `./-f*`.
 - `cat ./-file07`

![Bandit Level 4 to 5 first](images/image9.png)
![Bandit Level 4 to 5 second](images/image10.png)

### Level 5 &rarr; Level 6

Command: `find . -type f -readable ! -executable -size 1033c`

Explanation:
 - The `-readable` flag indicates file is in “human readable” form.
 - `! executable` because the file should not be executable :p
 - `-size 1033c` indicating file size specified by the problem statement.

![Bandit Level 5 to 6 first](images/image11.png)

### Level 6 &rarr; Level 7

Command: `find / -user bandit7 -group bandit6 -size 33c 2>&1 | grep -v "Permission denied" | grep -v "No such file or directory"`

Explanation:
 - `-user`, `-group`, `-size` to search for the specified user, group and file size.
 - `2>&1`: basically redirect any stdout message which is an error message of type “Permission denied” or “No such file or directory” to stderr.
 - The file containing password is the only file without the above mentioned errors.

![Bandit Level 6 to 7 first](images/image12.png)

### Level 7 &rarr; Level 8

Command: `cat data.txt | grep "millionth"`

Explanation:
 - `grep` is a command line utility to filter text with the help of regular expressions

![Bandit Level 7 to 8 first](images/image13.png)

### Level 8 &rarr; Level 9

Command: `sort data.txt | uniq -u`

Explanation:
 - `sort` command sorts all lines in the specified file
 - `uniq -u` return only the lines which are repeated only once

![Bandit Level 8 to 9 first](images/image14.png)
![Bandit Level 8 to 9 first](images/image15.png)

### Level 9 &rarr; Level 10

Command: `strings data.txt | grep "====="`

Explanation:
 - `strings` command prints only human readable characters from a file

![Bandit Level 9 to 10 first](images/image16.png)
![Bandit Level 9 to 10 first](images/image17.png)

### Level 10 &rarr; Level 11

Command: `base64 -d data.txt`

Explanation:
 - `base64 -d` decodes a base64 encoded string

![Bandit Level 10 to 11 first](images/image18.png)
![Bandit Level 10 to 11 first](images/image19.png)

### Level 11 &rarr; Level 12

Command: `cat data.txt | tr '[a-zA-Z]' '[n-za-mN-ZA-M'`

Explanation:
 - `tr` converts elements from one set to another
 - `[a-zA-Z]` makes a set of lowercase+uppercase in normal order
 - `[n-za-mN-ZA-M]` makes a set shifted by 13 digits

![Bandit Level 11 to 12 first](images/image20.png)
![Bandit Level 11 to 12 first](images/image21.png)