---
Fach: "[[DB]]"
Thema:
  - "[[Databases]]"
  - "[[Java]]"
---
>Ein **Data Access Object**  ist eine objektorientierte Schnittstelle zwischen Programm und Datenbank.

Darin in festgelegt:
- Wie Daten gelesen, und geändert werden (Methoden z.B. `createUser(User user)`)
- Wie die Daten aus der Datenbank in einem Objekt dargestellt werden

# Beispiel
---
![[Pasted image 20260102141100.png]]

```java
public class User { 
	private int id; 
	private String name; 
	
	public User() {} 
	
	public User(int id, String name) { 
		this.id = id; 
		this.name = name; 
	} 
	
	public User(String name) { 
		this.name = name; 
	} 
	
	public int getId() {return id;} 
	public void setId(int id) {this.id = id;} 
	
	public String getName() {return name;} 
	public void setName(String name) {this.name = name;} 
	
	@Override 
	public String toString() { 
		return String.format("User{id=%d, name='%s'}", id, name); 
	} 
}
```

```java
import db.DatabaseConnection; 
import model.User; 
import java.sql.*; 
import java.util.ArrayList; 
import java.util.List; 

public class UserDAO { 
	// CREATE 
	public void createUser(User user) { 
		String sql = "INSERT INTO users (name) VALUES (?)"; 
		try (Connection conn = DatabaseConnection.getConnection(); 
				PreparedStatement pstmt = conn.prepareStatement(sql)) {
			pstmt.setString(1, user.getName());  
			pstmt.executeUpdate(); 
			System.out.println("Benutzer hinzugefügt: " + user.getName()); 
		} catch (SQLException e) { 
			e.printStackTrace(); 
		} 
	} 
	// READ (by ID) 
	public User getUserById(int id) { 
		String sql = "SELECT * FROM users WHERE id = ?"; 
		try (Connection conn = DatabaseConnection.getConnection(); 
				PreparedStatement pstmt = conn.prepareStatement(sql)) { 
			pstmt.setInt(1, id); 
			try (ResultSet rs = pstmt.executeQuery()) { 
				if (rs.next()) { 
					return new User(rs.getInt("id"), rs.getString("name")); 
				} 
			} 
		} catch (SQLException e) { 
			e.printStackTrace(); 
		} 
		return null; 
	} 
	// READ (all) 
	public List getAllUsers() { 
		List users = new ArrayList<>(); 
		String sql = "SELECT * FROM users"; 
		try (Connection conn = DatabaseConnection.getConnection(); 
				Statement stmt = conn.createStatement(); 
				ResultSet rs = stmt.executeQuery(sql)) { 
			while (rs.next()){
				users.add(new User(rs.getInt("id"), rs.getString("name")); 
			} 
		} catch (SQLException e) { 
			e.printStackTrace(); 
		} 
		return users; 
	} 
	// DELETE 
	public void deleteUser(int id) { 
		String sql = "DELETE FROM users WHERE id = ?"; 
		try (Connection conn = DatabaseConnection.getConnection(); 
				PreparedStatement pstmt = conn.prepareStatement(sql)) { 
			pstmt.setInt(1, id); 
			int rows = pstmt.executeUpdate(); 
			System.out.println(" " + rows + " Benutzer gelöscht.");
		} catch (SQLException e) { 
			e.printStackTrace(); 
		} 
	} 
	// TRANSACTION Beispiel 
	public void transactionExample() { 
		try (Connection conn = DatabaseConnection.getConnection()) {
			conn.setAutoCommit(false); 
			try (
					PreparedStatement stmt1 = conn.prepareStatement("INSERT INTO users (name) VALUES (?)");) { 
				stmt1.setString(1, "TestUser"); 
				stmt1.setString(2, "test@demo.com"); 
				stmt1.executeUpdate(); 
				conn.commit(); 
				System.out.println("Transaktion erfolgreich!"); 
			} catch (SQLException e) { 
				conn.rollback(); 
				System.err.println("Transaktion zurückgerollt: " + e.getMessage()); 
			} finally { 
				conn.setAutoCommit(true); 
			} 
		} catch (SQLException e) { 
			e.printStackTrace(); 
		} 
	} 
}
```