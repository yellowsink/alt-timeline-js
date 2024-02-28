# Alt-Timeline.JS

Back in Netscape 2.0, when LiveScript was introduced to the world (I checked, the specific feature
here was literally added right in the first ever release with scripts), the vision for how you would build
dynamic content was very very different...

Introducing: The string prototype HTML wrapper methods:

```html
<script>
	document.write(("hi there, welcome to my " + "cool".italics() + " website!").fontcolor("red"));
</script>
```

Yes. This works in Netscape 2.0 (I checked).
It does not work in Netscape 1.22 (I checked).
And it works in Chrome 122 and Firefox 124.

What if we took this even further, to truly stupid levels of extension method madness?
This small script adds these extension methods for (mostly) every kind of element and also adds them for
DOM nodes, not just for strings.

The methods all output strings just like in good ol Sept '95.

## Example

```html
<body>
  <h1>My cool website, hi!</h1>
</body>

<style> button { color: inherit; } </style>

<script src="alt-timeline.js"></script>

<script>
	document.write(
	    "oh god why".a("https://google.com")
	        + "this is stupid"
	        + "why".em()
	        + "help".fontcolor("green")
	        + "what can go wrong!".button("mybutton")
	        + "https://i.yellows.ink/f2de34678.png".img()
	);

	function randomColor() {
		const cols = ["aliceblue","antiquewhite","aqua","aquamarine","azure","beige","bisque","black","blanchedalmond","blue","blueviolet","brown","burlywood","cadetblue","chartreuse","chocolate","coral","cornflowerblue","cornsilk","crimson","cyan","darkblue","darkcyan","darkgoldenrod","darkgray","darkgrey","darkgreen","darkkhaki","darkmagenta","darkolivegreen","darkorange","darkorchid","darkred","darksalmon","darkseagreen","darkslateblue","darkslategray","darkslategrey","darkturquoise","darkviolet","deeppink","deepskyblue","dimgray","dimgrey","dodgerblue","firebrick","floralwhite","forestgreen","fuchsia","gainsboro","ghostwhite","gold","goldenrod","gray","grey","green","greenyellow","honeydew","hotpink","indianred","indigo","ivory","khaki","lavender","lavenderblush","lawngreen","lemonchiffon","lightblue","lightcoral","lightcyan","lightgoldenrodyellow","lightgray","lightgrey","lightgreen","lightpink","lightsalmon","lightseagreen","lightskyblue","lightslategray","lightslategrey","lightsteelblue","lightyellow","lime","limegreen","linen","magenta","maroon","mediumaquamarine","mediumblue","mediumorchid","mediumpurple","mediumseagreen","mediumslateblue","mediumspringgreen","mediumturquoise","mediumvioletred","midnightblue","mintcream","mistyrose","moccasin","navajowhite","navy","oldlace","olive","olivedrab","orange","orangered","orchid","palegoldenrod","palegreen","paleturquoise","palevioletred","papayawhip","peachpuff","peru","pink","plum","powderblue","purple","rebeccapurple","red","rosybrown","royalblue","saddlebrown","salmon","sandybrown","seagreen","seashell","sienna","silver","skyblue","slateblue","slategray","slategrey","snow","springgreen","steelblue","tan","teal","thistle","tomato","turquoise","violet","wheat","white","whitesmoke","yellow","yellowgreen"];
		return cols[~~(Math.random() * cols.length + 0.5)];
	}

	const assignOnClick = () =>
		mybutton.onclick = () => {
				mybutton.outerHTML = mybutton.fontcolor(randomColor());
				assignOnClick();
			};

	assignOnClick();
</script>
```
