---
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
# Prinzip
![[Pasted image 20250522101551.png]]

# Beispiel
```php
<?php
	// 1. Template Quelltext laden
	$html = file_get_contents("template.html");
	// 2. alle Platzhalter ersetzen
	$html = str_replace("{Platzhalter1}","Wert1",$html);
	$html = str_replace("{Platzhalter2}","Wert2",$html);
	$html = str_replace("{Platzhalter3}","Wert3",$html);
	// 3. Fertige Seite ausgeben
	print($html);
?>
```
