# Multi-Stage Docker Build

This project demonstrates how **multi-stage Docker builds** can significantly reduce the size of a Docker image.

A simple **Go application** is used for this example because Go applications can be compiled into a standalone binary. This makes Go well suited for running in a minimal final container image without requiring the Go compiler or other build tools at runtime.

## Project Overview

Two Docker build approaches are compared:

* **Single-stage build** – the compiler, dependencies, and build environment remain in the final image.
* **Multi-stage build** – the application is compiled in a separate build stage, and only the compiled binary is copied into a minimal final image using `scratch`.

## Image Size Comparison

| Build                     | Image Size |
| ------------------------- | ---------: |
| Without multi-stage build |   ~1.01 GB |
| Multi-stage build         |   ~3.94 MB |

The multi-stage build removes unnecessary build tools and dependencies from the final image, resulting in a **much smaller and more lightweight container**.

## Technologies Used

* Docker
* Go
* AWS EC2
* Multi-stage Docker builds


