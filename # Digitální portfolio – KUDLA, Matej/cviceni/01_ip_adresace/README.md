# Cvičení 1 - Zjištění IP adresy

**Scénář**: Zjistěte, jakou IP adresu, masku podsítě a výchozí bránu má váš počítač.

---

## Zadání
- Použijte příkaz `ipconfig /all` (Windows) nebo `ip addr` (Linux).
- Zapište do tabulky hodnoty, které jste zjistili.
- Krátce vysvětlete, jakou funkci má výchozí brána.

---

## Řešení

1. V příkazovém řádku (CMD) jsem spustil příkaz `ipconfig /all` a zkopíroval důležité informace.  
2. Zapsal jsem IP adresu, masku podsítě, výchozí bránu a DNS servery do tabulky.  
3. Pomocí příkazu `ping` jsem ověřil, že výchozí brána odpovídá a je aktivní.  
4. Nakonec jsem stručně popsal, jak výchozí brána funguje v síti.

---

## Použité příkazy
– zobrazení detailní IP konfigurace
```bash
  ipconfig /all
```
– test dostupnosti výchozí brány
```bash 
  ping <IP adresa> 
```
## Výstupy / Testy
### Výstup z `ipconfig /all`:

```bash
---------------------------------------------------------------------
| Název položky        | Hodnota                                    |
|----------------------|--------------------------------------------|
| Název adaptéru       | Realtek PCIe GbE Family Controller         |
| IPv4 Address         | 192.168.1.100                              |
| Maska podsítě        | 255.255.255.0                              |
| Výchozí brána        | 192.168.1.1                                |
| DNS server           | 8.8.8.8                                    |
--------------------------------------------------------------------
```

---
## Co je to výchozí brána? 

Výchozí brána (default gateway) je síťové zařízení – obvykle router – přes které tvůj počítač komunikuje s jinými sítěmi mimo lokální síť (LAN).  

---

## Reflexe

- **Naučil jsem se:**  
  Jak zjistit síťové nastavení pomocí `ipconfig /all` a co znamená výchozí brána.

