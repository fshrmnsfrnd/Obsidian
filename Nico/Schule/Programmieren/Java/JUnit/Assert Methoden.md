---
Thema:
  - "[[Java]]"
  - "[[JUnit]]"
Fach: "[[Programmieren]]"
---
# True
---
```java
static void assertTrue(boolean condition)
static void assertTrue(boolean condition, String message)
static void assertFalse(boolean condition)
static void assertFalse(boolean condition, String message)
```
# Null
---
```java
static void assertNull(Object actual)
static void assertNull(Object actual, String message)
static void assertNotNull(Object actual)
static void assertNotNull(Object actual, String message)
```
# Same
---
>Prüft auf Referenz
```java
static void assertSame(Object expected, Object actual)
static void assertSame(Object expected, Object actual, String message)
static void assertNotSame(Object unexpected, Object actual)
static void assertNotSame(Object unexpected, Object actual, String message)
```
# Equals
---
>Prüft mit `.equals()`
```java
static void assertEquals(Object expected, Object actual)
static void assertEquals(Object expected, Object actual, String message)
static void assertNotEquals(Object unexpected, Object actual)
static void assertNotEquals(Object unexpected, Object actual, String message)
```
# Arrays
---
```java
static void assertArrayEquals(Object[] expected, Object[] actual)
static void assertArrayEquals(Object[] expected, Object[] actual, String message)
static void assertArrayNotEquals(Object[] unexpected, Object[] actual)
static void assertArrayNotEquals(Object[] unexpected, Object[] actual, String message)
```
# Fail
---
>Lässt den Test fehlschlagen. Nützlich, wenn man z.B. in einem `try`-Block erwartet, dass eine Exception geworfen wird, und falls nicht, den Test mit `fail()` fehlschlagen lassen möchte.
```java
static void fail()
static void fail(String message)
```
