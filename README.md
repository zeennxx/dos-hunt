# 🎯 DoS-Hunt - Ethical Server Load Tester

<p align="center">
  <strong>Find your limits before attackers do</strong>
</p>

<p align="center">
  <a href="https://www.gnu.org/licenses/gpl-3.0">
    <img src="https://img.shields.io/badge/License-GPLv3-blue.svg" alt="License: GPL v3"/>
  </a>
  <a href="https://www.python.org/downloads/">
    <img src="https://img.shields.io/badge/python-3.9+-blue.svg" alt="Python 3.9+"/>
  </a>
  <a href="https://github.com/ruyynn/dos-hunt/stargazers">
    <img src="https://img.shields.io/github/stars/ruyynn/dos-hunt?style=social" alt="GitHub stars"/>
  </a>
  <a href="https://github.com/ruyynn/dos-hunt/issues">
    <img src="https://img.shields.io/github/issues/ruyynn/dos-hunt" alt="GitHub issues"/>
  </a>
  <a href="https://github.com/ruyynn/dos-hunt/network/members">
    <img src="https://img.shields.io/github/forks/ruyynn/dos-hunt?style=social" alt="GitHub forks"/>
  </a>
</p>

---

## 📋 **DESKRIPSI TOOLS**

**DoS-Hunt** adalah *Ethical Server Load Tester* yang dirancang untuk menguji ketahanan server terhadap lonjakan traffic. Tools ini membantu developer dan sysadmin mengidentifikasi bottleneck, merencanakan kapasitas, dan memvalidasi keandalan server sebelum diluncurkan ke production.

### 🎯 **Yang Bisa Dilakukan DoS-Hunt:**

<div align="center">

| | | |
|:--------------------------:|:--------------------------:|:--------------------------:|
| 📊 **Load Testing** <br> Simulasi traffic tinggi ke server | 🔎 **Bottleneck Detection** <br> Temukan titik lemah infrastruktur | 📈 **Capacity Planning** <br> Tentukan kebutuhan resource |
| 🛡️ **Security Validation** <br> Uji ketahanan terhadap serangan | 📝 **PDF Reports** <br> Laporan profesional siap pakai | 🔒 **Legal Protection** <br> Log forensik & digital signature |

</div>

---

## ⚠️ **DISCLAIMER PENTING**

```diff
+ DoS-Hunt adalah tools untuk PENGUJIAN KEAMANAN yang LEGAL dan ETIS.
! DILARANG KERAS menggunakan tools ini untuk menyerang server orang lain!
! Pastikan Anda memiliki IZIN TERTULIS dari pemilik server sebelum testing.
! Penyalahgunaan tools ini dapat berakibat PIDANA (UU ITE Pasal 33).

© 2026 Ruyynn. GNU GPL v3. Pengguna bertanggung jawab penuh atas penggunaan.
```
---
## ✨ FITUR UTAMA

### 🛡️ Keamanan & Legalitas
| Fitur | Deskripsi |
|-------|-----------|
| ✅ **Whitelist system** | Hanya target yang diizinkan yang bisa di-test |
| ✅ **Peringatan hukum bertingkat** | Informasi risiko sebelum testing |
| ✅ **Log forensik** | Semua aktivitas tercatat untuk bukti legal |
| ✅ **Digital signature** | Laporan ditandatangani kriptografi |
| ✅ **Permission file** | Upload bukti izin tertulis (opsional) |
| ✅ **Forbidden domain detection** | Auto-warning untuk .go.id, .mil.id, dll |

### 📊 Load Testing
| Fitur | Deskripsi |
|-------|-----------|
| ✅ **Gradual loading** | Naik beban perlahan (100 → 5000 req/sec) |
| ✅ **Multi-protocol** | HTTP, HTTPS, TCP, UDP |
| ✅ **Custom headers** | Bawa cookie, token, user-agent |
| ✅ **Real-time metrics** | Response time, error rate, RPS |
| ✅ **Auto-stop** | Berhenti otomatis jika server kritis |
| ✅ **Multiple patterns** | Constant, spike, random |

### 📈 Reporting
| Fitur | Deskripsi |
|-------|-----------|
| ✅ **PDF reports** | Laporan profesional siap presentasi |
| ✅ **JSON/CSV export** | Data mentah untuk analisis lanjutan |
| ✅ **Recommendations** | Saran optimasi server berdasarkan hasil test |
| ✅ **Charts & graphs** | Visualisasi performa |
| ✅ **Legal disclaimer** | Setiap laporan punya bukti legal |

---

## 📦 INSTALASI

### Via pip (recommended)
```bash
pip install doshunt
```

### Via source (untuk development)
```bash
# Clone repository
git clone https://github.com/ruyynn/dos-hunt.git
cd dos-hunt

# Install dependensi
pip install -r requirements.txt

# Install dalam mode development
pip install -e .
```

### Via Docker (coming soon)
```bash
docker pull ruyynn/dos-hunt
docker run -it ruyynn/dos-hunt --help
```

# 🚀 CARA PENGGUNAAN
### Basic Test
```bash
# Test server lokal
doshunt test http://localhost:8080 --rps 100 --duration 30

# Test dengan method POST
doshunt test https://staging-api.com --method POST --rps 50 --data '{"key":"value"}'

# Test dengan custom headers
doshunt test http://localhost:3000 --headers "Authorization: Bearer token123"
```
### Gradual Load Test
```bash
# Naik beban perlahan dari 100 ke 5000 RPS
doshunt gradual http://localhost:3000 --start 100 --end 5000 --step 500

# Dengan stage duration 60 detik
doshunt gradual https://api.server.com --start 200 --end 10000 --step 1000 --stage-duration 60
```

### Manajemen Whitelist
```bash
# Lihat whitelist saat ini
doshunt whitelist show

# Tambah target ke whitelist
doshunt whitelist add staging-server.com
doshunt whitelist add 192.168.1.100

# Hapus dari whitelist
doshunt whitelist remove staging-server.com
```

### Laporan & Logs
```bash
# Generate key pair untuk signature
doshunt keygen

# Lihat status dan statistik
doshunt status

# Lihat logs terbaru
doshunt logs --days 7

# Generate laporan dari test sebelumnya
doshunt report dht-20260316-001 --format pdf
```

## ⚖️ ASPEK LEGAL & ETIKA
DoS-Hunt WAJIB digunakan dengan IZIN TERTULIS dari pemilik server. Melanggar ketentuan ini dapat mengakibatkan konsekuensi hukum serius, baik secara nasional maupun internasional.

### ✅ Yang BOLEH di-test:
```text
🖥️ Server sendiri        → localhost, 127.0.0.1, IP private (192.168.x.x, 10.x.x.x)
🏢 Server perusahaan     → Dengan izin tertulis dari pemilik
🧪 Staging server        → Milik sendiri/tim, bukan production
🔬 Layanan testing       → httpbin.org, postman-echo.com, webhook.site
```

### ❌ Yang TIDAK BOLEH:
```text
🏛️ Situs pemerintah      → .go.id, .mil.id, .polri.go.id, .gov, dll
🛒 Situs komersial       → google.com, tokopedia.com, shopee.co.id, dll (tanpa izin)
🌐 IP publik random      → Bukan milik sendiri
👤 Server orang lain     → Tanpa izin eksplisit tertulis
```

## 📁 STRUKTUR PROYEK
```text
doshunt/
├── 📁 doshunt/                 # Source code utama
│   ├── 📁 core/                # Engine load testing
│   ├── 📁 validation/           # Legal & safety checks
│   ├── 📁 metrics/              # Pengumpulan data
│   ├── 📁 report/               # Generator laporan
│   ├── 📁 utils/                # Utility functions
│   └── 📁 cli/                  # Command line interface
├── 📁 tests/                    # Unit tests
├── 📁 examples/                  # Contoh penggunaan
├── 📁 scripts/                   # Utility scripts
├── 📄 README.md                  # Dokumentasi utama
├── 📄 LICENSE                    # GNU GPL v3
├── 📄 requirements.txt           # Dependensi Python
└── 📄 setup.py                   # Installer
```


## 🤝 Kontribusi

Kontribusi sangat diterima! Lihat [CONTRIBUTING.md](CONTRIBUTING.md) untuk panduan lengkap.

**Cara cepat:**
- 🐛 [Lapor Bug](https://github.com/ruyynn/dos-hunt/issues/new?template=bug_report.md)
- 💡 [Saran Fitur](https://github.com/ruyynn/dos-hunt/issues/new?template=feature_request.md)
- 🔧 [Pull Request](https://github.com/ruyynn/dos-hunt/pulls)
- 📖 [Dokumentasi](CONTRIBUTING.md#-dokumentasi)

[![Contributors](https://img.shields.io/github/contributors/ruyynn/dos-hunt)](https://github.com/ruyynn/dos-hunt/graphs/contributors)

## 💰 DONASI
<div align="center"> <h3>Support Me </h3> <a href="https://saweria.co/Ruyynn"> <img src="https://user-images.githubusercontent.com/26188697/180601310-e82c63e4-412b-4c36-b7b5-7ba713c80380.png" width="200"/> </a> <p> <a href="https://saweria.co/Ruyynn"> <strong> so that it can be further developed </strong> </a> </p>
</div>

## 📞 Kontak

Ada pertanyaan atau ingin diskusi privat? Hubungi saya langsung:

<p align="center">
  <a href="https://web.facebook.com/profile.php?id=61587795784907">
    <img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook" />
  </a>
  <a href="mailto:ruyynn25@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-Click Me-D14836?style=for-the-badge&logo=gmail" />
  </a>
</p>

---

<p align="center"> <strong>Dari Indonesia, untuk keamanan dunia maya yang lebih baik.</strong><br> 🇮🇩 </p><p align="center"> <a href="https://github.com/ruyynn/dos-hunt"> <img src="https://img.shields.io/github/stars/ruyynn/dos-hunt?style=social" /> </a> <a href="https://twitter.com/intent/tweet?text=DoS-Hunt%20-%20Ethical%20Server%20Load%20Tester%20by%20Ruyynn%20(16)%20from%20Indonesia&url=https://github.com/ruyynn/dos-hunt"> <img src="https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Fgithub.com%2Fruyynn%2Fdos-hunt" /> </a> </p>
