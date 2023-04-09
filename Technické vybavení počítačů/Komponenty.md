# Komponenty
## Pevné disky
### SSD
```diff
+ Rychlost
+ Odolnost
- Postupným přepisem klesá rychlost a snižuje se použitelná kapacita
```
### HDD
```diff
+ Kapacita
- Náchylnost k poškození
- Pomalé
```
### Použití:
- Klasické PC
- Servery
- NAS (WD RED)
- Notebooky
- PVR

### Rozhraní dle umístění:
- Interní
  - IDE (PAT)
    - Připojení jednoho/dvou disků na jednu sběrnici
    - Napájení: MOLEX
  - SATA
    - Připojení jednoho disku na jednu sběrnici
    - Napájení: SATA POWER
  - SCSI
- Externí
  - USB
    - Připojení jednoho disku na jednu sběrnici
    - Napájení: 2,5" - USB, 5,25" - Adaptér
  - FireWire
    - Připojení jednoho disku na jednu sběrnici
    - Napájení: Adaptér
  - E-SATA
    - Připojení jednoho disku na jednu sběrnici
    - Napájení: E-SATA, SATA PWR
  - LAN
    - Připojení jednoho disku na jednu sběrnici
    - Napájení: Adaptér

### Pinout napájecích konektorů:
- SATA PWR - 12V; 5V; 3,3V
- MOLEX - / 12V; GND; GND; 5V \
- USB - 5V; D+; D-; GND

### Fyzická struktura pevného disku
Základní struktura:
- Plotny (povlak oxidu železa)

![fyzicka-struktura-pevneho-disku](https://user-images.githubusercontent.com/44552607/230747781-5c436cab-1711-4254-82db-97e93d31c72a.png)

Pozice čtených dat je podle geometrie CHS určena pomocí hodnot: stopa-hlava-sektor
![cylindr-stopa-sektor](https://user-images.githubusercontent.com/44552607/230747833-53959212-e32d-4453-b72b-d38cadb22e87.jpg)

Fyzické formátování:
- Disk se dělí na:
  - stopy
  - sektory (512b)
    - hlavička (100b) - informace o obsahu
- Formátování provádí řadič

Teplotní kalibrace:
- Při zátěži dochází ke vzniku telpla
- Kontrola polohy čtecí hlavy
- Nové disky i za provozu

Rychlost:
- 3600 rpm; 7200 rpm; 10000 rpm

Kapacita:
- 20 GB; 40 GB; 1 TB; 2 TB; 3 TB; 4 TB; 6 TB; 8 TB; 10 TB; 12 TB; 14 TB; 16 TB; 18 TB

Řadič:
- Zajišťuje komunikaci mezi základní deskou a pevným diskem

### Logická struktura pevného disku
- Relativní sektory
- Alokaní jednotky
- Master Boot Record (MBR) - 0. relativní sektor, 0. stopa (512 b)
  - Zaváděcí záznam
- DOS Boot record (DBR)
- Extended Pratitions Table (EPT)
- Hlavní adresář v organizaci FAT
- Hlavní adresář v organizaci VFAT

#### Raidová pole
- Existují 2 základná způsoby vytvoření RAID pole
  - Hardwarový (použití speciálního řadiče)
  - Softwarový (v OS)

##### Typy
- RAID 0 (stripping)
  - Součet kapacit disků
  - Zničení jednoho disku = zničení všech dat
  - 1 TB a 1 TB → 2 TB
- RAID 1 (mirror)
  - Stejná data na obou discích
  - 1 TB a 1 TB → 1 TB
- RAID 3, RAID 5, RAID 10, RAID 01, RAID 10, JBOD
