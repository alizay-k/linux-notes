# Day 7 — Logs & System Monitoring

## Important Log Files

/var/log/syslog           — general system messages
/var/log/auth.log         — login attempts and sudo activity
/var/log/kern.log         — kernel messages
/var/log/dmesg            — boot and hardware messages

## Viewing Logs

tail -f /var/log/syslog              — watch log live in real time
sudo grep "Failed" /var/log/auth.log — find failed login attempts
journalctl -f                        — systemd journal live feed
journalctl -u ssh                    — logs for SSH service only

## Disk Space

df -h                     — show all filesystems and space used
du -sh *                  — show size of everything in current folder
du -sh /* 2>/dev/null | sort -rh | head -10  — top 10 largest dirs

## RAM Usage

free -m                   — RAM in megabytes
free -h                   — RAM in human readable format

## System Info

uptime                    — how long system running + load averages
uname -a                  — kernel and system info
lscpu                     — CPU details
lsblk                     — block devices (disks)

## One Line System Report

{ echo "=DISK="; df -h; echo "=RAM="; free -m; echo "=UPTIME="; uptime; } | tee system_report.txt

## Load Averages Explained

uptime shows: load average: 0.5, 0.3, 0.1
              1 min  5 min  15 min
Under 1.0 = healthy
Over number of CPU cores = system under stress

## Real Sysadmin Workflow

1. Server is slow → check uptime (load average)
2. Load is high → check top (which process)
3. Disk full error → check df -h (which filesystem)
4. Login issues → check /var/log/auth.log (who tried)
5. Service crashed → check journalctl -u servicename

## What I Did Today

- Monitored syslog live with tail -f
- Found failed login attempts in auth.log
- Checked disk space with df -h
- Found largest directories with du
- Checked RAM with free -m
- Wrote one-line system report saved to file

## Confidence Question Answers

1. /var/log/auth.log — failed login attempts
2. df -h — disk space
3. free -m — RAM usage
4. tail -f /var/log/syslog — watch log file live

## What felt easy
Everything was easy.

## What felt confusing
Nothing