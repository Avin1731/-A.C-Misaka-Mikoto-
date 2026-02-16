<h1 align="center">⚡ [A.C] Misaka Mikoto ~ ⚡</h1>

<p align="center">
  <em>“My Lovely Bot – The Ultimate Railgun for Your Discord Productivity & Music Experience.”</em>
</p>

<p align="center">
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

## 🎵 Overview
**Misaka Mikoto** bukan sekadar bot musik biasa. Dibangun dengan arsitektur **TypeScript** yang modular, bot ini menggunakan **Lavalink v4** sebagai jantung audionya. Dirancang untuk stabilitas tinggi, respon cepat, dan kemampuan bypass algoritma YouTube terbaru.

---

## 🚀 Fitur Utama
* **⚡ High-Voltage Streaming:** Kualitas audio jernih tanpa buffering.
* **📜 Smart Queue:** Sistem antrian cerdas dengan fitur interupsi lagu.
* **🛠️ Modular Engine:** Command handler yang rapi, memudahkan skalabilitas fitur.
* **🛡️ Anti-Block System:** Menggunakan plugin YouTube terbaru (v1.17.0+) untuk menjamin kelancaran playback.
* **🤖 Slash Command Powered:** UI modern menggunakan interaksi resmi Discord.

---

## 📂 Project Anatomy

```text
├── 🛸 lavalink/             # Server audio & configuration
├── 📂 src/
│   ├── ⚔️ commands/         # Slash Command handler
│   │   ├── 🎵 music/        # play.ts, skip.ts, stop.ts
│   │   └── 📈 productivity/ # (Next: Pomodoro, Todo list?)
│   ├── 📅 events/           # (Next: Event handler for trackStart, trackEnd)
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
| `/play` | **Instant Play** | Memutar lagu & mereset antrian |
| `/next` | **Add Queue** | Menambahkan lagu ke daftar tunggu |
| `/skip` | **Skip Track** | Melewati lagu yang sedang aktif |
| `/stop` | **Terminate** | Menghentikan musik & keluar dari Voice |

---

## 🔧 Technical Log (Solved Issues)

* ✅ **Error 400 Bad Request:** Resolved via manual payload wrapping for Lavalink v4.
* ✅ **Silent Audio:** Fixed by implementing `libsodium-wrappers` and `opusscript`.
* ✅ **YouTube Signature Error:** Fixed by upgrading to YouTube-Source v1.17.0.

---

### 📝 The Next Steps (Development Plan)

#### 1. Implementasi Otomatisasi Antrian (`index.ts` & `events`)

* **Target:** Supaya pas lagu selesai, bot otomatis muter lagu berikutnya tanpa lu suruh.
* **Action:** Update `index.ts` untuk dengerin event `trackEnd` dari Shoukaku dan ambil data dari `QueueManager`.

#### 2. Menambah Fitur `/next` (Add to Queue)

* **Target:** Nambahin lagu ke antrian tanpa memutus lagu yang lagi jalan.
* **Action:** Buat file `src/commands/music/next.ts`.

#### 3. Fitur `/queue` (View List)

* **Target:** Biar lu bisa liat ada lagu apa aja yang lagi nunggu.
* **Action:** Buat file `src/commands/music/queue.ts` yang bakal narik data dari `QueueManager`.

#### 4. Enhancing UI (Embeds)

* **Target:** Balesan bot nggak cuma teks polosan, tapi pake **Discord Embed** (ada poster lagu, durasi, dan siapa yang request).
* **Action:** Update semua command musik buat pake `EmbedBuilder`.

#### 5. Productivity Side (The "Productivity" Bot)

* **Target:** Sesuai nama folder lu, kita mulai masuk ke fitur produktivitas.
* **Action:** Bikin `/pomodoro` atau `/reminder` di folder `productivity`.

---
