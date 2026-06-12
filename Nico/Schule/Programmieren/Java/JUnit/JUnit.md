---
Thema:
  - "[[Java]]"
  - "[[Tests]]"
Fach: "[[Programmieren]]"
---
>Für JUnit Test braucht man ein Maven Projekt
# Dependencies
---
`pom.xml`
```xml
...
<project>
...
    <dependencies>
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-api</artifactId>
            <version>5.6.0</version>
            <scope>test</scope>
        </dependency>
            <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-params</artifactId>
            <version>5.6.0</version>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>5.6.0</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project
```
# Tests erstellen
---
## NetBeans
Tools -> Create/Update Tests
# Test
---
```java
import org.junit.jupiter.api.AfterAll;
import org.junit.jupiter.api.BeforeAll;
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class RechnerTest {
	Rechner rechner = new Rechner();

    public RechnerTest() {}
    @BeforeAll
    public static void setUpClass() {}

    @AfterAll
    public static void tearDownClass() {}

    @Test
    public void testPlus() {
        assertEquals(2.0, rechner.plus(1.0, 1.0), 0);
    }

    /**
     * Test of minus method, of class Rechner.
     */
    @Test
    public void testMinus() {
		assertEquals(0.0, rechner.minus(1.0, 1.0), 0);
    }
}
```
# Test laufen lassen
---
## Netbeans
Run -> Test Project (Alt+F6)