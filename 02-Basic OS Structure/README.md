The operating system (OS) structure revolves around three core components: kernel architecture, system calls, and APIs. These elements work together to manage hardware resources, enable secure user-kernel interactions, and provide standardized interfaces for applications.

## Kernel Architecture

The kernel serves as the OS's core, operating in **kernel mode** with full hardware access, while applications run in restricted **user mode**. Two primary architectures exist:

| **Monolithic Kernel**                                              | **Modular Kernel**                                |
| ------------------------------------------------------------------ | ------------------------------------------------- |
| Entire kernel (drivers, protocols) compiled as a single executable | Components loaded dynamically as modules          |
| Faster inter-component communication                               | Easier maintenance and debugging                  |
| Higher complexity and stability risks                              | Reduced resource usage (load only needed modules) |

**Layered Representation**:

```
User Applications → System Call Interface → Kernel (Process/File/Memory Mgmt) → Hardware
```

Windows employs a **ring model** (0-3) for privilege separation, where the kernel operates in Ring 0 (full access), and user apps run in Ring 3.

## System Calls

System calls act as secure gateways between user applications and the kernel:

1. **Mechanism**:

   - Application invokes a system call (e.g., `read()` or `CreateFile()`)
   - Context switch from user to kernel mode via software interrupt
   - Kernel executes hardware operations, returns results to user space

2. **Key Functions**:
   - **Resource management**: Allocate CPU/memory via calls like `fork()` or `VirtualAlloc()`
   - **Security**: Validate permissions before file/device access (`chmod()`, `SetSecurityInfo()`)
   - **Abstraction**: Simplify hardware interactions (e.g., `socket()` hides network complexities)

**Common System Calls**:

```c
// UNIX
pid = fork();  // Create process
fd = open("file.txt", O_RDONLY);  // Open file

// Windows
CreateProcess("app.exe", ...);  // Launch process
ReadFile(file_handle, buffer, ...);  // Read data
```

## APIs

APIs provide structured interfaces for system call utilization:

- **Role**: Abstract low-level system calls into standardized functions (e.g., POSIX API for UNIX, Win32 API for Windows)
- **Structure Example** (OpenAPI YAML):
  ```yaml
  openapi: 3.0.3
  info:
    title: OS System Call API
    description: Interface for process/file management
    version: 1.0.0
  servers:
    - url: http://api.kernel.local
  paths:
    /process:
      post:
        summary: Create a new process
  ```
  This YAML defines metadata, servers, and endpoints mirroring system call functionality.

The OS structure ensures security through privilege separation, efficiency via modular design, and consistency through well-defined APIs. System calls maintain user-kernel boundaries while enabling essential operations, and kernel architectures balance performance with maintainability.
