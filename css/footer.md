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
````html
<div class="wrap">
  <header>Header</header>
  <main class="main">
    <div class="sidebar">Sidebar  </div>
    <div class="content">content </div>
  </main>
  <footer>footer</footer>
</div>
````
````css
html, body {
	margin:0;
	padding:0
}
.wrap {
	display: flex;
	min-height: 100vh;
	flex-direction: column;
	max-width:1200px;
  margin:auto;
}
.main {
	flex: 1;
	display:flex;
}
footer, header {
	background:green;
	padding:10px;
}
.sidebar {
	background:blue;
	flex:0 0 300px;
	padding:10px;
}
.content{
	background:yellow;
	padding:10px;
	flex:1;	
}
@media screen and (max-width:680px){
	.sidebar{flex: 0;order:2}
	.main {flex-direction:column;}	
}
````
