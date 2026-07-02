---
Thema:
  - "[[Elektrotechnik]]"
---
# 1.Fall
---
![[Bitrate vs. Baudrate 02-10-25 14.06.15.excalidraw]]$U=1V\widehat{=}$      logisch 1
$U=-1V\widehat{=}$    logisch 0
In diesem Beispiel liegt eine Bitrate von $1\frac{Bit}{s}$ vor.

# 2. Fall
---
Es gibt vier Spannungspegel, die pro Taktwechsel übertragen werden.
![[Bitrate vs. Baudrate 02-10-25 14.14.13.excalidraw]]
$U = 1V; U = 2V;  U = -1V; U = -2V;$    

> [!NOTE] 
> Hier Übertragung von 1 Symbol pro Sekunde

| 4 Zustände => 2 Bit | Symbole |
| ------------------- | ------- |
| 00                  | $-2V$   |
| 01                  | $-1V$   |
| 10                  | $1V$    |
| 11                  | $2V$    |
**Symbolrate:** 1 $Baud$ $\widehat{=}$ 1 $\frac{Symbol}{s}$
Hier haben wir 2$\frac{Bit}{Symbol}$ 

> [!NOTE] Datenübertragungsrate
> $C = 1$ Baud $*2\frac{Bit}{Symbol}$
> $C = 2\frac{Bit}{s}$

# Übungen
---
## Übung 1
Es sollen pro Taktwechsel 3 Bit übertragen werden. Wie viele Zustände muss das zu Übertragende Symbol haben .
**Lösung:** Zustände = $2^3 = 8$

## Übung 2
Es werden Symbole mit 32 Zuständen übertragen. Wie viele Bit transportiert jedes Symbol?
**Lösung:** $\frac{Bit}{Symbol} = log_2(32)$ 

## Übung 3
Es wird pro Sekunde ein Symbol mit insgesamt 24 Zuständen Übertragen. Wie viel Bit pro Sekunde sind das?
**Lösung:** $log_2(24) \approx 4,585 \frac{Bit}{S}$ 

## Übung 4
Welche Symbolrate ist bei einer Datenrate von 10Gbit/s mit 4D-PAM16-Codierung mindestens notwendig?
**Lösung:** $10 \frac{GBits}{s} / (4bit * log_2(16)) = 625MBaud$ 