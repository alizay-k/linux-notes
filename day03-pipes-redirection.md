# Day 3 — Pipes, Redirection & Filters

# Commands I learned today

cat file — shows entire file
cat -n file — shows file with line numbers

less file — scroll through large files
controls: Space=next page, q=quit, /word=search

head -3 file — first 3 lines
tail -2 file — last 2 lines
tail -f file — watch file live in real time

wc -l file — count lines
wc -w file — count words
wc -c file — count characters

sort file — sort alphabetically
sort -n — sort numbers
sort -r — reverse order
sort -u — sort and remove duplicates

uniq — removes duplicate adjacent lines
always sort first before uniq

tee — shows on screen AND saves to file
example: ls | tee output.txt

grep "word" file — filter lines containing word
grep -i — case insensitive
grep -n — show line numbers
grep -v — show lines NOT matching
grep -c — count matches

## Redirection

(>) overwrites file
(>>) appends to file

## Pipes

| sends output of one command into next command

## Pipelines I built today

ls /etc | grep "conf" | sort | wc -l > conf_count.txt
cat servers.txt | sort | uniq | grep -v "backup" | wc -l > final_count.txt

## Confidence question answer

[1.The difference between > ,>> is > used for over writing and >> for appending at the end of the file.
(>) this can destroy the work because it erases the earlier content and write new one to the file.
2.cat file.txt | sort | uniq | wc -l this pipeline take the content from file.txt sort it
alphabetically take only the unique lines and then count those unique lines.
3.I will use tail -f web.log because it will print the line as they are writen to the file and show it on screen.
4.tee shows the work on screen that is being done at the same time.]

## What felt easy
The pipes topic felts easy because it done so many thing in one command

## What felt confusing
In tdays learning nothing felt confusing.

## Extra things I figured out on my own

- Used cat servers.txt | grep "web" naturally without being told
- Used a for loop for step 9 on my own
- Wrote the final pipeline completely from memory
