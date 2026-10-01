Here is a comprehensive and professional `README.md` for your new standalone repository. It maintains the same enthusiastic and philosophy-driven tone as your previous tools, while perfectly highlighting the unique power of this aggregator.

***

# 📚 Repo Markdown Aggregator

A powerful, entirely client-side web application that fetches, cleans, sorts, and aggregates `.md` files from any GitHub repository into a single, unified text file. 

**[👉 Click here to use the App](https://sparktsang.github.io/aggregator/)**  

---

## ⚠️ The Problem
When performing text analysis or migrating a large number of articles (e.g., Jekyll blog posts, Obsidian notes), you often need to merge hundreds of Markdown files into one. 

Existing tools (like `uithub`) simply dump all repository files into a single document. They have fatal flaws:
1. **No Sorting Control:** Files are merged randomly or alphabetically. You cannot sort by custom front-matter tags (e.g., `classification` or `date`).
2. **Messy Data:** They force you to keep YAML front matter, messy URL links, and HTML tags, which ruins readability and text-mining processes.
3. **Inflexible Formatting:** They hardcode line numbers and separators that you cannot change.

## 💡 The Solution
This tool gives you absolute control over how your Markdown files are fetched, ordered, and cleaned—all running instantly in your browser.

### ✨ Key Features

*   **Multi-Level Smart Sorting:**
    *   Sort by any YAML front-matter key (e.g., `date`, `classification`, `order`).
    *   **Custom List Sorting:** Define exact ordering rules (e.g., `Investment, History, Politics`). The tool will strictly follow this hierarchy.
    *   **Smart Fallback:** Files missing the specified front-matter keys are automatically pushed to the bottom, continuing to sort by subsequent rules.
    *   **Implicit Date Extraction:** If a file lacks a `date` in its front matter, the tool automatically extracts it from Jekyll-style filenames (e.g., `2026-10-01-post.md`).
*   **Regex-Powered Content Cleaning:**
    *   **Link Stripping:** Converts inline links `[like this](/url)` into plain text `like this`. It also sweeps away footnote-style link definitions at the bottom of pages (`[id]: /url`).
    *   **HTML Removal:** Optionally strip out all `<...>` HTML tags while preserving pure Markdown.
    *   **Front Matter Control:** Choose whether to include or completely hide the YAML metadata blocks.
*   **Custom File Separators:** Define exactly how you want files to be divided in the final output (e.g., adding standard divider lines and injecting the `{path}` filename).

---

## 🚀 How to Use

1. **Target Repository:** Enter the GitHub owner (e.g., `torvalds`), the repo name (e.g., `linux`), and optionally a specific folder path (e.g., `_posts`).
2. **Configure Cleaning & Sorting:** Set up your multi-level sorting rules and toggle the cleaning checkboxes.
3. **Fetch & Aggregate:** Click the button. The app will fetch the directory tree, download the files concurrently, parse the YAML using `js-yaml`, apply your rules, and generate a clean, unified document.

---

## 🧠 The Philosophy (Why Build This?)

*   **100% Client-Side:** No backend servers, no Python scripts to configure, no local cloning required. Everything is processed using Vanilla JS and the browser's `fetch` API.
*   **Tailored Workflow:** Generic aggregation tools assume you want everything exactly as it is in the repo. This tool understands that aggregation is usually the first step of *data processing*—meaning you need the text clean, ordered, and formatted to your exact specifications.

## 🤝 Fork & Extend

This tool is built as a single `index.html` file for ultimate portability and easy customization. Feel free to fork this repository, tweak the CSS, or add your own custom Regex cleaning rules to fit your exact analytical workflow!
