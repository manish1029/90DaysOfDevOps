List 5 commands you would use daily

ping
Check network connectivity to another device/server.
example - ping google.com

Ls
Displays the contents of the current directory.

grep
Finds lines that match a specific word or pattern.
example - grep "error" logfile.txt

tail
Displays the last 10 lines of a file by default.
example - tail logfile.txt

cd
Change directory.
example - cd Documents

The core components of Linux (kernel, user space, init/systemd)
--The kernel is the core of the Linux operating system. It acts as a bridge between hardware and software. Its main responsibilities include
Managing CPU, memory, and storage

--User space is where user applications and services run. These include:
Command-line shells (bash, zsh)
System utilities (ls, cp, ps)

--When Linux boots, the kernel starts the first process called systemd

--Processes are typically created using:

fork()

Creates a copy of the current process.
The new process is called the child process.
exec()

Replaces the child process’s memory with a new program.

--The kernel manages processes by:

Assigning each process a Process ID (PID)
Scheduling CPU time (process scheduling)
Managing memory allocation
Handling signals (e.g., SIGTERM, SIGKILL)
Tracking process states:
Running
Sleeping
Stopped
Zombie

--What systemd Does
systemd is the first process started by the kernel (PID 1). It:

Starts and stops system services
Manages background daemons
Handles system boot process


The processes in a Linux system can be in one of the following states:

🔸(new): Initial state when a process is created via a fork system call.

🔸Runnable (ready): Process is ready to run and waiting to be scheduled on a CPU.

🔸Running (user): Process is executing in user mode, running user applications.

🔸Running (kernel): Process is executing in kernel mode, handling system calls or hardware interrupts.

🔸Sleeping (S): Process is waiting for an event (e.g., I/O operation) to complete and can be easily awakened.

🔸Sleeping (uninterruptible) (D): Process is in an uninterruptible sleep state, waiting for a specific condition (usually I/O) to complete, and cannot be interrupted by signals.

🔸Sleeping (disk sleep) (K): Process is waiting for disk I/O operations to complete.

🔸Sleeping (idle) (I): Process is idle, not doing any work, and waiting for an event to occur.

🔸Stopped (T): Process execution has been stopped, typically by a signal, and can be resumed later.

🔸Zombie (Z): Process has completed execution but still has an entry in the process table, waiting for its parent to read its exit status.

The transition between states can be in done in the following ways:

🔸Fork: Creates a new process from a parent process, transitioning from (new) to Runnable (ready)

🔸Schedule: Scheduler selects a runnable process, transitioning it to Running (user) or Running (kernel) state.

🔸Run: Process transitions from Runnable (ready) to Running (kernel) when scheduled for execution.

🔸Preempt or Reschedule: Process can be preempted or rescheduled, moving it back to Runnable (ready) state.

🔸Syscall: Process makes a system call, transitioning from Running (user) to Running (kernel).

🔸Return: Process completes a system call and returns to Running (user).

🔸Wait: Process waits for an event, transitioning from Running (kernel) to one of the Sleeping states (S, D, K, or I).

🔸Event or Signal: Process is awakened by an event or signal, moving it from a Sleeping state back to Runnable (ready) .

🔸Suspend: Process is suspended, transitioning from Running (kernel) or Runnable (ready) to Stopped (T).

🔸Resume: Process is resumed, moving from Stopped (T) back to Runnable (ready).

🔸Exit: Process terminates, transitioning from Running (user) or Running (kernel) to Zombie (Z).

🔸Reap: The parent process reads the exit status of the zombie process, removing it from the process table.
