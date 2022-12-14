# Layout
Basic layout of the UI should be

| arch | syscall | callreg | arg0 | arg1 | arg2 | arg3 | arg4 | arg5 |
|------|---------|---------|------|------|------|------|------|------|
| arch | syscall | callreg |  --  |  --  |  --  |  --  |  --  |  --  |
| arch | syscall | callreg |  --  |  --  |  --  |  --  |  --  |  --  |
| arch | syscall | callreg |  --  |  --  |  --  |  --  |  --  |  --  |
| arch | syscall | callreg |  --  |  --  |  --  |  --  |  --  |  --  |
| arch | syscall | callreg |  --  |  --  |  --  |  --  |  --  |  --  |

## Example 1 (Search 'read')
| arch  | syscall | callreg | arg0             | arg1      | arg2         | arg3 | arg4 | arg5 |
|-------|---------|---------|------------------|-----------|--------------|------|------|------|
| x86   | read    | 3       |  unsigned int fd | char *buf | size_t count |  --  |  --  |  --  |
| x64   | read    | 0       |  unsigned int fd | char *buf | size_t count |  --  |  --  |  --  |
| arm64 | read    | 3f      |  unsigned int fd | char *buf | size_t count |  --  |  --  |  --  |
| arm   | read    | 3       |  unsigned int fd | char *buf | size_t count |  --  |  --  |  --  |

## Example 2 (Search 'read' with arch filter)
| arch  | syscall | callreg | arg0             | arg1      | arg2         | arg3 | arg4 | arg5 |
|-------|---------|---------|------------------|-----------|--------------|------|------|------|
| arm   | read    | 3       |  unsigned int fd | char *buf | size_t count |  --  |  --  |  --  |

## Example 3 (Search arch spec)
| arch  | callreg | arg0 | arg1 | arg2| arg3 | arg4 | arg5 |
|-------|---------|------|----- |-----|------|------|------|
| x86   | eax     | ebx  | ecx  | edx | esi  | edi  | ebp  |
| x64   | rax     | rdi  | rsi  | rdx | rcx  | r9   | r8   |
| arm64 | x8      | x0   | x1   | x2  | x3   | x4   | x5   |
| arm   | r7      | r0   | r1   | r2  | r3   | r4   | r5   |

## Example 4 (Search arch spec with arch filter)
| arch  | callreg | arg0 | arg1 | arg2| arg3 | arg4 | arg5 |
|-------|---------|------|----- |-----|------|------|------|
| x64   | rax     | rdi  | rsi  | rdx | rcx  | r9   | r8   |
