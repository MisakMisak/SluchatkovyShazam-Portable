<div align="center">

# SluchatkovyShazam - Portable

![Windows](https://img.shields.io/badge/Windows-10%2F11-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Version](https://img.shields.io/badge/Version-1.5.1-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

Rozpoznávání hudby z filmů, seriálů, her a streamů — i když máš sluchátka.

*Žádný mikrofon, žádná instalace. Zachytí systémový audio výstup přímo z počítače.*

<img width="700" height="659" alt="SluchatkovyShazam UI" src="https://github.com/user-attachments/assets/35661af7-59d8-43cd-aaf1-5f95deb62f43" />

</div>

---

## Stažení a spuštění

1. Stáhni **[nejnovější verzi](https://github.com/MisakMisak/SluchatkovyShazam-Portable/releases/latest)** (`SluchatkovyShazam.zip`)
2. Rozbal kamkoliv — USB, plocha, `C:\` — nezáleží
3. Spusť `SluchatkovyShazam.exe`

Žádná instalace. Žádné závislosti. Data se ukládají vedle `.exe`.

---

## Jak to funguje

Aplikace zachytí systémový audio výstup (to, co slyšíš v uších) a pošle ho do kaskády rozpoznávacích databází. Databáze se spouštějí v pořadí od nejrychlejší po nejpokryvnější — pokud první vrstva selže, aktivuje se záchranná.

```
Audio výstup (WASAPI loopback)
        │
        ▼
   [1. vrstva — paralelně]
┌─────────────────┐    ┌───────────────────┐
│     Shazam      │    │    Chromaprint     │
│   70M+ skladeb  │    │  (AcoustID API)    │
│   primární      │    │  20M+ skladeb      │
└────────┬────────┘    └────────┬───────────┘
         │ oba selhaly          │
         └──────────┬───────────┘
                    ▼
   [2. vrstva — fallback]
         ┌──────────────────┐
         │    ACRCloud      │
         │  150M+ skladeb   │
         │  TV, reklamy     │
         └────────┬─────────┘
                  │ selhání
                  ▼
         ┌──────────────────┐
         │     AudD.io      │
         │   80M+ skladeb   │
         │  poslední záchrana│
         └──────────────────┘
```

Shazam a Chromaprint běží **paralelně** — vrátí se ten, kdo odpoví první. ACRCloud a AudD.io se aktivují jen když obě selžou.

---

## Databáze

| Databáze | Skladby | Bez API klíče | Kdy se použije |
|----------|---------|---------------|----------------|
| Shazam | 70M+ | Ano | Vždy, primární |
| Chromaprint / AcoustID | 20M+ | Volitelný | Vždy, paralelně se Shazam |
| ACRCloud | 150M+ | Volitelný | Fallback — nejlepší pro soundtracky a reklamy |
| AudD.io | 80M+ | Ano | Poslední záchrana |

Aplikace funguje bez API klíčů. ACRCloud a AcoustID jsou volitelné a zlepší pokrytí — viz [docs/API-KEYS-GUIDE.md](docs/API-KEYS-GUIDE.md).

---

## Funkce

### Rozpoznávání

- Systémový audio výstup — Netflix, HBO, hry, Twitch, YouTube, cokoliv
- 4 databáze v kaskádě s paralelní první vrstvou
- FFT spectrum analyzer — vizualizace v reálném čase
- Nastavitelná délka nahrávání

### Texty a překlad

- Automatické načtení textu po rozpoznání (LRCLIB.net, bez API klíče)
- Překlad do češtiny jedním kliknutím

<img width="683" height="318" alt="Texty skladeb" src="https://github.com/user-attachments/assets/d98d8257-4bcf-40ed-9ae3-bf736b332823" />

### Historie

- Kompletní historie rozpoznaných skladeb
- Mazání duplicit jedním kliknutím
- Klik na skladbu → otevře na vybrané platformě

<img width="684" height="207" alt="Historie skladeb" src="https://github.com/user-attachments/assets/0acc7c22-8d72-4d2a-bfe0-295f3f37c862" />

### Integrace platforem

YouTube, Spotify, Apple Music, Tidal, Deezer, SoundCloud

### Portable

- Žádná instalace — rozbal a spusť
- Data vedle `.exe` — přenosné na USB

---

## Stream Deck

Aplikace má plugin pro Elgato Stream Deck (v1.0.0) s vlastním API serverem.

<img width="180" alt="Stream Deck akce" src="https://github.com/user-attachments/assets/f9de4525-98a4-49e3-9dd3-0412ea7382e6" />

| Akce | Popis |
|------|-------|
| Hledat | Spustí nahrávání a rozpoznávání |
| Kopírovat | Zkopíruje skladbu do schránky |
| Skladba | Zobrazuje aktuálně rozpoznanou skladbu |
| Délka | Zobrazuje délku nahrávání |
| +5s / -5s | Upraví délku nahrávání |
| YouTube / Spotify / Tidal / Apple Music / Deezer / SoundCloud | Otevře výsledek na dané platformě |

---

## API Server

Aplikace spouští lokální FastAPI server na portu **8764**. Používá ho Stream Deck plugin — lze ho využít i vlastním skriptem nebo nástrojem.

| Metoda | Endpoint | Popis |
|--------|----------|-------|
| `GET` | `/api/health` | Health check |
| `GET` | `/api/status` | Stav aplikace (nahrává / čeká) |
| `POST` | `/api/record` | Spustí nahrávání a rozpoznávání |
| `GET` | `/api/result/last` | Poslední rozpoznaná skladba (JSON) |
| `GET` | `/api/config/duration` | Aktuální délka nahrávání v sekundách |
| `POST` | `/api/config/duration/plus` | Prodlouží nahrávání o 5 s |
| `POST` | `/api/config/duration/minus` | Zkrátí nahrávání o 5 s |

Příklad použití:

```bash
# Spusť rozpoznávání
curl -X POST http://localhost:8764/api/record

# Zjisti výsledek
curl http://localhost:8764/api/result/last
```

---

## Roadmap

### Fáze 1 — Základ (hotovo)

- ✅ Rozpoznávání hudby přes WASAPI loopback
- ✅ Historie a statistiky
- ✅ 3D UI efekty
- ✅ Portable režim
- ✅ FFT Spectrum Analyzer
- ✅ Audio preprocessing
- ✅ Multi-provider fallback

### Fáze 2 — Kvalita rozpoznávání + UX (v1.5.x)

- ✅ Recognition Architecture v2.0 — třívrstvá architektura
- ✅ Paralelní zpracování první vrstvy
- ✅ LCD Pipeline vizualizace
- ✅ Texty skladeb s překladem
- ✅ Větší historie (3 skladby)
- ⬚ ACRCloud integrace (volitelná)
- ⬚ Headless / Tray mód
- ⬚ Fuzzy Search v historii

### Fáze 3 — Stream Deck (v2.0.0)

- ✅ Stream Deck plugin v1.0.0
- ✅ 12 akcí (hledat, kopírovat, platformy...)
- ✅ Nastavení délky nahrávání
- ✅ API server na portu 8764
- ⬚ Cover Art na tlačítku
- ⬚ Historie na Stream Decku
- ⬚ LCD vizualizace

---

## Řešení problémů

Viz [docs/troubleshooting.md](docs/troubleshooting.md) pro kompletní seznam.

**Nejčastější problémy:**

- **Aplikace nic nerozpozná** — ověř výchozí přehrávací zařízení ve Windows (Nastavení → Zvuk). Aplikace čte systémový výstup, ne mikrofon.
- **ACRCloud: "Daily limit reached"** — free tier má ~100 rozpoznání/den, limit se resetuje o půlnoci UTC.
- **AcoustID nefunguje** — ověř, že `fpcalc.exe` existuje ve složce aplikace vedle `.exe`.
- **Klíče se neuloží** — zkontroluj práva zápisu do `%LOCALAPPDATA%\SluchatkovyShazam\`.

---

## Dokumentace

- [docs/API-KEYS-GUIDE.md](docs/API-KEYS-GUIDE.md) — jak získat a nastavit volitelné API klíče (ACRCloud, AcoustID)
- [docs/troubleshooting.md](docs/troubleshooting.md) — řešení problémů

---

## Licence

Osobní použití zdarma. Úpravy a redistribuce pouze se svolením autora.

**Verze:** 1.5.1 | [Plná licence](LICENSE)
