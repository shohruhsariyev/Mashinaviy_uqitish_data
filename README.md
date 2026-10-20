# Mashinaviy o‘qitishga kirish – darslik uchun ma’lumotlar to‘plamlari
«Mashinaviy o‘qitishga kirish» darsligi  dagi barcha misollar va dasturlar ikkita ma’lumotlar to‘plamiga tayanadi. Har biri ikki formatda berilgan: `.xlsx` (Excel) va `.csv`.

| Fayl | Mazmuni | Qatorlar | Masalalar |
|---|---|---|---|
| `data/Uy_baza.csv` / `.xlsx` | Toshkent shahridagi kvartiralar sotuvi e’lonlari | 7278 | regressiya, segmentlash, anomaliyalarni aniqlash |
| `data/diabet_kitob.csv` / `.xlsx` | Qandli diabet belgilari va tashxis | 12 066 | klassifikatsiya, klasterlash, optimallashtirish, giperparametrlarni sozlash |

## Uy_baza – ustunlar

| Ustun | Mazmuni | Turi |
|---|---|---|
| Hudud | kvartira joylashgan tuman (12 ta tuman) | nominal |
| Xona | xonalar soni | butun |
| Maydon | umumiy maydon, m² | uzluksiz |
| Qavat | kvartira joylashgan qavat | butun |
| Uy_qavati | binoning qavatlar soni | butun |
| Narx | kvartira narxi, AQSH dollari (maqsad o‘zgaruvchisi) | uzluksiz |

`Qavat` ustunida 24 ta, `Uy_qavati` ustunida 5 ta qiymat ko‘rsatilmagan; ma’lumotlarda 1117 ta takroriy yozuv bor. Darslikdagi dasturlar ularni `drop_duplicates().dropna()` bilan olib tashlaydi.

## diabet_kitob – ustunlar

| Ustun | Belgining ma’nosi | Turi |
|---|---|---|
| HTCH | haddan tashqari chanqoq | ikkilik (0/1) |
| USX1_5 | umumiy sog‘liq holati (1 dan 5 gacha baho) | tartibli (1–5) |
| TTPCH | tez-tez peshobga chiqish | ikkilik (0/1) |
| Jinsi | bemorning jinsi (erkak yoki ayol) | ikkilik (0/1) |
| Yoshi | bemorning yoshi (18–81) | butun |
| YSB | yaralarning sekin bitishi | ikkilik (0/1) |
| KHTT | kam harakat turmush tarzi | ikkilik (0/1) |
| OTDM | oila tarixida diabet mavjudligi | ikkilik (0/1) |
| YQB | yuqori qon bosimi | ikkilik (0/1) |
| QAU | qo‘l va oyoq uvishi | ikkilik (0/1) |
| TMI | tana massasi indeksi (12.1–50.0) | uzluksiz |
| KNP | ko‘z nuri pasayishi | ikkilik (0/1) |
| YYZCHQ | yurish yoki zinadan chiqishda qiyinchilik | ikkilik (0/1) |
| Diabet | maqsad o‘zgaruvchisi: 0 – sog‘lom, 1 – prediabet, 2 – qandli diabet | tartibli |

Uchta sinf muvozanatlangan: har birida 4022 tadan bemor.

## Python’da yuklash

```python
import pandas as pd

BAZA = "https://raw.githubusercontent.com/shohruhsariyev/Mashinaviy_uqitish_data/v1.0/data/"
uy = pd.read_csv(BAZA + "Uy_baza.csv")
diabet = pd.read_csv(BAZA + "diabet_kitob.csv")
```

## Manba va litsenziya

Ma’lumotlar manbasi: *(to‘ldiring)*

Litsenziya: *(to‘ldiring, masalan CC BY 4.0)*
