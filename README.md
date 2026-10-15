# p53 Clone 3D Interactive Viewer 🧬

Interactive 3D visualization of p53-mutant clone reconstructions from serial immunohistochemistry (IHC) sections.

🔗 **Live Demo**: [https://v1encent.github.io/3D_Clone/](https://v1encent.github.io/3D_Clone/)

<p align="center">
  <img src="qrcode.png" width="180" alt="Scan QR Code to Open on Mobile" />
  <br>
  <em>Scan with smartphone camera to view 3D clones in mobile browser</em>
</p>

---

## 🔬 Dataset Overview

| Sample | Antibody / Condition | Reconstructed Clones | Serial Sections | File Size (Binary PLY) |
| :--- | :--- | :--- | :--- | :--- |
| **PM092** | DO7 (p53) | **3 Clones** (C001, C002, C003) | 10 sections | ~4.2 MB total |
| **PM094** | Actinic Keratosis (AK) | **1 Clone** (Expanded p53 clone) | Serial IHC | ~22.2 MB |

- **Clone C001 (PM092)**: 7.45 × 10⁶ µm³ volume, 4,512 DAB+ nuclei, spans 10 sections (135 µm).
- **Clone C002 (PM092)**: 1.24 × 10⁶ µm³ volume, 873 DAB+ nuclei, spans 9 sections (120 µm).
- **Clone C003 (PM092)**: 2.15 × 10⁵ µm³ volume, 219 DAB+ nuclei, spans 3 sections (30 µm).
- **PM094 Clone**: 527,343 vertices, 1,058,766 faces, depth-encoded vertex color gradient.

---

## 🎮 Controls

### Desktop (Mouse)
- **Left Click + Drag**: Rotate view (orbit around reconstruction center)
- **Scroll Wheel**: Smooth zoom in / out
- **Right Click + Drag**: Pan / translate view

### Mobile / Tablet (Touchscreen)
- **1-Finger Drag**: Rotate view
- **Pinch In / Out**: Zoom
- **2-Finger Drag**: Pan

---

## 🛠️ Architecture & Technologies

- **Engine**: [Three.js r170](https://threejs.org/) via modern ES Modules and Import Maps (no build step, zero dependencies).
- **Loader**: `PLYLoader` supporting optimized **Binary Little-Endian PLY** format.
- **Controls**: `OrbitControls` with smooth damping and inertial physics.
- **Hosting**: GitHub Pages with automatic gzip / brotli compression (~12 MB total transfer).
- **Responsive UI**: Glassmorphic dark theme tailored for both desktop monitors and smartphone displays.

---

## 💻 Local Preview

To run the viewer locally:

```bash
# Using Python built-in HTTP server:
cd 3d_viewer
python -m http.server 8000
```

Then navigate to `http://localhost:8000` in any modern web browser.
