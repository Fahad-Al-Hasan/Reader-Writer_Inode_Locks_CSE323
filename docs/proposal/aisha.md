
Types of locks:
Spinlock –threads keep spinning in a while loop when the resource is locked waiting for it to unlock
Mutex– thread gives up cpu when resource is locked. Comes back to the cpu later. 

These are implemented by hardware.

Usespace locks are usually mutex.

OS core also needs locks. Only spinlocks can be used here. The OS cannot sleep, it needs to manage hardware. 

Precautions must be taken when the kernel has spinlock. Can't be interrupted, these need to be disabled. Should try to get out of Spinlock asap. Avoid blocking. 


Use locks for shared data structures. 

Thread safe data structures – using locks.

Coarse grain lock- one lock 
Fine grain lock- each element has a lock, allows parallelism, harder to implement but better performance 

User programs must have correct locking system. 

XV6 OS

A teaching OS

x86 version 

X86 registers- gp, stack pointers, pc, control,  segment 

Instructions: mov, push, pop, jmp



Files
Inode numbers
Open
Close
Read // sequentially
Read w offset
Write
Directories r like files
Hard Linking files // points to same file (inode)
When all pointers are gone, inode is deleted too, this deletes the file
Soft link // establishes an alias for a file, deleting one pointer, will delete the whole file
Mounting a filesystem // all files in a directory tree become accessible thru that point??
Memory mapping //mmap(), creates a page to store program data or copy and store a file, then treat it like a program, basically use it like an address for the file or program???

FILE SYSTEM
Organizes files
Data Blocks, inodes stored in inode blocks, bitmaps track which inodes and data blocks are free
Super block holds plan of all blocks
Made of data structure// data and metadata
System calls // open, read, write
Inode table
Inode stores, metadata, pointers to file data, might store indirect block, there can be multiple leveling (depending on the size of the file)
FAT is an alt way //kind of like a linked list, older method

Directory stores, filename, inode, len, etc as a linked list, is stored as a special type of file

Open file table
Per process open file table
Index of open file in array is the file descriptor returned 
0, 1, 2 are std in, out, err, opened by default in a process

Virtual file system
System calls look at higher level of abstraction
File systems are seen as objects
System calls work on vfs objects

Disk buffer cache
Recently fetched blocks are cached
Synchronous cache
Asynchronous cache
Memory is allocated to this dynamically
Buffer cache improves performance
Prevents multiple copies of same block in main memory

Hard Disk internals
Interface of 512 blocks usually


LOCKING in xv6
No threads in xv6, still has concurrency
Two processes may concurrently access shared data
Spinlocks are used to prevent issues in kernel programs
Interrupts must be disabled?

Ptable lock– important lock
Special case where next process acquires lock before fist one gives it up?





