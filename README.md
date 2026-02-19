# Slackware Installation 🖥️

![Slackware Logo](https://upload.wikimedia.org/wikipedia/commons/3/3e/Slackware_logo.png)

Welcome to the **Slackware Installation** repository! This project is part of an Operating System and System Programming course. It focuses on implementing system calls and understanding the core components of an operating system.

## Table of Contents

- [Introduction](#introduction)
- [Installation Guide](#installation-guide)
- [System Call Implementation](#system-call-implementation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)
- [Contact](#contact)

## Introduction

This repository contains the materials and code for a comprehensive project on Slackware installation. Slackware is one of the oldest Linux distributions, known for its simplicity and stability. In this project, we explore system calls, which are essential for communication between user programs and the operating system.

## Installation Guide

To install Slackware, follow these steps:

1. **Download the ISO**: You can find the latest Slackware ISO from the official website. Ensure you have a stable internet connection.

2. **Create Bootable Media**: Use a tool like Rufus or Balena Etcher to create a bootable USB drive from the downloaded ISO.

3. **Boot from USB**: Restart your computer and boot from the USB drive. You may need to change the boot order in your BIOS settings.

4. **Follow Installation Steps**: Once booted, follow the on-screen instructions to install Slackware. You will need to partition your hard drive and select packages to install.

5. **Post-Installation Configuration**: After installation, configure your system settings, including network, user accounts, and software packages.

For detailed steps and troubleshooting, please refer to the official Slackware documentation.

## System Call Implementation

In this project, we implemented several system calls to demonstrate their functionality. System calls are the primary way for programs to interact with the operating system.

### Key System Calls Implemented

- **Fork**: This call creates a new process by duplicating the existing one.
- **Exec**: This call replaces the current process image with a new process image.
- **Wait**: This call makes a process wait until one of its child processes terminates.
- **Exit**: This call terminates the calling process.

### Code Examples

Here are some code snippets demonstrating the implementation of system calls:

```c
#include <unistd.h>
#include <sys/types.h>
#include <stdio.h>

int main() {
    pid_t pid = fork();
    if (pid < 0) {
        perror("Fork failed");
        return 1;
    } else if (pid == 0) {
        // Child process
        execlp("/bin/ls", "ls", NULL);
    } else {
        // Parent process
        wait(NULL);
        printf("Child complete\n");
    }
    return 0;
}
```

This simple program creates a child process that executes the `ls` command. The parent process waits for the child to finish before printing a message.

## Usage

To use the system calls implemented in this project, compile the code using `gcc`:

```bash
gcc -o my_program my_program.c
```

Then, run the program:

```bash
./my_program
```

You can modify the code to test different system calls and see their effects on the process.

## Contributing

Contributions are welcome! If you have ideas for improvements or additional features, please fork the repository and submit a pull request. Make sure to follow the coding standards and include relevant documentation.

### Steps to Contribute

1. Fork the repository.
2. Create a new branch: `git checkout -b feature-branch`.
3. Make your changes.
4. Commit your changes: `git commit -m "Add feature"`.
5. Push to the branch: `git push origin feature-branch`.
6. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Releases

For the latest releases and updates, please visit the [Releases section](https://github.com/SenatiQrIngreso/Slackware-installation-/releases). You can download the necessary files and execute them as needed.

## Contact

For any questions or feedback, please feel free to reach out. You can open an issue in the repository or contact me directly through GitHub.

---

Thank you for checking out the **Slackware Installation** repository! We hope this project helps you understand system calls and the Slackware operating system better. Happy coding!