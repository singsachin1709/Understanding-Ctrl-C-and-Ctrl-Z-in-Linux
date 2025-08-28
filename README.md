# Understanding-Ctrl-C-and-Ctrl-Z-in-Linux
# 1️⃣ Ctrl+C → SIGINT (Interrupt Signal)
- Behind the scenes, pressing Ctrl+C sends the SIGINT (Signal Interrupt) signal to the foreground process.
- This asks the process to terminate gracefully.
  
👉 Equivalent command:
```
kill -SIGINT <pid>
```
or simply:
```
kill -2 <pid>
```
# 2️⃣ Ctrl+Z → SIGTSTP (Stop Signal)
- Pressing Ctrl+Z sends the SIGTSTP (Signal Terminal Stop) signal.
- This pauses (suspends) the process and pushes it into the background.
- You can then resume it with:
```
fg   # bring process back to foreground
bg   # continue process in background
```
👉 Equivalent command:
```
kill -SIGTSTP <pid>
```
or:
```
kill -20 <pid>
```
# 3️⃣ Process Control in Action
```
sleep 1000    # run a long process
# Press Ctrl+Z  → process stops
bg            # resume in background
jobs          # see background jobs
kill -SIGINT <pid>  # simulate Ctrl+C
```
