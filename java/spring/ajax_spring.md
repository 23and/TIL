#ajax spring
````
<dependency>
    <groupId>org.codehaus.jackson</groupId>
    <artifactId>jackson-mapper-asl</artifactId>
</dependency>
````
````jquery
$.ajax({
    url:'<%=request.getContextPath()%>/user/check',
    type:"POST",
    dataType : "json",
    data: {
    	"username" : $('#username').val()
    },
    success:function(data){
    	var result = data.result;
        if(result == 0){
        	$('#check').html('ok');
        }else if(result == 1){
        	$('#check').html('no');
        }
    },
    error:function(jqXHR, textStatus, errorThrown){
    	$('#checkUsername').html("error");
        self.close();
    }
});
````
````
@ResponseBody
@RequestMapping(value = "user/check", method = RequestMethod.POST)
public HashMap<String, Integer> checkUsername(@RequestParam HashMap<String, String> param) {
    HashMap<String, Integer> result = new HashMap<String, Integer>();
    result.put("result", 0);
    return result;
}
````