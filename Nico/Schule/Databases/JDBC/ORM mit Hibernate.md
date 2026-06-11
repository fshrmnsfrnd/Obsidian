---
Fach: "[[DB]]"
Thema:
  - "[[Databases]]"
  - "[[Java]]"
---
# Vorgegeben
---
- Als DBMS wird MySQL verwendet 
- Entitäten sind: Ort, Mitglied und Sportart 
- Beziehungen sind: Ort -> Mitglied (1: N), Mitglied <-> Sportart (N:M) 
- Es werden CRUD-Operationen für alle Entities eingerichtet 
- Es werden Abfragen mit Filterkriterien gezeigt. 
- Verwendete Bibliotheken: Hibernate 6.1.0, Jakarta 3.1.0, MySQL Connector 8.2.0

# `pom.xml`
---
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd">
	...
	<dependencies>
		<!-- Hibernate -->
		<dependency>
			<groupId>org.hibernate.orm</groupId>
			<artifactId>hibernate-core</artifactId>
			<version>6.1.0.Final</version>
		</dependency>
		<!-- Jakarta Persistence API -->
		<dependency>
			<groupId>jakarta.persistence</groupId>
			<artifactId>jakarta.persistence-api</artifactId>
			<version>3.1.0</version>
		</dependency>
		<!-- MySQL Connector -->
		<dependency>
			<groupId>com.mysql</groupId>
			<artifactId>mysql-connector-j</artifactId>
			<version>8.2.0</version>
		</dependency>
	</dependencies>
	...
</project>
```
### Erklärung:
- **Hibernate** ist der Kern deiner Datenbank-ORM (Object Relational Mapping) Bibliothek. 
- Die **Jakarta Persistence API** definiert die JPA-Annotationen wie @Entity, @OneToMany, @ManyToOne. Hibernate implementiert diese API. 
- Der **JDBC**-Treiber für MySQL ermöglicht, dass Java sich mit deiner MySQL-8-Datenbank verbinden kann.

# `/src/main/resources/hibernate.cfg.xml`
---
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hibernate-configuration PUBLIC
	"-//Hibernate/Hibernate Configuration DTD 6.0//EN"
	"https://hibernate.org/dtd/hibernate-configuration-6.0.dtd">
<hibernate-configuration>
	<session-factory>
		<!-- JDBC Verbindung -->
		<property name="hibernate.connection.driver_class">
			com.mysql.cj.jdbc.Driver
		</property>
		<property name="hibernate.connection.url">
			jdbc:mysql://localhost:3306/dbverein_orm?useSSL=false&amp;
			serverTimezone=UTC
		</property>
		<property name="hibernate.connection.username">
			root
		</property>
		<property name="hibernate.connection.password">
			password
		</property>
		<!-- Dialekt -->
		<property name="hibernate.dialect">
			org.hibernate.dialect.MySQLDialect
		</property>
		<!-- Schema automatisch erzeugen -->
		<property name="hibernate.hbm2ddl.auto">
			update
		</property>
		<!-- SQL Debugging -->
		<property name="hibernate.show_sql">
			true
		</property>
		<property name="hibernate.format_sql">
			true
		</property>
		
		<!-- Annotierte Entities -->
		<mapping class="hibernate.blogic.Ort"/>
		<mapping class="hibernate.blogic.Mitglied"/>
		<mapping class="hibernate.blogic.Sportart"/>
	</session-factory>
</hibernate-configuration>
```
### Erklärungen
- Die Konfiguration enthält die Datenbank-URL. Der Name der Datenbank ist dbverein_orm. Sie muss vorhanden sein. 
- Hibernate erzeugt oder aktualisiert die Tabellen automatisch, wenn sich die Entity-Klassen ändern. Das ist ideal für Entwickler – für die Produktion muss das geändert werden. 
- Die Klassen-Mappings legen fest, dass Hibernate diese Klassen als Entities behandeln soll und in Tabellen umwandet.

# `logback.xml`
---
```xml
<configuration>
	<logger name = "org.hibernate" level = "WARN"/>
	<logger name = "org.hibernate.SQL" level = "WARN"/>
	<logger name = "org.hibernate.type.drscriptor.sql.BasicBinder" level =
	"WARN"/>
	<root level = "ERROR">
		<apender-ref ref = "CONSOLE"/>
	</root>
</configuration>
```

# Entity Klassen
---
## `Ort.java`

```java
package hibernate.blogic;
  
import jakarta.persistence.*;
import java.util.ArrayList;
import java.util.List;
  
@Entity
public class Ort {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    @OneToMany(mappedBy = "ort", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<Mitglied> mitglieder = new ArrayList<>();
  
    // Getter / Setter
    public Long getId() {
        return id;
    }
  
    public void setId(Long id) {
        this.id = id;
    }
  
    public String getName() {
        return name;
    }
  
    public void setName(String name) {
        this.name = name;
    }
  
    public List<Mitglied> getMitglieder() {
        return mitglieder;
    }
}
```

## `Mitglied.java`

```java
package hibernate.blogic;
  
import jakarta.persistence.*;
import java.util.HashSet;
import java.util.Set;
  
@Entity
public class Mitglied {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    @ManyToOne
    @JoinColumn(name = "ort_id")
    private Ort ort;
    @ManyToMany(cascade = { CascadeType.PERSIST, CascadeType.MERGE })
    @JoinTable(name = "mitglied_sportart", joinColumns = @JoinColumn(name = "mitglied_id"), inverseJoinColumns = @JoinColumn(name = "sportart_id"))
    private Set<Sportart> sportarten = new HashSet<>();
  
    // Getter / Setter
    public Long getId() {
        return id;
    }
  
    public void setId(Long id) {
        this.id = id;
    }
  
    public String getName() {
        return name;
    }
  
    public void setName(String name) {
        this.name = name;
    }
  
    public Ort getOrt() {
        return ort;
    }
  
    public void setOrt(Ort ort) {
        this.ort = ort;
    }
 
    public Set<Sportart> getSportarten() {
        return sportarten;
    }
}
```

## `Sportart.java`

```java
package hibernate.blogic;
  
import jakarta.persistence.*;
import java.util.HashSet;
import java.util.Set;
  
@Entity
public class Sportart {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    @ManyToMany(mappedBy = "sportarten")
    private Set<Mitglied> mitglieder = new HashSet<>();
  
    // Getter / Setter
    public Long getId() {
        return id;
    }
  
    public void setId(Long id) {
        this.id = id;
    }
  
    public String getName() {
        return name;
    }
  
    public void setName(String name) {
        this.name = name;
    }
  
    public Set<Mitglied> getMitglieder() {
        return mitglieder;
    }
}
```

# Main
---
```java
package hibernate.blogic;
  
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import org.hibernate.Session;
import org.hibernate.SessionFactory;
import org.hibernate.cfg.Configuration;
  
public class App {
    public static void main(String[] args) {
        try {
            // ===================== Datenbank zurücksetzen =======
            Connection cnn = DriverManager
                    .getConnection("jdbc:mysql://localhost:3306/dbverein_orm",
                            "root", "kennwort1");
            cnn.createStatement()
                    .execute("DROP DATABASE IF EXISTS dbverein_orm");
            cnn.createStatement().execute("CREATE DATABASE dbverein_orm");
            cnn.close();
        } catch (SQLException e) {
            System.err.println(e);
        }
  
        // ===================== Hibernate =======================
        SessionFactory factory = new Configuration().configure().buildSessionFactory();
        Session session = factory.openSession();
        try {
  
            // ===================== INSERT =====================
            session.beginTransaction();
            Ort berlin = new Ort();
            berlin.setName("Berlin");
            Ort hamburg = new Ort();
            hamburg.setName("Hamburg");
            Sportart fussball = new Sportart();
            fussball.setName("Fußball");
            Sportart schwimmen = new Sportart();
            schwimmen.setName("Schwimmen");
            Mitglied anna = new Mitglied();
            anna.setName("Anna");
            anna.setOrt(berlin);
            anna.getSportarten().add(fussball);
            anna.getSportarten().add(schwimmen);
            Mitglied ben = new Mitglied();
            ben.setName("Ben");
            ben.setOrt(hamburg);
            ben.getSportarten().add(fussball);
            berlin.getMitglieder().add(anna);
            hamburg.getMitglieder().add(ben);
            session.persist(berlin);
            session.persist(hamburg);
            session.getTransaction().commit();
  
            // ===================== SELECT =====================
            session.beginTransaction();
            System.out.println("=== Alle Mitglieder ===");
            List<Mitglied> alle = session.createQuery(
                    "from Mitglied", Mitglied.class).list();
            for (Mitglied m : alle) {
                System.out.println("Mitglied: " + m.getName());
                System.out.println("Wohnort: " + m.getOrt().getName());
                System.out.println("Sportarten: ");
  
                for (Sportart s : m.getSportarten()) {
                    System.out.print("\n" + s.getName());
                }
            }
            session.getTransaction().commit();
            // ===================== FILTER =====================
            session.beginTransaction();
            System.out.println("=== Mitglieder aus Berlin ===");
           List<Mitglied> filtered = session
                    .createQuery("from Mitglied m where m.ort.name=:ortName",
                            Mitglied.class)
                    .setParameter("ortName", "Berlin").list();
            filtered.forEach(m -> System.out.println(m.getName()));
            session.getTransaction().commit();
            // ===================== UPDATE =====================
            session.beginTransaction();
            anna = session.get(Mitglied.class, anna.getId());
            anna.setName("Anna Müller");
            session.getTransaction().commit();
            // ===================== DELETE =====================
            session.beginTransaction();
            for (Sportart s : ben.getSportarten()) {
                s.getMitglieder().remove((ben));
            }
            ben.getSportarten().clear();
            ben.getOrt().getMitglieder().remove(ben);
            ben.setOrt(null);
            session.remove(ben); // Mitglied Ben löschen
            session.getTransaction().commit();
        } catch (Exception e) {
            System.err.println(e);
        } finally {
            session.close();
            factory.close();
        }
    }
}
```