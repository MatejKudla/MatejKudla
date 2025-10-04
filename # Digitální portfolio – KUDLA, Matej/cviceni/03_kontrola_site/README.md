# Cvičení 3 – Kontrola lokální sítě

**Scénář**: Váš počítač nemá přístup k internetu.

## Zadání
- Zjistěte svou IP adresu a masku (`ipconfig` / `ifconfig`).
- Ověřte dostupnost routeru (`ping <IP routeru>`).
- Zkontrolujte ARP tabulku (`arp -a`).
- Shrňte, zda je problém u vás nebo u poskytovatele.
---

## Řešení  

1. Pomocí příkazu `ipconfig` (Windows) jsem zjistil svou aktuální IP adresu a masku podsítě.  
2. Ověřil jsem dostupnost domácího routeru pomocí příkazu `ping` na jeho IP adresu.  
3. Prohlédl jsem si ARP tabulku příkazem `arp -a`, abych zjistil, zda má počítač správně přiřazené MAC adresy zařízení v síti.  
4. Na základě zjištěných údajů jsem vyhodnotil, jestli je problém v mém počítači, v lokální síti nebo u poskytovatele připojení.

---

## Použité příkazy
– zjištění IP adresy a masky
```bash
    ipconfig
```
– otestování dostupnosti routeru
```bash   
    ping <IP adresa>
```
– zobrazení ARP tabulky (MAC adresy zařízení v síti)
```bash
    arp -a 
```
---

## Výstupy / Testy

### Výstup z `ipconfig`:
```bash
   IPv4 Address. . . . . . . . . . . : 192.168.42.137
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . : 192.168.42.137
```
### Výstup z `ping 192.168.42.137`:
```bash
Pinging 192.168.42.137 with 32 bytes of data:
Reply from 192.168.42.137: bytes=32 time<1ms TTL=128
Reply from 192.168.42.137: bytes=32 time<1ms TTL=128
Reply from 192.168.42.137: bytes=32 time<1ms TTL=128
Reply from 192.168.42.137: bytes=32 time<1ms TTL=128

Ping statistics for 192.168.42.137:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
```

### Výstup z `arp -a`:
```bash
  Interface: 192.168.42.137 --- 0x9
  Internet Address      Physical Address      Type
  192.168.0.1           20-23-51-f4-4d-f0     dynamic
  192.168.0.144         4a-db-47-6c-cd-03     dynamic
```
## Shrnutí  
Síťová karta a router fungují správně, komunikace v lokální síti je bez problémů.  
Příčina nedostupnosti internetu je tedy pravděpodobně na straně poskytovatele.

---
## Reflexe

- **Naučil jsem se:**  
  Jak zkontrolovat základní síťové nastavení a ověřit funkčnost lokální sítě pomocí několika příkazů.
- **Příště bych:**  
  Zkusil také `tracert` nebo `nslookup`.
