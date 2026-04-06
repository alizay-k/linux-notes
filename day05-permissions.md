# Day 5 — File Permissions

## Reading the Permission String

-rwxrwxrwx
│  │   │   │
│  │   │   └── others (everyone else)
│  │   └── group
│  └── owner
└── type (- file, d directory)

r = read = 4
w = write = 2
x = execute = 1
- = no permission = 0

## The Numbers

rwx = 4+2+1 = 7
rw- = 4+2+0 = 6
r-x = 4+0+1 = 5
r-- = 4+0+0 = 4
--- = 0+0+0 = 0

## Permissions Cheatsheet

| Number | Symbolic  | When to use                        |
|--------|-----------|------------------------------------|
| 600    | rw------- | SSH private keys, password files   |
| 644    | rw-r--r-- | Normal files, config files         |
| 700    | rwx------ | Private scripts only you run       |
| 755    | rwxr-xr-x | Scripts and directories on servers |
| 777    | rwxrwxrwx | NEVER — dangerous security risk    |

## chmod Commands

chmod 644 file.txt       — set numeric permissions
chmod 755 script.sh      — set script permissions
chmod 600 private.txt    — make private
chmod +x script.sh       — add execute for everyone
chmod u+x script.sh      — add execute for owner only
chmod 750 script.sh      — owner+group yes, others no
chmod o-r file.txt       — remove read from others

## chmod Symbols

u = owner
g = group
o = others
a = all
+ = add
- = remove
= = set exactly

## chown — Change Ownership

chown alizay file.txt              — change owner
chown alizay:developers file.txt   — change owner and group
chown -R alizay folder/            — change everything inside folder

## Security Commands

whoami                          — show your username
id                              — show username, UID, all groups
find / -perm -4000 2>/dev/null  — find all SUID files (security audit)
find / -perm -002 2>/dev/null   — find world-writable files (dangerous)

## What is SUID

SUID is a special permission that makes a file run as its OWNER
instead of the person running it.

Example: passwd command is owned by root and has SUID.
When you run passwd — it temporarily gets root power to
write to /etc/shadow then gives it back.

Security risk: attackers exploit SUID files to become root.
That is why we audit them regularly.

## SUID Files on My System (all normal)

/usr/bin/passwd
/usr/bin/sudo
/usr/bin/su
/usr/bin/mount
/usr/bin/chsh
/usr/bin/gpasswd
/usr/bin/newgrp

## What I learned Today

- chmod 000 locks everyone out including owner
  (but owner can always run chmod to fix it)
- chmod +x adds execute for everyone
- chmod u+x adds execute for owner only
- Single quotes needed for shebang: echo '#!/bin/bash'
- sed -i '1d' deletes line 1 of a file
- sed -i '1i text' inserts text at line 1
- Every bash script must start with #!/bin/bash
.
## Confidence Question Answers

[1.-rw-r--r-- it means owner can read write but not execute. group and others can only read.
 2.644 for a private file is security risk because others and group can read it which we do not want.it should be 600.
 3.644 mean only owner can read and write not execute and for group and other they can only read so for this file it need to have 755 permission.
 4.In 755 owner can read,write,execute and in 700 only owner can read,write ,execute and others and group cannot do anything.  ]

## What felt easy
Everything felt so easy in day 5 unlike day 4

## What felt confusing
Nothing.