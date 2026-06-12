---
Fach:
Thema:
  - "[[Security]]"
---
# Was ist Diffie-Hellman
---
Diffie-Hellman ist ein Protokoll zum **Schlüsselaustausch** bzw. **Schlüsselvereinbarung**. Dieser ermöglicht, dass zwei Kommunikationspartner über eine **öffentliche**, **abhörbare** Leitung einen geheimen Schlüssel in Form einer **Zahl** vereinbaren. Dieser Schlüssel kann dann für symmetrische Krypto Systeme verwendet werden. (z. B. DES oder AES). Verschiedene Varianten des Diffie-Hellman-Merkle-Verfahrens werden heute in verschiedenen Kommunikations- und Sicherheitsprotokollen des Internets eingesetzt. (**HTTPS**, **IPsec**, **SSH**, ...)  
Weitere Protokolle zur Schlüssel Verteilung sind z. B.: Elgamal (ähnlich wie Diffie-Hellman) oder DSA (von der NSA entworfen und bassiert auf Elgamal)

# Veranschaulichung
---
1) Beide Kommunikationspartner **starten** mit der **selben Primzahl** (hier Farbe)  
2) Beide erstellen eine neue **geheime Primzahl**  
3) Primzahl 1 und 2 werden miteinander verrechnet (Farben gemischt)  
4) Das Ergebnis wird dem anderen übermittelt  
5) Anschließend wird die erhaltene Zahl wieder mit der eigenen geheime Verrechnet  
6) Das Ergebnis besteht bei beiden jetzt aus: 
	- gemeinsame Primzahl + 
	- eigene geheime Primzahl +
	- andere geheime Primzahl


![[Pasted image 20251117233703.png]]

# Vor- und Nachteile
---

| **Vorteile**                                                            | **Nachteile**                                           |
| ----------------------------------------------------------------------- | ------------------------------------------------------- |
| beseitigt Schlüssel austausch Problem der symmetrischen Verschlüsselung | Anfällig für Man-in-the-Middle Angriffe                 |
| jedes mal wird ein neuer schlüssel verwendet                            | verwendung von Festen Primzahlen kann ausgenutzt werden |
