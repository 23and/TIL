#file upload
````html
<form id="upload-file-form">
  <label for="upload-file-input">Upload your file:</label>
  <input id="upload-file-input" type="file" name="uploadfile" accept="*" />
</form>
````
````javascript
// bind the on-change event
$(document).ready(function() {
  $("#upload-file-input").on("change", uploadFile);
});

function uploadFile() {
  $.ajax({
    url: "/uploadFile",
    type: "POST",
    data: new FormData($("#upload-file-form")[0]),
    enctype: 'multipart/form-data',
    processData: false,
    contentType: false,
    cache: false,
    success: function () {
    },
    error: function () {
    }
  });
}
````
````java
@RequestMapping(value = "/uploadFile", method = RequestMethod.POST)
@ResponseBody
public ResponseEntity<?> uploadFile(
    @RequestParam("uploadfile") MultipartFile uploadfile) {
  
  try {
    String filename = uploadfile.getOriginalFilename();
    String directory = "/var/netgloo_blog/uploads";
    String filepath = Paths.get(directory, filename).toString();
    
    BufferedOutputStream stream =
        new BufferedOutputStream(new FileOutputStream(new File(filepath)));
    stream.write(uploadfile.getBytes());
    stream.close();
  }
  catch (Exception e) {
    System.out.println(e.getMessage());
    return new ResponseEntity<>(HttpStatus.BAD_REQUEST);
  }
  
  return new ResponseEntity<>(HttpStatus.OK);
}
````
- https://github.com/netgloo/spring-boot-samples/tree/master/spring-boot-file-upload-with-ajax