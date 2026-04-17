# Řešení problémů

---

## Aplikace nic nerozpozná

**Příčina:** Aplikace čte systémový audio výstup (WASAPI loopback) — co slyší Windows, to slyší i aplikace. Pokud výstup není nakonfigurován správně, aplikace nemá co analyzovat.

**Řešení:**

1. Otevři **Nastavení Windows → Systém → Zvuk**
2. Ověř, že je nastaveno výchozí přehrávací zařízení (reproduktory nebo sluchátka)
3. Ověř, že hlasitost systému není na nule nebo ztlumena
4. Pokud používáš virtuální audio zařízení (VB-Cable, Voicemeeter), ověř, že je nastaveno jako výchozí výstup

**Poznámka:** Aplikace nepotřebuje, aby zvuk byl slyšitelný — stačí, že prochází přes systémový výstup. Hlasitost může být nízká.

---

## Rozpoznávání trvá dlouho nebo selže

**Příčina:** Databáze mají různé latence. Shazam bývá nejrychlejší (~2 s), ACRCloud a AudD.io mohou trvat déle.

**Řešení:**

- Prodluž délku nahrávání (+5s tlačítkem nebo v nastavení) — delší vzorek = vyšší šance na úspěch
- Ověř internetové připojení — všechny databáze jsou online
- Soundtracky z filmů nebo reklamy mají nižší pokrytí v základních databázích → nastav [ACRCloud API klíč](API-KEYS-GUIDE.md#acrcloud)

---

## ACRCloud: "Daily limit reached"

**Příčina:** Free tier ACRCloud má limit ~100 rozpoznání/den.

**Řešení:**

- Počkej do půlnoci UTC (reset limitu)
- Aplikace automaticky přejde na AudD.io jako fallback
- Pokud potřebuješ vyšší limit, ACRCloud nabízí placené plány na [acrcloud.com](https://www.acrcloud.com)

---

## AcoustID / Chromaprint nefunguje

**Příčina:** Chybí `fpcalc.exe` nebo je neplatný API klíč.

**Řešení:**

1. Ověř, že `fpcalc.exe` existuje ve složce aplikace vedle `SluchatkovyShazam.exe`
2. Pokud soubor chybí, stáhni znovu zip z [releases](https://github.com/MisakMisak/SluchatkovyShazam-Portable/releases/latest) a rozbal ho znovu
3. Ověř správnost API klíče v dialogu API Klíče

---

## API klíče se neuloží

**Příčina:** Nedostatečná práva zápisu do `%LOCALAPPDATA%\SluchatkovyShazam\`.

**Řešení:**

1. Otevři `%LOCALAPPDATA%` v Průzkumníku (Win+R → `%LOCALAPPDATA%`)
2. Ověř, že složka `SluchatkovyShazam` existuje a jsi vlastníkem
3. Na firemních počítačích může být složka chráněná — obrať se na IT správce

---

## Texty skladeb se nenačítají

**Příčina:** LRCLIB.net API není dostupné nebo pro danou skladbu nemá text.

**Řešení:**

- Ověř internetové připojení
- Ne všechny skladby mají text v databázi LRCLIB — platí hlavně pro instrumentální, méně známé nebo velmi nové nahrávky
- Zkus rozpoznat znovu — občas pomůže jiný výsledek z jiné databáze (jiný ISRC kód → jiné hledání textů)

---

## Aplikace se nespustí

**Příčina:** Chybí Visual C++ redistributable nebo antivirus blokuje spuštění.

**Řešení:**

1. Ověř, že jsi rozbalil celý zip — nestačí spustit `.exe` přímo z archivu
2. Pokud antivirus označil soubor jako hrozbu: aplikace je unsigned (bez code signing certifikátu), což někteří antiviry hlásí jako false positive. Přidej výjimku pro složku aplikace.
3. Pokud chybí runtime: stáhni a nainstaluj [Visual C++ Redistributable 2022](https://aka.ms/vs/17/release/vc_redist.x64.exe)

---

## Stream Deck plugin nefunguje

**Příčina:** Aplikace není spuštěna nebo API server na portu 8764 není dostupný.

**Řešení:**

1. Ověř, že `SluchatkovyShazam.exe` běží
2. Ověř dostupnost API serveru: otevři `http://localhost:8764/api/health` v prohlížeči — měl by vrátit `{"status": "ok"}`
3. Zkontroluj firewall — port 8764 musí být dostupný lokálně
4. Restartuj Stream Deck software po každé reinstalaci pluginu

---

## Problém není v tomto seznamu

Otevři issue na [GitHubu](https://github.com/MisakMisak/SluchatkovyShazam-Portable/issues) s:

- Popisem problému
- Verzí aplikace (viz záhlaví okna nebo název zip souboru)
- Verzí Windows
- Co přesně jsi zkoušel
