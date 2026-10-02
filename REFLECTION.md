# Structured Reflection - IE3090 RemoteOps

## AI Tools Used
I used Claude (DeepSeek) as a coding assistant throughout this assignment. AI was primarily used for explaining BSD socket API functions, providing boilerplate code, debugging compilation errors, and suggesting design patterns for concurrency.

## What AI Did Well
- Generated correct socket programming boilerplate quickly
- Explained complex concepts like sysinfo() and pthreads clearly
- Helped identify and fix compiler warnings (buffer overflow, unused parameters)
- Provided working file transfer code with proper byte counting
- Suggested thread-safe patterns for shared state

## Where AI Got Things Wrong
- Initially suggested BUFFER_SIZE for all buffers, causing overflow warnings
- Used wrong Makefile capitalization (makefile vs Makefile)
- Did not account for function prototype ordering in C
- Some code had unused parameters causing -Wextra warnings

## What I Changed, Added, or Rejected
- Changed: Buffer sizes to BUFFER_SIZE / 2 where needed
- Added: (void)arg; to suppress unused parameter warnings
- Rejected: Some AI suggestions for overly complex error handling
- Modified: All code to match the exact protocol specification
- Personalised: All values (port, SID, token, paths) to my registration number

## What I Learned
Through this assignment, I learned:
1. Socket programming - How TCP/IP client-server communication works at the socket level
2. Protocol implementation - Following a strict specification for message formats
3. Concurrency - Using threads to handle multiple clients simultaneously
4. File transfer - Handling binary data with exact byte counting
5. UDP vs TCP - Difference between connectionless UDP and connection-oriented TCP
6. Debugging - Reading compiler warnings and fixing memory issues
7. Importance of understanding code - Not just copy-pasting AI output

The assignment taught me that AI is a powerful tool but requires critical evaluation. I now understand my own code well enough to explain it in the Viva and modify it in the Lab Assessment.
