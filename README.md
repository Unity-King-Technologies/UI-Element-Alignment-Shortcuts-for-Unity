# UI Element Alignment Shortcuts for Unity

A lightweight Unity Editor tool that **adds customizable keyboard shortcuts to snap UI elements** to specific positions within their parent. Designed to **speed up UI layout workflows** and reduce repetitive clicks in the Editor.

---

## Overview

Building precise UI layouts in Unity often requires **manually dragging RectTransforms** or using the default alignment tools. This is:

- Slow and repetitive
- Error-prone for large UI hierarchies
- Tedious when frequent adjustments are needed

**UI Element Alignment Shortcuts** introduces **keyboard-driven snapping**, letting developers align selected UI elements **instantly** with one hand, improving workflow and precision.

---

## Problem Statement

### Common Issues
- Multiple clicks needed to align objects
- Aligning many elements in complex hierarchies is slow
- Default Unity tools do not support quick keyboard shortcuts
- Inefficient for prototyping, menus, HUDs, and in-game overlays

---

## Solution

A **single editor script** that listens for **key events** in editor mode and snaps **selected UI elements** to predefined positions relative to their parent:

- Top-Left, Top-Center, Top-Right  
- Middle-Left, Middle-Center, Middle-Right  
- Bottom-Left, Bottom-Center, Bottom-Right  

Supports:
- Multi-selection snapping
- Immediate feedback in Scene view
- Configurable shortcuts

---

## Key Features

### Snap Positions
- **9 predefined positions** (like numpad layout) for fast alignment
- Positions relative to parent RectTransform
- Maintains current pivot and anchors

### Keyboard Shortcuts
- Default mapping: `Alt + 1-9` (configurable)
- Supports multi-selection snapping
- Non-intrusive, editor-only key handling

### Multi-Selection Support
- Snap multiple UI elements simultaneously
- Preserves relative offsets if desired (optional)

### Lightweight & Editor-Only
- One script, no additional Editor windows
- Zero runtime overhead
- Compatible with both UGUI and Canvas systems

### Workflow Optimizations
- Save time during HUD, menu, or popup design
- Reduce errors in precise layouts
- Quick adjustments during iterative prototyping

---

## Use Cases

### Game Developers
- Rapidly align UI buttons, panels, and HUD elements
- Standardize layout across screens
- Streamline level UI builds

### UI / UX Designers
- Quickly test multiple alignments
- Ensure consistent padding and spacing
- Reduce repetitive dragging and Inspector adjustments

### Technical Artists / QA
- Validate UI layouts across resolutions
- Fix alignment issues quickly without extra clicks

---

## Technical Architecture

### Folder Structure
```

Editor/
└── UIElementAlignmentShortcuts.cs

```

### Core Components

#### Key Event Listener
- Subscribes to `SceneView.duringSceneGui`
- Detects key presses (Alt + 1-9)
- Checks for selected UI elements

#### Snap Logic
- Computes target position within parent RectTransform
- Adjusts `anchoredPosition` while preserving pivot and size
- Supports optional offset preservation

#### Multi-Selection Handler
- Iterates over all selected elements
- Applies snap logic individually

---

## Installation

### Manual Installation
1. Copy the script to your project:
```

Assets/Editor/UIElementAlignmentShortcuts/

```
2. Open Unity
3. The shortcuts automatically work in the Scene view for selected UI elements

---

## Performance & Safety

- Editor-only execution; no runtime impact
- Minimal overhead even in large scenes
- Undo system integration via `Undo.RecordObject`
- Non-destructive; can revert alignment with standard Undo (`Ctrl+Z`)

---

## Compatibility

- Unity 2020 LTS and above
- UGUI / Canvas system
- Built-in, URP, and HDRP
- Works with version control (Git, Perforce)

---

## 🤝 Contributing

Contributions welcome:
- Shortcut customization improvements
- Performance enhancements
- UI feedback or visualization features

Fork the repo and submit a pull request with proper documentation.

---

## License

MIT License  
Free to use, modify, and distribute in personal or commercial projects.

---

## Why This Tool Matters

This tool exists because **UI alignment should be fast and painless**.  
It empowers developers and designers to:

> *Snap UI elements instantly, reduce repetitive clicks, and maintain precise layouts effortlessly.*

---

## Support & Feedback

Open an issue in the repository for bugs, suggestions, or feature requests.  
Happy and fast UI designing
