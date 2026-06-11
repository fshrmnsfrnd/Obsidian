---
tags:
Fach:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
# Umbruch nach jedem nth Child bei Floating Boxes
---
```css
.innerBox:nth-child(4n+1){
	clear: left;
}
```
# Menü mit Submenü bei Hover
---
```html
<div id="topnav">
	<ul id="topnavList">
		<li>
			Link1
			<ul class="subNavList" id="subNavList1">
				<li>Sublink1</li>
				<li>Sublink2</li>
				<li>Sublink3</li>
			</ul>
		</li>
		<li>
			Link2
			<ul class="subNavList" id="subNavList2">
				<li>Sublink4</li>
				<li>Sublink5</li>
				<li>Sublink6</li>
			</ul>
		</li>
		<li>
			Link3
			<ul class="subNavList" id="subNavList3">
				<li>Sublink7</li>
				<li>Sublink8</li>
				<li>Sublink9</li>
			</ul>
		</li>
	</ul>
</div>
```

```css
#topnav>ul>li{
	list-style: none;
	display: inline;
	position: relative;
}

.subNavList{
	opacity: 0;
	position: absolute;
	list-style: none;
	left: 0;
}

#topnav>ul>li:hover .subNavList{
	opacity: 1;
}
```