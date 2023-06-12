# Basic Linux commands 

`cd` change directory </br>
`cd ..` change directory, go back up tree  </br>
`pwd` print working directory  </br>
`grep` search  </br>
 `ls` list  </br>
`ls -la` list all  </br>
`cat` #concatenate command, reads data from the file and gives output  </br>
`su [username]` login as user </br>

### Extract files
`tar -zxvf filename` extract file to currect directory  </br>
`tar -jxvf filename` extract bzip file to currect directory  </br>
`bunzip2 backup.bz2` extract bzip `.bz2` file type  </br>
`cpio -idv --no-absolute-filename < [filename]` cpio archive extract </br> 

### MySQL 
`mysql -u root` access mysql
`mysql -u root -p` access mysql with password

#### Queries 
`show databases;` show available databases</br>
`use [DATABASE];` </br>
`show tables;` </br>
`select * from [TABLE];` Select * from table </br>

 the `show` and `use` command will not work in SQL injections, they are internal command that are not part of SQL </br>

### Encoding / Decoding 
`openssl enc -aes256 -k [KEY] -in /tmp/backup.tgz  -out /tmp/backup.tgz.enc` encode with passcode </br>
`openssl enc -d -aes256 -k [KEY] -in /tmp/backup.tgz.enc -out /tmp/backup.tgz` decode, (remember need to decompress tgz file!) </br> 
`john [FILE] --format=descrypt` john the ripper, where [FILE] is the filename you picked.

```victim:yX.TlL2TaIM3Y:19520:0:99999:7:::``` </br>
Here the algorithm used is DES (you can tell by the size and format of it).  </br>
This is common on very old systems and it's very weak (especially since only the first 8 bytes of the password are kept).  </br>

```victim:$1$x83NbBxt$E7AQumyC9qhT3TaIUe1Bx1:19520:0:99999:7:::```</br>
This time MD5 is used. It can be detected by the prefix of the password: `$1$`. </br>
Use `john [FILE] --format=md5crypt`

If you look at other files, you can tell that: </br>

if the hash starts by `$2$` or `$2a$`, Blowfish is used; </br>
if the hash starts by `$5$`, SHA-256 is used;</br>
if the hash starts by `$6$`, SHA-512 is used.</br>

### Specific Bash commands 
How many requests yielded a 200 status?
cat access.log | cut -d '"' -f3 | cut -d ' ' -f2 | sort | uniq -c | sort -rn 
