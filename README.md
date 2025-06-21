# 🖱️ Barrier Installation Guide (Linux)

**Kontrol banyak laptop dengan satu mouse dan keyboard**

---

## 📦 Apa Itu Barrier?

**Barrier** adalah aplikasi open-source yang memungkinkan kamu mengontrol beberapa komputer dengan **satu set mouse dan keyboard**, seperti **Synergy**, tetapi gratis.

Kamu bisa menggerakkan kursor antar komputer seolah-olah layar mereka adalah monitor tambahan.

---

## 🖥️ Sistem yang Didukung

* ✅ Windows
* ✅ macOS
* ✅ Linux (Arch, Ubuntu, Fedora, dsb)

---

## 🚀 Instalasi di Arch Linux / Archcraft

### 1. **Install dependencies**

```bash
sudo pacman -S git base-devel debugedit
```

> `debugedit` dibutuhkan untuk build paket dengan debug symbol.

---

### 2. **Install via AUR (menggunakan yay)**

```bash
yay -S barrier
```

> Jika belum punya `yay`, install dulu:

```bash
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

---

## 🔧 Konfigurasi Barrier

### 1. **Menentukan Peran Komputer**

* **Server** = Laptop/PC yang punya mouse & keyboard utama.
* **Client** = Komputer kedua yang akan dikontrol.

---

### 2. **Jalankan Barrier**

```bash
barrier
```

### 3. **Server Mode**

* Pilih "Server"
* Atur posisi client di grid layar (misal di kanan)
* Start server

### 4. **Client Mode**

* Pilih "Client"
* Masukkan IP Address dari server (cek dengan `ip a`)
* Start client

---

## 🌐 Tips Koneksi LAN (dengan kabel langsung)

Kalau dua laptop pakai **kabel LAN langsung**, lakukan:

* Set IP manual:

  * Laptop 1 (server): `192.168.1.1`
  * Laptop 2 (client): `192.168.1.2`
* Subnet: `255.255.255.0`
* Gateway bisa kosong

---

## 🔁 Autostart (Opsional)

Kamu bisa menambahkan Barrier ke autostart supaya otomatis jalan saat boot. Tergantung DE:

### Untuk i3, bspwm, atau WM:

Tambahkan ke `.xprofile` atau `autostart.sh`:

```bash
barrier --no-tray &
```

### Untuk GNOME/KDE:

Buat `.desktop` entry di `~/.config/autostart/`

---

## 🛠️ Troubleshooting

### ❌ Error: `Cannot find the debugedit binary`

**Solusi:**

```bash
sudo pacman -S debugedit
```

### ❌ Cursor tidak pindah ke client

* Pastikan IP benar
* Cek firewall
* Pastikan Barrier running di kedua sisi
* Coba disable SSL di setting

---

## 📋 Referensi

* GitHub: [https://github.com/debauchee/barrier](https://github.com/debauchee/barrier)
* Wiki Arch: [https://wiki.archlinux.org/title/Barrier](https://wiki.archlinux.org/title/Barrier)
