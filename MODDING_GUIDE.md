# Anabel in Sonic Classic Games - Modding Guide

This document provides a detailed guide for integrating Anabel as a playable character across various Sonic Classic Games, ROM hacks, and modern engines. It outlines the technical requirements, necessary tools, and general modding approaches for each platform.

## 🎮 Supported Games & Engines Overview

| Game / Engine | Release Year | Platform | Mod Type | Key Modding Tool(s) |
| :--- | :--- | :--- | :--- | :--- |
| **Sonic 1** | 1991 | Sega Genesis | ROM Hack | SonLVL, Hivebrain/ASMNK Disassemblies |
| **Sonic 1 Classic** | 2013 | Mobile (RSDK v4) | Decompilation Mod | RSDK Animation Editor, SpriteSheet tools |
| **Sonic 1 Forever** | 2024 | PC (Community Decomp) | Engine Enhancement | RSDK Animation Editor, SpriteSheet tools |
| **Sonic CD** | 1993 | Sega CD | ROM Hack | Custom CD Modding Tools (e.g., Retrun) |
| **Sonic CD Classic** | 2011 | PC/Mobile (RSDK v3) | Decompilation Mod | RSDK Animation Editor, SpriteSheet tools |
| **Sonic CD Miracle Edition** | 2023 | PC (Community Overhaul) | Engine Overhaul Mod | RSDK Animation Editor, SpriteSheet tools |
| **Sonic 2** | 1992 | Sega Genesis | ROM Hack | SonLVL, Hivebrain/ASMNK Disassemblies |
| **Sonic 2 Classic** | 2013 | Mobile (RSDK v4) | Decompilation Mod | RSDK Animation Editor, SpriteSheet tools |
| **Sonic 2 Absolute** | 2023 | PC (Community Decomp) | Engine Enhancement | RSDK Animation Editor, SpriteSheet tools |
| **Sonic 3 & Knuckles** | 1994 | Sega Genesis | ROM Hack | SonLVL, Hivebrain/ASMNK Disassemblies |
| **Sonic 3 A.I.R.** | 2024 | PC (Modern Engine) | Modern Engine Mod | Image Editor (Aseprite), JSON Editor |
| **Sonic Mania Plus** | 2018 | PC (Modern RSDK v5) | Modern Engine Mod | RSDK Animation Editor, SpriteSheet tools |

## 🛠️ Detailed Technical Requirements and Modding Approaches

### **1. Genesis ROM Hacks (Sonic 1, Sonic 2, Sonic 3 & Knuckles, Sonic CD)**

For the original Genesis and Sega CD ROMs, modding involves direct manipulation of the game's binary code and assets. This is generally the most complex approach.

-   **Tools:**
    -   **SonLVL:** A level editor for classic Sonic games, often used for importing and exporting graphics [1].
    -   **Hivebrain/ASMNK Disassemblies:** These provide a disassembled version of the game's code, allowing for direct code modifications. Knowledge of 68k assembly is often required.
    -   **Custom CD Modding Tools (e.g., Retrun for Sonic CD):** Specific tools may exist for Sonic CD to handle its unique data structure [2].
-   **File Formats:**
    -   **Graphics:** Typically 4-bpp (16-color) tiled graphics. Sprites need to be carefully crafted within these limitations.
    -   **Code:** Assembly language (`.asm`) files for logic changes.
-   **Approach:**
    1.  **Sprite Creation:** Design Anabel's sprites within the 16-color palette limitation, ensuring all animations (running, jumping, attacking, etc.) are covered.
    2.  **Art Importation:** Use tools like SonLVL to import the new sprite tiles into the ROM.
    3.  **Code Modification:** Modify the game's assembly code to recognize Anabel as a playable character, assign her unique abilities, and link her animations and palettes. This often involves finding unused character slots or replacing existing ones.

### **2. Retro Engine (RSDK) Mods (Sonic 1 Classic, Sonic CD Classic, Sonic 2 Classic, Sonic 1 Forever, Sonic 2 Absolute, Sonic CD Miracle Edition, Sonic Mania Plus)**

The Retro Engine, developed by Christian Whitehead, powers the mobile ports of Sonic 1, 2, and CD, as well as Sonic Mania. Its decompilations and community enhancements (like Sonic 1 Forever and Sonic 2 Absolute) offer more accessible modding capabilities.

-   **Tools:**
    -   **RSDK Animation Editor:** Essential for creating and editing character animations within the RSDK framework.
    -   **SpriteSheet Tools:** For preparing `.gif` or `.png` sprite sheets with specific indexed palettes. Tools like Aseprite are highly recommended for pixel art and sprite sheet management.
-   **File Formats:**
    -   **Graphics:** `.gif` or `.png` sprite sheets. These typically require specific indexed palettes to match the game's rendering.
    -   **Data:** RSDK-specific data files for animations, character properties, and level interactions.
-   **Approach:**
    1.  **Sprite Sheet Preparation:** Create comprehensive sprite sheets for Anabel, including all necessary frames for movement, actions, and expressions. Ensure correct palette indexing.
    2.  **Animation Definition:** Use the RSDK Animation Editor to define Anabel's animations, linking sprite frames to specific actions and timings.
    3.  **Character Integration:** Modify existing character data or create new character definitions within the RSDK framework to incorporate Anabel. This often involves editing `.json` or similar configuration files that define character properties, abilities, and how they interact with the game world.

### **3. Sonic 3 A.I.R. (Angel Island Revisited)**

Sonic 3 A.I.R. is a fan-made PC port of Sonic 3 & Knuckles with extensive modding support, offering a modern and flexible environment for custom characters.

-   **Tools:**
    -   **Image Editor (Aseprite recommended):** For creating and editing Anabel's sprite sheets. Aseprite is popular for its pixel art capabilities and sprite sheet management features.
    -   **JSON Editor:** For editing `mod.json` and other configuration files that define character properties and behaviors.
-   **File Formats:**
    -   **Graphics:** `.png` sprite sheets.
    -   **Data:** `.json` files for character metadata, animations, and custom scripts.
-   **Approach:**
    1.  **Sprite Sheet Creation:** Develop high-quality `.png` sprite sheets for Anabel, covering all animations. Sonic 3 A.I.R. often supports higher resolutions than the original Genesis games.
    2.  **`mod.json` Configuration:** Create or modify the `mod.json` file to define Anabel as a new character. This includes specifying her sprite sheet paths, animation definitions, and unique abilities.
    3.  **Custom Scripting:** Implement any unique character mechanics or abilities using custom script files (often in a Lua-like syntax) that interact with the Sonic 3 A.I.R. engine.

## 🤝 Community Resources

Joining the relevant modding communities is crucial for support, sharing knowledge, and discovering new tools. Here are some recommended Discord servers:

-   **Retro Engine Modding:** [Join Server](https://dc.railgun.works/retroengine) (For Sonic 1 Forever, Sonic 2 Absolute, and general RSDK mods)
-   **Sonic 3 A.I.R. Official:** [Join Server](https://dc.railgun.works/s3air)
-   **Sonic Mania Modding:** [Join Server](https://discord.gg/sonicmania)
-   **Sonic Retro:** [Join Server](https://discord.gg/sonicretro)

## 📚 References

[1] SonLVL - Sonic Retro Wiki. (n.d.). Retrieved from [https://info.sonicretro.org/SonLVL](https://info.sonicretro.org/SonLVL)
[2] Guide :: Modding Sonic CD With Retrun. (2017, December 10). Steam Community. Retrieved from [https://steamcommunity.com/sharedfiles/filedetails/?id=1228120176](https://steamcommunity.com/sharedfiles/filedetails/?id=1228120176)
