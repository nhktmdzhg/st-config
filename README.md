# 🖥️ ST Terminal - Catppuccin Mocha Edition

<div align="center">

![ST Version](https://img.shields.io/badge/ST-0.9.3-blue?style=for-the-badge)
![Theme](https://img.shields.io/badge/Theme-Catppuccin%20Mocha-pink?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTEyIDJDNi40OCAyIDIgNi40OCAyIDEyUzYuNDggMjIgMTIgMjJTMjIgMTcuNTIgMjIgMTJTMTcuNTIgMiAxMiAyWiIgZmlsbD0iI0Y1RTBEQyIvPgo8L3N2Zz4=)
![Build](https://img.shields.io/badge/Build-Optimized-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

**A blazingly fast, aesthetically pleasing terminal emulator**  
*Powered by st-flexipatch with custom optimizations*

</div>

---

## ✨ Features

### 🎨 **Visual Excellence**
- 🌙 **Catppuccin Mocha** color scheme - easy on the eyes
- 💫 **Transparency** support with 90% opacity
- ✨ **Blinking cursor** for better visibility
- 🔤 **Maple Mono NF CN** font with ligature support
- 🖼️ **Sixel** graphics protocol support

### ⚡ **Performance**
- 🚀 **Native CPU optimizations** (`-march=native -O3`)
- 🔗 **Link Time Optimization** (LTO) enabled
- ⚙️ **Minimal latency** configuration
- 🧹 **Stripped unnecessary features** for speed

### 🛠️ **Productivity**
- 🔗 **Clickable URLs** - just click to open
- 📋 **Smart clipboard** integration
- 🔄 **Text reflow** on window resize
- 📁 **Working directory** preservation
- 🚫 **IME disabled** by default (no accidental input method triggers)

## 🚀 Quick Start

### Prerequisites
```bash
# Required packages (Arch Linux)
sudo pacman -S base-devel libx11 libxft libxrender \
               fontconfig freetype2 harfbuzz imlib2

# Required font
yay -S maplemono-nf-cn
```

### Installation
```bash
# Clone the repository
git clone https://github.com/nhktmdzhg/st-config.git
cd st-config

# Build and install
make clean && make
sudo make install
```

## ⌨️ Keybindings

| Key Combination | Action |
|----------------|--------|
| `Ctrl+Shift+C` | Copy selection |
| `Ctrl+Shift+V` | Paste clipboard |
| `Click on URL` | Open in browser |

*Minimal keybindings by design - less is more!*

## 🎨 Color Palette

<table>
<tr>
<td>

**Base Colors**
- Background: `#1E1E2E`
- Foreground: `#CDD6F4`
- Cursor: `#F5E0DC`

</td>
<td>

**Accent Colors**
- Red: `#F38BA8`
- Green: `#A6E3A1`
- Yellow: `#F9E2AF`
- Blue: `#89B4FA`
- Purple: `#F5C2E7`
- Cyan: `#94E2D5`

</td>
</tr>
</table>

## ⚙️ Configuration

### Font Settings
Edit `config.def.h`:
```c
static char *font = "Maple Mono NF CN:pixelsize=16:antialias=true:autohint=true";
```

### Window Size
```c
static unsigned int cols = 128;
static unsigned int rows = 35;
```

### Transparency
```c
float alpha = 0.9;  // 90% opacity
```

## 🔧 Enabled Patches

- **ALPHA_PATCH** - Transparency support
- **BLINKING_CURSOR_PATCH** - Animated cursor
- **CLIPBOARD_PATCH** - System clipboard integration
- **HIDECURSOR_PATCH** - Auto-hide mouse cursor
- **HIDE_TERMINAL_CURSOR_PATCH** - Hide cursor when unfocused
- **LIGATURES_PATCH** - Programming ligatures
- **NO_WINDOW_DECORATIONS_PATCH** - Borderless window
- **OPENURLONCLICK_PATCH** - Clickable URLs
- **REFLOW_PATCH** - Smart text reflow
- **SIXEL_PATCH** - Image protocol support
- **WORKINGDIR_PATCH** - Working directory tracking

## 🏗️ Build Optimizations

```makefile
CFLAGS = -march=native -mtune=native -O3 -pipe -flto=auto \
         -fno-plt -fexceptions -Wp,-D_FORTIFY_SOURCE=2 \
         -Wformat -Werror=format-security \
         -fstack-clash-protection -fcf-protection

LDFLAGS = -Wl,-O3,--sort-common,--as-needed,-z,relro,-z,now -flto=auto
```

## 🐛 Troubleshooting

### Fish shell warnings
The `erresc: unknown` messages from fish shell are harmless and don't affect functionality.

### Font rendering issues
If you encounter font rendering problems, the fix is already applied:
```c
FcPatternAddBool(fcpattern, FC_COLOR, FcFalse);
```

## 📜 License

This project is based on [st-flexipatch](https://github.com/bakkeby/st-flexipatch) and inherits its MIT license.

## 🙏 Credits

- [Suckless Team](https://st.suckless.org/) - Original st terminal
- [bakkeby](https://github.com/bakkeby/st-flexipatch) - st-flexipatch framework
- [Catppuccin](https://github.com/catppuccin) - Beautiful color scheme
- [Maple Font](https://github.com/subframe7536/maple-font) - Clean monospace font

---

<div align="center">

### 🌟 **Show Your Support**

If this configuration helped you create an amazing desktop experience, please consider:

[![Star this repository](https://img.shields.io/github/stars/nhktmdzhg/st-config?style=social)](https://github.com/nhktmdzhg/st-config/stargazers)
[![Fork this repository](https://img.shields.io/github/forks/nhktmdzhg/st-config?style=social)](https://github.com/nhktmdzhg/st-config/network/members)

**Made with 💙 by [ミツキナノカ](https://github.com/nhktmdzhg)**

_Crafted for developers, by developers_

</div>
