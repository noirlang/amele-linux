# Worm Linux Agent

![Worm Linux Agent Demo](linux.gif)

## Turkce

Bu depo, Worm ana uygulamasi icin Linux Agent bileşenini icerir.

- Ana repo: https://github.com/noirlang/worm
- Linux Agent repo: https://github.com/noirlang/worm-linux
- Web sitesi: https://worm.noirlang.tr

### Hazir Binary Indirme

```bash
wget -O worm-linux https://worm.noirlang.tr/worm-linux
chmod +x worm-linux
```

### Linux Binary Derleme

```bash
python -m venv /tmp/worm-linux-build-venv
/tmp/worm-linux-build-venv/bin/pip install pyinstaller
/tmp/worm-linux-build-venv/bin/pyinstaller --onefile --name worm-linux --distpath dist --workpath build --specpath build linux.py
```

Cikti dosyasi:

```text
dist/worm-linux
```

### Calistirma

```bash
./worm-linux
```

### Ana Uygulama ile Baglanti

1. Worm masaustu uygulamasinda Linux araclari ekranina gecin.
2. Agent'in dinledigi IP/Port degerlerini uygulamaya girin.
3. Token kullaniyorsaniz ayni tokeni uygulamaya da girin.
4. Baglanti ve edinim adimlarini baslatin.

---

## English

This repository contains the Linux Agent component for the Worm main application.

- Main repo: https://github.com/noirlang/worm
- Linux Agent repo: https://github.com/noirlang/worm-linux
- Website: https://worm.noirlang.tr

### Download Prebuilt Binary

```bash
wget -O worm-linux https://worm.noirlang.tr/worm-linux
chmod +x worm-linux
```

### Build Linux Binary

```bash
python -m venv /tmp/worm-linux-build-venv
/tmp/worm-linux-build-venv/bin/pip install pyinstaller
/tmp/worm-linux-build-venv/bin/pyinstaller --onefile --name worm-linux --distpath dist --workpath build --specpath build linux.py
```

Output:

```text
dist/worm-linux
```

### Run

```bash
./worm-linux
```

### Connect with Main App

1. Open the Linux tools section in the Worm desktop app.
2. Enter the agent IP/Port values.
3. If token security is enabled, use the same token in the app.
4. Start connection and acquisition workflows.
