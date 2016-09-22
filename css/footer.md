#footer

````html
<header>HEADER</header>
<article>
</article>
<footer>FOOTER</footer>
````
````css
html{ height:100%; }
body{ min-height:100%; padding:0; margin:0; position:relative; }
body:after{ content:''; display:block; height:100px; }
header{ 
  background:#C7DD8B; 
  height:50px; 
}
footer{ 
  background:#DB8A8A; 
  position:absolute; 
  bottom:0; 
  width:100%; 
  height:100px; 
}
````