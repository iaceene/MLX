# 🚀 MLX42 Guide - Codam Edition

Welcome to the ultimate guide and README for working with **MLX42**, the modern graphical library provided by Codam (part of the 42 Network). This document explains what MLX42 is, how to install and use it in your C projects, and includes example code to get started.

## 📌 What is MLX42?

**MLX42** is the modern version of the old MiniLibX library, created for students at 42 schools to build graphical applications in **C**. It replaces outdated systems like X11 and Quartz with modern libraries like **GLFW** and **OpenGL**, making it faster, more stable, and cross-platform (Linux/macOS).

It's perfect for projects like:

- [`cub3D`](https://github.com/42Paris/42cursus-cub3d) — 3D raycasting engine
- [`fract-ol`](https://github.com/42Paris/42cursus-fract-ol) — fractal rendering
- Any graphical application you want to build in C

## 🛠️ Features

- Cross-platform (Linux/macOS)
- Modern backend (GLFW + OpenGL)
- Easy keyboard, mouse, and window event handling
- Load and draw PNG images with transparency
- Per-pixel manipulation
- Simple and efficient API

---

## 🔧 Installation

You must clone MLX42 as a submodule or manually include it in your project.

### 🧱 Clone with Submodule (recommended)

```bash
git clone --recurse-submodules https://github.com/iaceene/MLX.git
````

If you’ve already cloned the project:

```bash
git submodule update --init --recursive
```

### 🐧 Linux Dependencies

Install required packages:

```bash
sudo apt update && sudo apt install -y cmake libglfw3-dev libglfw3 libgl1-mesa-dev libglu1-mesa-dev
```

### 🍎 macOS Dependencies

You need to have Homebrew installed:

```bash
brew install cmake glfw
```

---

## 📂 Project Structure Example

```
your-project/
├── lib/
│   └── MLX42/           # Cloned MLX42 library
├── src/
│   └── main.c           # Your application code
├── include/
│   └── your_headers.h
├── Makefile
└── README.md
```

---

## 📜 Basic Example

Here's a minimal example using MLX42:

```c
#include "MLX42/MLX42.h"
#include <stdlib.h>

#define WIDTH 800
#define HEIGHT 600

void hook(void* param)
{
    mlx_t* mlx = (mlx_t*)param;

    if (mlx_is_key_down(mlx, MLX_KEY_ESCAPE))
        mlx_close_window(mlx);
}

int main(void)
{
    if (mlx_init(WIDTH, HEIGHT, "MLX42 Window", true) == NULL)
        return (EXIT_FAILURE);

    mlx_loop_hook(mlx, &hook, mlx);
    mlx_loop(mlx);
    mlx_terminate(mlx);
    return (EXIT_SUCCESS);
}
```

This code creates a window and closes it when you press **ESC**.

---

## 🔗 Useful MLX42 Functions

| Function                | Description                                    |
| ----------------------- | ---------------------------------------------- |
| `mlx_init()`            | Initializes the library and creates a context. |
| `mlx_new_image()`       | Creates an image buffer you can draw on.       |
| `mlx_put_pixel()`       | Writes a pixel to an image.                    |
| `mlx_image_to_window()` | Displays an image on the window.               |
| `mlx_loop()`            | Starts the render + input loop.                |
| `mlx_key_hook()`        | Sets a callback for key events.                |
| `mlx_loop_hook()`       | Sets a function that gets called every frame.  |

---

## 🎮 Input Handling

MLX42 offers easy-to-use functions for input:

```c
mlx_is_key_down(mlx, MLX_KEY_W);
mlx_is_mouse_down(mlx, MLX_MOUSE_BUTTON_LEFT);
mlx_get_mouse_pos(mlx, &x, &y);
```

---

## 🖼️ Images and PNG Support

MLX42 supports **loading PNGs** via its built-in image loader:

```c
mlx_texture_t* tex = mlx_load_png("sprite.png");
mlx_image_t* img = mlx_texture_to_image(mlx, tex);
mlx_image_to_window(mlx, img, 100, 200);
mlx_delete_texture(tex);
```

---

## 💡 Tips & Troubleshooting

* Always terminate with `mlx_terminate(mlx)` to avoid memory leaks.
* Use `mlx_set_cursor_mode()` to hide or lock the mouse in FPS-style projects.
* To debug inputs, print key/mouse states inside a loop hook.
* If the window doesn't open, verify OpenGL and GLFW are installed correctly.

---

## 📚 Documentation

Official MLX42 GitHub: [https://github.com/codam-coding-college/MLX42](https://github.com/codam-coding-college/MLX42)

GLFW Documentation: [https://www.glfw.org/docs/latest/](https://www.glfw.org/docs/latest/)

---

## 🤝 License

MLX42 is licensed under the **MIT License**. You are free to use it in personal and academic projects.

---

## 🙋‍♂️ Maintainers

* Codam Coding College
* 42 Network

---

## 🧪 Example Projects

Check out these public repositories using MLX42:



---

Happy coding with **MLX42**! 🧠🎨

```

