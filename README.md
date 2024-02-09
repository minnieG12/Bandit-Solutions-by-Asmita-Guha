# Bandit Solutions by Asmita Guha

All Information with reference to [Website](https://overthewire.org/wargames/bandit/)


## Level 0
*To log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0.*

**Notes:** SSH - Secure Shell

1. Type command ```ssh bandit0@bandit.labs.overthewire.org -p 2220```
2. Password: ```bandit0```
3. Server entered successfully

![Image](/Intro.png)

---
## Level 0 to 1
*The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.*

**Notes:** cat - to read files, exit - to exit server; ls - to list directories; ctrl+shift+c - to copy pw; ctrl+shift+v - to paste pw

1. Use ```ls``` to list directories
2. For next password stored in readme, use ```cat readme```
3. New Password: ```NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL```
4. Type ```exit``` 

![Image](/0-1.png)

---
## Level 1 to 2
*The password for the next level is stored in a file called - located in the home directory.*

**Notes:** To read files starting with - , cat ./- is used.

1. Type command ```ssh bandit1@bandit.labs.overthewire.org -p 2220```
2. Password: ```NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL```
3. Use ```ls``` to list directories
4. To read - file, use ```cat ./-```
5. New password: ```rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi```
6. Type ```exit```

![Image](/1-2.png)

---
## Level 2 to 3
*The password for the next level is stored in a file called spaces in this filename located in the home directory.*

**Notes:** In a file name with spaces, each word is counted as a file. In order to read the collective file \ needs to be used.

1. Type command ```ssh bandit2@bandit.labs.overthewire.org -p 2220```
2. Password: ```rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi```
3. Use ```ls``` to list directories
4. To read, use ```cat spaces\ in\ this\ filename```
5. New Password: ```aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG```
6. Type ```exit```

![Image](/2-3.png)

---
## Level 3 to 4
*The password for the next level is stored in a hidden file in the inhere directory.*

**Notes:** cd - change directory to enter a directory; ls -a - used to show hidden files under directories like .hidden in this case

1. Type command ```ssh bandit3@bandit.labs.overthewire.org -p 2220```
2. Password: ```aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG```
3. Use ```ls``` to list directories
4. Use ```cd inhere``` to enter inhere directory
5. Use ```ls -a``` command to list all directories in inhere including hidden files
6. To read, use ```cat .hidden```
7. New Password: ```2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe```
8. Type ```exit```

![Image](/3-4.png)

---
## Level 4 to 5
*The password for the next level is stored in the only human-readable file in the inhere directory.*

**Notes:** file - to specify data type of file when data type of multiple files needs to be found; use file0* where * takes values from 0 to 9; exit -d sequence can also be used to exit server

1. Type command ```ssh bandit4@bandit.labs.overthewire.org -p 2220```
2. Password: ```2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe```
3. Use ```ls``` to list all directories
4. Use ```cd inhere``` to enter inhere directory
5. Use ```ls``` to list all directories in inhere
6. To find data type of each file, use ```file ./-file0*```
7. File07 is the only file with ASCII text, hence, it is our required file
8. To read, use ```cat ./-file07```
9. New Password: ```lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR```
10. Type ```exit```

![Image](/4-5.png)

---
## Level 5 to 6
*The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties: human-readable, 1033 bytes in size, not executable*

**Notes:** cd .. - used to go to the previous directory; ./ - Human readable file, -size 1033c - file size of 1033 bytes

1. Type command ```ssh bandit5@bandit.labs.overthewire.org -p 2220```
2. Password: ```lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR```
3. Use ```ls``` to list all directories
4. To search for file with given specifications, use ```find ./ -type f -size 1033c```
5. Use ```cd maybehere07``` to enter directory with required file
6. To read required file, use ```cat .file2```
7. New Password: ```P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU```
1. Type ```exit```

![Image](/5-6.png)

---
## Level 6 to 7
*The password for the next level is stored somewhere on the server and has all of the following properties: owned by user bandit7, owned by group bandit6, 33 bytes in size*

**Notes:**  -user bandit7 - user of the file is bandit7; -group bandit6 - group of the file is bandit6; -size 33c - size of the file is 33 bytes

1. Type command ```ssh bandit6@bandit.labs.overthewire.org -p 2220```
2. Password: ```P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU```
3. Use ```cd /``` to enter directory
4. To search for required file with given specifications, use ```find ./ -user bandit7 -group bandit6 -size 33c```
5. Search for file where permission is not denied
6. To read, use ```cat ./var/lib/dpkg/info/bandit7.password```
7. New Password: ```z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S```
8. Type ```exit```

![Image](/6-7%201.png)
![Image](/6-7%202.png)

---
## Level 7 to 8
*The password for the next level is stored in the file data.txt next to the word millionth*

**Notes:** redirection & piping; grep - short for “global regular expression print”, is a command used for searching and matching text patterns in files contained in the regular expressions

1. Type command ```ssh bandit7@bandit.labs.overthewire.org -p 2220```
2. Password: ```z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S```
3. Use ```ls``` to list all directories
4. To read required file, use ```grep millionth data.txt```
5. New Password: ```TESKZC0XvTetK0S9xNwm25STk5iWrBvP```
6. Type ```exit```

![Image](/7-8.png)

---
## Level 8 to 9
*The password for the next level is stored in the file data.txt and is the only line of text that occurs only once*

**Notes:** piping method; sort - to sort all the possible pws in ascending order; uniq - to rule out repeated text and show unique text only; uniq -c - shows no. of times each text has been repeated; uniq -u - shows text that has been mentioned only once; | - the (|) Unix pipe connects the stdout from the first command and feeds it as stdin to the second command

1. Type command ```ssh bandit8@bandit.labs.overthewire.org -p 2220```
2. Password: ```ESKZC0XvTetK0S9xNwm25STk5iWrBvP```
3. Use ```ls``` to list all directories
4. To read, use piping ```cat data.txt | sort | uniq -u ```
5. New Password: ```EN632PlfYiZbn3PhVK3XOGSlNInNE00t```
6. Type ```exit```

![Image](/8-9.png)

---
## Level 9 to 10
*The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.*

**Notes:** strings - to read human-readable strings, grep = - to search text with =

1. Type command ```ssh bandit9@bandit.labs.overthewire.org -p 2220```
2. Password: ```EN632PlfYiZbn3PhVK3XOGSlNInNE00t```
3. To read, use ```strings data.txt```
4. Password is preceded by multiple "=", ```grep =``` command may be piped to make search easier
5. New Password: ```G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s```
6. Type ```exit```

![Image](/9-10%201.png)
![Image](/9-10%202.png)
![Image](/9-10%203.png)

---
## Level 10 to 11
*The password for the next level is stored in the file data.txt, which contains base64 encoded data*

**Notes:** base64 - preinstalled tool in linux system; -d - decode

1. Type command ```ssh bandit10@bandit.labs.overthewire.org -p 2220```
2. Password: ```G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s```
3. To read, use ```cat data.txt```
4. To get password stored in data.txt containing base64 encoded data, use ```cat data.txt | base64 -d```
5. New Password: ```6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM```
6. Type ```exit```

![Image](/10-11.png)

---
## Level 11 to 12
*The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions*

**Notes:** Using rot13.com to cipher given code where letters have been rotated by 13 positions; tr - command to translate data could have also been used

1. Type command ```ssh bandit11@bandit.labs.overthewire.org -p 2220```
2. Password: ```6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM```
3. To read, use ```cat data.txt```
4. Paste code on ```rot13.co``` to cipher it in order to obtain the password
5. New Password: ```JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv```
6. Type ```exit```

![Image](/11-12%201.png)

---
## Level 12 to 13
*The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir.*

**Notes:**  Creating temporary directory new1 using /tmp; xxd -r - used to generate as well as reverse a hexdump; gzip - used to decompress gzip file; bzip2 - used to decompress bzip2 file type; tar -xvf - used to extract POSIX tar archive (GNU) file; goal is to keep extracting files with gzip, bzip2 & tar extensions until ASCII text type file is found

1. Type command ```ssh bandit12@bandit.labs.overthewire.org -p 2220```
2. Password: ```JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv```
3. Change directory to /tmp ```cd /tmp``` & make new directory ```mkdir new1```
4. Copy data.txt file to new directory using ```cp data.txt /tmp/new1```
5. Read data.txt file and reverse hexdump using ```cat data.txt | xxd -r```
6. Store read data in file called hexdump by redirection ```cat data.txt | xxd -r > hexdump```
7. Check file type of hexdump with ```file hexdump``` & move file to new file with appropriate extension according to file type ```mv hexdump hexdump.gz```
8. To extract file, use ```gzip -d hexdump.gz```
9. Check file type of hexdump with ```file hexdump``` & move file to new file with appropriate extension according to file type ```mv hexdump hexdump.bz2```
10. To extract file, use ```bzip2 -d hexdump.bz2```
11. Continue process until POSIX tar archive (GNU) file is found
12. To extract file, use ```tar -xvf hexdump```
13. Keep extracting gzip, bzip2 & tar files until ASCII text data type file located
14. To read, use ```cat data8.bin```
15. New Password: ```wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw```
16. Type ```exit```

![Image](/12-13%201.png)
![Image](/12-13%202.png)
![Image](/12-13%203.png)
![Image](/12-13%204.png)
![Image](/12-13%205.png)

---
## Level 13 to 14
*The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on.*

**Notes:** Password stored is in localhost; -i - identifier that we have privatekey and not a password; whoami - to check server; /etc - to navigate into the etc folder; bandit_pass - folder with password

1. Type command ```ssh bandit13@bandit.labs.overthewire.org -p 2220```
2. Password: ```wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw```
3. List directories using ```ls```
4. Enter localhost with sshkey.private ```ssh bandit14@localhost -p 2220 -i sshkey.private``` & authenticate connection by typing yes
5. Check server with ```whoami```
6. To read, use ```cat /etc/bandit_pass/bandit14```
7. New Password: ```fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq```
8. Type ```exit```

![Image](/13-14%201.png)
![Image](/13-14%202.png)

---
## Level 14 to 15
*The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.*

**Notes:** port - 30000; nc - netcat is a swiss army tool to make TCP & UDP connections used to listen for ports

1. Use ```nc localhost 30000```
2. Password: ```fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq```
3. New Password: ```jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt```
4. Type ```exit```

![Image](/14-15.png)

---
## Level 15 to 16
*The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.*

**Notes:** pass= - used to store password in variable pass; ssl - secure socket layer; ssl connection is to be used with openssl command; port - 30001; read R block - prompt that asks for password 

1. Type command ```ssh bandit15@bandit.labs.overthewire.org -p 2220```
2. Password: ```jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt```
3. Store password in a variable using ```pass=jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt```
4. Establish new connection using ```openssl s_client -connect localhost:30001```
5. To read R block, just paste old password
6. New Password: ```JQttfApK4SeyHwDlI9SXGR50qclOAil1```
7. Type ```exit```

![Image](/15-16%201.png)
![Image](/15-16%202.png)

---
## Level 16 to 17
*The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.*



