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
```bash
1. V příkazovém řádku (CMD) jsem spustil příkaz `ipconfig /all` a zkopíroval důležité informace.  
2. Zapsal jsem IP adresu, masku podsítě, výchozí bránu, MAC adresu a DNS servery do tabulky.  
3. Pomocí příkazu `ping` jsem ověřil, že výchozí brána odpovídá a je aktivní.  
4. Nakonec jsem stručně popsal, jak výchozí brána funguje v síti.
```
---

## Použité příkazy
```bash
- `ipconfig /all` – zobrazení detailní IP konfigurace  
- `ping 192.168.1.1` – test dostupnosti výchozí brány
```
## Výstupy / Testy
### Výstup z `ipconfig /all`:
```bash

| Název položky        | Hodnota              |
|----------------------|----------------------|
| Název adaptéru       | Ethernet             |
| IPv4 Address         | 192.168.1.100        |
| Maska podsítě        | 255.255.255.0        |
| Výchozí brána        | 192.168.1.1          |
| DHCP server          | 192.168.1.1          |
| DNS server           | 8.8.8.8              |
```

---

## Reflexe

- **Naučil jsem se:**  
  Jak zjistit síťové nastavení pomocí `ipconfig /all` a co znamená výchozí brána.


