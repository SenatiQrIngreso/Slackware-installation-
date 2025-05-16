# Slackware Linux operating system installation. 
This section explains how I installed Slackware Linux in VMware Workstation.
I followed the full installation steps including partitioning and user setup.
Each command and setting is included clearly for easy understanding.

## System call implementation.
I implemented a custom system call in Slackware Linux that returns the current time in seconds and nanoseconds.  
It uses `clock_gettime()` to fetch high-precision time values from the kernel.  
This system call helps understand kernel modification and user-kernel interaction.    
All changes were made, compiled, and tested successfully in VMware.
