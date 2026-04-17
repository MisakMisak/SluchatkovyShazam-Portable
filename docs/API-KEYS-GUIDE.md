# Návod na instalaci API klíčů

SluchatkovyShazam funguje i bez API klíčů — Shazam a AudD.io jsou vždy aktivní. ACRCloud a AcoustID jsou volitelné a zlepší pokrytí hlavně pro soundtracky, reklamy a méně známou hudbu.

## Přehled databází

| Databáze | Bez klíče | Pokrytí | Kdy pomáhá |
|----------|-----------|---------|------------|
| Shazam | Ano | 70M+ skladeb | Vždy aktivní, primární |
| AudD.io | Ano | 80M+ skladeb | Záchranná vrstva |
| ACRCloud | Volitelný | 150M+ skladeb | TV, reklamy, soundtracky |
| AcoustID | Volitelný | 20M+ skladeb | Indie, alternativa, méně známé |

---

## ACRCloud

Profesionální služba s vysokou přesností (~95 %). Free tier: ~100 rozpoznání/den.

### Krok 1: Registrace

1. Jdi na [acrcloud.com](https://www.acrcloud.com)
2. Klikni **Sign Up** (pravý horní roh)
3. Vyplň formulář a potvrď email

### Krok 2: Vytvoření projektu

1. Po přihlášení uvidíš dashboard:

   ![ACRCloud dashboard](https://github.com/user-attachments/assets/d6cc9c45-1035-4f41-ad62-53bebdcbb395)

2. V levém panelu klikni na **Create Project**:

   ![Create Project](https://github.com/user-attachments/assets/e22ae59d-c24c-4c81-b546-f9a96418eadf)

3. Vyplň nastavení projektu (typ: Audio Recognition, region libovolný):

   ![Nastavení projektu](https://github.com/user-attachments/assets/b673ef29-69cf-472c-8587-86ee8888702a)

### Krok 3: Zkopírování klíčů

V dashboardu projektu najdeš:

- **Access Key** — zkopíruj
- **Access Secret** — zkopíruj

Oba klíče vlož do dialogu **API Klíče** v aplikaci.

> ACRCloud klíče lze používat opakovaně — nemusíš zakládat nový projekt pro každou instalaci.

---

## AcoustID / Chromaprint

Open-source databáze napojená na MusicBrainz. Dobrá pro méně známou a indie hudbu.

### Krok 1: Registrace aplikace

1. Jdi na [acoustid.org/new-application](https://acoustid.org/new-application)
2. Přihlas se přes MusicBrainz účet (nebo si ho vytvoř na místě)
3. Vyplň **Application Name**: `SluchatkovyShazam`
4. Klikni **Register**

   ![AcoustID registrace](https://github.com/user-attachments/assets/a7cc00c3-4a9f-4021-95e0-9f30a601d8b9)

### Krok 2: Zkopírování klíče

Po registraci se zobrazí tvůj **API Key** — zkopíruj ho a vlož do dialogu **API Klíče** v aplikaci.

> AcoustID vyžaduje nový klíč pro každou aplikaci. Nemůžeš použít klíč z jiné aplikace.

---

## Ověření funkčnosti

Po uložení klíčů v dialogu uvidíš indikátory stavu:

- Zelené kolečko — databáze je aktivní a klíč je platný
- Červené kolečko — chybí klíč nebo ověření selhalo

![Indikátory stavu](https://github.com/user-attachments/assets/02b0af9b-008b-48b9-8ab4-e31336e39153)

Klíče jsou ověřovány **skutečným voláním API** před uložením — neplatný klíč je odmítnut okamžitě.

---

## Časté problémy

### ACRCloud: "Daily limit reached"

Free tier má limit ~100 rozpoznání/den. Limit se resetuje o půlnoci UTC. Pokud potřebuješ vyšší limit, ACRCloud nabízí placené plány.

### AcoustID nefunguje

1. Ověř, že `fpcalc.exe` existuje ve složce aplikace vedle `SluchatkovyShazam.exe`
2. Ověř správnost API klíče — AcoustID klíč musí být registrován pro tuto aplikaci
3. Restartuj aplikaci po vložení klíče

### Klíče se neuloží

Zkontroluj práva zápisu do `%LOCALAPPDATA%\SluchatkovyShazam\`. Na některých firemních počítačích může být složka chráněná.
