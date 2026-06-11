
Framework auf Basis von [[React]], das Server-Side-Rendering (SSR), Static Site Generation (SSG) und Client-Side Rendering kombiniert.

# Eigenschaften von Next.js
---
Im Folgenden stellen wir dir die Funktionen von Next.js vor und zeigen dir, was du mit Next.js in deinem Projekt erreichen kannst.
## Routing
---
Das Routing ist eine der wichtigsten Funktionen von Next.js. Next.js nutzt das dateibasierte Routing-System, das auf den **Seiten** basiert, um zu strukturieren, wie das Routing deiner Anwendung aussehen wird. Jede Datei und jeder Ordner, der im **Seitenordner** erstellt wird, wird automatisch in eine Route in Next.js umgewandelt.

Das Next.js-Routing-System ist in 3 verschiedene Typen unterteilt, die wir im Folgenden näher erläutern.

### Index-Routing
---
Der **Seitenordner** hat automatisch eine index.js, die zur Route für die Homepage-Route **/** wird. Du kannst auch eine **index.js-Seite** für alle deine Routen in einem beliebigen Ordner definieren. Du kannst zum Beispiel **pages/profiles/index.js** definieren, die automatisch der Seite **/profiles** zugeordnet wird.

Nimm zum Beispiel dieses Beispiel:

```json
- pages
  - index.js
  - profile
    - index.js
    - [user].js
```

Die obige Seitenstruktur ordnet die Ordner und Dateien einer URL-Struktur zu. Zum Beispiel **/** für die **pages****/index.js**, **/profile/** für die **pages****/profile/index.js**, und **/profile/user** für die **pages****/profile/user.js**.

### Verschachtelte Routen
---
Verschachtelte Routen werden innerhalb einer übergeordneten Route erstellt. Um eine verschachtelte Route zu erstellen, musst du eine übergeordnete Route/einen übergeordneten Ordner im Ordner **pages** erstellen und darin entweder Ordner oder Dateien hinzufügen, um eine verschachtelte Route zu erstellen.

Sieh dir dieses Beispiel an:

```json
- pages
  - index.js
  - dashboard
    - index.js
    - user.js
```

Im obigen Skript sind die Dateien **user.js** und **index.js** in der übergeordneten Dashboard-Route verschachtelt, was bedeutet, dass die URLs nur über die **Dashboard-Route** aufgerufen werden können.

### Dynamische Routen
---
Dies wird über dynamische Routen erreicht. Dynamische Routen sind immer unbestimmt. Sie können über API-Aufrufe erstellt werden oder der URL eine ID oder einen Slug zuweisen.

Um eine dynamische Route in Next.js zu erstellen, fügst du eine eckige Klammer **[id].js** um den Dateinamen oder den Verzeichnisnamen ein. Du kannst die Datei oder das Verzeichnis beliebig benennen, aber eine eckige Klammer **[]** muss angehängt werden, damit sie dynamisch wird.

Sieh dir dieses Beispiel an:

```json
- pages
  - dashboard
    - [user].js
        - profile
```

Das obige Skript macht die Datei **[user].js** dynamisch, was bedeutet, dass die Profilseite mit **/dashboard/2/profile** oder **/dashboard/johndoe/profile** aufgerufen werden muss.

In der offiziellen Dokumentation erfährst du mehr und lernst verschiedene Tricks kennen, um ein fortschrittlicheres Routing-System in Next.js zu erstellen.

## Static File Serving
---
In Next.js werden statische Dateien oder Assets wie Icons, selbst gehostete Schriftarten oder Bilder über den **öffentlichen** Ordner bereitgestellt, der die einzige Quelle der Wahrheit für statische Assets ist.

Der **öffentliche** Ordner sollte laut der Next.js-Dokumentation nicht umbenannt werden. Je nachdem, wie Next.js ihn konfiguriert hat, ist es sehr einfach, statische Dateien über den **öffentlichen** Ordner bereitzustellen.

## Pre-Rendering
---
Eine der wichtigsten Funktionen von Next.js ist das Pre-Rendering, mit dem Next.js sehr gut und schnell arbeitet. Next.js rendert jede Seite vor, indem es den HTML-Code jeder Seite im Voraus zusammen mit dem minimalen JavaScript generiert, das durch einen Prozess namens Hydration ausgeführt werden muss.

Es gibt zwei Formen des Pre-Rendering in Next.js:

1. Server-seitiges Rendering (SSR)
2. Statische Generierung (SG)

Der entscheidende Unterschied zwischen SG und SSR ist, wie die Daten geholt werden. Bei SG werden die Daten zum Zeitpunkt der Erstellung abgerufen und bei jeder Anfrage wiederverwendet (was schneller ist, weil sie zwischengespeichert werden können), während bei SSR die Daten bei jeder Anfrage abgerufen werden.

## Absolute Importe
---
Mit Next.js 9.4 wurden absolute Importe eingeführt, was bedeutet, dass du keine Komponenten mit relativ langen Verzeichnissen mehr importieren musst.

So musst du zum Beispiel Komponenten wie die folgende nicht mehr importieren:

```javascript
import InputField from "../../../../../../components/general/forms/inputfield"
```

Aber du verwendest den folgenden Stil, um Komponenten zu importieren:

```javascript
import InputField from "components/general/forms/inputfield";
```

## Seiten verlinken
---
Next.js bietet die Komponente **next/link** für die Navigation zwischen Seiten. Die Navigation zwischen den Seiten in deinen Anwendungen kann mit der [Link-Komponente](https://nextjs.org/docs/api-reference/next/link) erfolgen, die von **next/link** exportiert wird.

Angenommen, wir haben diese Seitenstrukturen in deinem **Seitenordner** und du möchtest die Seiten miteinander verknüpfen, dann kannst du das mit folgendem Skript erreichen:

```javascript
- pages
  - index.js
  - profile.js
  - settings.js
  - users
    - index.js
    - [user].js
```

Du verknüpfst die Seiten mit dem folgenden Skript:

```javascript
import Link from "next/link";

export default function Users({users) {
  return (
    <div>
      <Link href="/">Home</Link>
      <Link href="/profile">Profile</Link>
      <Link href="/settings">
        <a> Settings </a>
      </Link>
      <Link href="/users">
        <a> Settings </a>
      </Link>
      <Link href="/users/bob">
        <a> Settings </a>
      </Link>
    </div>
  )
}
```

## Styling
---
Next.js bietet dir den Luxus, viele verschiedene Stile für dein Projekt zu erstellen und zu verwenden. Next.js wird standardmäßig mit drei verschiedenen Stilen ausgeliefert: globales CSS, CSS-Module und style-jsx.