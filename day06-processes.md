# Day 6 — Processes & Job Control

## What is a Process
A process is a running program. Every process has a unique PID (Process ID).

## Key Commands

ps aux                    — show ALL running processes
top                       — real-time process monitor (q to quit)
htop                      — better version of top (sudo apt install htop)

## Background Jobs

command &                 — run command in background
jobs                      — list all background jobs
fg %1                     — bring job 1 to foreground
bg %1                     — resume job 1 in background
Ctrl+C                    — kill foreground process
Ctrl+Z                    — suspend foreground process

## Killing Processes

kill PID                  — send SIGTERM (polite request to stop)
kill -9 PID               — send SIGKILL (force kill immediately)
killall processname        — kill all processes with that name
pkill processname          — kill process by name (most flexible)

## Difference Between kill and kill -9

kill     → sends polite message asking process to stop gracefully
           process can finish cleanup before stopping
kill -9  → forces immediate termination
           no cleanup, use only when kill does not work

## Special Variables

$!   — PID of last background job
$?   — exit code of last command (0 = success)

## Practical Examples

sleep 300 &               — run sleep in background
jobs                      — see it listed
fg %1                     — bring it forward
Ctrl+Z                    — suspend it
bg %1                     — resume in background
pkill sleep               — kill it by name

## What I Did Today

- Ran 5 background sleep jobs
- Managed them with jobs, fg, bg
- Killed processes by PID and by name
- Used top to find highest CPU processes

## Confidence Question Answers

1. ps aux — shows all running processes
2. command & — runs in background
3. pkill processname — kill by name
4. kill sends polite SIGTERM, kill -9 forces immediate SIGKILL

## What felt easy
Everything felt easy 

## What felt confusing
Nothing.