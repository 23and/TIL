#datatables
- table plug-in for jQuery
- https://datatables.net/
- maven : add webjars
````
<dependency>
    <groupId>org.webjars</groupId>
    <artifactId>datatables</artifactId>
    <version>1.10.12</version>
</dependency>	
````
- css, javascript link
````
<link rel="stylesheet" href="/webjars/datatables/1.10.12/css/dataTables.bootstrap.min.css">
<script type="text/javascript" src="/webjars/datatables/1.10.12/js/dataTables.bootstrap.min.js"></script>
<script type="text/javascript" src="/webjars/datatables/1.10.12/js/jquery.dataTables.min.js"></script>
````
- jQuery
````
$(document).ready(function() {
    $('#example').DataTable();
});
````
- datatables column with
````
$('#example').dataTable( {
  "columnDefs": [
    { "width": "20%", "targets": 0 }
  ]
} );
````
- DOM positioning
 - https://datatables.net/examples/basic_init/dom.html
````
l - Length changing
f - Filtering input
t - The Table!
i - Information
p - Pagination
r - pRocessing
< and > - div elements
<"#id" and > - div with an id
<"class" and > - div with a class
<"#id.class" and > - div with an id and class
````
````
$(document).ready(function() {
    $('#example').DataTable( {
        "dom": '<"top"i>rt<"bottom"flp><"clear">'
    } );
} );
````