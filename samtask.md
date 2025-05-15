
# Fundamental Part

## 1. Introduction

## 2. How to Ask Questions

* Use good search engines like Google or ChatGPT (which can also be used as a search engine).

  1. Use keywords in your search.
  2. Use official documentation and pages, for example, Linux manual.
  3. Use apps like:

     * Stack Overflow
     * GitHub
     * Wikipedia
     * W3Schools

## 3. An Overview of Computer Knowledge

> A computer is a machine that makes calculations — it's like a factory.

* **Alan Turing**: Inventor of the Turing machine

* **Von Neumann Architecture**: Involves:

  * Arithmetic and Logic Unit (ALU)
  * Controller
  * Memory
  * Input and Output devices

* **ENIAC**: The first computer

### CPU

* **ISA (Instruction Set Architecture)**

### Memory

* **RAM**: Random Access Memory
* **Hard Disk**:

  1. Mechanical hard drive
  2. SSD (Solid State Drive)

### GPU

* Graphics Processing Unit

### Motherboard

### Power Supply

### Peripherals

### Software

* **Kernel Mode**
* **Operating System**: Acts as the manager of resources

  1. Windows
  2. Linux
  3. macOS
* **Boot Up**

---

## 4. Overview of Basic Computer Knowledge II: Evaluation of Computers

### Evaluation of Computers: Past, Present, and Future

#### Metrics for Measuring Computers — Evaluation Oriented Towards Final Delivery

* **Power Consumption**: Energy used by a chip per unit time
* **Energy Consumption**: Energy required to complete a unit of work

> 💡 *Energy consumption is better for comparing devices; power consumption is more for design constraints.*

#### Practical Problems

* Excessive power consumption: mobile phone heating, laptop slowdown, server heat dissipation bottlenecks
* Diminishing Marginal Benefit: High power does not always mean better performance

### Performance

**Performance = Number of Instructions × Execution Time per Instruction**

* Related to:

  * IPC (Instructions Per Cycle)
  * Frequency
  * Architecture
* Instruction count varies between architectures

### Benchmark Testing

* Tools: `Geekbench`, `Passmark`, `Spec2017`, `Cinebench`, `Blender`
* Be cautious of adversarial optimization and benchmark limitations
* Software optimization: vectorization, parallelism

### Example: GPU

* Great for parallel tasks (deep learning, video processing)
* Poor performance on non-parallel tasks
* **Takeaway**: *Targeted design matters*

### Cost

* **Manufacturing Cost**: Procurement + R\&D
* **Operation Cost**: Electricity, cooling, space, maintenance
* **Profit** = (Value Created ÷ Cost) - 1

#### Trade-offs in Practice

* Deep Learning vs Storage: Different investment needs
* **Cost** = Full system-level consideration, not just parts

### Ecosystem

* Parallelism is key to improving performance
* Tools: SIMD, OpenMP, multithreading, GPU acceleration (CUDA)
* Programmer’s system understanding impacts performance
* **Architectural Stickiness**: Popular ecosystems have more support; niche ones do not

---

## 5. Make the Most of Your Computer I

### Environment Configuration

* Selecting, installing, and uninstalling common software

---

## 6. Make the Most of Your Computer II

### Version Control Overview

A version control system tracks and manages file versions.

* **Centralized** (e.g., SVN): Requires server
* **Decentralized** (e.g., Git): Everyone has full version history

### Git Basics

* Git history = Directed Acyclic Graph (DAG)
* Three areas:

  * Working area
  * Staging area
  * Repository

### Git Usage

#### Initialize Repository

```bash
mkdir git-example
cd git-example
git init
```

#### Configure Git

```bash
git config --global --edit
```

Example config:

```ini
[user]
name = Your Name
email = Your Email
```

#### Add & Commit Changes

```bash
echo Hello, world! > example1.txt
git add .
git status
git commit -m "My first commit"
```

#### Commit Shortcuts

```bash
git commit -am "message"  # Stages modified/deleted files (not new ones)
```

#### View & Roll Back History

```bash
git log
git checkout <version-hash>
git reset --hard <version-hash>
```

#### Ignore Files

```bash
echo confidential > .gitignore
echo "*.o" >> .gitignore
git add .
git commit -m "Add .gitignore"
```

#### Branching

```bash
git checkout -b update-example <hash>
git commit -am "Branch!"
git rebase master
```

#### Merging

```bash
git checkout master
git merge merge-example
```

Handle conflicts manually and use:

```bash
git add .
git merge --continue
```

#### Remote Repos

```bash
git clone <url>
git pull
git push
```

#### Forking and PR/MR

* No write permission? Fork and create a PR/MR.
* Merge Strategies:

  * **Merge**: Keeps all history
  * **Rebase**: Linear history
  * **Squash**: One commit

#### Git Tools

* VSCode (built-in Git)
* GUI tools: `gitg`, `kommit`

---

## 7. Make Good Use of Your Computer III: Troubleshooting & Knowledge Review

### Hardware Monitoring

#### Disk Info

* Windows/Linux: File manager
* Linux Health: `smartctl`
* Windows Health: `CrystalDiskInfo`

#### CPU & Memory

* Windows: Task Manager (`Ctrl + Shift + Esc`)
* Linux: `btop`

#### Battery

* Windows: `powercfg`
* Linux: `upower`

### Common Issues

* **BSOD (Windows)**: Driver or hardware issues
* **Kernel Panic (Linux)**: Driver or process 1 issues
* **App Crash**: Bugs, improper use
* **Slow Boot**: Disable startup apps or slow services
* **Network Issues**: Check cables, DNS, proxies

  * Linux tools: `rfkill`, `ip`

---

## 8. Make Good Use of Your Computer IV

### What is a URL?

* Format: `Protocol + Domain + Path + Query Parameters`
* Example query string: `?key=value&key2=value2`

> 💡 Remove the query string when sharing to protect privacy

### Privacy

* **Security Tips**:

  * Avoid phishing and fake sites
  * Use **Proxy** or **VPN**

#### Proxy

* Browser requests go through a proxy server
* Benefits: Privacy, speed, caching, load balancing

#### VPN

* Encrypted tunnel for secure remote access
* Warning: Proxy/VPN traffic visible to middle node

---

## 9. Make Good Use of Your Computer V

### Operating Systems (OS)

* Manages hardware/software and provides an interface
* Abstracts hardware for programmers
* Enables multitasking, resource management, and security

### UI Types

* **CLI**: Command-line interface
* **TUI**: Text-based UI (e.g., Vim)
* **GUI**: Graphical (icons, menus)

### Editors & IDEs

* **IDEs**: Visual Studio, PyCharm (full-featured)
* **Text Editors**: VSCode, Vim (lightweight)

> VSCode + Code Runner plugin = lightweight IDE

---

### Programming Languages

#### Imperative

* Examples: C/C++, Python
* Intuitive control flow, beginner-friendly

#### Compiled vs Interpreted

| Type        | Examples | Traits                           |
| ----------- | -------- | -------------------------------- |
| Compiled    | C, C++   | Fast, compiled into machine code |
| Interpreted | Python   | Flexible, runs line by line      |

> Compilers catch more errors early; Interpreters allow quick testing

### Debugging & Errors

* Types: Syntax, Semantic, Logic errors
* Read error messages carefully
* Debugging: Use debugger or print statements
* Test edge cases

---

## 10. Introduction to Linux and Servers I

### `/proc` – Virtual Kernel File System

* Real-time info about kernel, processes, hardware
* Examples:

  * `/proc/1234`: Info about process with PID 1234
  * `/proc/meminfo`, `/proc/cpuinfo`

### `/dev` – Device Files

* Linux treats everything as a file
* Examples:

  * `/dev/sda`: Hard drive
  * `/dev/null`: Discards output

---

## 11. Introduction to Linux and Servers II

(Installed content)

---

## 12. Text Editing: Markdown and Typst

* Markdown: Lightweight text formatting for web
* Typst: Modern typesetting system (like LaTeX, but simpler)