# AI Prompt Log - IE3090 RemoteOps

## Interaction 1: Socket Programming Basics
- Tool: Claude (DeepSeek)
- Prompt: "How to create a TCP server in C using BSD sockets"
- Output Used: Basic socket(), bind(), listen(), accept() structure
- Changes Made: Modified to use personalised port 9410

## Interaction 2: SYSINFO Implementation
- Tool: Claude (DeepSeek)
- Prompt: "How to get CPU load and memory usage in C on Linux"
- Output Used: sysinfo() syscall with loads[], totalram, freeram
- Changes Made: Formatted output to match protocol spec exactly

## Interaction 3: File Transfer (PUT/GET)
- Tool: Claude (DeepSeek)
- Prompt: "How to transfer binary files over TCP socket in C"
- Output Used: Loop with read()/write() to handle partial reads
- Changes Made: Added exact byte counting with filesize parameter

## Interaction 4: Threads for Multiple Clients
- Tool: Claude (DeepSeek)
- Prompt: "How to handle multiple clients with pthreads in C"
- Output Used: pthread_create + pthread_detach pattern
- Changes Made: Added malloc for client_fd to avoid stack overwrite

## Interaction 5: UDP Monitoring
- Tool: Claude (DeepSeek)
- Prompt: "How to send periodic UDP datagrams in C"
- Output Used: Separate thread with sendto() and sleep(2)
- Changes Made: Added mutex for thread-safe monitoring_active flag

## Interaction 6: Logging
- Tool: Claude (DeepSeek)
- Prompt: "How to log with timestamps in C"
- Output Used: time() + strftime() + fprintf() with va_list
- Changes Made: Added specific log format for each event type

## Interaction 7: Debugging Compiler Warnings
- Tool: Claude (DeepSeek)
- Prompt: "How to fix -Wformat-truncation warning in gcc"
- Output Used: Suggested reducing buffer size to BUFFER_SIZE / 2
- Changes Made: Applied to proc_list and output buffers

## Interaction 8: Function Prototype Error
- Tool: Claude (DeepSeek)
- Prompt: "implicit declaration of function error in C"
- Output Used: Add function prototype before usage
- Changes Made: Added void handle_client(int client_fd); before client_thread

## Notes
All AI-generated code was critically evaluated, tested, and modified to fit the specific protocol requirements.
