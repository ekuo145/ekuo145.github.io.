---
layout: post
title: Bandit Solutions!
---
*This is documentation for completing all bandit levels*  
Note: The level names come from the first part of the level name, for example, 0-1 would be level 0.  
***Level 0***  
ssh bandit0@bandit.labs.overthewire.org -p 2220  
cat readme  
exit  
***Level 1***  
ssh bandit1@bandit.labs.overthewire.org -p 2220  
cat <-  
exit  
***Level 2***  
ssh bandit2@bandit.labs.overthewire.org -p 2220  
cat "spaces in this filename"  
exit  
***Level 3***  
ssh bandit3@bandit.labs.overthewire.org -p 2220  
cd inhere  
find  
cat ./...Hiding-From-You  
exit  
***Level 4***  
ssh bandit4@bandit.labs.overthewire.org -p 2220  
cd inhere  
ls -ah  
cat <-file07  
exit  
***Level 5***  
ssh bandit5@bandit.labs.overthewire.org -p 2220  
cd inhere  
du  
cd .  
du -ab  
cat ./maybehere07/.file2  
exit  
***Level 6***  
ssh bandit6@bandit.labs.overthewire.org -p 2220  
find / -user bandit7 -group bandit6 -size 33c  
cat /var/lib/dpkg/info/bandit7.password  
exit  
***Level 7***  
ssh bandit7@bandit.labs.overthewire.org -p 2220  
ls -ah  
less data.txt  
*used /millionth to search for the entry*  
exit  
***Level 8***  
ssh bandit8@bandit.labs.overthewire.org -p 2220  
ls -ah  
sort data.txt | uniq -u  
exit  
***Level 9***  
ssh bandit9@bandit.labs.overthewire.org -p 2220  
ls -ah  
strings data.txt  
*Tested all of the possible options (only one seemed to fit the password pattern but was worth testing either way)*  
exit  
***Level 10***  
ssh bandit10@bandit.labs.overthewire.org -p 2220  
ls -ah  
man base64  
base64 -d data.txt  
exit  
***Level 11***  
ssh bandit11@bandit.labs.overthewire.org -p 2220  
ls -ah  
cat data.txt  
echo Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4 | tr 'A-Za-z' 'N-ZA-Mn-za-m'  
exit  
***Level 12***  
*Quick note: for this level, because there were so many commands, I left the inputs and outputs as they come in the terminal*  
ssh bandit12@bandit.labs.overthewire.org -p 2220  
bandit12@bandit:~ ls -a  
.  ..  .bash_logout  .bashrc  data.txt  .profile  
bandit12@bandit:~ mktemp -d  
/tmp/tmp.puZi0T4HOb  
bandit12@bandit:~ cp data.txt /tmp/tmp.puZi0T4HOb  
bandit12@bandit:~ cd /tmp/tmp.puZi0T4HOb  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ ls -ah  
.  ..  data.txt  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file data.txt  
data.txt: ASCII text  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ xxd -r data.txt > binary.txt  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file binary.txt  
binary.txt: gzip compressed data, was "data2.bin", last modified: Thu Sep 19 07:08:15 2024, max compression, from Unix, original size modulo 2^32 574  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ mv binary.txt binary.gz  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ gzip -d binary.gz  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ ls   
binary  data.txt  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file binary  
binary: bzip2 compressed data, block size = 900k  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ mv binary binary.bz2  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ bzip2 -d binary.bz2  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file binary  
binary: gzip compressed data, was "data4.bin", last modified: Thu Sep 19 07:08:15 2024, max compression, from Unix, original size modulo 2^32 20480  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ mv binary binary.gz  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ gzip -d binary.gz  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file binary  
binary: POSIX tar archive (GNU)  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ mv binary binary.tar  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ tar -xvf binary.tar  
data5.bin  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file data5.bin  
data5.bin: POSIX tar archive (GNU)  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ mv data5.bin data5.tar  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ tar -xvf data5.tar  
data6.bin  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file data6.bin  
data6.bin: bzip2 compressed data, block size = 900k  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ mv data6.bin data6.bz2  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ bzip2 -d data6.bz2  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file data6  
data6: POSIX tar archive (GNU)  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ mv data6 data6.tar  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ tar -xvf data6.tar  
data8.bin  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file data8.bin  
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Sep 19 07:08:15 2024, max compression, from Unix, original size modulo 2^32 49  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ mv data8.bin data8.gz  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ gzip -d data8.gz  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ file data8  
data8: ASCII text  
bandit12@bandit:/tmp/tmp.puZi0T4HOb$ cat data8  
exit  
***Level 13***  
ssh bandit13@bandit.labs.overthewire.org -p 2220  
ls  
ssh -i sshkey.private bandit14@localhost -p 2220  
cd /etc/bandit_pass  
cat bandit14  
***Level 14***  
telnet localhost 30000  
*enter password here*  
exit  
exit  
***Level 15***  
ssh bandit15@bandit.labs.overthewire.org -p 2220  
openssl s_client -connect localhost:30001  
*enter password here*  
exit  
***Level 16***  
ssh bandit16@bandit.labs.overthewire.org -p 2220  
nmap  
nmap -p 31000-32000 localhost  
openssl s_client -connect localhost:31790   
*Took a ton of errors before I realized I had to add the -quiet flag (DO NOT RUN ABOVE COMMAND AS IT DOESN"T WORK, JUST BROUGHT IT UP BECAUSE IT WAS A TOUGH ERROR FOR ME TO SOLVE)*  
openssl s_client -quiet -connect localhost:31790    
*enter password*  
touch /tmp/sshkey17.private  
nano /tmp/sshkey17.private  
*COPY THE PRIVATE KEY HERE + control o and control x to save and exit, need to change permissions like below or it will deny you from entering*
chmod 700 /tmp/sshkey17.private  
ls -l /tmp/sshkey17.private  
ssh -i /tmp/sshkey17.private bandit17@localhost -p 2220  
***Level 17***  
diff passwords.old passwords.new  
*We want the one with the > in front of it, paste it into level 18 and if you get bye bye, move on from there*  
***Level 18***  
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme  
***Level 19***  
ssh bandit19@bandit.labs.overthewire.org -p 2220  
ls -ah  
./bandit20-do  
./bandit20-do whoami  
./bandit20-do cat /etc/bandit_pass/bandit20  
exit  
***Level 20***   
ssh bandit20@bandit.labs.overthewire.org -p 2220  
ls -ah  
echo "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -l localhost 12345 &  
./suconnect 12345  
***Level 21***  
ssh bandit21@bandit.labs.overthewire.org -p 2220  
cd /etc/cron.d/  
ls  
cat cronjob_bandit22  
cat /usr/bin/cronjob_bandit22.sh  
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv  
exit    
***Level 22***  
ssh bandit22@bandit.labs.overthewire.org -p 2220  
cd /etc/cron.d  
ls  
cat /usr/bin/cronjob_bandit23.sh  
/usr/bin/cronjob_bandit23.sh  
cat /tmp/8169b67bd894ddbb4412f91573b38db3  
*Realized above folder was wrong*  
echo I am user bandit23 | md5sum | cut -d ' ' -f 1  
cat /tmp/8ca319486bfbbc3663ea0fbe81326349  
exit  
***Level 23***  
ssh bandit23@bandit.labs.overthewire.org -p 2220  
cat /etc/cron.d/cronjob_bandit24  
cat /usr/bin/cronjob_bandit24.sh  
mkdir -p /tmp/123456  
cd /tmp/123456  
touch script.sh  
nano script.sh  
*Below is the script I used*  
#!/bin/bash  
cat /etc/bandit_pass/bandit24 > /tmp/1234567890/password  
*exit the script*  
touch password  
chmod 777 -R /tmp/123456  
cp script.sh /var/spool/bandit24/foo  
cat password  
exit  
#Level 24  
ssh bandit24@bandit.labs.overthewire.org -p 2220  
mkdir -p /tmp/123456  
cd /tmp/123456  
touch script.sh  
nano script.sh  
*Below is the script I used*  
#!/bin/bash  
pass=UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ  
for i in {0000..9999}  
do  
	echo $i >> out.txt  
	echo $pass $i | nc localhost 30002 >> out.txt &  
	pid=$!  
	sleep 1  
	kill $pid  
	echo "" >> out.txt  
done   
*Script done*  
touch out.txt  
./script.sh  
less out.txt  
#Ran Overnight, was taking a long time to finish  
#Level 25  
ssh bandit25@bandit.labs.overthewire.org -p 2220  
ssh -i bandit26.sshkey bandit26@localhost -p 2220 *Doesn't work right yet*   
cat /etc/passwd | grep bandit26  
cat /usr/bin/showtext  
*Make window super small*  
ssh -i bandit26.sshkey bandit26@localhost -p 2220  
*press v to open vim*  
:e /etc/bandit_pass/bandit26  
:set shell=/bin/bash  
:shell  
***Level 26***  
ls  
./bandit27-do  
./bandit27-do whoami  
./bandit27-do cat /etc/bandit_pass/bandit27  
exit  
***Level 27***  
ssh bandit27@bandit.labs.overthewire.org -p 2220  
mktemp -d  
cd /tmp/tmp.9hSckLflKM  
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo  
cd repo  
ls  
cat README  
exit  
***Level 28***  
ssh bandit28@bandit.labs.overthewire.org -p 2220  
mktemp -d  
cd /tmp/tmp.7f1Ts0Xb9j  
git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo  
cd repo  
ls  
cat README.md  
git log  
git checkout 3621de   
*Note: this doesn't need full commit name, just first 6 digits*  
cat README.md  
exit  
***Level 29***  
ssh bandit29@bandit.labs.overthewire.org -p 2220  
mktemp -d  
cd /tmp/tmp.D9MqQMiuLi  
git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo  
cd repo  
ls  
cat README.md  
git log  
git branch -a  
git checkout remotes/origin/dev  
ls  
cat README.md  
exit  
***Level 30***  
ssh bandit30@bandit.labs.overthewire.org -p 2220  
mktemp -d  
cd /tmp/tmp.4pwmlbKRRO  
git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo  
cd repo  
ls  
cat README.md  
git log  
git branch -a  
git tag  
git show secret  
exit  
***Level 31***  
ssh bandit31@bandit.labs.overthewire.org -p 2220  
mktemp -d  
cd /tmp/tmp.Xm3GJTqL6J  
git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo  
cd repo  
ls  
cat README.md  
echo "May I come in?" > key.txt  
ls -ah  
cat .gitignore  
rm .gitignore  
ls -ah  
git add .  
git commit -m "Added key.txt"  
git push origin master  
exit  
***Level 32***
ssh bandit32@bandit.labs.overthewire.org -p 2220  
$0  
ls -lah  
whoami  
cat /etc/bandit_pass/bandit33  
***THE END***
***Level 33***
*At this moment, level 33->34 does not exist yet.*
