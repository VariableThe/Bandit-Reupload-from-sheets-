The Bandit wargame is a series of challenges designed to teach beginners the basics of Linux command-line operations. Below is a comprehensive guide to solving levels 1 through 18, including the passwords for each level.

---

## Level 0 ➜ Level 1

*Goal:* The password for the next level is stored in a file called readme located in the home directory.

*Commands you may need to solve this level:* ls, cat

### Solution:

1. *Log into Bandit0:*

   bash
   ssh bandit0@bandit.labs.overthewire.org -p 2220
   

   - *Password:* bandit0

2. *List the files in the home directory:*

   bash
   ls
   

3. **Display the contents of the readme file:**

   bash
   cat readme
   

   - *Password for Bandit1:* NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

---

## Level 1 ➜ Level 2

*Goal:* The password for the next level is stored in a file called - located in the home directory.

*Commands you may need to solve this level:* ls, cat

### Solution:

1. *Log into Bandit1:*

   bash
   ssh bandit1@bandit.labs.overthewire.org -p 2220
   

   - *Password:* NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

2. *List the files:*

   bash
   ls
   

3. **Since the file is named -, use one of the following commands to read it:**

   bash
   cat ./-
   # or
   cat -- -
   

   - *Password for Bandit2:* rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

---

## Level 2 ➜ Level 3

*Goal:* The password for the next level is stored in a file called spaces in this filename located in the home directory.

*Commands you may need to solve this level:* ls, cat

### Solution:

1. *Log into Bandit2:*

   bash
   ssh bandit2@bandit.labs.overthewire.org -p 2220
   

   - *Password:* rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

2. *List the files:*

   bash
   ls
   

3. *Read the file with spaces in its name:*

   bash
   cat "spaces in this filename"
   # or
   cat spaces\ in\ this\ filename
   

   - *Password for Bandit3:* aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

---

## Level 3 ➜ Level 4

*Goal:* The password for the next level is stored in a hidden file in the inhere directory.

*Commands you may need to solve this level:* ls, cd, cat

### Solution:

1. *Log into Bandit3:*

   bash
   ssh bandit3@bandit.labs.overthewire.org -p 2220
   

   - *Password:* aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

2. **Navigate to the inhere directory:**

   bash
   cd inhere/
   

3. *List all files, including hidden ones:*

   bash
   ls -a
   

4. **Display the contents of the hidden file (.hidden):**

   bash
   cat .hidden
   

   - *Password for Bandit4:* 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

---

## Level 4 ➜ Level 5

*Goal:* The password for the next level is stored in the only human-readable file in the inhere directory.

*Commands you may need to solve this level:* ls, cd, file, cat

### Solution:

1. *Log into Bandit4:*

   bash
   ssh bandit4@bandit.labs.overthewire.org -p 2220
   

   - *Password:* 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

2. **Navigate to the inhere directory:**

   bash
   cd inhere/
   

3. *Identify the human-readable file:*

   bash
   file ./*
   

   - *Output:*
     
     ./-file00: data
     ./-file01: data
     ./-file02: data
     ./-file03: data
     ./-file04: data
     ./-file05: data
     ./-file06: data
     ./-file07: ASCII text
     ./-file08: data
     ./-file09: data
     

4. *Display the contents of the ASCII text file:*

   bash
   cat ./-file07
   

   - *Password for Bandit5:* lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

---

## Level 5 ➜ Level 6

*Goal:* The password for the next level is stored in a file somewhere under the inhere directory and has the following properties:

- Human-readable
- 1033 bytes in size
- Not executable

*Commands you may need to solve this level:* find, cat

### Solution:

1. *Log into Bandit5:*

   bash
   ssh bandit5@bandit.labs.overthewire.org -p 2220
   

   - *Password:* lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

2. **Use find to locate the file:**

   bash
   find ./inhere -type f -size 1033c ! -executable
   

   - *Output:*
     
     ./inhere/maybehere07/.file2
     

3. *Display the contents of the found file:*

   bash
   cat ./inhere/maybehere07/.file2
   

   - *Password for Bandit6:* P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

---

## Level 6 ➜ Level 7

*Goal:* The password for the next level is stored somewhere on the server and has the following properties:

- Owned by user bandit7
- Owned by group bandit6
- 33 bytes in size

*Commands you may need to solve this level:* find, cat

### Solution:

1. *Log into Bandit6:*

   bash
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   

   - *Password:* P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

2. *Search for the file with the specified properties:*

   bash
   find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
   

   - *Output:*
     
     /var/lib/dpkg/info/bandit7.password
     

3. *Display the contents of the found file:*

   bash
   cat /var/lib/dpkg/info/bandit7.password
   

   - *Password for Bandit7:* z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

---

## Level 7 ➜ Level 8

*Goal:* The password for the next level is stored in the file data.txt next to the word *millionth*.

*Commands you may need to solve this level:* grep

### Solution:

1. *Log into Bandit7:*

   bash
   ssh bandit7@bandit.labs.overthewire.org -p 2220
   

   - *Password:* z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

2. **Search for the word "millionth" in data.txt:**

   bash
   grep "millionth" data.txt
   

   - *Output:*
     
     millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV
     

   - *Password for Bandit8:* cvX2JJa4CFALtqS87jk27qwqGhBM9plV

---

## Level 8 ➜ Level 9

*Goal:* The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.

*Commands you may need to solve this level:* sort, uniq

### Solution:

1. *Log into Bandit8:*

   bash
   ssh bandit8@bandit.labs.overthewire.org -p 2220
   

   - *Password:* cvX2JJa4CFALtqS87jk27qwqGhBM9plV

2. *Find the unique line:*

   bash
   sort data.txt | uniq -u
   

   - *Output:*
     
     usvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
     

   - *Password for Bandit9:* usvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

---

## Level 9 ➜ Level 10

*Goal:* The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several = characters.

*Commands you may need to solve this level:* strings, grep

### Solution:

1. *Log into Bandit9:*

   bash
   ssh bandit9@bandit.labs.overthewire.org -p 2220
   

   - *Password:* usvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

2. *Extract human-readable strings and filter:*

   bash
   strings data.txt | grep "=="
   

   - *Output:*
     
     ========= The password is truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
     

   - *Password for Bandit10:* truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

---

## Level 10 ➜ Level 11

*Goal:* The password for the next level is stored in the file data.txt, which contains base64 encoded data.

*Commands you may need to solve this level:* base64

### Solution:

1. *Log into Bandit10:*

   bash
   ssh bandit10@bandit.labs.overthewire.org -p 2220
   

   - *Password:* truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

2. *Decode the base64 data:*

   bash
   base64 -d data.txt
   

   - *Output:*
     
     The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
     

   - *Password for Bandit11:* IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

---

## Level 11 ➜ Level 12

*Goal:* The password for the next level is stored in the file data.txt, where all letters have been rotated by 13 positions (ROT13).

*Commands you may need to solve this level:* tr

### Solution:

1. *Log into Bandit11:*

   bash
   ssh bandit11@bandit.labs.overthewire.org -p 2220
   

   - *Password:* IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

2. *Decode the ROT13 text:*

   bash
   cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
   

   - *Output:*
     
     The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
     

   - *Password for Bandit12:* 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

---

## Level 12 ➜ Level 13

*Goal:* The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed.

*Commands you may need to solve this level:* xxd, tar, gzip, bzip2, mv, file

### Solution:

1. *Log into Bandit12:*

   bash
   ssh bandit12@bandit.labs.overthewire.org -p 2220
   

   - *Password:* 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

2. *Recreate the binary from the hexdump:*

   bash
   xxd -r data.txt data.bin
   

3. *Identify the file type and decompress accordingly:*

   - *First Iteration:*

     bash
     file data.bin
     # Output: data.bin: gzip compressed data
     mv data.bin data.gz
     gzip -d data.gz
     

   - *Second Iteration:*

     bash
     file data
     # Output: data: bzip2 compressed data
     mv data data.bz2
     bzip2 -d data.bz2
     

   - *Third Iteration:*

     bash
     file data
     # Output: data: gzip compressed data
     mv data data.gz
     gzip -d data.gz
     

   - *Fourth Iteration:*

     bash
     file data
     # Output: data: tar archive
     tar -xf data
     

   - *Continue these steps, checking the file type each time and decompressing accordingly, until you extract the password file.*

4. *Eventually, you'll find a file containing the password:*

   bash
   cat data.txt
   

   - *Password for Bandit13:* 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

---

## Level 13 ➜ Level 14

*Goal:* The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. You have the private SSH key needed to log into bandit14.

*Commands you may need to solve this level:* ssh, cat

### Solution:

1. *Log into Bandit13:*

   bash
   ssh bandit13@bandit.labs.overthewire.org -p 2220
   

   - *Password:* 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

2. *Use the provided SSH key to log into Bandit14:*

   bash
   ssh -i sshkey.private bandit14@localhost -p 2220
   

3. *Display the password file:*

   bash
   cat /etc/bandit_pass/bandit14
   

   - *Password for Bandit14:* 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

---

## Level 14 ➜ Level 15

*Goal:* The password for the next level can be retrieved by submitting the password of the current level to port *30000* on localhost using SSL encryption.

*Commands you may need to solve this level:* openssl, s_client

### Solution:

1. *Log into Bandit14:*

   bash
   ssh bandit14@bandit.labs.overthewire.org -p 2220
   

   - *Password:* 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

2. **Connect to the server using openssl:**

   bash
   echo '4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e' | openssl s_client -connect localhost:30000 -quiet
   

3. *The server will respond with the password for Bandit15:*

   - *Password for Bandit15:* BfMYroe26WYalil77FoDi9qh59eK5xNr

---

## Level 15 ➜ Level 16

*Goal:* The password for the next level can be retrieved by submitting the password of the current level to port *30001* on localhost using SSL, but the server also requires the use of an appropriate client certificate.

*Commands you may need to solve this level:* openssl, s_client

### Solution:

1. *Log into Bandit15:*

   bash
   ssh bandit15@bandit.labs.overthewire.org -p 2220
   

   - *Password:* BfMYroe26WYalil77FoDi9qh59eK5xNr

2. **Connect using openssl, providing the certificate and key:**

   bash
   openssl s_client -connect localhost:30001 -quiet -key ~/sshkey.private -cert ~/sshkey.cert
   

   - **If the key and certificate are in a single file named client.pem:**

     bash
     openssl s_client -connect localhost:30001 -quiet -key client.pem -cert client.pem
     

3. *When connected, enter the password for Bandit15:*

   bash
   BfMYroe26WYalil77FoDi9qh59eK5xNr
   

4. *Receive and note the password for Bandit16:*

   - *Password for Bandit16:* cluFn7wTiGryunymYOu4RcffSxQluehd

---

## Level 16 ➜ Level 17

*Goal:* The password for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range *31000 to 32000*. First, find the correct port by scanning for listening services, then connect using SSL and provide the password.

*Commands you may need to solve this level:* nmap, openssl, s_client

### Solution:

1. *Log into Bandit16:*

   bash
   ssh bandit16@bandit.labs.overthewire.org -p 2220
   

   - *Password:* cluFn7wTiGryunymYOu4RcffSxQluehd

2. *Scan for open ports with SSL services:*

   bash
   nmap -sV -p31000-32000 localhost
   

   - *Output (Example):*
     
     PORT      STATE SERVICE  VERSION
     31518/tcp open  ssl/echo
     31790/tcp open  ssl/unknown
     

3. **Connect to the identified port (e.g., 31790):**

   bash
   openssl s_client -connect localhost:31790 -quiet
   

4. *Submit the password for Bandit16 when prompted:*

   bash
   cluFn7wTiGryunymYOu4RcffSxQluehd
   

5. *The server will provide a private SSH key.*

6. **Save the key to a file (e.g., bandit17_key):**

   bash
   vi bandit17_key
   # Paste the key
   chmod 600 bandit17_key
   

7. *Use the key to log into Bandit17:*

   bash
   ssh -i bandit17_key bandit17@bandit.labs.overthewire.org -p 2220
   

---

## Level 17 ➜ Level 18

*Goal:* There are two files in the home directory: passwords.old and passwords.new. The password for the next level is the only line that has been added between the two files.

*Commands you may need to solve this level:* diff, grep

### Solution:

1. *Log into Bandit17:*

   bash
   ssh bandit17@bandit.labs.overthewire.org -p 2220
   

   - *Password:* (Use the private key obtained in the previous level)

2. *Find the difference between the two files:*

   bash
   diff passwords.old passwords.new
   

   - *Output:*
     
     42c42
     < S0meOldPassword
     ---
     > hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
     

   - *Password for Bandit18:* hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

---

By following these steps and using the provided passwords, you should be able to progress through Bandit levels 1 to 18. Remember to carefully read each level's description and use the appropriate commands to solve the challenges. Always ensure you have the necessary permissions and that you're following ethical guidelines when practicing these skills.