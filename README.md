# isnady-data

The data of [isnady](https://github.com/bayramkotan/isnady): every hadith collection and rijal work it reads, Sunni and Shia, in one format. isnady imports from here (Settings → Data sources, or `iy catalog import ID`).

- `sunni/<book>/`, `shia/<book>/` — `book.json` (numbers, chapters, references, grades) and one file per language (`ara.json`, `eng.json` …)
- `rijal/sunni/`, `rijal/shia/` — the works on the narrators
- `catalog.json` — the list isnady reads

## Sunni collections

| Book | | Compiler | Languages | Hadith |
|---|---|---|---|---|
| Sahih al-Bukhari | صحيح البخاري | al-Bukhari (d | ara, eng, tur, urd, ind, ben, fra, rus, tam | 7,590 |
| Sahih Muslim | صحيح مسلم | Muslim (d | ara, eng, tur, urd, ind, ben, fra, rus, tam | 7,564 |
| Sunan Abi Dawud | سنن أبي داود | Abu Dawud (d | ara, eng, tur, urd, ind, ben, fra, rus | 5,274 |
| Jami' al-Tirmidhi | جامع الترمذي | al-Tirmidhi (d | ara, eng, tur, urd, ind, ben | 3,998 |
| Sunan al-Nasa'i | سنن النسائي | al-Nasa'i (d | ara, eng, tur, urd, ind, ben, fra | 5,765 |
| Sunan Ibn Majah | سنن ابن ماجه | Ibn Maja (d | ara, eng, tur, urd, ind, ben, fra | 4,343 |
| Muwatta Malik | موطأ مالك | Malik (d | ara, eng, tur, urd, ind, ben, fra | 1,927 |
| Forty Hadith of al-Nawawi | الأربعون النووية | al-Nawawi (d | ara, eng, tur, ben, fra | 42 |
| Forty Hadith Qudsi | الأربعون القدسية |  | ara, eng, fra | 40 |
| Forty Hadith of Shah Waliullah Dehlawi | أربعون الدهلوي | Shah Waliullah (d | ara, eng, fra | 40 |
| Musnad Ahmad ibn Hanbal | مسند أحمد بن حنبل | Ahmad ibn Hanbal (d | ara | 26,363 |
| Sunan al-Darimi | سنن الدارمي | al-Darimi (d | ara | 3,367 |
| Riyad al-Salihin | رياض الصالحين | al-Nawawi (d | ara, eng | 1,896 |
| al-Shama'il al-Muhammadiyya | الشمائل المحمدية | al-Tirmidhi (d | ara, eng | 402 |
| Bulugh al-Maram | بلوغ المرام | Ibn Hajar (d | ara, eng | 1,767 |
| al-Adab al-Mufrad | الأدب المفرد | al-Bukhari (d | ara, eng | 1,326 |
| Mishkat al-Masabih | مشكاة المصابيح | al-Khatib al-Tabrizi (d | ara, eng | 4,428 |

## Shia collections

| Book | | Compiler | Languages | Hadith |
|---|---|---|---|---|
| al-Kafi — al-Kulayni | الكافي | al-Kulayni (d | ara, eng | 14,241 |
| 'Uyun Akhbar al-Rida — al-Saduq | عيون أخبار الرضا | al-Saduq (d | ara, eng | 954 |
| al-Amali — al-Saduq | الأمالي (الصدوق) | al-Saduq (d | ara, eng | 1,082 |
| al-Khisal — al-Saduq | الخصال | al-Saduq (d | ara, eng | 1,282 |
| al-Tawhid — al-Saduq | التوحيد | al-Saduq (d | ara, eng | 575 |
| Ma'ani al-Akhbar — al-Saduq | معاني الأخبار | al-Saduq (d | ara, eng | 832 |
| Thawab al-A'mal wa 'Iqab al-A'mal — al-Saduq | ثواب الأعمال وعقاب الأعمال | al-Saduq (d | ara, eng | 1,107 |
| Sifat al-Shi'a — al-Saduq | صفات الشيعة | al-Saduq (d | ara, eng | 71 |
| Fada'il al-Shi'a — al-Saduq | فضائل الشيعة | al-Saduq (d | ara, eng | 45 |
| al-Amali — al-Mufid | الأمالي (المفيد) | al-Mufid (d | ara, eng | 387 |
| Kamil al-Ziyarat — Ibn Qulawayh | كامل الزيارات | Ibn Qulawayh al-Qummi (d | ara, eng | 750 |
| Kitab al-Ghayba — al-Nu'mani | كتاب الغيبة (النعماني) | al-Nu'mani (d | ara, eng | 468 |
| Kitab al-Ghayba — al-Tusi | كتاب الغيبة (الطوسي) | al-Tusi (d | ara, eng | 774 |
| Kitab al-Mu'min — al-Ahwazi | كتاب المؤمن | al-Husayn b | ara, eng | 201 |
| Kitab al-Zuhd — al-Ahwazi | كتاب الزهد | al-Husayn b | ara, eng | 290 |
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
