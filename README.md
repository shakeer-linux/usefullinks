# usefullinks


Example:1 Search the pattern (word) in a file
Search the “linuxtechi” word in the file /etc/passwd file

root@Linux-world:~# grep linuxtechi /etc/passwd
linuxtechi:x:1000:1000:linuxtechi,,,:/home/linuxtechi:/bin/bash
root@Linux-world:~#
Example:2 Search the pattern in the multiple files.
root@Linux-world:~# grep linuxtechi /etc/passwd /etc/shadow /etc/gshadow
/etc/passwd:linuxtechi:x:1000:1000:linuxtechi,,,:/home/linuxtechi:/bin/bash
/etc/shadow:linuxtechi:$6$DdgXjxlM$4flz4JRvefvKp0DG6re:16550:0:99999:7:::/etc/gshadow:adm:*::syslog,linuxtechi
/etc/gshadow:cdrom:*::linuxtechi
/etc/gshadow:sudo:*::linuxtechi
/etc/gshadow:dip:*::linuxtechi
/etc/gshadow:plugdev:*::linuxtechi
/etc/gshadow:lpadmin:!::linuxtechi
/etc/gshadow:linuxtechi:!::
/etc/gshadow:sambashare:!::linuxtechi
root@Linux-world:~#
Example:3 List the name of those files which contain a specific pattern using -l option.
root@Linux-world:~# grep -l linuxtechi /etc/passwd /etc/shadow /etc/fstab /etc/mtab
/etc/passwd
/etc/shadow
root@Linux-world:~#
Example:4 Search the pattern in the file along with associated line number(s) using the -n option
root@Linux-world:~# grep -n linuxtechi /etc/passwd
39:linuxtechi:x:1000:1000:linuxtechi,,,:/home/linuxtechi:/bin/bash
root@Linux-world:~#
root@Linux-world:~# grep -n root /etc/passwd /etc/shadow

grep-n-root

Example:5 Print the line excluding the pattern using -v option
List all the lines of the file /etc/passwd that does not contain specific word “linuxtechi”.

root@Linux-world:~# grep -v linuxtechi /etc/passwd
grep-v-option

Example:6 Display all the lines that starts with specific pattern using ^ symbol
Bash shell treats carrot symbol (^) as a special character which marks the beginning of line or a word. Let’s display the lines which starts with “root” word in the file /etc/passwd.

root@Linux-world:~# grep ^root /etc/passwd
root:x:0:0:root:/root:/bin/bash
root@Linux-world:~#
Example: 7 Display all the lines that ends with specific pattern using $ symbol
List all the lines of /etc/passwd that ends with “bash” word.

root@Linux-world:~# grep bash$ /etc/passwd
root:x:0:0:root:/root:/bin/bash
linuxtechi:x:1000:1000:linuxtechi,,,:/home/linuxtechi:/bin/bash
root@Linux-world:~#
Bash shell treats dollar ($) symbol as a special character which marks the end of line or word.

Example:8 Search the pattern recursively using -r option
root@Linux-world:~# grep -r linuxtechi /etc/
/etc/subuid:linuxtechi:100000:65536
/etc/group:adm:x:4:syslog,linuxtechi
/etc/group:cdrom:x:24:linuxtechi
/etc/group:sudo:x:27:linuxtechi
/etc/group:dip:x:30:linuxtechi
/etc/group:plugdev:x:46:linuxtechi
/etc/group:lpadmin:x:115:linuxtechi
/etc/group:linuxtechi:x:1000:
/etc/group:sambashare:x:131:linuxtechi
/etc/passwd-:linuxtechi:x:1000:1000:linuxtechi,,,:/home/linuxtechi:/bin/bash
/etc/passwd:linuxtechi:x:1000:1000:linuxtechi,,,:/home/linuxtechi:/bin/bash
............................................................................
Above command will search linuxtechi in the “/etc” directory recursively.

Example:9 Search all the empty or blank lines of a file using grep
root@Linux-world:~# grep ^$ /etc/shadow
root@Linux-world:~#
As there is no empty line in /etc/shadow file , so nothing is displayed.

Example:10 Search the pattern using ‘grep -i’ option
-i option in the grep command ignores the letter case i.e it will not discriminate upper case or lower case letters while searching

Lets take an example , i want to search “LinuxTechi” word in the passwd file.

nextstep4it@localhost:~$ grep -i LinuxTechi /etc/passwd
linuxtechi:x:1001:1001::/home/linuxtechi:/bin/bash
nextstep4it@localhost:~$
Note : In grep command,we can also do the search based on exact word using ‘-w’ option, example is shown below,

nextstep4it@localhost:~$ grep -w cook /mnt/my_dish.txt
Above command will search and look for the lines which have “cook” word. It wont give results which has cooking.

Example:11 Search multiple patterns using -e option
For example i want to search ‘linuxtechi’ and ‘root’ word in a single grep command , then using -e option we can search multiple patterns .

root@Linux-world:~# grep -e "linuxtechi" -e "root" /etc/passwd
root:x:0:0:root:/root:/bin/bash
linuxtechi:x:1000:1000:linuxtechi,,,:/home/linuxtechi:/bin/bash
root@Linux-world:~#
Example:12 Getting Search pattern from a file using “grep -f”
First create a search pattern file “grep_pattern” in your current working directory. In my case i have put the below contents.

root@Linux-world:~# cat grep_pattern
^linuxtechi
root
false$
root@Linux-world:~#
Now try to search using grep_pattern file.

root@Linux-world:~# grep -f grep_pattern /etc/passwd
grep-f-option

Example:13 Count the number of matching patterns using -c option
Let take the above example , we can count the number of matching patterns using -c option in grep command.

root@Linux-world:~# grep -c -f grep_pattern /etc/passwd
22
root@Linux-world:~#
Example:14 Display N number of lines before & after pattern matching
a) Display Four lines before pattern matching using -B option

root@Linux-world:~# grep -B 4 "games" /etc/passwd
grep-B-option

b) Display Four lines after pattern matching using -A option

root@Linux-world:~# grep -A 4 "games" /etc/passwd
grep-A-option

c) Display Four lines around the pattern matching using -C option

root@Linux-world:~# grep -C 4 "games" /etc/passwd
grep-C-option



