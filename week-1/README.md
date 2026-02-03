# Week 1: Image Basics & OpenCV

**Computer Vision Fundamentals** — Temasek Poly IIT AAI
---

## Summary

Week 1 builds intuition for **what an image is** in the computer, how it is **represented in memory**, and how we **manipulate it** with OpenCV and NumPy. Students move from concepts (channels, bit depth, BGR vs RGB) to hands-on inspection (shape, dtype, slicing), then to a practical **application** (colour-based masking in HSV) and **in-class practice** (several ways to change brightness). The goal is a solid foundation before filtering, detection, and higher-level vision tasks.

---

## Learning objectives

By the end of Week 1, students will be able to:

- Explain where Computer Vision is used (security, manufacturing, agriculture, healthcare, transport, entertainment).
- Distinguish **traditional/classical CV** (rules, edges, thresholds) from **ML/DL** (learning from data), and when each is useful.
- Describe **image data representation**: channels, **8-bit** depth (values **0–255**), and how that connects to what we see on screen (bits/bytes, 24-bit colour).
- Explain **grayscale** (single channel), **RGB vs RGBA**, and **OpenCV’s BGR** convention; convert BGR to RGB for display.
- **Load** an image with `cv2.imread`, **display** it with Matplotlib (with correct colour conversion), and **inspect** the underlying NumPy array (shape, dtype, min/max).
- Use basic **NumPy** operations for image work: single-pixel indexing, ROI slicing, and channel indexing (`img[:, :, 0]` etc.).
- Be aware of **storage/transport** options (file formats, byte strings in databases/APIs) and when they matter.
- Use **HSV** for a simple **colour-based masking** application: `cv2.inRange`, mask, and masked image (e.g. isolate blue sky/water).
- Change **brightness** in several ways: add/subtract constant, multiply by factor, scale+offset; use `np.clip` and `astype(np.uint8)` safely.

---

## Content overview

| Section | Topic | What students do |
|--------|--------|------------------|
| **1.1** | Introduction to Computer Vision | Read: history, applications (security, manufacturing, agriculture, healthcare, transport, entertainment), traditional AI vs ML/DL. |
| **1.2** | Image data representation | Read: channels, 8-bit depth (0–255), grayscale, RGB/BGR/RGBA, OpenCV BGR convention, connecting bits/bytes to the screen. |
| **1.3** | Setup: imports and loading | **Task:** Import `cv2`, `numpy`, `matplotlib.pyplot`; load `data/marina_bay_sands.jpg`; convert BGR→RGB and display with Matplotlib. |
| **1.4** | Inspecting the NumPy array | **Task:** Print shape, dtype, min/max; get centre pixel and a ROI; interpret shape as (H, W, C). |
| **1.5** | Grayscale and channel splitting | **Task (1):** Convert to grayscale, print shape/dtype. **Task (2):** Build RGB images with only R, only G, only B; show 5 subplots (RGB, grayscale, red, green, blue). |
| **1.6** | Storage and transport formats | Read: file formats (JPEG, PNG, etc.), byte strings in databases/APIs, `cv2.imdecode` from memory. |
| **1.7** | Application: colour-based masking with HSV | **Task:** Convert to HSV, set `lower_blue`/`upper_blue`, use `cv2.inRange`, build masked image; show original, mask, and masked result in 3 subplots. |
| **1.8** | In class: ways to darken and brighten | **Task:** Implement add/subtract, multiply, and optionally scale+offset; use float, `np.clip`, `astype(np.uint8)`; display in a 2×3 grid. |
| **1.9** | Summary | Read: recap of array representation, BGR/RGB, 8-bit, HSV masking, brightness methods, classical CV + ML/DL. |

---

## Materials

| File | Purpose |
|------|--------|
| **`image_basics_teacher.ipynb`** | **Teacher copy** — Full solutions and explanations. Use this to teach and to show code; students can copy from here during class. |
| **`image_basics_student.ipynb`** | **Student copy** — Same structure and explanations, with **Task** prompts and placeholder/comment-only code cells. Students fill in code (or copy from the teacher copy) as they go. |
| **`data/marina_bay_sands.jpg`** | Sample image; all notebook paths assume it is used from the `week-1` directory. |

Both notebooks are **synchronized**: same 9 sections (1.1–1.9), same conceptual text, same order of cells (23 cells, 9 code cells). The student version adds **Task** instructions where code is to be written or completed.

---

## Prerequisites

- **Python 3** with `opencv-python`, `numpy`, and `matplotlib` installed.
- Run the notebooks from the **`week-1`** directory so that `data/marina_bay_sands.jpg` is found.

---

## Optional enrichment

- Try different **HSV ranges** in the colour-masking application (e.g. orange/red for sunset, green for vegetation).
- Other colour spaces (LAB, YCbCr) and where they are used (e.g. video in YUV).
- Where **byte string** or base64 image payloads appear in real systems (APIs, databases) and how to decode them with OpenCV.
