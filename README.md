# Amele Linux Agent

![Amele Linux Agent Demo](linux.gif)

## Turkce

Bu depo, Amele ana uygulamasi icin Linux Agent bileşenini icerir.

- Ana repo: https://github.com/noirlang/amele
- Linux Agent repo: https://github.com/noirlang/amele-linux
- Web sitesi: https://amele.noirlang.tr

### Hazir Binary Indirme

```bash
wget -O amele-linux https://amele.noirlang.tr/amele-linux
chmod +x amele-linux
```

### Linux Binary Derleme

```bash
python -m venv /tmp/amele-linux-build-venv
/tmp/amele-linux-build-venv/bin/pip install pyinstaller
/tmp/amele-linux-build-venv/bin/pyinstaller --onefile --name amele-linux --distpath dist --workpath build --specpath build linux.py
```

Cikti dosyasi:

```text
dist/amele-linux
```

### Calistirma

```bash
./amele-linux
```

### Ana Uygulama ile Baglanti

1. Amele masaustu uygulamasinda Linux araclari ekranina gecin.
2. Agent'in dinledigi IP/Port degerlerini uygulamaya girin.
3. Token kullaniyorsaniz ayni tokeni uygulamaya da girin.
4. Baglanti ve edinim adimlarini baslatin.

---

## English

This repository contains the Linux Agent component for the Amele main application.

- Main repo: https://github.com/noirlang/amele
- Linux Agent repo: https://github.com/noirlang/amele-linux
- Website: https://amele.noirlang.tr

### Download Prebuilt Binary

```bash
wget -O amele-linux https://amele.noirlang.tr/amele-linux
chmod +x amele-linux
```

### Build Linux Binary

```bash
python -m venv /tmp/amele-linux-build-venv
/tmp/amele-linux-build-venv/bin/pip install pyinstaller
/tmp/amele-linux-build-venv/bin/pyinstaller --onefile --name amele-linux --distpath dist --workpath build --specpath build linux.py
```

Output:

```text
dist/amele-linux
```

### Run

```bash
./amele-linux
```

### Connect with Main App

1. Open the Linux tools section in the Amele desktop app.
2. Enter the agent IP/Port values.
3. If token security is enabled, use the same token in the app.
4. Start connection and acquisition workflows.
