<div align="center">

# SluchatkovyShazam - Portable

![Windows](https://img.shields.io/badge/Windows-10%2F11-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

Rozpoznávání hudby z filmů, seriálů, her a streamů - i když máš sluchátka!
*Žádný mikrofon, žádná instalace, žádné komplikace. Prostě to funguje s čímkoliv, kde ti hraje hudba.*

<img width="700" height="571" alt="image" src="https://github.com/user-attachments/assets/29ec7971-36ee-452c-b14f-857ca7cc7741" />

</div>

---

## Rozpoznávací databáze

<table>
<tr>
<td width="25%" align="center">

### Shazam
**Primární databáze**

![Shazam](https://img.shields.io/badge/Shazam-0088FF?style=flat-square&logo=shazam&logoColor=white)

- **70+ milionů** skladeb
- Nejrychlejší rozpoznání (~2s)
- Celosvětová hudba
- Nejlepší úspěšnost

</td>
<td width="25%" align="center">

### AudD.io
**Záložní databáze**

![AudD](https://img.shields.io/badge/AudD.io-FF6B35?style=flat-square)

- **50+ milionů** skladeb
- Fallback když Shazam selže
- Dobré pro soundtracky
- Rozpozná i reklamy

</td>
<td width="25%" align="center">

### Chromaprint
**Experimentální**

![AcoustID](https://img.shields.io/badge/AcoustID-888888?style=flat-square)

- **15+ milionů** skladeb
- Open-source databáze
- Hlavně indie hudba
- Vyžaduje fpcalc

</td>
<td width="25%" align="center">

### ACRCloud
**Připravuje se**

![ACRCloud](https://img.shields.io/badge/ACRCloud-4A90D9?style=flat-square)

- **100+ milionů** skladeb
- TV pořady & reklamy
- Nejlepší pro soundtracky
- Vyžaduje registraci (zdarma)

</td>
</tr>
</table>

> **Jak to funguje:** Aplikace nejprve zkusí Shazam (nejlepší). Pokud nenajde, automaticky zkouší další. Většina skladeb se najde na první pokus!

---

## Stažení

**[Stáhnout nejnovější verzi](https://github.com/MisakMisak/SluchatkovyShazam-Portable/releases/latest)**

## Instalace

1. **Stáhni** `SluchatkovyShazam.zip`
2. **Rozbal** kamkoliv
3. **Spusť** `SluchatkovyShazam.exe`

## Funkce

<table>
<tr>
<td width="50%">

### Rozpoznávání
- **Soundtracky z filmů a seriálů, live streamů atd.** (Netflix, HBO, Disney+, Twitch, YouTube atd.)
- **Okamžité** rozpoznání přes **Shazam API a další..**
- Zachytává systémový audio výstup

### Historie & Stats
- **Kompletní historie** všech skladeb
- **Statistiky poslechu**
- **Mazání duplicit** jedním kliknutím
- Export dat
- Funguje i offline (ukládá nahrávky)

<img width="683" height="318" alt="image" src="https://github.com/user-attachments/assets/d98d8257-4bcf-40ed-9ae3-bf736b332823" />

</td>
<td width="50%">

### Integrace
- **YouTube**
- **Spotify**
- **Apple Music**
- **Tidal**
- **SoundCloud**
- **Deezer**

<img width="684" height="207" alt="image" src="https://github.com/user-attachments/assets/0acc7c22-8d72-4d2a-bfe0-295f3f37c862" />

### Portabilní
- **Žádná instalace**
- Data vedle EXE
- Přenosné na USB

<img width="604" height="145" alt="image" src="https://github.com/user-attachments/assets/5f17b361-b972-43de-ba94-9b16b9128692" />

</td>
</tr>
</table>

---

## Roadmap - Kam směřujeme

<table>
<tr>
<td width="33%">

### Fáze 1 (Hotovo)
**Windows aplikace**
- [x] Rozpoznávání hudby
- [x] Historie & statistiky
- [x] 3D UI efekty
- [x] Mazání duplicit
- [x] Portable režim
- [x] FFT Spectrum Analyzer
- [x] Audio preprocessing
- [x] Multi-provider fallback

</td>
<td width="33%">

### Fáze 2 (Připravuje se)
**Kvalita rozpoznávání**
- [x] Recognition Architecture v2.0
- [ ] ACRCloud integrace
- [ ] Decision Engine (3 vrstvy)
- [ ] Usage tracking & limity
- [ ] Signal quality detection

</td>
<td width="33%">

### Fáze 3 (Připraveno)
**Stream Deck integrace**
- [x] Stream Deck plugin v1.0.0
- [x] Rozpoznání na tlačítko
- [x] 12 akcí (Hledat, Copy, platformy...)
- [x] Nastavení délky (+5s/-5s)
- [ ] Cover Art na tlačítku
- [ ] Historie na Stream Decku

</td>
</tr>
</table>

---

### Fáze 4: UX vylepšení (Plánováno)

| Funkce | Popis | Priorita |
|--------|-------|----------|
| **Headless / Tray mód** | Aplikace běží na pozadí v System Tray. Ovládání pouze přes Stream Deck. | 
| **Fuzzy Search v historii** | Vyhledávací pole v panelu historie. Hledá v názvu, interpretu, albu. | 
| **Lyrics zobrazení** | Po kliknutí na skladbu zobrazit text písničky (Genius API). |
| **Lokální Cache obrázků** | Album art uložený offline. Rychlejší načítání, funguje bez internetu. | 
| **Cover Art na tlačítku** | Album art místo ikony na tlačítku "Skladba" |
| **Historie na Stream Decku** | Procházení historie přímo na Stream Decku |
| **LCD vizualizace** | Waveform nebo progress na Stream Deck+ LCD strip |

---

## Stream Deck Plugin

**Status:** Funkční (v1.0.0) - součást Fáze 3

### 12 akcí

| Akce | Funkce |
|------|--------|
| **Hledat** | Spustí nahrávání a rozpoznávání |
| **Kopírovat** | Zkopíruje skladbu do schránky |
| **Skladba** | Zobrazuje rozpoznanou skladbu |
| **Délka** | Zobrazuje délku nahrávání |
| **+5s / -5s** | Upraví délku nahrávání |
| **YouTube** | Otevře skladbu na YouTube |
| **Spotify** | Otevře skladbu na Spotify |
| **Tidal** | Otevře skladbu na Tidal |
| **Apple Music** | Otevře skladbu na Apple Music |
| **Deezer** | Otevře skladbu na Deezer |
| **SoundCloud** | Otevře skladbu na SoundCloud |

<img width="180" height="523" alt="Stream Deck actions" src="https://github.com/user-attachments/assets/f9de4525-98a4-49e3-9dd3-0412ea7382e6" />

---

## API Server

Aplikace obsahuje FastAPI server na portu **8764** pro komunikaci se Stream Deckem.

```
GET  /api/health           - Health check
GET  /api/status           - Stav aplikace
POST /api/record           - Spustit nahrávání
GET  /api/result/last      - Poslední skladba
GET  /api/config/duration  - Délka nahrávání
POST /api/config/duration/plus   - +5s
POST /api/config/duration/minus  - -5s
```

---

**Verze:** 1.4.0 | **Licence:** Proprietary | **Autor:** MisakMisak



