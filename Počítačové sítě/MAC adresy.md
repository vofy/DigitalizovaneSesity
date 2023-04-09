# MAC adresy
- Slouží ke komunikaci an L2 OSI
- Dělení
  - Unicast
    - Jedinečný identifikátor síťového rozhraní
    - Lze ji "podvrhnout" tzv. MAC spoofing
    - Je pevně přiřazená výrobcem

      ```
      08-00-24-EC-10-61
      |        |
      |        UI - Unique identifier (device)
      OVI - Organizationally unique identifier (vendor)
      ```
  - Multicast
    - Používá se pro aplikaci nebo protokol

      ```
      01-00-5E-00-00-05
      |        |
      |        UI - Unique identifier (device)
      Multicast prefix
      ```
  - Broadcast
    - Všechna zařízení v síti
      ```
      FF-FF-FF-FF-FF-FF
      |
      Broadcast
      ```
      
- Zápis:
  - Linux, Apple, UNIX:
    - `08:00:27:EC:10:61`
  - Microsoft:
    - `08-00-27-EC-10-61`
  - Cisco:
    - `0800.27EC.1061`
- Zjištění MAC adresy zařízení:
  - Linux: `ip a`
  - Windows: `ipconfig`
