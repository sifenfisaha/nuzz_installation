# Nuzz Installation

Before you start, put both files in `~/Downloads`:

- `Nuzz.AppImage`
- `nuzz.png` (the icon)

## 1. Move it somewhere permanent and make it executable

```bash
mkdir -p ~/Applications
mv ~/Downloads/Nuzz.AppImage ~/Applications/
chmod +x ~/Applications/Nuzz.AppImage
```

## 2. Run it to check it works

```bash
~/Applications/Nuzz.AppImage --ozone-platform=x11
```

That's all you strictly need. Steps 3 and 4 are only for making it appear in the app launcher.

## 3. Install the icon

```bash
mkdir -p ~/.local/share/icons/hicolor/1024x1024/apps
mv ~/Downloads/nuzz.png ~/.local/share/icons/hicolor/1024x1024/apps/
```

## 4. Create the launcher entry

```bash
cat > ~/.local/share/applications/nuzz.desktop <<EOF
[Desktop Entry]
Name=Nuzz
Exec=$HOME/Applications/Nuzz.AppImage --ozone-platform=x11 %U
Icon=nuzz
Type=Application
Terminal=false
StartupWMClass=nuzz
Categories=Utility;
EOF
```

Now search "Nuzz" in the launcher (Super + Space).
