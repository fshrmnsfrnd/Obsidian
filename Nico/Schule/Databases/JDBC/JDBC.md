---
Fach: "[[DB]]"
Thema:
  - "[[Databases]]"
  - "[[Java]]"
---
**JDBC** oder auch **J**ava **D**ata**b**ase **C**onnectivity ist eine Standard-API in Java welche eine Verbindung zu Datenbanken ermöglicht. Zudem werden darüber Befehle ausgeführt.
Dazu gehört:  
-  Java-Anwendung mit einer **Datenbank** (hier) **verbinden**  
- Ausführen von **SQL Befehlen** mit und ohne Parametern (`PreparedStatement`) **ausführen**  
- **Abfragen** von Daten und dessen Weiterverarbeitung  
-  **CRUD**-Operationen (**C**reate, **R**ead, **U**pdate, **D**elete)
# Voraussetzungen
---
+ Verbindung zu Datenbank (z.B. `localhost:3306`)
+ MySQL JDBC Treiber im `Maven` Projekt: `pom.xml`:
```xml
<dependency>
	<groupId>com.mysql</groupId>
	<artifactId>mysql-connector-j</artifactId>
	<version>9.0.0</version>
</dependency>
```
# Database Connection
---
**Connection URL:** `jdbc:mysql://HOST:PORT/DATABASE?OPTIONS`

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class DatabaseConnection{
    private static Connection con = null;

    public static void connect(String host,String port, String user, String pwd) throws SQLException{
        if (con != null) {
            if (!con.isClosed()) {
                con.close();
            }
        }
        String url = "jdbc:mysql://%host:%port/dbVerein";
        url = url.replace("%host", host);
        url = url.replace("%port", port);
        con = DriverManager.getConnection(url,user,pwd);
    }

    public static Connection getConnection(){return con;}

    public static void close() throws SQLException{
        if (con != null){
            con.close(); con = null;
        }
    }
}
```
# Best Practise 
---
- Immer `PreparedStatement` verwenden – vermeidet SQL-Injection 
- Ressourcen immer mit ``try-with-resources`` schließen 
- Verbindungspools nutzen in größeren Projekten 
- Exception-Handling sauber strukturieren 
- Bei häufigem Zugriff sollten DAO-Klassen (Data Access Objects) verwendet werden.
# Ohne Parameter
---
```java
import java.sql.*; 

String sql = "DELETE FROM users"; // löscht alle Zeilen 

try(Connection conn = DatabaseConnection.getConnection(); 
		Statement stmt = conn.createStatement()){ 
	int affected = stmt.executeUpdate(sql); //Anzahl affected Rows
} catch (SQLException e) { 
	e.printStackTrace(); 
}
```
# Mit Parameter
---
```java
import java.sql.*; 
String sql = "INSERT INTO users (name, email) VALUES (?, ?)"; 

try(Connection conn = DatabaseConnection.getConnection(); 
		PreparedStatement pstmt = conn.prepareStatement(sql)) { 
	pstmt.setString(1, "Max Mustermann"); 
	pstmt.setString(2, "max@example.com"); 
	int rows = pstmt.executeUpdate(); //Anzahl affected Rows
} catch (SQLException e) { 
	e.printStackTrace(); 
}
```
# Abfragen
---
```java
import java.sql.*; 
String sql = "SELECT * FROM users"; 

try (Connection conn = DatabaseConnection.getConnection(); 
		Statement stmt = conn.createStatement(); 
		ResultSet rs = stmt.executeQuery(sql)) { 
	while (rs.next()) { 
		int id = rs.getInt("id"); 
		String name = rs.getString("name"); 
		String email = rs.getString("email"); 
		System.out.printf("%d | %s | %s%n", id, name, email); 
	} 
} catch (SQLException e) { 
	e.printStackTrace();
} 
```
# CRUD
---
## Insert
```java
import java.sql.*;
  
String sql = "INSERT INTO users (name, email) VALUES (?, ?)";
  
try (Connection conn = DatabaseConnection.getConnection();
        PreparedStatement pstmt = conn.prepareStatement(sql)) {
    pstmt.setString(1, "Max Mustermann");
    pstmt.setString(2, "max@example.com");
    int rows = pstmt.executeUpdate();
    System.out.println(rows + " Benutzer hinzugefügt.");
} catch (SQLException e) {
    e.getLocalizedMessage();
}
```
## SELECT
```java
String sql = "SELECT * FROM users WHERE email = ?"; 
try (Connection conn = DatabaseConnection.getConnection(); 
		PreparedStatement pstmt = conn.prepareStatement(sql)) { 
	pstmt.setString(1, "max@example.com"); 
	try (ResultSet rs = pstmt.executeQuery()) { 
		if (rs.next()) { 
			System.out.println("Benutzer: " + rs.getString("name")); 
		} else { 
			System.out.println("Kein Benutzer gefunden."); 
		} 
	} 
} catch (SQLException e) { 
	e.getLocalizedMessage();
}
```
## Update
```java
String sql = "UPDATE users SET email = ? WHERE name = ?"; 

try (Connection conn = DatabaseConnection.getConnection(); 
		PreparedStatement pstmt = conn.prepareStatement(sql)) { 
	pstmt.setString(1, "neueAdresse@example.com"); 
	pstmt.setString(2, "Max Mustermann"); 
	int rows = pstmt.executeUpdate(); 
	System.out.println(rows + " Datensätze aktualisiert."); 
} catch (SQLException e) {
	e.getLocalizedMessage();
}
```
## DELETE
```java
String sql = "DELETE FROM users WHERE email = ?"; 

try (Connection conn = DatabaseConnection.getConnection(); 
		PreparedStatement pstmt = conn.prepareStatement(sql)) { 
	pstmt.setString(1, "neueAdresse@example.com"); 
	int rows = pstmt.executeUpdate(); 
	System.out.println(rows + " Benutzer gelöscht."); 
} catch (SQLException e) { 
	e.getLocalizedMessage();
}
```
# Transaktionen
---
```java
try (Connection conn = DatabaseConnection.getConnection()) {
	conn.setAutoCommit(false); // Autocommit deaktivieren
	try (PreparedStatement insert = conn.prepareStatement(
		"INSERT INTO users (name, email) VALUES (?, ?)");
		PreparedStatement update = conn.prepareStatement(
		"UPDATE users SET email = ? WHERE name = ?")) {
		insert.setString(1, "Anna Beispiel");
		insert.setString(2, "anna@example.com");
		insert.executeUpdate();
		update.setString(1, "anna.neu@example.com");
		update.setString(2, "Anna Beispiel");
		update.executeUpdate();
		conn.commit(); // Alles OK → committen
		System.out.println("Transaktion erfolgreich!");
	} catch (SQLException e) {
		conn.rollback(); // Fehler → alles zurückrollen
		System.err.println("Fehler! Rollback ausgeführt: " + e.getMessage());
	} finally {
		conn.setAutoCommit(true);
	}
} catch (SQLException e) {
	e.getLocalizedMessage();
}
```