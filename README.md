# IE3090-RemoteOps
RemoteOps - Remote System Monitoring Tool (IT24102595)
# RemoteOps - Remote System Monitoring Tool

**Student:** IT24102595
**Module:** IE3090 - Network Programming (Year 3, Semester 1)

## Personalised Values
- **Agent Port:** 9410
- **SID:** 5952
- **Auth Token:** OPS-2595
- **Log File:** remoteops_IT24102595.log
- **Storage Path:** ./agentfiles/IT24102595/

## Build
make -f Makefile_595

## Run
Terminal 1 (Agent): ./agent_595
Terminal 2 (Controller): ./controller_595

## Features
- AUTH - Token-based authentication (OPS-2595)
- SYSINFO - CPU load, memory usage, uptime
- LISTPROC - Running processes snapshot
- EXEC - Whitelisted commands (DATE, UPTIME, DISKFREE, HOSTNAME, WHOAMI)
- PUT/GET - File upload/download with byte-for-byte integrity
- Threads - Multiple simultaneous Controller connections
- UDP Monitoring - MONITOR START/STOP with periodic system stats
- Logging - All events logged with timestamps

## Architecture
- Agent (Server): TCP listener on port 9410, spawns thread per client
- Controller (Client): TCP client + UDP listener for monitoring
- Protocol: Line-based text over TCP, raw bytes for file transfer

## Concurrency Model
Thread-per-client using POSIX threads (pthreads). Each new connection spawns a detached thread that handles the full session independently.

## Author
IT24102595 - SLIIT

