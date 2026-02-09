# ✍️ Hydrust Documentation Manifest

Welcome, **Scribe**. You are the bridge between the Hydrust Host Engine and the developers building on top of it. This repository houses the official technical documentation, powered by **MkDocs**.

---

## 🏗️ The Documentation Stack

We use a **Docs-as-Code** workflow. This ensures that every change is peer-reviewed by a **Core Architect** before it goes live.

* **Engine:** [MkDocs](https://www.mkdocs.org/)
* **Theme:** Material for MkDocs
* **Source:** All content is written in standard Markdown (`.md`) located in the `/docs` directory.
* **Deployment:** Automated via GitHub Actions on every merge to `main`.

---

## 🛠️ How to Contribute

### Option A: The "Quick Patch" (Web Interface)
Ideal for fixing typos, updating WIT definitions, or adding small notes.
1.  Navigate to the `/docs` folder in this repository.
2.  Select the file you wish to edit.
3.  Click the **pencil icon (Edit this file)**.
4.  Make your changes and click **"Propose changes"**.
5.  This will create a Pull Request (PR) for review.

### Option B: The "Deep Link" (Local Development)
> [!NOTE]
> We use [uv]() for dependancy managment
> If you wish to run local preview server, you need to install `uv`.

Ideal for writing entire new sections or restructuring the SDK reference.
1.  **Clone the repository:**
    `git clone https://github.com/razorblade23/hydrust-docs.git`
2.  **Install dependencies:**
    `uv sync`
3.  **Run the local preview server:**
    `uv run mkdocs serve`
4.  View your changes in real-time at `http://127.0.0.1:8000`.

---

## 📜 Scribe Protocols (Style Guide)

To maintain "High Performance" documentation, follow these constraints:

1.  **Strict Typing:** When documenting WIT interfaces, always use backticks for types (e.g., `list<u8>`, `result<s32, error>`).
2.  **File Naming:** Use kebab-case for all filenames (e.g., `getting-started.md`, not `GettingStarted.md`).
3.  **The Sidebar:** If you add a new page, you **must** register it in the `mkdocs.yml` file under the `nav` section, or it won't appear in the site navigation.
4.  **Admonitions:** Use notes and warnings to highlight critical DRM/CDM information:
    ```markdown
    !!! danger "Legal Compliance"
        Never document methods for bypassing hardware-level DRM.
    ```

---

## 🚥 The Review Pipeline

1.  **Submit PR:** Label your PR with `documentation`.
2.  **CI Check:** GitHub Actions will verify that the Markdown is valid and the site builds.
3.  **Architect Review:** A **Core Architect** will review for technical accuracy.
4.  **LTO (Merge):** Once merged, the site updates automatically within 60 seconds.

---

**Questions?** Reach out in the `#docs-and-wiki` channel on the [Hydrust Discord](https://discord.gg/uX4EFqD6ew).