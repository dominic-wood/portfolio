---
title: QR Code Generator
parent: Projects
nav_order: 3
---

# 📸 QR Code Studio

A simple Python application for generating QR codes with custom styles, templates, and a modern preview interface.

---

## ✨ Features

- 🔗 Generate QR codes from any URL, email, phone number, or WiFi credentials  
- 🎨 Customise foreground and background colours using a visual colour picker  
- 🖌️ Select from built-in design templates (Dark Mode, Colourful, Gradient, etc.)  
- 🖼️ Add a logo image to embed in the centre of your QR code  
- 📏 Adjust QR code size (1–20) and error correction level (Low to Highest)  
- 👁️ Live preview panel with size and metadata display  
- 📋 Copy QR code to clipboard or save as PNG, JPEG, SVG, or PDF  
- 🧠 Automatically formats content (e.g. adds `https://`, `mailto:`, etc.)  
- 🕘 History panel keeps track of recently generated QR codes  
- 🖥️ GUI built with `ttkbootstrap` for a sleek, modern UI  

## 🧱 Project Structure

- **`qr-generator.py`** – Core logic using `qrcode` and `pillow`, with custom SVG export  
- **`app.py`** – GUI built with `tkinter` and `ttkbootstrap`, handling UX, clipboard, theming, and history

## 🖼️ Interface

![QR Code Generator Preview](../../assets/qr_preview.png)

## ⚙️ Requirements

- Python 3.6+
- Required packages:
  - `qrcode`
  - `pillow`
  - `ttkbootstrap`
  - `svgwrite`
  - `requests`
- Optional:
  - `pywin32` (for Windows clipboard support)

> **Note:** `tkinter` is usually bundled with Python.

## 🚀 Installation

```bash
git clone https://github.com/jobbieontheknee/qr-code-generator.git
cd qr-code-generator
pip install qrcode pillow ttkbootstrap svgwrite requests
```
# Optional (Windows only)
```bash
pip install pywin32
```
## 🧪 Usage

1. **Run the application:**
   ```bash
   python app.py
   ```

2. **Enter Content**
   - Paste or type your content (URL, email, phone, etc.)
   - Use quick buttons to insert the appropriate prefix (`https://`, `mailto:`, `tel:`) or configure WiFi.

3. **Customise Appearance**
   - Set foreground/background colours using the visual pickers  
   - Adjust size (1–20) and error correction  
   - Select a template or upload a logo

4. **Generate and Preview**
   - Click **Generate** to view the QR code in the preview panel  
   - Metadata like size and timestamp is shown below

5. **Save, Copy or Test**
   - Save QR as PNG, JPEG, SVG, or PDF  
   - Copy QR to clipboard  
   - Double-click history entries to reload previous QR codes  
   - Use **Test QR Code** to open the URL in your browser or preview content

## ⚙️ Customisation Options

| Parameter           | Description                              | Default Value     |
|---------------------|------------------------------------------|-------------------|
| Content             | URL, email, phone, or WiFi config        | -                 |
| Foreground Colour   | Colour of the QR code                    | `#000000` (black) |
| Background Colour   | Background of the QR code                | `#FFFFFF` (white) |
| Size                | QR size (1–20)                           | 10                |
| Error Correction    | Fault tolerance level                    | High (25%)        |
| Template            | Predefined style (Dark, Colourful, etc.) | Default           |
| Logo                | Optional image in centre                 | None              |

## 🛠️ Troubleshooting

- ❗ **"Invalid URL" error**: Make sure to include the full protocol (e.g. `https://example.com`)  
- 🎨 **Colour not displaying**: Ensure valid hex values (e.g. `#FF0000`) or use the colour picker  
- 🖼️ **Logo not showing**: Confirm the image is supported (PNG, JPG, BMP, etc.)  
- 📋 **Clipboard fails**: May depend on OS and Python version. Try installing `pywin32` on Windows.

## 🤝 Contributing

Contributions are welcome!  
Feel free to open issues, suggest new features, or submit pull requests.

## 📄 License

This project is licensed under the MIT License.  
See the [LICENSE](https://license/) file for details.

## 🙏 Acknowledgements

- [QRCode Python Library](https://github.com/lincolnloop/python-qrcode)  
- [Pillow (PIL Fork)](https://python-pillow.org/)  
- [ttkbootstrap](https://github.com/israel-dryer/ttkbootstrap)  
- [svgwrite](https://github.com/mozman/svgwrite)

## 🔗 GitHub Repo

[View on GitHub](https://github.com/dominic-wood/qr-code-generator)

[← Back to Projects](docs/projects.md)
