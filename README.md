# SpaceSwitcher

A macOS menu-bar app that switches Spaces and remaps a mouse button + swipe gesture to Space / Mission Control navigation.

[中文说明](README.zh.md)

---

## Download

Clone or download this repository, then double-click **SpaceSwitcher.app** to launch.

> **macOS may show "unidentified developer" the first time.**  
> Right-click (or Control-click) → **Open**, then click **Open** in the dialog.

---

## Requirements

- macOS 12 Monterey or later
- **Accessibility** permission (System Settings → Privacy & Security → Accessibility)
- **Input Monitoring** permission (required for the mouse button test window)

---

## First launch

1. Double-click **SpaceSwitcher.app** (or right-click → Open if Gatekeeper blocks it).
2. macOS will prompt for **Accessibility** permission — grant it in System Settings.
3. Relaunch the app.  The cursor-arrow icon (↖) appears in the menu bar.

---

## Menu bar

Click the ↖ icon to open the menu.

| Item | Action |
|------|--------|
| Space Left | Switch to the Space on the left (Ctrl+←) |
| Space Right | Switch to the Space on the right (Ctrl+→) |
| Gesture Remap… | Open gesture settings |
| Test Mouse Buttons… | Open the button debug window |
| Quit | Quit the app |

---

## Gesture remap

Open **Gesture Remap…** from the menu bar.

### Setup

1. **Enable gesture remap** — check the box to activate.
2. **Mouse** — choose a specific mouse, or leave on *Any Mouse* to match all devices.
3. **Button** — the button you hold while swiping (default: Button 4, the typical "Back" button).

### Sensitivity

| Slider | What it controls |
|--------|-----------------|
| Distance | How far (px) you must drag before a space switch fires. Higher = less sensitive. |
| Speed | How fast (px/s) a flick must travel to fire early, before the distance is reached. Higher = less sensitive. |

### Gestures

Hold the configured button and move the mouse:

| Direction | Action |
|-----------|--------|
| Swipe left | Space Left (Ctrl+←) |
| Swipe right | Space Right (Ctrl+→) |
| Swipe up | Mission Control / Space up (Ctrl+↑) |
| Swipe down | App Exposé / Space down (Ctrl+↓) |

**Short click** (hold < 0.3 s with no swipe): the original button click is passed through unchanged.

Settings are saved automatically and restored on next launch.

---

## Mouse button test window

Open **Test Mouse Buttons…** to see raw HID events from your mice. Useful for identifying which button number corresponds to a physical button.

---

## Permissions explained

| Permission | Why it's needed |
|-----------|----------------|
| Accessibility | Allows the app to send key events (Ctrl+Arrow) to switch Spaces, and to intercept/suppress mouse buttons via CGEventTap. |
| Input Monitoring | Allows the app to read raw HID events from mice for the test window and device identification. |

---

## Version

**1.0.0** — macOS 12+

---

## Source code

[github.com/yzhang318/space-switcher-mac](https://github.com/yzhang318/space-switcher-mac)
