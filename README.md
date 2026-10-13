# 🌍 Diplomatic Activity Tracker
### Diplomatik Temas Haritası

**An interactive map of high-level diplomatic meetings, with searchable weekly and monthly archives.**

**🌐 [Visit the live website](https://muhammed1187ad-svg.github.io/diplomatic-tracker/)**

## What is this project?

Diplomatic Activity Tracker is a public research tool for exploring **where high-level diplomatic meetings take place, who attends them, and what is discussed**.

It brings meeting records from government announcements and other reputable sources into one interactive world map. Instead of browsing dozens of separate announcements, visitors can explore meetings by **location, date, country, participant, or topic**.

The project began with a September 2026 map and is being expanded with weekly updates. It is intended for researchers, students, journalists, policy professionals, and anyone interested in international affairs.

## What can visitors do?

- 🗺️ **Explore the world map:** Each numbered marker shows how many recorded meetings are associated with that location.
- 📍 **Open meeting details:** Select a marker to see the date, participants, short description, and original source link.
- 📅 **Browse previous weeks and months:** New weekly records are added without removing earlier archives.
- 🔎 **Search and filter:** Find meetings by country, leader, city, or subject; switch between **İkili** (bilateral) and **Çok taraflı** (multilateral) events.
- 📥 **Download CSV data:** Export the currently filtered meetings for your own research.

### Using the map on a phone

The mobile interface has three sections: **Harita** (Map), **Görüşmeler** (Meetings), and **Filtreler** (Filters).

- **One finger:** Drag to move around the map.
- **Two fingers:** Pinch to zoom in or out.
- **Tap a city marker:** Open the meetings recorded there.
- **Filtreler:** Choose a month, week, meeting type, or search term.

On desktop, the map and browsing controls appear side by side.

## What meetings are included?

The tracker focuses on **completed, in-person high-level diplomatic meetings and visits**, particularly those involving presidents, prime ministers, foreign ministers, and defence ministers in the countries being monitored. Bilateral meetings and multilateral events are classified separately.

Routine phone calls, future visit announcements, and meetings involving only lower-ranking officials are excluded from new weekly reporting. Each record includes a link to its source where available.

> **Data notice:** The 152 September 2026 entries originated from the first version of the map and **have not all been independently rechecked**. The October archive initially contains a selected set of sourced meetings, not an exhaustive worldwide survey. Please consult the linked original source for important research or publication. This is an independent project, not an official government website.

## How is the website built?

This is a **static GitHub Pages website**: no account, subscription, or separate application is needed to view it.

- **`index.html`** is the website itself. It contains the map, interface, mobile touch controls, filters, meeting panels, and code that loads new weekly records.
- **`data/weeks/`** contains the weekly `.json` files with meeting details.
- **`README.md`** is this project guide, displayed on GitHub.

The website builds its monthly and weekly archive from the dates in the available records. **Adding a new weekly JSON file does not require editing `index.html`.**

## 🔄 How to update the map each Monday

This section is for the person maintaining the website. Visitors do not have to do anything.

1. **Prepare last week's records.** For example, on Monday **19 October 2026**, report on **12–18 October**.
2. **Get the weekly JSON file.** Its name is the **Monday when that reporting week began**: in this example, `2026-10-12.json`.
3. Open the repository's **[data/weeks folder](https://github.com/muhammed1187ad-svg/diplomatic-tracker/tree/main/data/weeks)**.
4. **For a new week:** Click **Add file → Upload files**, select the JSON file, and commit to `main`.
5. **If the file already exists:** Open it, click the pencil icon to edit, paste the **complete updated JSON** (including any earlier entries for that week), and commit. Do not delete previously recorded meetings when adding more.
6. After GitHub Pages republishes, the website displays the updated meetings. Previous weeks and months remain in the archive.

**You do not need to replace `index.html` each week.** The scheduled diplomatic research report can prepare a downloadable JSON file, but the maintainer must still **commit that file to GitHub**; research scheduling alone does not update the live site.

### Example of a meeting record

*This is a fictional formatting example, not a real meeting.*

```json
[
  {
    "id": "2026-10-12-example-001",
    "city": "Ankara",
    "date": "14 Ekim 2026",
    "start_date": "2026-10-14",
    "end_date": "2026-10-14",
    "parties": "Country A–Country B | Foreign ministers",
    "topic": "Bilateral consultations",
    "kind": "İkili",
    "source": "https://example.org/meeting",
    "lat": 39.9334,
    "lon": 32.8597
  }
]
```

Use `İkili` or `Çok taraflı` for `kind`. Keep dates in `YYYY-MM-DD` format, source links as HTTPS URLs, and meeting IDs unique. Include `lat` and `lon` for a new city not already known to the map. Even a single-meeting weekly JSON file needs the enclosing square brackets `[` and `]`.

## Project status and future plans

The website is **publicly accessible**, although it asks search engines not to index it; that request is **not** a privacy or access restriction. The map has no sign-in or per-meeting approval system.

The longer-term goal is a more comprehensive, transparent diplomatic archive with improved historical coverage, data checks, country comparisons, and potential community contributions. An open-source license and contribution guide can be added when the project is ready to accept them.

---

### 🇹🇷 Türkçe kısa açıklama

**Diplomatik Temas Haritası**, üst düzey diplomatik görüşmeleri dünya haritasında gösteren ve haftalık/aylık arşiv sunan bağımsız bir araştırma projesidir. Konumlara tıklayarak görüşmenin tarihini, taraflarını, konusunu ve kaynak bağlantısını görebilir; arama, filtreleme ve CSV indirme özelliklerinden yararlanabilirsiniz.

Yeni haftanın verileri `data/weeks/` klasörüne **haftanın pazartesi tarihiyle adlandırılmış JSON dosyası** olarak eklenir. Eski kayıtlar silinmez. **Eylül 2026 kayıtlarının tamamı yeniden teyit edilmiş değildir**; önemli kullanımlarda kaynakların incelenmesi tavsiye edilir.
