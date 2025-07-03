# WeensyOS

WeensyOS: Process Isolation & Virtual Memory Kernel

Recruiters: Please email me at elif_cebe@brown.edu to access the code!

This project involved extending the WeensyOS educational kernel to implement Unix-style process isolation, memory management, and system calls, as part of Brown University's CS300: Introduction to Systems Programming.

## ⚙️ Objectives
- Develop a minimal operating system kernel from scratch
- Understand virtual memory and page table manipulation
- Implement safe process isolation and memory sharing

## 🔧 Key Features Implemented
- `syscall_fork()`: Clone process state and virtual memory (via `copy_mappings`)
- `syscall_exit()`: Clean process exit, freeing page table and user memory
- `syscall_page_alloc()`: Demand-based page allocation for user space
- `copy_mappings()`: Deep copy of user-accessible pages into new process address space
- `free_pagetable()`: Deallocation of multi-level page tables on process exit

## 🔐 Memory Safety & Sharing
- Implemented copy-on-write (COW) and permission enforcement to isolate user processes
- Avoided kernel memory leaks through `free()` logic
- Wrote `syscall_kernel()` to manage privileged operations securely

## 🧪 Testing
- Ran ~40 test cases covering page faults, syscall behavior, memory leaks, and race conditions
- Passed ASan + LeakSan-based memory sanitizer validation

## 🧠 Learning Outcomes
- Built a working OS kernel from scratch using C
- Gained deep experience in virtual memory, syscalls, page table architecture, and x86–64
