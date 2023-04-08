# Active directory
- Objektová systémová databáze obsahující objekty reálné sítě
- Vytváří tak obraz sítě
- Objekty v AD:
  - Počítače
  - Uživatelé
  - Skupiny
  - Tiskárny
  - Sdílené složky

## 1. Vytváření složky v kořenovám adresáři
- Vytvoříme adresář pro adresáře domovské např. s názvem "Home" 
- **Vlastnosti** → **Sdílení** → **Rozšířené možnosti sdílení** → **☑ Sdílet tuto složku** → **Oprávnění**
- **Přidat...** → <u>**Název uživatele nebo skupiny**</u> → **Kontrola názvu** → **Ok** → **Oprávnění: ☑ změnit, ☑ číst** → **Ok**
- V kořenovém adresáři disku vytvoříme pro každou z organizačních jednotek adresář

## 2. Uživatelé a počítače služby Active directory
- **Uživatel** → **Vlastnosti** → **Profil** → **◉ Připojit _Z_: k: _\\SERVER\Home\<nazev organizační jednotky>\%username%_** → **Ok**

### Odstranění chráněného objektu
- **Zobrazit** → **Upřesňující funkce** → V kontextové nabídce vybereme **Vlastnosti** objektu → Karta **Objekt** → **□ Ochránit před náhodným odstraněním**

## Mapování jednotek
- Nasdílíme a zabezpečíme adresář
- **Start** → **Nástroje pro správu** → **Správa zásad skupiny**
- Vybereme organizační jednotku (nebo doménu), pro kterou se mapování vztahuje
- V kontextové nabídce vybereme **Vytvořit objekt zásady skupiny** -> Pojmenujeme zásadu
- **Konfigurace uživatele** → **Předvolby** → **Nastavení systému Windows** → **Mapování jednotek**
- V kontextové nabídce vybereme **Vytvořřit novou mapovanou jednotku**
- Provedeme nastavení mapované jednotky:
  - **Umístění**: síťová cesta k sdílení složce (\\<IP/FQDN>\<cesta k sdílenému adresáři>)
  - **Akce**: **Aktualizovat** (v případě existující)
  - **Použít**: **Volné písmeno síťové jednotky** (např. **I:**)
  - Volitelné zobrazení/skrytí síťové jednotky
- Vše potvrdit

## Synchronizace času
```cmd
NET TIME \\<IP/FQDN>\ /yes
```

## Zásady skupiny
- Slouží ke změně registrů na klientské stanici (logopn skripty, instalaci tiskáren, mapování disků)
- Konfigurace se provádí pomocí editoru zásad skupiny
- **Editor...** se nachází v **Nástroje pro správu**
- Po spuštění editoru vytvoříme novou zásadu skupiny na vhodném místě (je stále funkční dědění)
- Objekt zásad vytvoříme pravým tlačítkem a vybráním **Vytvořit objekt zásad skupny...**
- Pro úpravu v kontextové nabídce zásady vybereme **Upravit**

## Omezení uživatelskách účtů na klientské stanici
- V zásadách skupiny vybereme **Konfigurace** → **Uživatelé** → **Zásady**
- V položce **Šablony pro správu...** pak nastavujeme jednotlivá omezení (např. skrytí ikon na ploše)
- Pro aktualizaci politik na klientské stanicy je nutné stanici restartovat nebo provézt aktualizaci pomocí příkazu `GPUPDATE`
