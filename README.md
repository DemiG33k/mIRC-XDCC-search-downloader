# mIRC Advanced Protocol & Stream Management Suite

A high-performance, event-driven automation and stream management suite built natively in mIRC Scripting Language (mSL). This project provides a robust graphical user interface (GUI) and background indexing engine designed to parse, index, query, and orchestrate asynchronous data transfers and automated network pipelines.

---

## Architecture & Core Features

### 1. Dynamic Indexing & Parsing Engine
* **Universal Stream Ingestion:** Listens to public channel telemetry and search bot broadcasts in real-time, executing high-speed regular expression matching to isolate target vectors, identifiers, and node signatures.
* **Persistent Hashing:** Utilizes mIRC's native hash table architecture (`/hmake`, `/hadd`) backed by serialized binary dumps (`hsave`/`hload`) to maintain a high-performance, non-blocking local database.
* **Byte-Normalized Sorting Algorithm:** Converts human-readable scale factors (KB, MB, GB, KiB/s, MiB/s) into raw byte integers on-the-fly, allowing precise multi-metric sorting (size, throughput speed, chronological timestamps, and lexicographical order) without index corruption.

### 2. Advanced GUI & State Machine
* **Multi-Tiered Staging & Queue Pipelines:** Features an interactive split-pane interface separating active search results, pending staging queues, and live execution monitors.
* **Real-Time Telemetry Tracking:** Dynamically parses asynchronous server notices and private system messages to update operational states (e.g., node slot availability, queue positioning, active handshakes, and completion flags) instantly.
* **Duplicate Elimination & Filtering:** Includes dynamic filtering layers for resolution parameters, codec variants, temporal metadata, and unique-title deduplication.

### 3. Pipeline Orchestration & Post-Processing
* **Asynchronous File-Lock Bypass:** Implements a controlled micro-delay queuing mechanism (`.timer`) to securely release OS-level file handles before executing automated file routing and relocation.
* **Drive-Space Safety Guard:** Evaluates available disk space on target storage volumes prior to executing batch pipelines, aborting operations and triggering alerts if storage thresholds are breached.
* **Webhook & Notification Integration:** Features a native HTTP POST communication pipeline (`MSXML2.ServerXMLHTTP`) designed to route real-time telemetry updates and status alerts to external notification endpoints (e.g., `ntfy.sh`).

---

## System Requirements

* **mIRC Client:** Version 7.x or higher (fully compatible with modern 64-bit builds).
* **Operating System:** Windows (utilizes native Windows COM objects and file-system commands for directory management and routing).

---

## Installation & Configuration

1. Open mIRC and press **ALT + R** to open the **Scripts Editor**.
2. Navigate to the **Remote** tab and create a new file or paste the code into an existing remote block.
3. Save the script and type the following command in any active window to launch the control panel:
   ```text
   /xdcc
