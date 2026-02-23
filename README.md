<h1 align="center">⚡ [A.C] Misaka Mikoto ~ ⚡</h1>

<p align="center">
  <em>“My Lovely Bot – The Ultimate Railgun for Your Discord Productivity & Music Experience.”</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-In%20Development%20(Coming%20Soon)-yellow.svg" alt="Status">
  <img src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" alt="Maintained">
  <img src="https://img.shields.io/badge/TypeScript-Ready-blue.svg" alt="TypeScript">
  <img src="https://img.shields.io/badge/Lavalink-v4.1.2-orange.svg" alt="Lavalink">
  <img src="https://img.shields.io/badge/Shoukaku-v4-red.svg" alt="Shoukaku">
</p>

<p align="center">
  <b>Connect with the Developers:</b><br><br>
  <a href="https://github.com/avin1731">
    <img src="https://img.shields.io/badge/⚡%20Developer-Avin1731-blueviolet?style=for-the-badge&logo=github" />
  </a>&nbsp;
  <a href="https://github.com/Xte-1412">
    <img src="https://img.shields.io/badge/⚡%20Developer-Xte--1412-444?style=for-the-badge&logo=github" />
  </a>
</p>

<p align="center">
  <i>"Developed with ❤️ for productivity and music lovers."</i>
</p>

---

> ⚠️ **PEMBERITAHUAN:** Bot ini masih dalam tahap **Active Development** dan belum dirilis secara publik. Pantau terus *repository* ini untuk *update* perilisan resminya. *Coming soon and stay tuned!*

---

## 🎵 Overview
**Misaka Mikoto** bukan sekadar bot musik biasa. Dibangun dengan arsitektur **TypeScript** yang modular, bot ini menggunakan **Lavalink v4** sebagai jantung audionya. Dirancang untuk stabilitas tinggi, respon cepat, dan kemampuan bypass algoritma YouTube terbaru.

---

## 🚀 Fitur Utama
* **⚡ High-Voltage Streaming:** Kualitas audio jernih tanpa buffering.
* **📜 Smart Queue & Standby Mode:** Sistem antrian cerdas yang mengalir mulus, lengkap dengan status *Standby* saat bot menganggur di Voice Channel.
* **🛠️ Modular Engine:** Command handler yang rapi, memudahkan skalabilitas fitur.
* **🛡️ Anti-Block System:** Menggunakan plugin YouTube terbaru (v1.17.0+) untuk menjamin kelancaran playback.
* **🤖 Slash Command Powered:** UI modern menggunakan interaksi resmi Discord (Embeds & Visual Progress Bar).

---

## 📂 Project Anatomy

```text
├── 🛸 lavalink/             # Server audio & configuration
├── 📂 src/
│   ├── ⚔️ commands/         # Slash Command handler
│   │   ├── 🎵 music/        # play, skip, stop, next, queue, nowplaying, invite, bye, info
│   │   └── 📈 productivity/ # (Next: Pomodoro, Todo list?)
│   ├── 📅 events/           # Client & Node event handlers
│   ├── 🧬 interfaces/       # Command.ts
│   ├── 🧠 services/         # QueueManager.ts
│   ├── 🏗️ struct/           # BotClient.ts
│   ├── 🛠️ utils/            # config.ts
│   └── 🚀 index.ts          # Entry point

```

---

## 🛠️ Installation & Setup

### 1. Jantung Audio (Lavalink)

1. Pastikan **Java 17/21** sudah terpasang.
2. Edit `lavalink/application.yml` dan pastikan plugin terbaru aktif:

```yaml
- dependency: "dev.lavalink.youtube:youtube-plugin:1.17.0"

```

3. Jalankan mesin:

```bash
java -jar Lavalink.jar

```

### 2. Otak Bot (Node.js)

1. Install dependencies:

```bash
npm install

```

2. Setup Environment:

```env
DISCORD_TOKEN=your_top_secret_token

```

3. Jalankan bot:

```bash
npm run dev

```

---

## 📝 Command List

| Trigger | Action | Impact |
| --- | --- | --- |
| `/play` | **Instant Play** | Memutar lagu langsung & mereset antrian |
| `/next` | **Add Queue** | Menambahkan lagu ke dalam antrian berikutnya |
| `/skip` | **Skip Track** | Melewati lagu saat ini dan memutar antrian selanjutnya |
| `/stop` | **Standby Mode** | Menghentikan musik, hapus antrian, masuk Mode Standby 🟢 |
| `/queue` | **View List** | Menampilkan daftar antrian lagu saat ini |
| `/nowplaying` | **Track Info** | Menampilkan detail lagu dan *progress bar* |
| `/invite` | **Summon Bot** | Memanggil bot ke Voice Channel untuk *Standby* |
| `/bye` | **Terminate** | Mengeluarkan bot dari VC & membersihkan memori |
| `/info` | **Command Center** | Menampilkan panel informasi seluruh komando bot |

---

## 🔄 Update History (Changelog)

* **v1.0.2** - *Smart Queue & Standby Integration:* Implemented queue system & standby mode, added `/next`, `/queue`, `/nowplaying`, `/invite`, `/bye`, `/info`, and updated logic for existing music controls.
* **v1.0.1** - *Core Initialization:* Setup initial bot architecture with Lavalink and base music system.

---

## 🔧 Technical Log (Solved Issues)

* ✅ **Error 400 Bad Request:** Resolved via manual payload wrapping for Lavalink v4.
* ✅ **Silent Audio:** Fixed by implementing `libsodium-wrappers` and `opusscript`.
* ✅ **YouTube Signature Error:** Fixed by upgrading to YouTube-Source v1.17.0.
* ✅ **Automated Queue System:** Implemented `QueueManager` and integrated `end` event listeners to auto-play queued tracks.
* ✅ **Standby Architecture:** Separated the `/stop` logic (idle in VC) from `/bye` (disconnect). Handled empty queues gracefully by forcing memory wipe (`encoded: null`).
* ✅ **Lavalink Track Decoding:** Resolved TypeScript errors in Shoukaku v4 by implementing `node.rest.decode(player.track)` to safely fetch song titles and durations.
* ✅ **UI Enhancements:** Migrated responses to Discord EmbedBuilder to provide a premium user experience.

---

### 🚀 The Next Steps (Development Plan)

#### 1. Productivity Side (The Core Identity)

* **Target:** Karena nama bot ini mengandung unsur "productivity", kita perlu fitur untuk menemani user fokus bekerja/belajar.
* **Action:** Buat sistem timer `/pomodoro` (25 menit kerja, 5 menit istirahat) lengkap dengan notifikasi suara saat waktu habis.

#### 2. Auto-Disconnect System (Save Resources)

* **Target:** Bot tidak boleh terus-terusan diam di VC jika semua orang sudah keluar atau tidak ada lagu selama kelamaan.
* **Action:** Buat *timer* otomatis di Mode Standby. Jika tidak ada aktivitas selama 5 menit, bot akan otomatis mengeksekusi fungsi `/bye`.

#### 3. Multi-Source Integrations

* **Target:** Supaya user tidak hanya bisa nge-*play* dari YouTube, tapi juga dari *platform* lain.
* **Action:** Mengaktifkan dan mengonfigurasi plugin **Spotify** atau **SoundCloud** di `application.yml` milik Lavalink.

#### 4. Fitur Lirik Lagu

* **Target:** Menampilkan lirik dari lagu yang sedang diputar.
* **Action:** Integrasi API lirik pihak ketiga (seperti Ksoft atau Lyrical) via command `/lyrics`.

---
