# ZMK Keyboard Firmware Configuration

This repository contains the personalized ZMK firmware configuration for a split mechanical keyboard. The layout features custom layer switching and advanced power management behaviors.

## Features

- **Soft Off Support:** Advanced power management configurations.
  - The `hold-time-ms` is configured to `3000` ms (3 seconds) to prevent accidental trigger shutdowns.
  - The `split-peripheral-off-on-press` property is removed from the soft-off behavior to change how the peripheral split half responds.
- **Multi-Layer Layout:** Organized layers optimizing space for numbers, navigation, symbols, and Bluetooth management.

## Keymap Layers

### 1. Base Layer

The default layout uses a standard alphanumeric layout with special navigation and modifier keys placed along the bottom row and inner columns.

```text
------------------------------------------------------------------------------------------------------------

|  ESC  |  1  |  2  |  3   |  4   |  5   |                   |  6   |  7    |  8    |  9   |   0   |   -   |
|  TAB  |  Q  |  W  |  E   |  R   |  T   |                   |  Y   |  U    |  I    |  O   |   P   |   =   |
|  SHIFT|  A  |  S  |  D   |  F   |  G   |                   |  H   |  J    |  K    |  L   |   ;   |   '   |
|  CTRL |  Z  |  X  |  C   |  V   |  B   |   "["  |  |  "]"  |  N   |  M    |  ,    |  .   |   /   |   \   |
                    | LOWER|  GUI | ALT  |  SPACE |  | ENTER| BSPC |  GUI  | RAISE |
```

- **Thumb Cluster Actions:**
  - Hold `LOWER` (Layer 1) to access navigation, page keys, and Bluetooth controls.
  - Hold `RAISE` (Layer 2) to access function keys and media shortcuts.

### 2. Lower Layer

Activated by holding down the `LOWER` key on the bottom row. This layer provides quick access to your navigation shortcuts and Bluetooth profiles.

```text
------------------------------------------------------------------------------------------------------------

|   `   |     |     |      |      |      |                   | BTCLR | BT1   | BT2   | BT3  | BT4   | BT5   |
|       |     |     |      |      |      |                   |       | PG_DN | PG_UP |      |       |       |
|       |     |     |      |      |      |                   |  <-   |   v   |   ^   |  ->  |       |       |
|       |     |     |      |      |      |  Off   |  |       | HOME  |  END  |       |      |       |       |
                    |      |      |      |        |  |       |       |  DEL  |       |
```

- **Bluetooth Management:** The top right row manages device switching (`BT1` to `BT5`) and profile clearing (`BTCLR`).
- **Power Management:** The left inner column features the `Soft Off` power key.

### 3. Raise Layer

Activated by holding down the `RAISE` key on the bottom row. This layer houses function keys and dedicated media controls.

```text
------------------------------------------------------------------------------------------------------------

|  F1   |  F2  |  F3  |  F4  |  F5  |  F6  |                   |  F7  |  F8   |  F9   |  F10 |  F11  |  F12  |
|       |      |      |      |      |      |                   |      |       |       |      |       |       |
|       | PREV |  PP  | NEXT | MUTE |      |                   |      |       |       |      |       |       |
|       |      |      |      |      |      |        |  |       |      |       |       |      |       |       |
                       |      |      |      |        |  |       |      |       |       |
```

- **Media Control block:** The left home row keys control media navigation (`Previous`, `Play/Pause`, `Next`, and `Mute`).

## Build and Flash Instructions

1. **Commit Changes:** Save and commit this `keymap` file to your GitHub config repository.
2. **GitHub Actions:** Allow the automated ZMK compiler workflow to build the firmware `.uf2` files.
3. **Flash Firmware:**
   - Put your keyboard controllers into bootloader mode (usually by double-tapping the physical reset button).
   - Drag and drop the compiled `.uf2` files onto the respective left and right drives.
