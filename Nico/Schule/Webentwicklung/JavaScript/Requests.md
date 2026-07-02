---
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
>Kommunikation mit externen Ressourcen (z. B. APIs)
>Abrufen oder Senden von Daten über HTTP(S).

# [[AJAX]]
---
Siehe AJAX
# fetch api
---
- Moderne Schnittstelle für HTTP-Anfragen.
- Arbeitet Promise-basiert.
- Unterstützt Header, Methoden, Body und Fehlerbehandlung.

```javascript
fetch(url, {
	method: 'POST',
	headers: {
	'Content-type': 'application/json',
	'apikey': apiKey
	}, 
	body: data
}).then(response => {
	if (response.ok) {
		return response.json();
	}
	throw new Error('Request failed!');
}, networkError => {
	console.log(networkError.message)
})
```
# JSON Formatted
---
- Wandelt eine Fetch-Antwort in ein JavaScript-Objekt um.
- `response.json()` liest und parsed JSON-Daten.
- Ermöglicht direkten Zugriff auf die Antwortdaten.

```javascript
fetch('url-that-returns-JSON').then((response) => response.json()).then((jsonResponse) => {
	console.log(jsonResponse);
});
```
# promise url parameter fetch api
---
- Verarbeitet die Fetch-Antwort direkt im Promise.
- Trennung von erfolgreicher Antwort und Fehlerfall.
- Zeigt den rohen Response-Status oder Netzwerkfehler.

```javascript
fetch('url').then(
	(response) => {
	    console.log(response);
	},
	rejection => {
    console.error(rejection.message);
);
```
# Fetch API Function
---
- Kombiniert Request-Logik und Fehlerprüfung.
- Prüft, ob die HTTP-Antwort erfolgreich ist.
- Verarbeitet anschließend die JSON-Antwort.

```javascript
fetch('https://api-xxx.com/endpoint', {
  method: 'POST',
  body: JSON.stringify({ id: '200' })
}).then((response) => {
	if (response.ok) {
	    return response.json();
	}
	throw new Error('Request failed!');
},(networkError) => {
	console.log(networkError.message);
}).then((jsonResponse) => {
    console.log(jsonResponse);
});
```
# async await syntax
---
- Macht asynchronen Code lesbarer und linear.
- Fehler werden über `try / catch` behandelt.

```javascript
const getSuggestions = async () => {
	const wordQuery = inputField.value;
	const endpoint = `${url}${queryParams}${wordQuery}`;
	try {
		const response = await fetch(endpoint, { cache: 'no-cache' });
		if (response.ok) {
			const jsonResponse = await response.json();
		}
	} catch (error) {
		console.log(error);
	}
};
```