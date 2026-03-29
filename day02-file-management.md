# Day 2 — File Management

# Commands I learned today

mkdir foldername — creates a folder
mkdir -p a/b/c — creates nested folders in one command

touch filename — creates empty file
Example I tried: touch log1.txt

cp source destination — copies a file
cp -r folder/ destination/ — copies entire folder
Example I tried:

mv oldname newname — moves OR renames
Example I tried:

rm filename — deletes forever, no trash bin
rm -r folder/ — deletes entire folder
Safety rule: always run ls *.txt BEFORE rm *.txt

rmdir folder — only works on empty folders

# Wildcards

* matches anything — example: rm *.txt deletes all txt files
? matches exactly one character

## My folder structure today

(cloud-journey/
├── data
│   ├── archive6.txt
│   ├── file1.txt
│   ├── file2.txt
│   ├── file3.txt
│   ├── file4.txt
│   ├── file5.txt
│   ├── log11.txt
│   ├── log13.txt
│   ├── log15.txt
│   ├── log17.txt
│   ├── log19.txt
│   ├── log7.txt
│   └── log9.txt
├── file1.txt
├── file2.txt
├── file3.txt
├── file4.txt
├── file5.txt
├── projects
│   └── src
│       └── utils
│           └── helpers
└── scripts
    ├── file1.sh
    ├── file2.sh
    ├── file3.sh
    ├── file4.sh
    ├── file5.sh
    ├── log1.txt
    ├── log2.txt
    ├── log3.txt
    ├── log4.txt
    └── log5.txt

7 directories, 28 files)

## Confidence question answer

(The exact one comman would be cp /home/user/reports.txt /home/user/backup/report_backup.txt
the diffrence between rm and rmdir is rm deletes instantly but rmdir check if the directory is empty only than it will be deleted
if i run rm *.log it will delete all the files having log extension * it works as all the files having log extension
mkdir -p is useful for creating parental directories)

## What felt easy
cp commands felt so easy 

## What felt confusing
At the beginning the moving commands felt confusing it takes a little time