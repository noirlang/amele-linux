<div align="center">
<img src="https://amele.noirlang.tr/amele.png" alt="Amele Logo" width="120" />

# Amele Linux Agent

![Amele Linux Agent Demo](linux.gif)
</div>

## 🇹🇷 Türkçe

Bu depo, **Amele Adli Bilişim Platformu** için geliştirilmiş Linux Agent bileşenidir. Hedef Linux sistemler üzerinde bağımsız çalışarak disk, RAM ve Docker konteyner delillerinin güvenli TCP soketi üzerinden ana Amele uygulamasına aktarılmasını sağlar.

- **Ana Repo:** https://github.com/noirlang/amele
- **Linux Agent Repo:** https://github.com/noirlang/amele-linux
- **Web Sitesi:** https://amele.noirlang.tr

---

### Yetenekler

- **TUI Başlatma Sihirbazı:** Dil (TR/EN), port ve güvenlik anahtarı/parolası yapılandırması.
- **Disk Edinimi:** `/dev/sd*`, `/dev/nvme*`, `/dev/vd*` blok aygıtlarından canlı RAW veya AFF4 formatında bit-by-bit imaj aktarımı.
- **Canlı Hashleme:** İmaj ve RAM transferi sırasında eşzamanlı SHA-256 ve MD5 hash üretimi.
- **RAM Edinimi:** AVML aracılığıyla canlı bellek dökümü (otomatik indirme/kurulum desteği).
- **Docker Konteyner DFIR:** Çalışan/duran konteynerleri listeleme, log çekme, konfigürasyon (`config.v2.json`, `hostconfig.json`) ve Overlay2 UpperDir drift katmanını `.tar.gz` olarak paketleme.

---

### Hazır Binary İndirme

```bash
wget -O amele-linux https://amele.noirlang.tr/amele-linux
chmod +x amele-linux
sudo ./amele-linux
```

---

### Kaynak Koddan Derleme

```bash
python -m venv /tmp/amele-linux-build-venv
/tmp/amele-linux-build-venv/bin/pip install pyinstaller
/tmp/amele-linux-build-venv/bin/pyinstaller --onefile --name amele-linux --distpath dist --workpath build --specpath build linux.py
```

Çıktı: `dist/amele-linux`

---

### Ana Uygulama ile Bağlantı

1. Hedef makinede `sudo ./amele-linux` çalıştırın.
2. Amele masaüstü uygulamasında **Ajan / Uzak Araçlar** ekranına geçin.
3. Hedef IP, Port (varsayılan: `4444`) ve parola/token değerini girerek bağlanın.

---

## 🇬🇧 English

This repository contains the Linux Agent component for the **Amele Digital Forensics Platform**. It runs independently on target Linux systems to stream disk, memory, and Docker evidence to the main Amele desktop application over secure TCP sockets.

- **Main Repo:** https://github.com/noirlang/amele
- **Linux Agent Repo:** https://github.com/noirlang/amele-linux
- **Website:** https://amele.noirlang.tr

---

### Capabilities

- **Interactive TUI Wizard:** Language selection (TR/EN), port configuration, and security key setup.
- **Disk Acquisition:** Live bit-by-bit image streaming from `/dev/sd*`, `/dev/nvme*`, and `/dev/vd*` devices in RAW or AFF4 formats.
- **Live Hashing:** Simultaneous on-the-fly SHA-256 and MD5 checksum computation.
- **RAM Acquisition:** Volatile memory capture via AVML (with automatic download/install assistance).
- **Docker & Container DFIR:** Container listing, log extraction, raw runtime configs (`config.v2.json`, `hostconfig.json`), and Overlay2 UpperDir runtime drift packaging into `.tar.gz`.

---

### Download Prebuilt Binary

```bash
wget -O amele-linux https://amele.noirlang.tr/amele-linux
chmod +x amele-linux
sudo ./amele-linux
```

---

### Build from Source

```bash
python -m venv /tmp/amele-linux-build-venv
/tmp/amele-linux-build-venv/bin/pip install pyinstaller
/tmp/amele-linux-build-venv/bin/pyinstaller --onefile --name amele-linux --distpath dist --workpath build --specpath build linux.py
```

Output: `dist/amele-linux`

---

### Connect with Main App

1. Run `sudo ./amele-linux` on the target machine.
2. Open the **Agent / Remote Tools** tab in Amele desktop application.
3. Enter the target IP, Port (default: `4444`), and optional security token.

