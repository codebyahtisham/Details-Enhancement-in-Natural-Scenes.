# 🌄 Details Enhancement in Natural Scenes

> A MATLAB GUI application that enhances dark landscape regions in natural scene photographs while preserving sky brightness, using Gaussian filtering, histogram equalization, and selective gamma correction.

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Language](https://img.shields.io/badge/Language-MATLAB-orange)
![Type](https://img.shields.io/badge/Type-University%20Project-blue)
![Course](https://img.shields.io/badge/Course-Digital%20Image%20Processing-purple)

---

## 📌 Overview

Natural scene photographs often suffer from an imbalance between overly bright skies and underexposed dark landscapes, causing critical details to be lost. This project implements a **MATLAB-based GUI** that selectively enhances dark landscape areas using **gamma correction** while preserving the original brightness and texture of the sky. The pipeline applies Gaussian smoothing, sharpening, and histogram equalization as preprocessing steps, then uses **intensity-based region masking** to separate sky from landscape for targeted enhancement.

---

## 🎯 Objectives

- Develop a method to enhance dark landscape regions without affecting bright sky details
- Build an interactive MATLAB GUI for easy image upload, processing, and comparison
- Implement a multi-step pipeline combining smoothing, sharpening, equalization, and gamma correction
- Demonstrate results across diverse natural scene images

---

## ⚙️ Processing Pipeline

```
  ┌──────────────┐     ┌──────────────┐     ┌──────────────────┐
  │ Upload Image │────▶│  Gaussian     │────▶│   Sharpening     │
  │ (RGB)        │     │  Smoothing    │     │   (imsharpen)    │
  └──────────────┘     │  (σ = 2)      │     └────────┬─────────┘
                       └──────────────┘              │
                                                     ▼
                                          ┌──────────────────┐
                                          │    Histogram      │
                                          │   Equalization    │
                                          │  (per-channel)    │
                                          └────────┬─────────┘
                                                   │
                              ┌─────────────────────┼────────────────────┐
                              ▼                     ▼                    │
                     ┌────────────────┐   ┌──────────────────┐          │
                     │  Sky Mask       │   │  Landscape Mask   │          │
                     │ (gray > 235)    │   │  (~sky_mask)      │          │
                     └───────┬────────┘   └────────┬─────────┘          │
                             │                     │                    │
                             │                     ▼                    │
                             │            ┌──────────────────┐          │
                             │            │ Gamma Correction  │          │
                             │            │   (γ = 2.8)       │          │
                             │            └────────┬─────────┘          │
                             │                     │                    │
                             ▼                     ▼                    │
                     ┌─────────────────────────────────────┐            │
                     │  Final Output: Original Sky +        │            │
                     │  Enhanced Landscape (composited)     │            │
                     └─────────────────────────────────────┘
```

---

## 🧰 Tech Stack

| Category        | Tools                                |
|----------------|---------------------------------------|
| Language        | MATLAB                               |
| GUI Framework   | MATLAB GUI (uicontrol, figure, axes) |
| Key Functions   | `imgaussfilt`, `imsharpen`, `histeq`, `rgb2gray` |
| Techniques      | Gaussian Filtering, Histogram Equalization, Gamma Correction, Region Masking |

---

## 🔑 Key Algorithms

| Algorithm                | Purpose                                          |
|-------------------------|--------------------------------------------------|
| **Gaussian Filtering**   | Noise reduction and image smoothing (σ = 2)      |
| **Image Sharpening**     | Restoring edge details lost during smoothing      |
| **Histogram Equalization** | Per-channel contrast enhancement                |
| **Intensity Thresholding** | Sky/landscape segmentation (threshold = 235)    |
| **Gamma Correction**     | Selective brightness boost for dark regions (γ = 2.8) |
| **Region Masking**       | Combining original sky with enhanced landscape    |

---

## 🖥️ GUI Features

The MATLAB GUI provides an interactive workflow with:

- **Upload Image** — Load any natural scene image (JPG, PNG, BMP)
- **Sky + Enhanced Landscape** — One-click processing that segments, enhances, and composites the result
- **Side-by-side comparison** — Original image and enhanced output displayed simultaneously
- **Reset** — Clear all processed images and start fresh

---

## 📊 Results

The method was tested on **8 diverse natural scenes** including sunsets, foggy landscapes, mountain views, and aerial photographs. In all cases, dark landscape regions showed significant detail improvement while sky brightness and texture remained intact.

| Scenario                | Enhancement Quality |
|------------------------|---------------------|
| Sunset with dark foreground | Excellent — landscape details revealed |
| Foggy urban landscape  | Good — buildings and terrain clarified |
| Dense forest at dusk   | Excellent — tree details recovered |
| Colorful wildflower field | Good — maintained vivid colors |
| Mountain with flowers  | Excellent — foreground flora enhanced |
| Dirt road with mountains | Good — path and vegetation visible |
| Aerial hillside view   | Excellent — terrain features sharpened |
| Mountain ridge panorama | Good — balanced sky-land transition |

---

## 📁 Repository Structure

```
├── README.md                             # Project documentation
├── Report.pdf                            # Full lab project report
└── src/
    └── digital_image_processing_gui.m    # Complete MATLAB source code
```

---

## 📄 Documentation

| Document             | Link                            |
|---------------------|---------------------------------|
| 📘 Full Report (PDF) | [View Report](./Report.pdf)     |

---

## 📸 Screenshots

<details>
<summary>Click to view before/after comparisons</summary>

The GUI displays the original image (left) alongside the Sky + Enhanced Landscape output (right). Dark foreground regions are visibly brightened while sky regions retain their original appearance. Results were tested across 8 different natural landscape scenes with varying lighting conditions.

</details>

---

## 👥 Team

| Name              | Roll Number        |
|------------------|--------------------|
| Muhammad Yousaf   | NIM-BSEE-2021-30  |
| Ahtisham Saleem   | NIM-BSEE-2021-19  |

---

## 🏫 Academic Info

| Detail          | Info                                      |
|----------------|-------------------------------------------|
| University      | Namal University, Mianwali                |
| Department      | Electrical Engineering                    |
| Course          | EE-449 (L) Digital Image Processing Lab   |
| Supervisor      | Zulaikha Kiran                            |
| Date            | January 2025                              |

---

## 📬 Contact

- **Email:** engr.ahtishamsaleem@gmail.com
- **LinkedIn:** [Ahtisham Saleem](https://www.linkedin.com/in/ahtisham-salim)
- **GitHub:** [@codebyahtisham](https://github.com/codebyahtisham)

---

<p align="center">
  ⭐ If you found this project interesting, consider giving it a star!
</p>
