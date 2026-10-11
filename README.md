<h1 align="center">📚 isnady-data</h1>

<p align="center"><strong>The data of <a href="https://github.com/bayramkotan/isnady">isnady</a>: every hadith collection and rijal work it reads, Sunni and Shia, in one place and one format</strong></p>

<p align="center">
  <img src="https://img.shields.io/badge/hadith%20collections-33-1D4777?style=for-the-badge" alt="collections">
  <img src="https://img.shields.io/badge/hadith-99%2C746-A47E24?style=for-the-badge" alt="hadith">
  <img src="https://img.shields.io/badge/rijal%20works-2-5B6878?style=for-the-badge" alt="rijal">
  <img src="https://img.shields.io/badge/languages-9-14304F?style=for-the-badge" alt="languages">
</p>

isnady ships without hadith data. It reads it from a **data repository**, and this one is its default: everything isnady can read — **17 Sunni and 16 Shia hadith collections (99,746 hadith)** and **2 works on the narrators** — converted once into isnady's own format, each book in a folder named by its full title and its compiler. Nothing here has to be prepared by hand: isnady lists these books in **Settings → Data sources** and imports any of them with one click, or all of them at once.

<p align="center"><img src="https://raw.githubusercontent.com/bayramkotan/isnady/main/assets/screenshots/data-sources.png" alt="isnady — Settings → Data sources: this repository and its books, Sunni and Shia apart" width="760"></p>

---

## 🚀 Use it

**In isnady (the default).** Open **File → Data Sources** (or **Settings → Data sources**): this repository is already chosen. Tick the books and the languages you want and press **Import**, or **Import all**. Every hadith keeps its number, chapter, references and grades; the search index, the chains of transmission and the narrators are built as part of the import.

**From the command line** — the same engine:

```bash
iy catalog list                                           # every book of this repository
iy catalog import sahih_al_bukhari --language ara --language tur
iy catalog import al_kafi_al_kulayni                      # with al-Majlisi's and al-Behbudi's grades
iy catalog import taqrib_al_tahdhib_ibn_hajar_al_asqalani # identifies the narrators of the Sunni chains
iy catalog import rijal_al_najashi_ahmad_ibn_ali_al_najashi  # … and of the Shia chains
iy catalog import --all                                   # everything
```

**Without the network.** Clone this repository once (a USB stick or a shared folder works too) and read every book from it:

```bash
git clone https://github.com/bayramkotan/isnady-data ~/isnady-data
iy repo add ~/isnady-data      # in the window: Data sources → A folder on this computer…
iy catalog import --all
```

**A whole ready database.** The [Releases](https://github.com/bayramkotan/isnady-data/releases) carry `isnady-db-<date>.zip`: a complete isnady database built from this repository, its chains read and its narrators identified (`database.json` beside it gives its date, size, sha256 and contents). Take it with **Data folder → Use a ready database…** or:

```bash
iy database use ~/Downloads/isnady-db-<date>.zip
```

isnady checks the file (the zip must hold `isnady.db`, the schema must be one it reads, the sha256 must match `database.json`), puts it in place at the next start and keeps your previous database beside it (`isnady.<date-time>.bak.db`). Nothing is deleted.

---

## 🗂️ What is inside

```
isnady-data/
├── catalog.json                     the list isnady reads (schema isnady-catalog/1)
├── sunni/
│   ├── sahih_al_bukhari/
│   │   ├── book.json                numbers, chapters, references, grades (schema isnady-book/1)
│   │   ├── ara.json                 the Arabic text, chapter titles
│   │   ├── eng.json  tur.json …     one file per translation
│   ├── musnad_ahmad_ibn_hanbal/
│   └── …
├── shia/
│   ├── al_kafi_al_kulayni/
│   └── …
├── rijal/
│   ├── sunni/taqrib_al_tahdhib_ibn_hajar_al_asqalani.md
│   └── shia/rijal_al_najashi_ahmad_ibn_ali_al_najashi.md
├── derived/                         computations already made (statistics, models …), as JSON
└── database.json                    the ready database of the latest Release
```

**Names.** Every folder and every id is the book's full title with its compiler's name — `musnad_ahmad_ibn_hanbal`, `al_kafi_al_kulayni`, `taqrib_al_tahdhib_ibn_hajar_al_asqalani` — never a bare name. The same ids are what isnady imports by, and what its exports and saved computations are named after.

**Sunni and Shia apart.** Every book says its tradition. isnady keeps the two side by side and never mixes their measures: the chains of a Sunni book are read the Sunni way and their narrators identified in Ibn Hajar's *Taqrib*; the chains of a Shia book are read the Shia way (al-Kulayni's teacher named without a term, his groups, the chain ending at one of the Fourteen Ma'sumun) and their narrators identified only in the Shia rijal works, judged in the Imami critics' own terms.

---

## 📗 Sunni hadith collections

The six books, the Muwatta and the Forties in Arabic and up to eight translations, with the grades of al-Albani, Shu'ayb al-Arna'ut, Zubair 'Ali Za'i and others where they graded them; Musnad Ahmad and Sunan al-Darimi in fully voweled Arabic; five more books in Arabic and English, by chapter.

| Book | | Compiler | Hadith | Languages | Import id |
|---|---|---|--:|---|---|
| **Sahih al-Bukhari** | صحيح البخاري | al-Bukhari (d. 256) | 7,590 | Arabic, English, Turkish, Urdu, Indonesian, Bengali, French, Russian, Tamil | `sahih_al_bukhari` |
| **Sahih Muslim** | صحيح مسلم | Muslim (d. 261) | 7,564 | Arabic, English, Turkish, Urdu, Indonesian, Bengali, French, Russian, Tamil | `sahih_muslim` |
| **Sunan Abi Dawud** | سنن أبي داود | Abu Dawud (d. 275) | 5,274 | Arabic, English, Turkish, Urdu, Indonesian, Bengali, French, Russian | `sunan_abi_dawud` |
| **Jami' al-Tirmidhi** | جامع الترمذي | al-Tirmidhi (d. 279) | 3,998 | Arabic, English, Turkish, Urdu, Indonesian, Bengali | `jami_al_tirmidhi` |
| **Sunan al-Nasa'i** | سنن النسائي | al-Nasa'i (d. 303) | 5,765 | Arabic, English, Turkish, Urdu, Indonesian, Bengali, French | `sunan_al_nasai` |
| **Sunan Ibn Majah** | سنن ابن ماجه | Ibn Maja (d. 273) | 4,343 | Arabic, English, Turkish, Urdu, Indonesian, Bengali, French | `sunan_ibn_majah` |
| **Muwatta Malik** | موطأ مالك | Malik (d. 179) | 1,927 | Arabic, English, Turkish, Urdu, Indonesian, Bengali, French | `muwatta_malik_ibn_anas` |
| **Forty Hadith of al-Nawawi** | الأربعون النووية | al-Nawawi (d. 676) | 42 | Arabic, English, Turkish, Bengali, French | `al_arbain_al_nawawiyya` |
| **Forty Hadith Qudsi** | الأربعون القدسية | — | 40 | Arabic, English, French | `al_arbain_al_qudsiyya` |
| **Forty Hadith of Shah Waliullah Dehlawi** | أربعون الدهلوي | Shah Waliullah (d. 1176) | 40 | Arabic, English, French | `al_arbain_shah_waliullah_al_dehlawi` |
| **Musnad Ahmad ibn Hanbal** | مسند أحمد بن حنبل | Ahmad ibn Hanbal (d. 241) | 26,363 | Arabic | `musnad_ahmad_ibn_hanbal` |
| **Sunan al-Darimi** | سنن الدارمي | al-Darimi (d. 255) | 3,367 | Arabic | `sunan_al_darimi` |
| **Riyad al-Salihin** | رياض الصالحين | al-Nawawi (d. 676) | 1,896 | Arabic, English | `riyad_al_salihin_al_nawawi` |
| **al-Shama'il al-Muhammadiyya** | الشمائل المحمدية | al-Tirmidhi (d. 279) | 402 | Arabic, English | `al_shamail_al_muhammadiyya_al_tirmidhi` |
| **Bulugh al-Maram** | بلوغ المرام | Ibn Hajar (d. 852) | 1,767 | Arabic, English | `bulugh_al_maram_ibn_hajar_al_asqalani` |
| **al-Adab al-Mufrad** | الأدب المفرد | al-Bukhari (d. 256) | 1,326 | Arabic, English | `al_adab_al_mufrad_al_bukhari` |
| **Mishkat al-Masabih** | مشكاة المصابيح | al-Khatib al-Tabrizi (d. 741) | 4,428 | Arabic, English | `mishkat_al_masabih_al_khatib_al_tabrizi` |
| | | **17 books** | **76,132** | | |

## 📘 Shia hadith collections

al-Kafi in its eight volumes with al-Majlisi's grade on nearly every hadith (*Mir'at al-'Uqul*, 13,931) and al-Behbudi's selection (*Sahih al-Kafi*), and fifteen more works of al-Saduq, al-Mufid, Ibn Qulawayh, al-Nu'mani, al-Tusi, al-Ahwazi and al-Muhsini, in Arabic and English.

| Book | | Compiler | Hadith | Languages | Import id |
|---|---|---|--:|---|---|
| **al-Kafi — al-Kulayni** | الكافي | al-Kulayni (d. 329) | 14,241 | Arabic, English | `al_kafi_al_kulayni` |
| **ʿUyun Akhbar al-Rida — al-Saduq** | عيون أخبار الرضا | al-Saduq (d. 381) | 954 | Arabic, English | `uyun_akhbar_al_rida_al_shaykh_al_saduq` |
| **al-Amali — al-Saduq** | الأمالي (الصدوق) | al-Saduq (d. 381) | 1,082 | Arabic, English | `al_amali_al_shaykh_al_saduq` |
| **al-Khisal — al-Saduq** | الخصال | al-Saduq (d. 381) | 1,282 | Arabic, English | `al_khisal_al_shaykh_al_saduq` |
| **al-Tawhid — al-Saduq** | التوحيد | al-Saduq (d. 381) | 575 | Arabic, English | `al_tawhid_al_shaykh_al_saduq` |
| **Ma'ani al-Akhbar — al-Saduq** | معاني الأخبار | al-Saduq (d. 381) | 832 | Arabic, English | `maani_al_akhbar_al_shaykh_al_saduq` |
| **Thawab al-A'mal wa 'Iqab al-A'mal — al-Saduq** | ثواب الأعمال وعقاب الأعمال | al-Saduq (d. 381) | 1,107 | Arabic, English | `thawab_al_amal_wa_iqab_al_amal_al_shaykh_al_saduq` |
| **Sifat al-Shi'a — al-Saduq** | صفات الشيعة | al-Saduq (d. 381) | 71 | Arabic, English | `sifat_al_shia_al_shaykh_al_saduq` |
| **Fada'il al-Shi'a — al-Saduq** | فضائل الشيعة | al-Saduq (d. 381) | 45 | Arabic, English | `fadail_al_shia_al_shaykh_al_saduq` |
| **al-Amali — al-Mufid** | الأمالي (المفيد) | al-Mufid (d. 413) | 387 | Arabic, English | `al_amali_al_shaykh_al_mufid` |
| **Kamil al-Ziyarat — Ibn Qulawayh** | كامل الزيارات | Ibn Qulawayh al-Qummi (d. 368) | 750 | Arabic, English | `kamil_al_ziyarat_ibn_qulawayh_al_qummi` |
| **Kitab al-Ghayba — al-Nu'mani** | كتاب الغيبة (النعماني) | al-Nu'mani (d. c. 360) | 468 | Arabic, English | `kitab_al_ghayba_ibn_abi_zaynab_al_numani` |
| **Kitab al-Ghayba — al-Tusi** | كتاب الغيبة (الطوسي) | al-Tusi (d. 460) | 774 | Arabic, English | `kitab_al_ghayba_al_shaykh_al_tusi` |
| **Kitab al-Mu'min — al-Ahwazi** | كتاب المؤمن | al-Husayn b. Sa'id al-Ahwazi | 201 | Arabic, English | `kitab_al_mumin_al_husayn_ibn_said_al_ahwazi` |
| **Kitab al-Zuhd — al-Ahwazi** | كتاب الزهد | al-Husayn b. Sa'id al-Ahwazi | 290 | Arabic, English | `kitab_al_zuhd_al_husayn_ibn_said_al_ahwazi` |
| **Mu'jam al-Ahadith al-Mu'tabara — al-Muhsini** | معجم الأحاديث المعتبرة | Asif al-Muhsini | 555 | Arabic, English | `mujam_al_ahadith_al_mutabara_asif_al_muhsini` |
| | | **16 books** | **23,614** | | |

## 👥 Narrators (rijal)

| Work | | Tradition | Entries | What isnady does with it | Import id |
|---|---|---|--:|---|---|
| **Taqrib al-Tahdhib — Ibn Hajar al-'Asqalani** | تقريب التهذيب | Sunni | 8,824 | every name in the Sunni chains is matched to its narrator; his rank on Ibn Hajar's twelve-step scale, tabaqa, death year and book marks | `taqrib_al_tahdhib_ibn_hajar_al_asqalani` |
| **Rijal al-Najashi — al-Najashi (Shia)** | رجال النجاشي | Shia | 1,266 | every name in the Shia chains is matched to its narrator; his reliability and creed in the critic's own (Imami) terms — never on the Sunni scale | `rijal_al_najashi_ahmad_ibn_ali_al_najashi` |

---

## 🧩 The formats

<details>
<summary><b>catalog.json — <code>isnady-catalog/1</code></b></summary>

```json
{
  "schema": "isnady-catalog/1",
  "id": "isnady", "name": "isnady — all sources (default)",
  "homepage": "https://github.com/bayramkotan/isnady-data",
  "entries": [
    { "id": "sahih_al_bukhari", "title": "Sahih al-Bukhari", "title_ar": "صحيح البخاري",
      "kind": "hadith", "tradition": "sunni", "format": "isnady",
      "location": "sunni/sahih_al_bukhari/book.json", "book": "bukhari",
      "languages": ["ara", "eng", "tur"], "license": "Unlicense", "hadith": 7590 }
  ]
}
```

`location` is relative to the catalog, so the same catalog works on GitHub, in a clone and on a USB stick. `kind` is `hadith` or `rijal`; `tradition` is `sunni` or `shia`; `format` names the reader isnady uses (`isnady`, `taqrib`, `najashi` …).

</details>

<details>
<summary><b>book.json and the language files — <code>isnady-book/1</code></b></summary>

```json
{
  "schema": "isnady-book/1", "key": "kafi", "title": "al-Kafi — al-Kulayni", "title_ar": "الكافي",
  "tradition": "shia", "compiler": "al-Kulayni (d. 329)",
  "languages": { "ara": { "file": "ara.json", "name": "Arabic", "direction": "rtl" },
                 "eng": { "file": "eng.json", "name": "English", "direction": "ltr" } },
  "hadiths": [
    { "n": "1:6", "sort": 100006.0, "s": 1002,
      "grades": [["al-Majlisi (Mir'at al-'Uqul)", "موثق ول يقصر عن الصحيح"]] }
  ]
}
```

Each hadith: `n` its number as the book gives it, `sort` its place, `s` its chapter, `refs` other numberings, `grades` every grade as `[scholar, grade]`, exactly as written. Each language file (`ara.json`, `eng.json` …) holds `{"language", "sections": {chapter: title}, "texts": {number: text}}`.

</details>

---

## 🔄 How it is made

Both are tools in the isnady repository:

```bash
python tools/build_data_repo.py --mirror ~/Github/isnady-data   # convert every source into this repository
python tools/publish_database.py ~/Github/isnady-data           # a ready database for a Release, and derived/
```

`publish_database.py` copies the database compactly, leaves out everything imported from a user's own files (they never leave that computer), zips it for a Release (`db-<date>`) and copies the saved computations into `derived/`, so they are not computed again for the same data.

---

## 📜 Licences and credits

Every book records its licence, and isnady shows them all under **Help → Licences**. The texts here were first made available by others; thank you:

| Texts | First published by | Licence |
|---|---|---|
| The six books, the Muwatta, the Forties — text and translations | fawazahmed0/hadith-api | The Unlicense |
| Musnad Ahmad, Sunan al-Darimi — voweled text | Open Hadith Data | ODbL 1.0 (a database made from it stays under the ODbL) |
| Riyad al-Salihin, al-Shama'il, Bulugh al-Maram, al-Adab al-Mufrad, Mishkat — text and English | sunnah.com, via AhmedBaset/hadith-json | not stated |
| The Shia collections — text, English, grades | thaqalayn.net, via MohammedArab1/ThaqalaynAPI | not stated |
| The Taqrib, al-Najashi's Rijal | the OpenITI corpus | not stated |

isnady itself is MIT-licensed: [bayramkotan/isnady](https://github.com/bayramkotan/isnady).
