# Cvičení 4 – Trasa k serveru  

## Scénář  
Chcete analyzovat cestu paketů k serveru Google (www.google.com).  

## Úkoly  
- Spusťte trasování (`tracert` / `traceroute`).  
- Poznamenejte si, kolik „hopů“ paketům trvá dosáhnout cíle.  
- Zhodnoťte, zda je trasa efektivní nebo obsahuje problémy.  

## Řešení  
Pomocí příkazu `tracert www.google.com` (Windows) / `traceroute www.google.com` (Linux) jsem sledoval cestu paketů až k cílovému serveru.  
Zaznamenal jsem počet „hopů“ a dobu odezvy jednotlivých uzlů.  
Na základě výsledků jsem vyhodnotil, zda je trasa efektivní nebo zda se vyskytují problémy (např. timeouty, velká latence).  

## Použité příkazy  
- `tracert www.google.com` – sledování cesty paketů k serveru  

## Výstupy / Testy  
*(ukázkový výstup z Windows)*  
```bash
Tracing route to www.google.com
 [142.251.36.164]
over a maximum of 30 hops:

1 <1 ms <1 ms <1 ms 192.168.0.1
2 7 ms 6 ms 8 ms 10.55.208.129
3 9 ms 8 ms 9 ms brn-core-r2-vl251.netbox.cz [83.240.0.57]
4 12 ms 11 ms 11 ms prg-core-r2-vl32.netbox.cz [83.240.2.46]
5 15 ms 14 ms 15 ms 74.125.37.100
6 16 ms 15 ms 15 ms 142.251.36.164

Trace complete.
```


