# Design Diary - IE3090 RemoteOps

## Day 1: Socket Programming Basics
- Learned TCP socket programming in C
- Created hello_server.c and hello_client.c for practice
- Understood bind, listen, accept, connect flow
- Chose thread-per-client concurrency model over fork/select

## Day 2: Personalisation & AUTH
- Calculated personalised values (port 9410, SID 5952, token OPS-2595)
- Implemented AUTH command with token validation
- Created Makefile for compilation
- Learned about function prototypes in C

## Day 3: System Commands
- Added SYSINFO using sysinfo() syscall
- Added LISTPROC using popen() with ps command
- Fixed memory buffer warnings (BUFFER_SIZE / 2)
- Learned sizeof() best practice for memset()

## Day 4: EXEC & File Transfer
- Implemented whitelisted EXEC commands (DATE, UPTIME, DISKFREE, HOSTNAME, WHOAMI)
- Added PUT/GET with binary file handling
- Solved byte-counting issues in file transfer
- Used exact filesize parameter for byte-for-byte integrity

## Day 5: Concurrency & UDP
- Added pthreads for multiple clients
- Implemented UDP monitoring thread with mutex
- Added MONITOR START/STOP commands
- Learned thread synchronization with pthread_mutex

## Day 6: Logging
- Added log_event() function with timestamps
- Logged all connections, commands, transfers
- Tested full system integration
- Verified log file format

## Challenges Faced
1. Makefile case sensitivity - Makefile vs makefile caused "No targets" error
2. SSH connection drops - Resolved by restarting agent
3. Buffer overflow warnings - Fixed with sizeof() and BUFFER_SIZE / 2
4. Function prototype ordering - handle_client had to be declared before client_thread
5. Port already in use - Old agent process needed pkill before restart

## Key Decisions
- Threads over fork: Lighter weight, easier synchronization
- Mutex for monitoring: Prevent race conditions on monitoring_active flag
- malloc for client_fd: Avoid stack overwrite in accept loop
- Exact byte-count loop: Handle partial read()/send() calls correctly
- Append mode logging: fopen("a") preserves log history
