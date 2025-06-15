--[[
=============================
ReverbAPI System - v1.2.1 (Added "ReverbAPI_Active" Bool value to ensure the reverb works)
=============================

Credits: Sylzyrical | GibusWeilder (Original concept)

Overview:
This is a dynamic reverb system that automatically detects the player's surroundings using raycasting and the Fibonacci sphere algorithm
to apply environment-accurate reverb presets. It supports both Roblox's new AudioAPI and legacy audio reverb setups.

Features:
- Fibonacci Sphere-based raycasting for accurate environmental detection
- Applies reverb settings to both ambient sounds and voice chat
- Supports both AudioAPI and legacy audio systems

Setup Instructions:
1. Put ReverbAPI system under StarterPlayerScripts:
   - ReverbAPI (Core system)
   -- MaterialsLegacyAudio (Reverb presets for legacy audio)
    -- Materials (Material reverb definitions)
    -- Settings (All configurations for ReverbAPI)
    
2. Create a folder named "Barriers" to make raycast ignore anything inside that folder

3. Tune audio reverb settings to your liking in MaterialPresets (AudioAPI) / LegacyReverbMap (Legacy Sounds)

AudioAPI Preset Example
    ExampleMaterial = {
        DecayTime = 1.4,           -- How long the reverb lasts after the sound stops (1.4 = medium)
                                   -- e.g. 3.0 = long echo (big hall), 0.5 = short echo (small room)
        Density = 0.6,             -- How thick the reverb sounds (0.6 = smooth)
                                   -- e.g. 1.0 = very dense & crowded, 0.2 = thin & airy
        Diffusion = 0.7,           -- How spread out the echoes are (0.7 = natural)
                                   -- e.g. 0.9 = super scattered, 0.3 = tight & focused
        DryLevel = 0,              -- Original sound volume (0 = full)
                                   -- e.g. -6 = quieter original sound
        WetLevel = -9,             -- Reverb effect volume (-9 = subtle)
                                   -- e.g. 0 = loud reverb, -20 = very soft
        HighCutFrequency = 18000,  -- Max high freq kept (18000 = bright)
                                   -- e.g. 8000 = darker reverb
        LowShelfFrequency = 220,   -- Bass cutoff start frequency (220 Hz)
        LowShelfGain = 0,          -- Bass boost/cut (0 = neutral)
                                   -- e.g. 5 = bass boost, -5 = bass cut
    },
}

Performance Tips:
- Adjust NumRays and RayLength for accuracy vs. performance trade-offs
- UpdateInterval controls how often the system samples surroundings
- VisualizeHits and labels help with debugging reverb zones
]]
