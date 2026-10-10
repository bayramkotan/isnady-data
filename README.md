# isnady-data

The data of [isnady](https://github.com/bayramkotan/isnady): every hadith collection and rijal work it reads, Sunni and Shia, in one format. isnady imports from here (Settings → Data sources, or `iy catalog import ID`).

- `sunni/<book>/`, `shia/<book>/` (the book's full title and its compiler's name, e.g. `sunni/musnad_ahmad_ibn_hanbal/`) — `book.json` (numbers, chapters, references, grades) and one file per language (`ara.json`, `eng.json` …)
- `rijal/sunni/`, `rijal/shia/` — the works on the narrators
- `catalog.json` — the list isnady reads

## Use

In isnady: **Settings → Data sources** — this repository is the default; tick a book and Import. Without the network, clone it and read it from this computer:

```bash
git clone https://github.com/bayramkotan/isnady-data ~/isnady-data
iy repo add ~/isnady-data            # every book is read from this folder
iy catalog import sahih_al_bukhari --language ara --language tur
iy database use isnady-db-<date>.zip   # or a whole ready database (Releases)
```

<p align="center"><img src="https://raw.githubusercontent.com/bayramkotan/isnady/main/assets/screenshots/data-sources.png" alt="isnady — Settings → Data sources" width="760"></p>

## Sunni collections

| Book | | Compiler | Languages | Hadith |
|---|---|---|---|---|
| Sahih al-Bukhari | صحيح البخاري | al-Bukhari (d. 256) | ara, eng, tur, urd, ind, ben, fra, rus, tam | 7,590 |
| Sahih Muslim | صحيح مسلم | Muslim (d. 261) | ara, eng, tur, urd, ind, ben, fra, rus, tam | 7,564 |
| Sunan Abi Dawud | سنن أبي داود | Abu Dawud (d. 275) | ara, eng, tur, urd, ind, ben, fra, rus | 5,274 |
| Jami' al-Tirmidhi | جامع الترمذي | al-Tirmidhi (d. 279) | ara, eng, tur, urd, ind, ben | 3,998 |
| Sunan al-Nasa'i | سنن النسائي | al-Nasa'i (d. 303) | ara, eng, tur, urd, ind, ben, fra | 5,765 |
| Sunan Ibn Majah | سنن ابن ماجه | Ibn Maja (d. 273) | ara, eng, tur, urd, ind, ben, fra | 4,343 |
| Muwatta Malik | موطأ مالك | Malik (d. 179) | ara, eng, tur, urd, ind, ben, fra | 1,927 |
| Forty Hadith of al-Nawawi | الأربعون النووية | al-Nawawi (d. 676) | ara, eng, tur, ben, fra | 42 |
| Forty Hadith Qudsi | الأربعون القدسية |  | ara, eng, fra | 40 |
| Forty Hadith of Shah Waliullah Dehlawi | أربعون الدهلوي | Shah Waliullah (d. 1176) | ara, eng, fra | 40 |
| Musnad Ahmad ibn Hanbal | مسند أحمد بن حنبل | Ahmad ibn Hanbal (d. 241) | ara | 26,363 |
| Sunan al-Darimi | سنن الدارمي | al-Darimi (d. 255) | ara | 3,367 |
| Riyad al-Salihin | رياض الصالحين | al-Nawawi (d. 676) | ara, eng | 1,896 |
| al-Shama'il al-Muhammadiyya | الشمائل المحمدية | al-Tirmidhi (d. 279) | ara, eng | 402 |
| Bulugh al-Maram | بلوغ المرام | Ibn Hajar (d. 852) | ara, eng | 1,767 |
| al-Adab al-Mufrad | الأدب المفرد | al-Bukhari (d. 256) | ara, eng | 1,326 |
| Mishkat al-Masabih | مشكاة المصابيح | al-Khatib al-Tabrizi (d. 741) | ara, eng | 4,428 |

## Shia collections

| Book | | Compiler | Languages | Hadith |
|---|---|---|---|---|
| al-Kafi — al-Kulayni | الكافي | al-Kulayni (d. 329) | ara, eng | 14,241 |
| ʿUyun Akhbar al-Rida — al-Saduq | عيون أخبار الرضا | al-Saduq (d. 381) | ara, eng | 954 |
| al-Amali — al-Saduq | الأمالي (الصدوق) | al-Saduq (d. 381) | ara, eng | 1,082 |
| al-Khisal — al-Saduq | الخصال | al-Saduq (d. 381) | ara, eng | 1,282 |
| al-Tawhid — al-Saduq | التوحيد | al-Saduq (d. 381) | ara, eng | 575 |
| Ma'ani al-Akhbar — al-Saduq | معاني الأخبار | al-Saduq (d. 381) | ara, eng | 832 |
| Thawab al-A'mal wa 'Iqab al-A'mal — al-Saduq | ثواب الأعمال وعقاب الأعمال | al-Saduq (d. 381) | ara, eng | 1,107 |
| Sifat al-Shi'a — al-Saduq | صفات الشيعة | al-Saduq (d. 381) | ara, eng | 71 |
| Fada'il al-Shi'a — al-Saduq | فضائل الشيعة | al-Saduq (d. 381) | ara, eng | 45 |
| al-Amali — al-Mufid | الأمالي (المفيد) | al-Mufid (d. 413) | ara, eng | 387 |
| Kamil al-Ziyarat — Ibn Qulawayh | كامل الزيارات | Ibn Qulawayh al-Qummi (d. 368) | ara, eng | 750 |
| Kitab al-Ghayba — al-Nu'mani | كتاب الغيبة (النعماني) | al-Nu'mani (d. c. 360) | ara, eng | 468 |
| Kitab al-Ghayba — al-Tusi | كتاب الغيبة (الطوسي) | al-Tusi (d. 460) | ara, eng | 774 |
| Kitab al-Mu'min — al-Ahwazi | كتاب المؤمن | al-Husayn b. Sa'id al-Ahwazi | ara, eng | 201 |
| Kitab al-Zuhd — al-Ahwazi | كتاب الزهد | al-Husayn b. Sa'id al-Ahwazi | ara, eng | 290 |
| Mu'jam al-Ahadith al-Mu'tabara — al-Muhsini | معجم الأحاديث المعتبرة | Asif al-Muhsini | ara, eng | 555 |

## Narrators (rijal)

| Work | | Tradition |
|---|---|---|
| Taqrib al-Tahdhib — Ibn Hajar al-'Asqalani | تقريب التهذيب | sunni |
| Rijal al-Najashi — al-Najashi (Shia) | رجال النجاشي | shia |

## Credits

These texts were first made available by others; thank you.

- Text and translations: fawazahmed0/hadith-api (The Unlicense).
- Text: the Open Hadith Data project (ODbL 1.0; contents under the Database Contents License). A database made from it stays under the ODbL.
- Text and English: sunnah.com, as collected by AhmedBaset/hadith-json.
- Text, English and grades: thaqalayn.net, as collected by MohammedArab1/ThaqalaynAPI.
- Text: the OpenITI corpus.
