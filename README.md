# Misc. small projects

by András Jankovics

All of these are Unlicensed (see below).

### Ammann–Beenker tiling

ammann-beenker_tiling_svg.html will render two SVGs with the usual and the alternate tileset. 

![Ammann–Beenker tiling](https://github.com/jankovicsandras/misc/blob/master/ammann-beenker_tiling.png)

[Wikipedia article on Ammann–Beenker tiling](https://en.wikipedia.org/wiki/Ammann%E2%80%93Beenker_tiling)

### Browser crashing HTML redirect

**!!! Warning: use with caution, read the code first! I take no responsibility for the damages caused by these files. As of 2016-02-12, these can make major browsers become unresponsive and possibly cause OS instability or crash. !!!**

When these files are served from a server (not just opened as local files), they will recursively load each other with [Meta refresh](https://en.wikipedia.org/wiki/Meta_refresh) . As of 2016-02-12, this leads to resource exhaustion (mostly RAM) and the browser becomes unresponsive after 15+ seconds. 

![Screenshot](https://github.com/jankovicsandras/misc/blob/master/browser_crashing_html_redirect.png)

#### 1.html

```html
<!DOCTYPE html>
<html>
	<head>
		<title>1</title>
		<meta http-equiv="refresh" content="3;URL='3.html'">
	</head>
	<body style="background-color:rgb(0,0,255);"></body>
</html>
```

#### 2.html

```html
<!DOCTYPE html>
<html>
	<head>
		<title>2</title>
		<meta http-equiv="refresh" content="3;URL='3.html'">
	</head>
	<body style="background-color:rgb(0,255,0);"></body>
</html>
```

#### 3.html

```html
<!DOCTYPE html>
<html>
	<head>
		<title>3</title>
	</head>
	<body>
		<iframe src="1.html" frameborder="0" border="0" cellspacing="0" style="position:absolute;border-style: none;top:0%;left:0%;width: 100%; height: 50%;margin:0;padding:0;border:none;clear:none;display:block;" ></iframe> 
		<iframe src="2.html" frameborder="0" border="0" cellspacing="0" style="position:absolute;border-style: none;top:50%;left:0%;width: 100%; height: 50%;margin:0;padding:0;border:none;clear:none;display:block;" ></iframe> 
	</body>
</html>
```

### Concentric Moiré patterns

Animated SVG eyecandy.

![Screenshot](https://github.com/jankovicsandras/misc/blob/master/concentric_moire_patterns.png)

[Wikipedia article on Moiré patterns](https://en.wikipedia.org/wiki/Moire_patterns)

### Image to slashes

Simple "ASCII art" generator.

![Screenshot](https://github.com/jankovicsandras/misc/blob/master/image_to_slashes.png)

### Sierpinski carpet L-system

The following 677 bytes will render a [Sierpinski carpet](https://en.wikipedia.org/wiki/Sierpinski_carpet) using an [L-system](https://en.wikipedia.org/wiki/L-system) to create a [Z-order curve](https://en.wikipedia.org/wiki/Z-order_curve) :

```html
<html><style>body{font-family:monospace;}</style><body onload='document.body.innerHTML=g(f({".":"....O....","O":"OOOOOOOOO"},".",5))'><script>function f(r,s,i){for(j=i;j--;){var a=s.split('');for(k=a.length;k--;){a[k]=r[a[k]]}s=a.join('')}return s}function p(i){var n=1;while(i%Math.pow(3,n)==0){n++}return n-1}function g(s){var b='',m,n=0,d=Math.sqrt(s.length);var a=[];for(m=0;m<d;m++){a[m]=[]}m=0;a[0][0]=s.charAt(0);for(i=1;i<s.length;i++){var x,y,z=p(i);if(z>0){if(z%2==1){x=Math.pow(3,(z+1)/2);y=0}else{x=0;y=Math.pow(3,z/2)}x=-x+1;y=-y+1}else{x=1;y=0}m+=x;n+=y;a[m][n]=s.charAt(i)}for(m=0;m<d;m++){for(n=0;n<d;n++){b+=a[m][n];}b+='<br/>'}return b}</script></body></html>
```

![Screenshot](https://github.com/jankovicsandras/misc/blob/master/sierpinski_carpet_l-system.png)

There's a somewhat commented version as well.

### X3D Menger Sponge and 3D Vicsek fractal

![Menger Sponge and 3D Vicsek fractal](https://github.com/jankovicsandras/misc/blob/master/x3d_menger_vicsek.png)

[Wikipedia article on X3D](https://en.wikipedia.org/wiki/X3d)
[Wikipedia article on Menger Sponge](https://en.wikipedia.org/wiki/Menger_sponge)
[Wikipedia article on Vicsek fractal](https://en.wikipedia.org/wiki/Vicsek_fractal)

### License
#### The Unlicense / PUBLIC DOMAIN

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to [http://unlicense.org](http://unlicense.org)
