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
 – zjištění IP adresy serveru
```bash
nslookup www.eduxo.cz
```
– ověření dostupnosti 
```bash
ping www.eduxo.cz  
```
– sledování cesty paketů
```bash
tracert www.eduxo.cz  
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
  1    <1 ms    <1 ms    <1 ms  192.168.0.1
  2    98 ms     8 ms    35 ms  10.55.208.129
  3     1 ms     1 ms     1 ms  brn-core-r2-vl251.netbox.cz [83.240.0.57]
  4     5 ms     4 ms     4 ms  prg-core-r2-vl32.netbox.cz [83.240.2.46]
  5     5 ms     4 ms     4 ms  prg-edge-r2-vl32.netbox.cz [83.240.2.45]
  6     4 ms     4 ms     4 ms  94.74.231.221
  7     *        *        5 ms  90-182-199-220.rcp.o2.cz [90.182.199.220]
  8     *        *        *     Request timed out.
  9     6 ms     6 ms     6 ms  192.178.98.175
 10     5 ms     6 ms     5 ms  142.251.224.123
 11     5 ms     5 ms     6 ms  prg03s11-in-f19.1e100.net [142.251.36.115]
```
---
# Zpráva – Diagnostika dostupnosti webu www.eduxo.cz    
- Příkaz `ping` potvrdil, že server odpovídá – všechny pakety byly doručeny bez ztrát, s odezvou kolem 15 ms.    
- Při sledování cesty paketů (`tracert`) byla vidět funkční komunikace přes lokální síť i poskytovatele, nicméně na jednom z uzlů došlo k časovému vypršení odpovědi. Trasa však pokračovala dál a cílový server byl     dosažen.  

## Možné příčiny problému  
- Dočasné omezení nebo filtrování ICMP odpovědí na některém směrovači (běžná praxe u providerů).    
- Krátkodobé přetížení konkrétního uzlu na trase.    
- Samotný server **www.eduxo.cz** je podle testů dostupný, problém tedy nebude přímo na cílovém stroji, ale mohl být vyvolán buď lokálním nastavením u zákazníka, nebo výpadkem v trase, který byl mezitím obnoven.    
---
## Reflexe

- **Naučil jsem se:**  
  Jak pomocí jednoduchých nástrojů (`nslookup`, `ping`, `tracert`) rychle zjistit, zda je webový server        dostupný a kde může být problém.

- **Příště bych:**  
  Otestoval i jiné servery pro porovnání.
