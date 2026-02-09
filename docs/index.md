# 🏠 Welcome to the Hydrust Wiki

**Hydrust** is a modular media orchestration engine designed for performance, safety, and long-term maintainability. This wiki serves as the technical source of truth for the project's internals, SDK, and plugin ecosystem.

---

> This documentation is under heavy development and it is not in any way complete or representative.

## 🏗️ The Hydrust Paradigm

Unlike traditional scrapers that rely on monolithic scripts, Hydrust utilizes a **Host-Guest Architecture**. This separates the volatile logic of site-specific scraping from the high-performance stability of the media engine.

### 🧩 Core Components

* **The Host (Rust):** The "Engine Room." Handles GStreamer pipelines, network orchestration, and the DRM lifecycle.
* **The Guest (WASM):** The "Site Logic." Sandboxed modules that navigate APIs and manifests to find media sources.
* **The WIT (Interface):** The "Contract." A strictly typed communication layer that ensures the Host and Guest can exchange data safely without memory leaks.

---

## 📚 Technical Documentation Sections

| Section | Target Audience | Description |
| :--- | :--- | :--- |
| **[Getting Started](getting-started)** | Users / New Devs | How to compile the host and run your first download. |
| **[SDK Reference](sdk-reference)** | WASM Developers | Detailed guide on writing site plugins using the Hydrust SDK. |
| **[WIT Specifications](wit-specs)** | Core Architects | The underlying interface definitions (World IDL) for Host calls. |
| **[CDM & DRM Mounting](drm-mounting)** | Security Researchers | How the Host handles Content Decryption Modules and license requests. |

---

## 🤝 Project Roles & Permissions

Hydrust is a community-driven effort. We utilize a tier-based progression system synchronized with our **[Discord Server](https://discord.gg/Mk7E2x5933)**.

* **📦 Uncompiled:** New arrivals observing the tree.
* **🏗️ Linkers:** Active contributors providing logs and bug reports.
* **🧩 Plugin Masters:** Developers maintaining verified WASM extensions.
* **🌟 Core Architects:** Project maintainers with write access to the Host Engine.

---

## ⚖️ Legal Policy

Hydrust is provided for **educational and personal archival purposes only**. Contributors and users are expected to respect the copyright laws and Terms of Service of the platforms they interact with. For more details, see our [Legal Disclaimer](legal-disclaimer).

---