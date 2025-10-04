# Cvičení 4 – Trasa k serveru  

## Scénář  
Chcete analyzovat cestu paketů k serveru Google (www.google.com).  

## Úkoly  
- Spusťte trasování (`tracert` / `traceroute`).  
- Poznamenejte si, kolik „hopů“ paketům trvá dosáhnout cíle.  
- Zhodnoťte, zda je trasa efektivní nebo obsahuje problémy.  

## Řešení  
- Pomocí příkazu `tracert www.google.com` (Windows) / `traceroute www.google.com` (Linux) jsem sledoval cestu paketů až k cílovému serveru.  
- Zaznamenal jsem počet „hopů“ a dobu odezvy jednotlivých uzlů.  
- Na základě výsledků jsem vyhodnotil, zda je trasa efektivní nebo zda se vyskytují problémy (např. timeouty, velká latence).  

## Použité příkazy
```bash
tracert www.google.com
# nebo na Linuxu
# traceroute www.google.com
```
## Výstup
```bash
tracert www.google.com
Tracing route to www.google.com [142.251.36.164]
over a maximum of 30 hops:

  1    <1 ms    <1 ms    <1 ms  192.168.1.1
  2    12 ms    14 ms    20 ms  10.100.50.1
  3     2 ms     2 ms     2 ms  core-r1-a12.example.net [83.240.10.53]
  4     6 ms     6 ms     6 ms  83.240.20.5
  5     6 ms     6 ms     6 ms  core-r2-b34.example.net [83.240.22.1]
  6     6 ms     6 ms     6 ms  94.74.99.217
  7     6 ms     6 ms     6 ms  isp-r1-c56.example.net [90.182.199.92]
  8     6 ms     6 ms     6 ms  74.125.48.222
  9     7 ms     7 ms     7 ms  192.178.200.183
 10     6 ms     6 ms     6 ms  209.85.240.117
 11     6 ms     6 ms     6 ms  google-server.example.net [142.251.36.68]

Trace complete.

```
## Závěr

- Počet hopů: 11
- Efektivita trasy: Trasa je rychlá a stabilní, latence je nízká (většinou 2–7 ms, maximum 20 ms na hopu 2).
- Problémy: Nebyly zjištěny žádné výpadky ani nestandardní chování.

## Reflexe

**Naučil jsem se:**
- Jak zjistit trasu paketů k cílovému serveru pomocí příkazu `tracert`.
- Jak vyhodnotit efektivitu trasy na základě počtu hopů a odezvy.

**Příště bych:**
- Porovnal výsledky trasování k různým serverům (např. v jiné zemi), abych viděl rozdíly v délce a latenci trasy.
