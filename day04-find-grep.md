# Day 4 — find & grep — Searching Like a Pro

# find — searches for FILES by their properties

find . -name "*.txt"         — find by name in current folder
find / -name file 2>/dev/null — search whole system, hide errors
find . -type f               — files only
find . -type d               — directories only
find . -size +1M             — larger than 1MB
find . -mtime -7             — modified last 7 days
find . -mtime 0              — modified today

# find with -exec — run a command on every result

find . -name "*.log" -exec rm {} \;
→ finds all .log files and deletes each one
→ {} gets replaced by each filename found
→ \; marks the end of the exec command

# 2>/dev/null — hide error messages

find / -name "*.txt" 2>/dev/null
→ /dev/null is Linux trash bin
→ 2 means error output
→ throws away permission denied messages

## grep new flags today

grep -r "word" .              — search recursively through all files
grep -E "error|warning" file  — match error OR warning
grep -c "word" file           — count how many lines match

# Three ways to search inside files

# Way 1 — simplest
grep -r "Security" . --include="*.txt" -l

# Way 2 — find with exec
find . -name "*.txt" -exec grep -l "Security" {} \;

# Way 3 — find with xargs
find . -name "*.txt" | xargs grep -l "Security"

## difference between find and grep

find  — searches for FILES by name, size, date, type
grep  — searches INSIDE files for words or patterns

## What I figured out on my own

- Used grep -r naturally instead of find+exec
- Understood that find | grep searches filenames not content
- Learned all 3 ways to combine find and grep

# Exercises I completed today

- Created 10 files with Linux, Cloud, Security content
- Found 62 .txt files across entire home directory
- Found files modified today with mtime 0
- Searched /var/log for real system errors
- Used grep -c to count matches in files

## Confidence question answer

[1.Find searches for the file itself when we dont know about the folder and grep searches inside the file.
i would use find when i dontknow the folder and i am searching for the file and grep when i am searching for specific word r topic inside a file.
2.find / -size +5M.
3.grep -riE "ERROR|FAILED"  --include="*.txt"  .
4. It ignores all the permission error and throws it in the dustbin. ]

## What felt easy
For today if I am honest nothinf felts easy.

## What felt confusing
Grep and Find were really confusing i spent two days on the day 4 learning.

But wrote this day challenge by my self after alot of practice and solving more than 50 questions:
find /var/log -type f -mtime -1  2>/dev/null| xargs grep -E "fail|error" -ln > incidents_report.txt