# ADA P1 Meter integráció

![HACS Default](https://img.shields.io/badge/HACS-Default-orange.svg?style=flat-square)
![Home Assistant](https://img.shields.io/badge/Supports-Home%20Assistant-blue?style=flat-square)
![HACS Supported](https://img.shields.io/badge/HACS-Supported-41BDF5?style=flat-square)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/greenhess/adap1meter?style=flat-square)
![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green?style=flat-square)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)
![Platform: Sensor](https://img.shields.io/badge/Platform-Sensor-lightgrey?style=flat-square)

Ez az integráció lehetővé teszi az **ADA P1 Meter** eszköz adatainak lekérését a Home Assistant rendszerbe. Az integráció egy helyi hálózaton keresztül kommunikál az eszközzel, és számos szenzorral látja el a rendszert, amelyek az energiafogyasztással, feszültséggel, áramerősséggel és egyéb adatokkal kapcsolatos információkat jelenítenek meg.

---

## Telepítés

### 1. HACS-en keresztül
1. Nyisd meg a Home Assistant felületét, és menj a **HACS** menübe.
2. Kattints a **Integrációk** fülre.
3. Kattints a jobb felső sarokban lévő három pontra, majd válaszd a **Custom repositories** lehetőséget.
4. Add meg a GitHub repository URL-jét:  
   `https://github.com/faustlod/adap1meter`
5. Válaszd ki a **Integration** kategóriát, majd kattints a **Hozzáadás** gombra.
6. Az integráció meg fog jelenni a HACS-ben. Telepítsd és konfiguráld a szokásos módon.

### 2. Manuális telepítés
1. Töltsd le az integráció fájljait a GitHub repository-ból.
2. Másold az `ada_okos_mero` mappát a `custom_components` mappába a Home Assistant konfigurációs könyvtárában.
3. Indítsd újra a Home Assistant-t.

---

## Konfiguráció

Az integráció hozzáadása után a Home Assistant felületén keresztül konfigurálhatod az eszközt:

1. Menj a **Beállítások** > **Eszközök és szolgáltatások** menübe.
2. Kattints a jobb alsó sarokban lévő **+ Integráció hozzáadása** gombra.
3. Keress rá az **ADA P1 Meter** integrációra, és kattints rá.
4. Add meg az eszköz IP-címét és portját (alapértelmezett port: `8989`).
5. Kattints a **Küldés** gombra.

---

## Szenzorok

Az integráció a következő szenzorokat hozza létre:

### Energiafogyasztás
- **Összes importált energia** (`active_import_energy_total`)
- **Első tarifán mért összes energia** (`active_import_energy_tariff_1`)
- **Második tarifán mért összes energia** (`active_import_energy_tariff_2`)
- **Harmadik tarifán mért összes energia** (`active_import_energy_tariff_3`)
- **Negyedik tarifán mért összes energia** (`active_import_energy_tariff_4`)
- **Összes exportált aktív energia** (`active_export_energy_total`)
- **Első tarifán mért exportált energia** (`active_export_energy_tariff_1`)
- **Második tarifán mért exportált energia** (`active_export_energy_tariff_2`)
- **Harmadik tarifán mért exportált energia** (`active_export_energy_tariff_3`)
- **Negyedik tarifán mért exportált energia** (`active_export_energy_tariff_4`)
- **Összes energia** (`total_active_energy`)

### Feszültség és áramerősség
- **Feszültség L1** (`voltage_phase_l1`)
- **Feszültség L2** (`voltage_phase_l2`)
- **Feszültség L3** (`voltage_phase_l3`)
- **Áramerősség L1 (mérőóra adat)** (`current_phase_l1`)
- **Áramerősség L2 (mérőóra adat)** (`current_phase_l2`)
- **Áramerősség L3 (mérőóra adat)** (`current_phase_l3`)
- **Áramerősség L1 (kalkulált adat)** (`current_phase_Bl1`)
- **Áramerősség L2 (kalkulált adat)** (`current_phase_Bl2`)
- **Áramerősség L3 (kalkulált adat)** (`current_phase_Bl3`)

### Egyéb szenzorok
- **Teljesítménytényező** (`power_factor`)
- **Teljesítménytényező L1** (`power_factor_l1`)
- **Teljesítménytényező L2** (`power_factor_l2`)
- **Teljesítménytényező L3** (`power_factor_l3`)
- **Rendszer frekvencia** (`frequency`)
- **Jelenlegi áramfelvétel** (`instantaneous_power_import`)
- **Jelenlegi exportált teljesítmény** (`instantaneous_power_export`)
- **Pillanatnyi meddő teljesítmény (Import Induktív)** (`instantaneous_reactive_power_qi`)
- **Pillanatnyi meddő teljesítmény (Import Kapacitív)** (`instantaneous_reactive_power_qii`)
- **Pillanatnyi meddő teljesítmény (Export Induktív)** (`instantaneous_reactive_power_qiii`)
- **Pillanatnyi meddő teljesítmény (Export Kapacitív)** (`instantaneous_reactive_power_qiv`)
- **Áramerősség korlátja L1** (`current_limit_l1`)
- **Áramerősség korlátja L2** (`current_limit_l2`)
- **Áramerősség korlátja L3** (`current_limit_l3`)

---

## Köszönet

Ez a projekt a **GreenHESS** által kifejlesztett [ADA P1 Meter integráció](https://github.com/greenhess/adap1meter) inspirálta. Köszönet a **GreenHESS**-nek az eszközért és az ötletért!

---

## Hibaelhárítás

- **Az eszköz nem található**: Ellenőrizd, hogy az eszköz és a Home Assistant ugyanazon a hálózaton van-e, és hogy az IP-cím és port helyesen van-e megadva.
- **Hibás adatok**: Ellenőrizd, hogy az eszköz firmware-e naprakész-e, és hogy az API elérhető-e a megadott URL-en.

---

## Közreműködés

Ha szeretnél közreműködni az integráció fejlesztésében, nyisd meg az issue-kat vagy küldj pull request-et a GitHub repository-ban:  
[GitHub Repository](https://github.com/faustlod/adap1meter)

---

## Licenc

Ez a projekt az **MIT licenc** alatt áll. További információkért lásd a [LICENSE](LICENSE) fájlt.

---

Köszönjük, hogy az **ADA P1 Meter** integrációt használod! Ha bármilyen kérdésed van, nyugodtan lépj kapcsolatba velünk. 😊

---

### További információk
- **Fejlesztő**: Faustlod
- **GitHub**: [faustlod](https://github.com/faustlod)
- **Verzió**: 1.0
