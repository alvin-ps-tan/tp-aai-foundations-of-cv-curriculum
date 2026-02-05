# Week 1: NumPy Basics & Image Basics

**Computer Vision Fundamentals** — Temasek Poly IIT AAI

---

## Summary

Week 1 is split into **two parts**. First you get comfortable with **NumPy**—the toolkit we use for every image (shape, slicing, stacking, masks). Then you learn **what an image actually is** in the computer: how it’s stored (channels, 8-bit values, BGR vs RGB), how to load and display it, and how to work with it in code. You’ll move from concepts to hands-on tasks—inspecting pixels, splitting channels, and doing a practical **colour-based masking** application in HSV—and finish with **in-class practice** on changing brightness in several ways. The goal is a solid foundation before filtering, detection, and higher-level vision tasks.

**Order:** Do the NumPy notebook (1.1–1.9) first, then the Image notebook (2.1–2.9). Run everything from the `week-1` folder so the sample image path works.

---

## Learning objectives

By the end of Week 1, you will be able to:

**NumPy (Part 1)**  
- Use **shape** and **reshape** (including “flatten” and inferring one dimension) and say why shape matters when working with images.
- Pick out **single pixels**, **rows**, **columns**, and **rectangular regions (ROIs)** using indexing and slicing; know the row–column (y–x) convention.
- **Join** arrays (side by side or one above the other) and build simple **grids** of images with vstack and hstack.
- Use **conditional logic** to turn values into masks (e.g. “above 128 → 255, else 0”).
- **Clip** values to a range so you don’t get overflow when converting back to image format.
- Use **boolean masks** to read or change only certain pixels.
- Create new arrays that have the **same shape** as an existing one (e.g. for masks).

**Image & OpenCV (Part 2)**  
- Explain where **Computer Vision** is used (e.g. security, manufacturing, healthcare, transport, entertainment).
- Distinguish **traditional/classical CV** (rules, edges, thresholds) from **ML/DL** (learning from data), and when each is useful.
- Describe **image data**: channels, **8-bit** depth (0–255), grayscale, **RGB vs BGR** (OpenCV’s order), and how that connects to what we see on screen.
- **Load** an image, **convert BGR to RGB** for display, and **show** it with Matplotlib.
- **Inspect** the image as a NumPy array: shape, dtype, min/max; get the centre pixel and a region of interest.
- Use basic **NumPy** on images: single-pixel indexing, ROI slicing, and channel indexing.
- **Convert** to grayscale and **split** into R, G, B channels; show full colour, grayscale, and single-channel views in subplots.
- Be aware of **storage/transport** (file formats, byte strings in APIs) and encode/decode an image to and from bytes.
- Use **HSV** for **colour-based masking**: choose blue (or other) ranges, build a mask, and show the masked image (e.g. isolate blue sky or water).
- Change **brightness** in several ways (add/subtract, multiply, scale+offset) and use clipping and safe conversion so values stay in range.

---

## Content overview

### Part 1 — NumPy basics (1.1–1.9)

| Section | Topic | What you do |
|--------|--------|------------------|
| **1.1** | Setup and why shape matters | Use shape and reshape (flatten, change layout); see why shape matters for images. |
| **1.2** | Indexing and slicing — ROIs and regions | Get single pixel, row, column; slice a rectangle (ROI); use negative indices; know view vs copy. |
| **1.3** | Concatenate — join arrays along an axis | Join two arrays vertically or horizontally. |
| **1.4** | vstack and hstack — stack into grids | Stack same-size arrays vertically or horizontally (e.g. for grids). |
| **1.5** | np.where — conditional values (thresholds, masks) | Use conditions to produce new values (e.g. threshold to 0 or 255). |
| **1.6** | np.clip — keep values in range | Clip numbers to [0, 255] (or another range) before converting to image type. |
| **1.7** | Boolean indexing and masks | Use a True/False mask to read or set only some pixels. |
| **1.8** | zeros_like, ones_like — same shape as another array | Create arrays that match the shape of an existing one. |
| **1.9** | Summary | Recap of shape, slicing, stacking, where, clip, masks. |

### Part 2 — Image basics & OpenCV (2.1–2.9)

| Section | Topic | What you do |
|--------|--------|------------------|
| **2.1** | Introduction to Computer Vision | Read: history, applications (security, manufacturing, agriculture, healthcare, transport, entertainment), traditional vs ML/DL. |
| **2.2** | Image data representation | Read: channels, 8-bit (0–255), grayscale, RGB/BGR/RGBA, OpenCV BGR, bits/bytes and the screen. |
| **2.3** | Setup: imports and loading | **Task:** Import cv2, numpy, matplotlib; load the sample image; convert BGR→RGB and display. |
| **2.4** | Inspecting the NumPy array | **Task:** Print shape, dtype, min/max; get centre pixel and a ROI; interpret shape as (height, width, channels). |
| **2.5** | Grayscale and channel splitting | **Task (1):** Convert to grayscale, check shape/dtype. **Task (2):** Build R-only, G-only, B-only views; show 5 subplots (RGB, grayscale, red, green, blue). |
| **2.6** | Storage and transport formats | Read: file formats (JPEG, PNG), byte strings in APIs. **Task:** Encode image to bytes and decode back; show original vs decoded. |
| **2.7** | Application: colour-based masking with HSV | Read: what S (saturation) and V (value) mean, with visuals. **Task:** Convert to HSV, set blue range, use inRange, build masked image; show original, mask, and result. |
| **2.8** | In class: ways to darken and brighten | **Task:** Try add/subtract, multiply, and optionally scale+offset; use float, clip, and safe conversion; show in a 2×3 grid. |
| **2.9** | Summary | Read: recap of image-as-array, BGR/RGB, 8-bit, HSV masking, brightness methods, classical vs ML/DL. |

---

## Materials

| File | Purpose |
|------|--------|
| **`numpy_basics_teacher.ipynb`** | **Teacher copy** for Part 1 — full solutions and explanations. Use to teach and show code; students can refer during class. |
| **`numpy_basics_student.ipynb`** | **Student copy** for Part 1 — same structure and explanations, with **Task** prompts and placeholder/comment-only code cells. Fill in (or copy from teacher) as you go. |
| **`image_basics_teacher.ipynb`** | **Teacher copy** for Part 2 — full solutions and explanations. Use to teach and show code. |
| **`image_basics_student.ipynb`** | **Student copy** for Part 2 — same structure and explanations, with **Task** prompts and placeholder/comment-only code cells. Fill in (or copy from teacher) as you go. |
| **`data/marina_bay_sands.jpg`** | Sample image; notebook paths assume you run from the `week-1` directory. |

Teacher and student notebooks are **synchronised**: same section numbers (1.1–1.9 and 2.1–2.9), same text, same order of cells. The student versions add **Task** instructions where you write or complete code.

---

## Prerequisites

- **Python 3** with `opencv-python`, `numpy`, and `matplotlib` installed.
- Run the notebooks from the **`week-1`** directory so that `data/marina_bay_sands.jpg` is found.

---

## Optional enrichment

- Try different **HSV ranges** in the colour-masking application (e.g. orange/red for sunset, green for vegetation).
- Other colour spaces (e.g. LAB, YCbCr) and where they’re used (e.g. video).
- Where **byte strings** or base64 image payloads appear in real systems (APIs, databases) and how to decode them with OpenCV.
