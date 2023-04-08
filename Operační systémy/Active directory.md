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
- **Uživatel** → **Vlastnosti** → **Profil** → **◉ Připojit _Z_: k: _\\server\Home\<nazev organizační jednotky>\%username%_** → **Ok**

### Odstranění chráněného objektu
- **Zobrazit** → **Upřesňující funkce** → **Vlastnosti** objektu → Karta **Objekt** → **□ Ochránit před náhodným odstraněním**

## Mapování jednotek
- Nasdílíme a zabezpečíme adresář
- **Start** → **Nástroje pro správu** → **Správa zásad skupiny**
