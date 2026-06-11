---
tags:
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
>Repräsentieren zukünftige Werte
>Kapseln asynchrone Operationen mit Erfolgs- oder Fehlerzustand.
# Promise states
---
- Erstellt ein Promise mit einer asynchronen Entscheidung.
- Je nach Ergebnis wird es **erfüllt (resolved)** oder **abgelehnt (rejected)**.
- `.then()` reagiert auf Erfolg oder Fehler des Promises.

```javascript
const promise = new Promise((resolve, reject) => {
  const res = true;
  // An asynchronous operation.
  if (res) {
    resolve('Resolved!');
  } else {
    reject(Error('Error'));
  }
});

promise.then(
  (res) => console.log(res),
  (err) => console.error(err)
);
```
# Executor function
---
- Die Executor-Funktion wird **sofort** beim Erstellen des Promises ausgeführt.
- Sie entscheidet, wann `resolve` oder `reject` aufgerufen wird.
- Steuert den Zustand des Promises.

```javascript
const executorFn = (resolve, reject) => {
  resolve('Resolved!');
};

const promise = new Promise(executorFn);
```
# setTimeout()
---
- Verzögert die Ausführung einer Funktion um eine bestimmte Zeit.
- Blockiert den Hauptthread nicht.
- Wird häufig genutzt, um asynchrones Verhalten zu simulieren.

```javascript
const loginAlert = () => {
  console.log('Login');
};

setTimeout(loginAlert, 6000);
```
# .then() method
---
- Verarbeitet das Ergebnis eines erfüllten Promises.
- Wird erst ausgeführt, wenn `resolve` aufgerufen wurde.
- Kann auch einen Fehler-Handler enthalten.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('Result');
  }, 200);
});

promise.then(
  (res) => {
    console.log(res);
  },
  (err) => {
    console.error(err);
  }
);

fetch(url+"?details="+id).then((response)=>{
	return response.json()
}).then((json)=>{
	printDetails(json)
})
```
# Promise.catch()
---
- Fängt Fehler aus einem Promise oder einer vorherigen `.then()`-Kette ab.
- Sorgt für saubere Fehlerbehandlung bei abgelehnten Promises.
- Trennt Erfolgs- und Fehlerlogik klar.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject(Error('Promise Rejected Unconditionally.'));
  }, 1000);
});

promise.then((res) => {
  console.log(value);
});

promise.catch((err) => {
  console.error(err);
});
```
# Promise.all()
---
- Führt mehrere Promises parallel aus.
- Gibt ein Ergebnis **erst zurück, wenn alle erfolgreich sind**.
- Schlägt sofort fehl, wenn ein Promise rejected wird.

```javascript
const promise1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve(3);
  }, 300);
});
const promise2 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve(2);
  }, 200);
});

Promise.all([promise1, promise2]).then((res) => {
  console.log(res[0]);
  console.log(res[1]);
});
```
# Promise.allSettled()
---
- Wartet auf **alle** Promises, unabhängig von Erfolg oder Fehler.
- Liefert für jedes Promise den Endzustand (`fulfilled` oder `rejected`).
- Nützlich, wenn alle Ergebnisse ausgewertet werden müssen.

```javascript
const promise1 = Promise.resolve(3);
const promise2 = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject(2);
  }, 100);
});

Promise.allSettled([promise1, promise2]).then((res) => {
  console.log(res[0].status);
  console.log(res[1].status);
});
```
# Chaining multiple .then()
---
- Mehrere `.then()` werden nacheinander ausgeführt.
- Jeder Schritt kann ein neues Promise zurückgeben.
- Fehler werden automatisch an den nächsten Fehler-Handler weitergereicht.

```javascript
const promise = new Promise((resolve) =>
  setTimeout(() => resolve('dAlan'), 100)
);

promise
  .then((res) => {
    return res === 'Alan'
      ? Promise.resolve('Hey Alan!')
      : Promise.reject('Who are you?');
  })
  .then(
    (res) => {
      console.log(res);
    },
    (err) => {
      console.error(err);
    }
  );
```
# Fake http Request with Promise
---
- Simuliert einen asynchronen Netzwerkrequest.
- `resolve` steht für eine erfolgreiche Antwort, `reject` für einen Fehler.
- `async/await` sorgt für lesbaren, synchron wirkenden Code mit Fehlerbehandlung über `try/catch`.

```javascript
const mock = (success, timeout = 1000) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      if (success) {
        resolve({ status: 200, data: {} });
      } else {
        reject({ message: 'Error' });
      }
    }, timeout);
  });
};
const someEvent = async () => {
  try {
    await mock(true, 1000);
  } catch (e) {
    console.log(e.message);
  }
};
```
