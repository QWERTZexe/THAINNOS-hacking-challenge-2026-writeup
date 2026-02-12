# Running

*This challenge was removed due to the flag being set incorrectly on the CTF platform.*

We are given a linux binary `run`. It is built for aarch64, running it with an emulator: 

``qemu-aarch64 -L /usr/aarch64-linux-gnu -E AURA_FILE=/root/bb-1369.tmp ./run ``

Output:
```
AURA will always help me finish my work faster!
You are being traced.
```

After compiling a simple Ptrace Bypass and loading it:

ptrace_bypass.c
```c
#define _GNU_SOURCE
#include <stdarg.h>
#include <errno.h>

// ptrace is declared as: long ptrace(enum __ptrace_request request, ...);
// We avoid depending on the enum type and just accept a long.
long ptrace(long request, ...) {
    errno = 0;
    return 0; // pretend success
}
```

Also make sure the file bb-1369.tmp exists, has exactly 32 bytes and the env var AURA_FILE is set.

Output:
```
AURA will always help me finish my work faster!
You are being traced.
Hurry!
```

Now you got 60 seconds to connect with nc to localhost:54321

You will get the flag as output

## Additional Notes
- There is a fake decoy flag being set in the env var "FLAG", saying that you have been "bamboozeld"