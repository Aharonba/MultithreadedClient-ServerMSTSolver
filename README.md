# Multithreaded Client‑Server MST Solver (C++)

## 📜 Overview

This project provides a multithreaded **client–server** platform written in C++ that lets multiple clients build weighted, undirected graphs over a TCP socket and request **Minimum‑Spanning Tree (MST)** solutions computed with **Prim** or **Kruskal** algorithms.  The server employs a **Pipeline Active Object** pattern to process MST requests concurrently, streaming metrics such as total weight and path statistics back to each client without blocking new connections.

## ✨ Key Features

- **Client–Server over TCP** – Supports multiple simultaneous clients, each with an independent in‑memory graph.
- **Multithreading** – Worker threads handle request parsing, MST computation, and response formatting in parallel.
- **Design Patterns** – Uses Pipeline Active Object for staged processing and modular extensibility.
- **Algorithms** – Includes clean, header‑only implementations of **Prim** and **Kruskal** backed by an efficient **Union‑Find** structure.
- **Graph Analytics** – Calculates total weight, longest path, average path length, and all‑pairs shortest paths of the MST via a lightweight `Tree` utility.
- **Robust Testing & Profiling** – Doctest unit tests plus Valgrind & Cachegrind scripts ensure correctness and performance.

##






