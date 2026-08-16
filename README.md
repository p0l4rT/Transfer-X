# TransferX

> Secure local file transfer from any device. No cloud, no cables, no accounts — just your Wi-Fi network.

---

## What is TransferX?

TransferX turns your Windows PC into a local file-transfer hub. Run it on your computer, then send files from any phone, tablet, or browser connected to the same Wi-Fi network.

- Upload files and folders through the browser.
- Connect as a network drive via WebDAV from Android file managers like MiX Explorer or Solid Explorer.
- Everything is saved to the `uploads/` folder next to the program.

**No internet required** — it works entirely on your local network.

---

## Quick Start

1. Extract the ZIP file to any folder.
2. Double-click **`TransferX.exe`** (or `INICIAR_GUI.bat`) to open the control panel.
3. Click **Start Server**.
4. From your phone or tablet, open the shown URL (for example: `http://192.168.1.100:8765/`).

---

## Control Panel

| Function | Description |
|---|---|
| **Start / Stop Server** | Starts or stops the HTTP + WebDAV server. |
| **Configuration** | Change port, WebDAV user, and max upload size. |
| **Change Password** | Set a password to protect access. |
| **Access URLs** | Shows the exact web and WebDAV URLs with copy buttons. |
| **Uploaded Files** | Lists all files received, with size and date. |
| **Activity Log** | Click the **Activity Log** bar to open or close the live server log. |
| **Open Folder** | Opens the `uploads/` folder in Windows Explorer. |
| **Language** | Switch between English, Spanish, and French instantly. |

---

## Send files from your phone or tablet

### Via web browser

1. Open Chrome, Firefox, or Safari on your device.
2. Type the URL shown in the TransferX window (for example: `http://192.168.1.100:8765/`).
3. Enter the password if required.
4. Select files or folders and click **Send**.

> The web interface supports drag & drop, folder uploads, and an unlimited file queue. You can also switch languages from the web header.

### Via WebDAV (MiX Explorer, Solid Explorer, etc.)

1. In your Android file manager, add a new **WebDAV** connection.
2. Configure:
   - **URL:** `http://<PC_IP>:<PORT>/dav/`
   - **User:** the WebDAV user shown in TransferX (default `transferx`).
   - **Password:** the same password used for the web interface.
3. Browse, copy, and paste files as if it were a local folder on your device.

---

## Configuration

The first time you run TransferX, it creates a `config.json` file next to the program. You can change most settings directly in the GUI, or edit the file manually.

| Setting | Description |
|---|---|
| `port` | Server port (default `8765`). |
| `require_auth` | Require a password to access the interface. |
| `max_upload_mb` | Upload limit in MB. `0` = unlimited. |
| `webdav_enabled` | Enable or disable the WebDAV endpoint. |
| `webdav_user` | Username for WebDAV authentication. |
| `language` | Default interface language: `en`, `es`, or `fr`. |

---

## Troubleshooting

### Cannot connect from my phone
- Make sure both devices are connected to the **same Wi-Fi network**.
- Check that the server is active (green **ACTIVE** badge in the GUI).
- Make sure Windows Firewall is not blocking the port.
- Use `http://` (not `https://`).

### The taskbar shows a generic icon
Make sure `xicon.ico` is in the same folder as `TransferX.exe`.

### Layout looks wrong or texts overlap
Resize the window to at least **860×640**. The GUI is designed to be responsive, but very small windows may clip content.

### Activity Log is empty
The Activity Log is closed by default. Click the **Activity Log** bar to open it. New events will appear while the panel is open.

---

## Frequently Asked Questions

### Does it work without internet?
Yes. TransferX works entirely on your local Wi-Fi network.

### Are my files secure?
- The password is stored as a hash (PBKDF2-HMAC-SHA256).
- Only devices on your same Wi-Fi network can connect.

### Can I upload entire folders?
Yes. In the browser, use **"Choose folder"** to upload whole directories. The folder structure is preserved.

### What if a file already exists?
It is automatically renamed with a numeric suffix: `photo.jpg` → `photo_1.jpg`, `photo_2.jpg`, etc.

### Can I change the port?
Yes, from the GUI or by editing `config.json`. Restart the server after changing it.

---

## License

This project is distributed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

<p align="center">
  <b>TransferX</b> — Secure local transfers, no cables, no cloud.<br>
  Developed by <b>P0l4rT</b>
</p>
