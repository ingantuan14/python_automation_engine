
# ⚡ Enterprise Async Inventory Synchronization Engine

High-performance, non-blocking asynchronous pipeline designed to synchronize multi-supplier e-commerce inventories concurrently, preventing rate-limiting and offloading CPU-bound cryptographic checks.

## 🏛️ Architecture & Core Concepts
This project demonstrates production-grade Python asynchronous engineering principles:
* **Event Loop & Cooperative Concurrency:** Powered by `asyncio` to eliminate idle I/O wait times.
* **Connection Pooling:** Uses `httpx.AsyncClient` to maintain persistent TCP sockets, drastically reducing handshake latency.
* **Rate Limiting:** Controlled via `asyncio.Semaphore` to protect downstream supplier APIs from traffic spikes (preventing `HTTP 429` errors).
* **Structured Concurrency:** Implements Python 3.11+ `asyncio.TaskGroup` for safe exception propagation and automatic task cancellation.
* **Blocking Code Isolation:** Safely bridges CPU-bound signature verification routines to a `ThreadPoolExecutor` using `loop.run_in_executor()`, preserving Event Loop fluidity.
* **Non-Blocking File I/O:** Leverages `aiofiles` for asynchronous audit log generation.

## 🛠️ Tech Stack
* **Python 3.11+**
* `asyncio` (Standard Library)
* `httpx` (Async HTTP Client)
* `aiofiles` (Async File I/O)

## 🚀 Quick Start

1. Clone the repository:
   ```bash
   git clone [https://github.com/TU_USUARIO/async-inventory-sync-engine.git](https://github.com/TU_USUARIO/async-inventory-sync-engine.git)
   cd async-inventory-sync-engine