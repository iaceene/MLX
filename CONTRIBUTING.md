# 🤝 Contributing to MLX

First off, thanks for taking the time to contribute! 🎉  
This document will guide you through the process of contributing to this MLX42-based C project.

---

## 🧰 Prerequisites

Before you begin contributing, make sure you have:

- A basic understanding of **C programming**
- Installed all required dependencies for MLX42:
  - **Linux**: `cmake`, `libglfw3-dev`, `libgl1-mesa-dev`
  - **macOS**: `brew install cmake glfw`
- A working version of **MLX42** (included as a submodule or installed manually)
- A compiler like `gcc` or `clang`

---

## 🚀 Getting Started

1. **Fork** the repository
2. **Clone** your fork locally:
   ```bash
   git clone --recurse-submodules https://github.com/iaceene/MLX.git
   cd your-project

3. **Create a new branch** for your feature or bugfix:

   ```bash
   git checkout -b my-feature
   ```
4. **Build the project**:

   ```bash
   make
   ./your_project_executable
   ```

---

## 🧑‍💻 Code Guidelines

* Use **`clang-format`** to format your C code.
* Indentation: 4 spaces, no tabs.
* No memory leaks! Always clean up with `mlx_terminate()` and `free()`.
* Keep functions short and focused (ideally under 40 lines).
* Use meaningful variable and function names.
* Group related functions in separate files when needed (e.g., `input.c`, `render.c`).

---

## 🧪 Testing & Validation

* Always run the project and test your changes thoroughly.
* If you're adding a feature, consider writing a minimal test scene in `main.c` or a dedicated test file.
* Use tools like `valgrind` (Linux) or `leaks` (macOS) to check for memory leaks.

---

## 📦 Commit Messages

Follow this structure for commits:

```
[type]: short summary

[optional body]
```

Examples:

* `feat: add image rendering function`
* `fix: prevent crash on NULL texture`
* `style: format main.c with clang-format`

---

## ✅ Pull Requests

1. Push your branch:

   ```bash
   git push origin my-feature
   ```
2. Open a **Pull Request** against the `main` or `dev` branch.
3. Make sure your PR includes:

   * A clear description of what you changed
   * Screenshots (if applicable)
   * Any issues or bugs it addresses
4. A maintainer will review it and may request changes.

---

## 📄 License

By contributing, you agree that your contributions will be licensed under the same license as the project (usually MIT).

---

## 🙌 Need Help?

Feel free to open an issue or discussion if you're:

* Not sure where to start
* Stuck on an MLX42 behavior
* Have suggestions or feedback

---

Thank you for contributing! 🎨
Together we’re making something awesome. 🚀
