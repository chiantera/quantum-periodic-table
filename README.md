# Quantum Periodic Table

![Version](https://img.shields.io/badge/version-5.0_Gold-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-success)

## ⚛️ Interactive 3D Visualization of the Elements

**Quantum Periodic Table** is an open-source, web-based simulation that visualizes the electron configurations of all 118 elements in real-time.

Unlike standard periodic tables that display static text, this tool renders the actual **quantum probability clouds** ($|\psi|^2$) of electrons as they accumulate around the nucleus. It features a fully automated **"Lecture Mode"** that builds atoms sequentially according to the **Aufbau Principle** and the **Madelung Rule**.

🔗 **[Live Demo](https://chiantera.github.io/quantum-periodic-table/)** 



![gifmobile](https://github.com/user-attachments/assets/2f523450-cade-443d-8bf4-eee506effa6c)

![gif1](https://github.com/user-attachments/assets/882a4861-f090-446e-bc4d-98bc88e4844b)




https://github.com/chiantera/quantum-periodic-table/tree/main/img/screenshot_titanium.jpg
![screenshot_titanium](https://github.com/user-attachments/assets/470cc424-43cd-489d-8290-d1c776ecb1ea)

---

## 🎓 Key Features

### 1. The Aufbau Engine
* **Sequential Filling:** Watch electrons populate orbitals in order of energy levels ($1s \rightarrow 2s \rightarrow 2p \rightarrow 3s \dots$).
* **Lecture Mode:** Automated playback (1.2s intervals) designed for classroom demonstration. Pause, rewind, or scrub through the timeline at any point.
* **Visual Proof:** Observe counter-intuitive filling orders visually (e.g., the Potassium $4s$ shell appearing before the Scandium $3d$ shell fills).

### 2. "Research-Grade" Visualization
* **Monte Carlo Rendering:** Electrons are not depicted as planetary orbits but as **probability density functions**. Thousands of samples are taken per frame to generate physically accurate "clouds."
* **Volumetric Slicing ("MRI Mode"):** A hardware-accelerated clipping plane allows users to slice through the atom in real-time, revealing the internal nodal structure and shell layering.
* **Plasma Bloom:** Post-processing shaders simulate the high-energy glow of electron density, creating distinct visual separation between the dense core and the diffuse valence shells.

### 3. Full Periodic Table Support (Z=1 to Z=118)
* **Dynamic Scaling:** An inverse-density algorithm automatically adjusts particle count to ensure smooth performance whether rendering Hydrogen (1 electron) or Oganesson (118 electrons).
* **Nucleon Packing:** The nucleus is not a static sphere; it simulates the packing of individual protons (Red) and neutrons (Blue) based on isotope stability curves.
* **Extended Orbitals:** Includes approximations for complex $f$-orbitals (Lanthanides/Actinides).

---

## 🛠️ Usage Controls

### Playback
* **▶ SEQUENCE:** Starts the automated buildup from the current element.
* **❚❚ PAUSE:** Freezes the simulation for discussion/inspection.
* **↺ RESET:** Returns to Hydrogen ($Z=1$).

### Inspection
* **Atomic Number (Z) Slider:** Manually scrub to any element.
* **Mouse Drag:** Rotate the camera around the atom.
* **Scroll:** Zoom in/out.
* **Right-Click:** Pan the camera.

### Visual Options
* **Plasma Bloom:** Toggles the glow effect (turn off for a cleaner, wireframe-like view).
* **MRI Cross-Section:** Toggles the X-axis clipping plane to see inside the atom.

---

## 🔬 Scientific Notes & Approximations

To ensure real-time performance in a web browser, this simulation makes specific trade-offs:
1.  **Madelung Rule:** The simulation strictly follows the Madelung $(n+l)$ rule for electron filling. It does not currently account for specific irregular exceptions found in nature (e.g., Copper $[Ar] 3d^{10} 4s^1$ or Chromium $[Ar] 3d^5 4s^1$).
2.  **Orbital Shapes:** $s$, $p$, and $d$ orbitals use exact Spherical Harmonic angular functions. $f$ orbitals are rendered using simplified lobed approximations for visual clarity.
3.  **Radial Distance:** Shell distances are idealized ($r \propto n$) to allow users to visually distinguish layers, rather than using exact radial probability distribution functions which would result in severe visual occlusion.

---

## 💻 Installation (Zero Dependency)

This project is built with **Vanilla JavaScript** and relies on **Three.js** via CDN. There are no build steps, no `npm install`, and no backend requirements.

1.  Clone the repository.
2.  Navigate to the folder.
3.  Open `index.html` in any modern browser.

---

## 📚 Technologies Used

* **Three.js (r128):** WebGL rendering engine.
* **EffectComposer:** Post-processing pipeline (UnrealBloomPass).
* **Tailwind CSS:** UI styling.
* **Custom Shader Logic:** Monte Carlo rejection sampling for probability clouds.

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---
*Developed as an open-source educational tool for visualizing Quantum Mechanics.*
