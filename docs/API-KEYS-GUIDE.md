# Návod na instalaci API klíčů

SluchatkovyShazam funguje i bez API klíčů (používá Shazam a AudD.io), ale pro lepší rozpoznávání můžete přidat další poskytovatele.

## Dostupné databáze

| Databáze | Stav | API klíč potřeba |
|----------|------|------------------|
| Shazam | ✅ Vždy funkční | Ne |
| AudD.io | ✅ Vždy funkční | Ne |
| ACRCloud | ⚙️ Volitelný | Ano |
| AcoustID | ⚙️ Volitelný | Ano |

---

## ACRCloud (150+ milionů skladeb)

Profesionální služba s vysokou přesností (~95%). Free tier: ~100 rozpoznání/den.

### Krok 1: Registrace
1. Jděte na [acrcloud.com](https://www.acrcloud.com)
2. Klikněte **Sign Up** (pravý horní roh)
3. Vyplňte formulář a potvrďte email

### Krok 2: Vytvoření projektu
1. Po přihlášení klikněte **Create Project**
2. Vyplňte nastavení: 

| Pole | Hodnota |
|------|---------|
| **Project Name** | SluchatkovyShazam |
| **Audio Source** | **Recorded Audio** |
| **Audio Engine** | Audio Fingerprinting |
| **Buckets** | ACRCloud Music |

3. V sekci **3rd Party ID Integration** zaškrtněte:
   - ☑️ spotify
   - ☑️ deezer  
   - ☑️ youtube
   - ☑️ isrc
   - ☑️ upc

4. Zaškrtněte **Include Works**
5. Klikněte **Create**

### Krok 3: Zkopírujte klíče
V dashboard projektu najdete:
- **Access Key** - zkopírujte
- **Access Secret** - zkopírujte

### Krok 4: Vložte do aplikace
1. V SluchatkovyShazam otevřete **Nastavení** (ozubené kolečko)
2. Klikněte **API Klíče**
3. Vyplňte ACRCloud Access Key a Access Secret
4. Klikněte **Uložit**

✅ Zelené kolečko u ACRCloud = správně nakonfigurováno

---

## AcoustID / Chromaprint (20+ milionů skladeb)

Open-source databáze napojená na MusicBrainz. Dobrá pro méně známou hudbu.

### Krok 1: Registrace aplikace
1. Jděte na [acoustid.org/new-application](https://acoustid.org/new-application)
2. Přihlaste se pomocí MusicBrainz účtu (nebo si ho vytvořte)
3. Vyplňte **Application Name**: `SluchatkovyShazam`
4. Klikněte **Register**

<img width="909" height="468" alt="image" src="https://github.com/user-attachments/assets/a7cc00c3-4a9f-4021-95e0-9f30a601d8b9" />


### Krok 2: Zkopírujte API klíč
Po registraci se zobrazí váš **API Key** - zkopírujte ho.

### Krok 3: Vložte do aplikace
1. V SluchatkovyShazam → **Nastavení** → **API Klíče**
2. Vyplňte AcoustID API Key
3. Klikněte **Uložit**

✅ Zelené kolečko u AcoustID = správně nakonfigurováno

---

## Ověření funkčnosti

Po uložení klíčů v dialogu API Klíče uvidíte:
- 🟢 Zelené kolečko = databáze je funkční
- 🔴 Červené kolečko = chybí klíč nebo nefunguje

---

## Časté problémy

### ACRCloud hlásí "Daily limit reached"
Free tier má limit ~100 rozpoznání/den. Počkejte do půlnoci UTC.

### AcoustID nefunguje
1. Zkontrolujte, že `fpcalc.exe` existuje ve složce aplikace
2. Ověřte správnost API klíče
3. Restartujte aplikaci

### Klíče se neuloží
Zkontrolujte práva zápisu do `%LOCALAPPDATA%\SluchatkovyShazam\`
