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