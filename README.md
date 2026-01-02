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
**(Připravuje se do verze 1.5.0)**

![ACRCloud](https://img.shields.io/badge/ACRCloud-4A90D9?style=flat-square)

- **100+ milionů** skladeb
- TV pořady & reklamy
- Nejlepší pro soundtracky
- Vyžaduje registraci (zdarma)

</td>
</tr>
</table>

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
<td width="33%" valign="top">

### Fáze 1 (Hotovo)
**Windows aplikace**<br>
✅ Rozpoznávání hudby<br>
✅ Historie & statistiky<br>
✅ 3D UI efekty<br>
✅ Mazání duplicit<br>
✅ Portable režim<br>
✅ FFT Spectrum Analyzer<br>
✅ Audio preprocessing<br>
✅ Multi-provider fallback

</td>
<td width="33%" valign="top">

### Fáze 2 (Připravuje se)
**Kvalita rozpoznávání + UX**<br>
✅ Recognition Architecture v2.0<br>
⬚ ACRCloud integrace<br>
⬚ Decision Engine (3 vrstvy)<br>
⬚ Usage tracking & limity<br>
⬚ Signal quality detection<br>
⬚ Headless / Tray mód<br>
⬚ Fuzzy Search v historii<br>
⬚ Lyrics zobrazení<br>
⬚ Lokální Cache obrázků

</td>
<td width="33%" valign="top">

### Fáze 3 (Přijde ve verze 2.0)
**Stream Deck integrace**<br>
✅ Stream Deck plugin v1.0.0<br>
✅ Rozpoznání na tlačítko<br>
✅ 12 akcí (Hledat, Copy, platformy...)<br>
✅ Nastavení délky (+5s/-5s)<br>
⬚ Cover Art na tlačítku<br>
⬚ Historie na Stream Decku<br>
⬚ LCD vizualizace

</td>
</tr>
</table>

---

## Stream Deck Plugin

**Status:** Funkční (v0.8.0) - součást Fáze 3 - verze 2.0

<table>
<tr>
<td width="30%" align="center">

<img width="180" alt="Stream Deck actions" src="https://github.com/user-attachments/assets/f9de4525-98a4-49e3-9dd3-0412ea7382e6" />

</td>
<td width="70%">

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

</td>
</tr>
</table>

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

