---
Fach:
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
>Mit **A**synchronous **J**avaScript **A**nd **X**ML kann man HTTP Requests machen. Meistens aber JSON statt XML


> [!WARNING] Deprecated
> [[Requests]] sind der aktuellere heiße Scheiß

# Request erstellen
---
```javascript
const request = new XMLHttpRequest()
```
# Fetch Data
---
```javascript
request.open("get", <url>)
request.setRequestHeader("Content-Type", "application/x-www-form-urlencoded")
request.send([<DocumentBody>|<null>])
```
# Return verarbeiten
---
```javascript
request.onload = function (){
	let response = this.responseText
	let data = JSON.parse(this.responseText)
	//Code
}
```
# Request Status
---

| Value | State            | Description                                                                    |
| ----- | ---------------- | ------------------------------------------------------------------------------ |
| 0     | UNSENT           | Client has been created. open() not called yet.                                |
| 1     | OPENED           | open() has been called. Server connection established                          |
| 2     | HEADERS_RECEIVED | send() has been called, and headers and status are available, request received |
| 3     | LOADING          | Downloading; responseText holds partial data. Processing Request               |
| 4     | DONE             | Request finished and response is ready                                         |
[[HTTP Status Codes]]

```javascript
request.onreadystatechange = function() {
	let status = this.status //HTTP Status like 200, 400, 500
	let readState = this.readyState //AJAX Request Status
	let response = this.responseText //Data delivered
};
```
# POST
---
```javascript
const data = {
  fish: 'Salmon',
  weight: '1.5 KG',
  units: 5
};
const xhr = new XMLHttpRequest();
xhr.open('POST', '/inventory/add');
xhr.responseType = 'json';
xhr.send(JSON.stringify(data));

xhr.onload = () => {
  console.log(xhr.response);
};
```
# Mit Fetch
---
```js
fetch(url+"?details="+id).then((response)=>{
	return response.json()
}).then((json)=>{
	printDetails(json)
})
```
