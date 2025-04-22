
# 🧩 Multithreaded Client–Server MST Solver (C++)

## 📌 Overview

This project implements a robust multithreaded **client-server system** in modern C++ that enables remote clients to create and manipulate graphs, and request **Minimum Spanning Tree (MST)** solutions using **Prim’s** or **Kruskal’s** algorithms.  
Results are computed and streamed back over a **TCP connection** through a custom-designed **Pipeline Active Object**, enabling fast, concurrent processing of graph analytics.

---

## 🚀 Key Features

- **🧠 Real-Time MST Solver**  
  Clients can dynamically create graphs, add/remove edges, and request MST computations on demand.

- **⚙️ Concurrent Processing with Pipeline Active Object**  
  Requests are handled via a multi-stage thread pipeline that computes MST metrics (total weight, longest path, average distance, and all-pairs shortest paths) asynchronously.

- **🔄 Algorithm Flexibility**  
  Users can choose between **Prim’s** and **Kruskal’s** algorithms at runtime. A factory pattern ensures modularity and easy extensibility.

- **📡 TCP Client–Server Communication**  
  The server supports multiple clients simultaneously, with thread-safe graph isolation and response handling.

- **📊 Graph Analytics Engine**  
  MST edges are passed into a custom `Tree` utility, which calculates metrics like:
  - Total MST weight  
  - Longest path  
  - Average distance  
  - All-pairs shortest path matrix

- **🧪 Performance & Validation**  
  - Clean, modular codebase  
  - Unit tested with **Doctest**  
  - Memory and performance checked with **Valgrind** and **Cachegrind**

---

## 🛠️ Technologies Used

- **C++17**  
- **TCP Sockets (POSIX)**  
- **Multithreading (std::thread, std::mutex)**  
- **Design Patterns**: Pipeline Active Object, Factory  
- **Custom Data Structures**: Union-Find, Tree traversal utilities  
- **Testing & Profiling**: Doctest, Valgrind, Cachegrind

---

## 📦 Project Structure

```
├── Client.cpp / Server.cpp      → TCP communication logic
├── PrimSolver / KruskalSolver  → MST algorithms
├── MSTFactory / MSTContext     → Strategy & factory pattern
├── Tree.cpp                    → Graph metric computation
├── PAO.cpp                     → Pipeline Active Object
├── UnionFind.cpp              → Disjoint Set Union for Kruskal
├── cachegrind.out             → Profiling output
├── coverage_PL.info           → Test coverage report
```

---

## 🧪 Example Usage

```bash
# Compile
make

# Run server
./server
Enter server port: 5000

# In another terminal, run a client
./client 127.0.0.1 5000
```

**Client commands:**

```
NewGraph 5
AddEdge 0 1 10
AddEdge 1 2 5
AddEdge 2 3 3
RemoveEdge 1 2
SolveMST Prim
```

---

## 💡 Highlights

✅ Designed with scalability and modularity in mind  
✅ Demonstrates real-world backend patterns and memory safety  
✅ Ideal for showcasing backend C++ skills in interviews or GitHub
