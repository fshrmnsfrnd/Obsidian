# React — Kurzreferenz
- React: JS‑Bibliothek für deklarative UIs, oft für SPAs; kombiniert mit Router + State‑Management (Context/Redux/Zustand).

# Grundprinzip
- Komponentenbasiert: UI = kleine, wiederverwendbare Komponenten  
- Kapselung: eigene Props, State, Nebenwirkungen  
- Zusammensetzbar: Komponenten verschachteln für komplexe UIs  
- Vorteil: bessere Testbarkeit & Wiederverwendung

# JSX
- HTML‑ähnliche Syntax in JS; wird transpiled (z.B. Babel)  
- JS‑Ausdrücke in `{}`; Attribute: `className`, `htmlFor`  
- Kurzbeispiel:
```js
const btn = <button className="primary">{label || "OK"}</button>;
```

# State & Props
- Props: unveränderliche Eingaben vom Elternteil (wie Funktionsargumente)  
- State: lokaler, veränderbarer Zustand (z.B. `useState`)  
- Kommunikation: Props down, Events/Callbacks up  
- Kurzbeispiel:
```js
function Counter({ start }) {
  const [count, setCount] = useState(start);
  return <button onClick={() => setCount(c => c + 1)}>{count}</button>;
}
```

# Lifecycle / Hooks
- Hooks ersetzen klassische Lifecycle‑Methoden in Funktionskomponenten  
- Wichtige Hooks: `useState`, `useEffect`, `useContext`, `useReducer`, `useRef`, `useMemo`, `useCallback`  
- useEffect (Abhängigkeiten + Cleanup) — Beispiel:
```js
useEffect(() => {
  const id = setInterval(tick, 1000);
  return () => clearInterval(id); // Cleanup
}, [deps]); // [] = einmal, keine Angabe = bei jedem Render
```

# Virtuelles DOM & Performance
- Virtual DOM: Diffing → minimale DOM‑Änderungen  
- Performance‑Tipps:
- Verwende `key` bei Listen (`key` = stabiler Identifier)  
- Memoize: `React.memo`, `useMemo`, `useCallback` bei teuren Berechnungen / Props  
- Vermeide unnötige Re‑Renders (stabiles Props/Callbacks)

# Schnellreferenz Hooks (1‑Zeiler)
- useState: lokaler State  
- useEffect: Nebenwirkungen & Cleanup  
- useContext: Zugriff auf Context  
- useReducer: komplexe State‑Logik (Redux‑ähnlich)  
- useRef: DOM/Mutable Ref ohne Re‑Render  
- useMemo: Werte memoizen (teure Berechnung)  
- useCallback: Funktionen memoizen (stabile Referenz)
Hier kurze Code‑Beispiele für alle Hooks / Commands. Erklärungen nur in Kommentaren.

- useState
```js
import { useState } from 'react';

function Counter({ start = 0 }) {
  const [count, setCount] = useState(start);
  // count = aktueller Wert
  // setCount(newVal) = State aktualisieren
  return <button onClick={() => setCount(c => c + 1)}>{count}</button>;
}
```

- useEffect
```js
import { useEffect, useState } from 'react';

function Timer() {
  const [sec, setSec] = useState(0);

  useEffect(() => {
    // Effekt: startet Interval beim Mount
    const id = setInterval(() => setSec(s => s + 1), 1000);
    return () => clearInterval(id); // Cleanup beim Unmount
  }, []); // [] = nur einmal nach Mount

  return <div>{sec}s</div>;
}
```

- useContext
```js
import { createContext, useContext } from 'react';

const ThemeContext = createContext('light');

function Toolbar() {
  // konsumiert Context: erhält aktuellen Theme‑Wert
  const theme = useContext(ThemeContext);
  return <div className={theme}>Toolbar</div>;
}

// Verwendung:
// <ThemeContext.Provider value="dark"><Toolbar/></ThemeContext.Provider>
```

- useReducer
```js
import { useReducer } from 'react';

function reducer(state, action) {
  switch (action.type) {
    case 'inc': return { count: state.count + 1 };
    case 'dec': return { count: state.count - 1 };
    default: return state;
  }
}

function CounterReducer() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });
  // dispatch({type: 'inc'}) statt setState für komplexe Logik
  return (
    <>
      <button onClick={() => dispatch({type: 'dec'})}>-</button>
      <span>{state.count}</span>
      <button onClick={() => dispatch({type: 'inc'})}>+</button>
    </>
  );
}
```

- useRef
```js
import { useRef, useEffect } from 'react';

function FocusInput() {
  const inputRef = useRef(null);
  // inputRef.current verweist auf DOM‑Element, ändert sich ohne Re‑Render
  useEffect(() => {
    inputRef.current?.focus(); // Fokus setzen beim Mount
  }, []);

  return <input ref={inputRef} />;
}
```

- useMemo
```js
import { useMemo, useState } from 'react';

function Expensive({ n }) {
  const [toggle, setToggle] = useState(false);

  const fib = useMemo(() => {
    // teure Berechnung wird nur neu berechnet, wenn n sich ändert
    function f(x){ return x < 2 ? x : f(x-1)+f(x-2); }
    return f(n);
  }, [n]);

  return (
    <>
      <div>{fib}</div>
      <button onClick={() => setToggle(t => !t)}>{String(toggle)}</button>
    </>
  );
}
```

- useCallback
```js
import { useState, useCallback } from 'react';

function Parent() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    // stabile Funktion‑Referenz, nützlich für optimierte Kinderkomponenten
    setCount(c => c + 1);
  }, []); // Abhängigkeiten: neu erstellen wenn leer => nie

  return <Child onClick={increment} />;
}

function Child({ onClick }) {
  // Child kann mit React.memo gerendert werden, wenn onClick stabil ist
  return <button onClick={onClick}>Inc</button>;
}
```

- React.memo (Komponentenmemo)
```js
import React from 'react';

const Child = React.memo(function Child({ value }) {
  // rendert nur neu, wenn props.value sich ändert (shallow)
  return <div>{value}</div>;
});
```
