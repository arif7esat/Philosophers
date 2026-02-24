# Philosophers — Concurrent Programming & Synchronization (C)

> *⚠️ **Notice on Source Code Availability:** The source codes for this project are currently hosted on the highly restricted internal servers (Vogsphere) of the 42 Network. Full source code migration to this public repository is scheduled and will be completed soon. Below is the architectural documentation and technical constraints of the project.*

## ⚙️ Multithreading Architecture & RTOS Simulation
This project tackles the classic "Dining Philosophers" synchronization problem. It serves as a rigorous simulation of highly concurrent execution, memory sharing, and precise timing—constraints identical to those found in **Real-Time Operating Systems (RTOS) used in automotive Electronic Control Units (ECUs).**

### Core Engineering Features
* **High-Concurrency Multithreading:** Engineered complex simulation logic using POSIX threads (`pthreads`), managing continuous resource allocation and context switching between competitive threads.
* **Microsecond-Level Synchronization:** Achieved deterministic execution and extremely precise timing (using `gettimeofday`), ensuring no thread starves under heavy CPU load.
* **Mutex Lock Hierarchies:** Architected strict mutex lock protocols to safely manage shared memory access across multiple concurrent threads.

## 🛡️ Deadlock & Race Condition Prevention
Concurrency without safety leads to catastrophic system failures. This system was engineered with absolute strictness:
* Established definitive measures to prevent **Data Races** during read/write operations on shared variables.
* Implemented architectural safeguards to completely eliminate **Deadlocks**, ensuring continuous and stable execution.
* Valgrind (`--tool=helgrind` & `--tool=drd`) tested: Zero race conditions and zero memory leaks.

---
*Developed as part of the 42 Network Common Core Curriculum.*
