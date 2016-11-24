#radio button event
````
<input type="radio" name="level" value="yes"> Yes 
<input type="radio" name="level" value="no" checked> No
````
````
$('input[name="level"]').change(function(){
 	if($(':radio[name="level"]:checked').val() == "yes"){
    	$('#selectYear').show();
    }else if($(':radio[name="level"]:checked').val() == "no"){
    	$('#selectYear').hide();
    }
});
````
- checked
````
$('input[name="level"][value=“yes”]’).attr('checked', true);
````