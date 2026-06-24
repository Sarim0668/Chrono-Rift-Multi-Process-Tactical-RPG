# ⚔️ Chrono Rift – Multi-Process Tactical RPG

Chrono Rift is a turn-based tactical RPG developed in C++17 for Linux that demonstrates real-world Operating Systems concepts through an interactive game environment. The project combines multi-process architecture, shared memory IPC, multithreading, synchronization primitives, deadlock detection, scheduling algorithms, and memory management into a fully playable SFML-powered game.

---

## 🎯 Project Overview

Traditional Operating Systems concepts are often studied in isolation. Chrono Rift bridges theory and practice by integrating core OS mechanisms into a real-time tactical RPG.

The game consists of three independent processes communicating through shared memory:

* **Arbiter Process** – Central game authority and scheduler
* **Human Interfacing Process (HIP)** – Handles player actions
* **Automated Strategic Process (ASP)** – Controls enemy AI

Each component runs in its own address space while coordinating gameplay through POSIX shared memory and synchronization primitives.

---

## ✨ Features

### ⚔️ Tactical Turn-Based Combat

* Stamina-based turn scheduling
* Multiple player characters
* AI-controlled enemy waves
* Dynamic combat system

### 🔄 Multi-Process Architecture

* Independent Linux processes
* Process isolation using fork() and exec()
* Shared-memory communication

### 🧵 Advanced Multithreading

* Thread-per-player architecture
* Thread-per-enemy architecture
* Dedicated rendering thread
* Background monitoring threads

### 🔗 Inter-Process Communication (IPC)

* POSIX Shared Memory
* Process-shared Mutexes
* POSIX Semaphores
* Signal-based coordination

### 🛡 Concurrency Control

* Race condition prevention
* Critical section protection
* Synchronization across processes
* Safe shared-state updates

### 🔍 Deadlock Detection System

* Resource allocation tracking
* Wait-for graph generation
* Cycle detection using DFS
* Continuous deadlock monitoring

### 🎮 Real-Time Graphics

* SFML rendering engine
* Animated battle interface
* Health and stamina visualization
* Combat event logging

---

## 🏗 System Architecture

### Arbiter Process

Responsible for:

* Global game state management
* Turn scheduling
* Rendering
* Signal handling
* Deadlock detection
* Resource management

### HIP (Human Interfacing Process)

Responsible for:

* Capturing player input
* Managing player threads
* Sending actions to Arbiter
* Turn synchronization

### ASP (Automated Strategic Process)

Responsible for:

* Enemy AI logic
* NPC thread management
* Wave progression
* Strategic decision-making

---

## 📚 Operating Systems Concepts Implemented

### Process Management

* fork()
* exec()
* Process lifecycle management
* Parent-child relationships

### Inter-Process Communication

* POSIX Shared Memory
* Shared State Management
* Semaphore-Based Communication

### Synchronization

* pthread_mutex_t
* POSIX Semaphores
* Condition Variables
* Critical Sections

### Multithreading

* Pthreads
* Thread Scheduling
* Concurrent Execution
* Thread Synchronization

### CPU Scheduling

* Turn-based scheduling mechanism
* Stamina-driven execution model
* Fair resource allocation

### Deadlock Handling

* Wait-for Graph Construction
* Cycle Detection
* Resource Allocation Tracking
* Deadlock Monitoring Thread

### Signal Handling

* SIGTERM Processing
* Graceful Shutdown
* Process Coordination

### Memory Management

* Shared Memory Segments
* Memory Mapping
* Controlled Resource Access

---

## 💻 Tech Stack

### Languages

* C++17

### Libraries

* POSIX Threads (pthreads)
* POSIX Shared Memory
* POSIX Semaphores
* SFML

### Environment

* Linux
* Docker
* Ubuntu 22.04

---

## 📂 Project Structure

```text
Chrono-Rift/
│
├── arbiter/
│   ├── arbiter.cpp
│   ├── GameState.h
│   ├── SharedMemoryManager.h
│   └── Weapons.h
│
├── hip/
│   ├── hip.cpp
│   ├── GameState.h
│   └── SharedMemoryManager.h
│
├── asp/
│   ├── asp.cpp
│   ├── GameState.h
│   └── SharedMemoryManager.h
│
├── sprites/
│   ├── player sprites
│   ├── enemy sprites
│   └── background assets
│
├── Dockerfile
├── Makefile
└── README.md
```

---

## 🚀 Key Achievements

* Designed a fully shared-memory-based IPC system without using pipes.
* Implemented thread-per-NPC and thread-per-player execution models.
* Developed a custom stamina-based scheduling mechanism.
* Built a real-time deadlock detection system using wait-for graphs.
* Created a concurrent rendering system running independently of gameplay scheduling.
* Applied advanced synchronization techniques to eliminate race conditions.

---

## 🎓 Academic Context

Developed as part of the Operating Systems course project at FAST-NUCES.

The project demonstrates practical implementation of operating system principles through a real-world software system rather than isolated simulations.

---

## 👥 Team Members

* Muhammad Sarim (24I-0668)
* Hafiz Anas Mumtaz (24I-0653)

---

## ⭐ Future Improvements

* Multiplayer networking support
* Distributed game servers
* Advanced AI decision systems
* Save/load functionality
* Inventory and equipment systems
* Additional character classes
* Performance profiling dashboard
