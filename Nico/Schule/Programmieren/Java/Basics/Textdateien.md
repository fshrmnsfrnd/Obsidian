---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[Java]]"
---

> [!NOTE] Exceptions
> Bei Dateizugriffen sollten immer `Try-Catch` Blöcke verwenden werden. Sonst kann es zu Programmabstürzen oder Fehlern in den Dateien führen. 
> [[Schule/Programmieren/Java/Basics/Fehlerbehandlung#Exceptions bei Dateizugriffen]]  
# Pfad zur Datei
---
Der Pfad muss vom Typ `Path` sein. Dafür muss `import java.nio.file.Path` und `import java.nio.file.Paths` importiert sein.

Um mit `./datei.txt` auf die Datei zuzugreifen, muss sie auf oberster Ebene im Projekt liegen.

**Pfad zum Userprofil:**
`Path pfad = Paths.get(System.getProperty("user.home")+"/datei.txt");`
# Exceptions bei Dateizugriffen
---
Bei Dateizugriffen sollte das Öffnen der Datei immer in den runden Klammern `()` des `try` Blocks passieren. Wenn anschließend das Programm abgebrochen wird bevor die Datei geschlossen wurde, werden diese Dateien trotzdem wieder geschlossen

```java
try ( 
	PrintWriter out = new PrintWriter("/Pfas/zur/Datei.txt") 
){ 
	out.println("Test2"); 
} catch (FileNotFoundException e) {
	// ... Fehlermeldung ... 
}
```
# Ganze Datei ausgeben
---
```java
try { 
	Path pfad = Paths.get("D:/wortliste.txt"); 
	for(String zeile : Files.readAllLines(pfad)){ 
		System.out.println(zeile); 
	} 
} catch (IOException e) { 
	System.err.println("Ein- oder Ausgabefehler: " + e.getLocalizedMessage()); 
} catch (InvalidPathException e) { 
	System.err.println("Ungültiger Pfad: " + e.getLocalizedMessage()); 
}
```
# In Datei schreiben
---
**Modul:** `import java.io.PrintWriter`
```java
try (
	PrintWriter out = new PrintWriter("D:/Ausgabedatei.txt"); // Stream öffnen
)
{
	out.println("Test2"); // eine Zeile schreiben 
catch(FileNotFoundException ex){
	System.out.println("Datei nicht gefunden");
}
```

> [!WARNING] Hier wird der Text in der Datei überschrieben
# Text an Datei anhängen
---
```java
Path pfad = Paths.get("D:/Ausgabedatei.txt"); 
try(
	BufferedWriter bw = Files.newBufferedWriter(pfad, StandardOpenOption.APPEND);
	PrintWriter out = new PrintWriter(bw); 
) 
{ 
	out.println("Test4"); 
}catch(FileNotFoundException ex){
	System.out.println("Datei nicht gefunden");
}
```
# Dateiauswahlfenster
---
```java
FileChooser fileChooser = new FileChooser(); 
fileChooser.setTitle("Datei öffnen"); 
File selectedFile = fileChooser.showOpenDialog(); 
if(selectedFile != null){
	Path pfad = selectedFile.toPath(); 
	// oder z.B. String pfadString = selectedFile.getPath();
```