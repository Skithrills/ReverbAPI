# 🎧 ReverbAPI System v1.2.1

**Dynamic environmental reverb for Roblox games — powered by raycasting + Fibonacci sphere logic.**
Now includes `ReverbAPI_Active` boolean to ensure the reverb system remains active.
Created by **Sylzyrical** and **GibusWeilder** (original concept).

---

## ✨ Overview

ReverbAPI detects a player's environment using raycasting and applies immersive, real-time reverb effects based on their surroundings.

* Compatible with both **Roblox AudioAPI** and **legacy reverb systems**
* Dynamically adjusts to walls, ceilings, and terrain
* Fully customizable through material presets

---

## 🎯 Features

* 🔵 **Fibonacci Sphere Raycasting** for natural detection spread
* 🎙️ Applies reverb to both **ambient sounds** and **voice chat**
* 🔄 Supports both **AudioAPI** and legacy systems
* ⚙️ Modular setup with easily adjustable configurations

---

## 🛠️ Setup Instructions

1. **Place the `ReverbAPI` folder under `StarterPlayerScripts`**

   ```
   ReverbAPI/
   ├── MaterialsLegacyAudio     # Presets for legacy audio
   ├── Materials                # Definitions for AudioAPI reverb
   └── Settings                 # Main configuration modules
   ```

2. **Create a folder named `Barriers` in Workspace**

   * Raycasts will ignore all objects inside this folder
   * Useful for transparent or pass-through objects

3. **Customize the reverb settings**

   * Use `Materials/MaterialPresets` for **AudioAPI** presets
   * Use `MaterialsLegacyAudio/LegacyReverbMap` for **Legacy audio** settings

---

## 🎚️ AudioAPI Preset Example

```lua
ExampleMaterial = {
    DecayTime = 1.4,           -- Duration of the reverb effect
    Density = 0.6,             -- Perceived thickness of the reverb
    Diffusion = 0.7,           -- Echo spread and distribution
    DryLevel = 0,              -- Volume level of the original sound
    WetLevel = -9,             -- Volume level of the reverb effect
    HighCutFrequency = 18000,  -- Maximum frequency retained in reverb
    LowShelfFrequency = 220,   -- Frequency threshold for bass adjustments
    LowShelfGain = 0,          -- Bass adjustment level
}
```

---

## ⚙️ Performance Tips

* Adjust `NumRays` and `RayLength` for performance vs. precision
* Use `UpdateInterval` to control how often the environment is sampled
* Enable `VisualizeHits` and `LabelsEnabled` for debugging and tuning

---

## 📄 License

This project is open-source. Refer to the [LICENSE](./LICENSE) file for full terms.
Distributed under the MIT License.

---

## 💬 Credits

Created by:

* **Sylzyrical** – System design and implementation
* **GibusWeilder** – Original concept and inspiration

If you find this useful, consider giving the repository a star ⭐ or sharing it with others.
