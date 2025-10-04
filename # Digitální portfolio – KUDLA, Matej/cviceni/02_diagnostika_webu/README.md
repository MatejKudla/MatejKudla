# Cvičení 2 - Diagnostika dostupnosti webu

**Scénář**: Zákazník nahlásil problém s dosažitelností webového serveru www.eduxo.cz. 

---

## Zadání
- Zjistěte IP adresu serveru (`nslookup`).
- Ověřte dostupnost serveru (`ping`).
- Sledujte cestu paketů (`tracert` / `traceroute`).
- Napište krátkou zprávu s výsledky a možnými příčinami problému.


---

## Řešení

1. Pomocí příkazu `nslookup` jsem zjistil, jaká IP adresa je přiřazena doméně www.eduxo.cz.  
2. Pro ověření dostupnosti serveru jsem použil příkaz `ping`.  
3. Pomocí příkazu `tracert` (Windows) jsem sledoval cestu paketů k serveru a zkontroloval, kde může nastat problém.  
4. Na základě výsledků jsem sepsal krátkou zprávu s možným vysvětlením příčiny problému.
  
---

## Použité příkazy
```bash
- `nslookup www.eduxo.cz` – zjištění IP adresy serveru  
- `ping www.eduxo.cz` – ověření dostupnosti  
- `tracert www.eduxo.cz` – sledování cesty paketů
```
## Výstupy / Testy
### Výstup z `nslookup`:
```bash
Server: dns.google
Address: 8.8.8.8

Non-authoritative answer:
Name: www.eduxo.cz

Address: 193.85.203.98
```

### Výstup z `ping`:
```bash
Pinging www.eduxo.cz  
 [193.85.203.98] with 32 bytes of data:  
Reply from 193.85.203.98: bytes=32 time=15ms TTL=56  
Reply from 193.85.203.98: bytes=32 time=16ms TTL=56  
Reply from 193.85.203.98: bytes=32 time=14ms TTL=56  
Reply from 193.85.203.98: bytes=32 time=15ms TTL=56  

Ping statistics for 193.85.203.98:
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
```
### Výstup z `tracert`:
```bash
Tracing route to www.eduxo.cz
 [193.85.203.98]
over a maximum of 30 hops:

1 1 ms 1 ms 1 ms 192.168.1.1
2 8 ms 8 ms 8 ms 10.0.0.1
3 14 ms 13 ms 14 ms ...
...
9 16 ms 15 ms 15 ms 193.85.203.98
```
---

## Reflexe

- **Naučil jsem se:**  
  Jak pomocí jednoduchých nástrojů (`nslookup`, `ping`, `tracert`) rychle zjistit, zda je webový server        dostupný a kde může být problém.

- **Příště bych:**  
  Otestoval i jiné servery pro porovnání.

