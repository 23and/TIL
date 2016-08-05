#smart editor

- 글쓰기 기능을 구현할 때, 글 양식을 꾸미고 싶었다. 직접 모든 기능을 구현하기에는 시간이 부족하기 때문에 smart editor open source를 사용하게 되었다.
- smart editor은 글꼴, 글자 크기, 줄 간격 등을 자유롭게 설정할 수 있으며, 단어 찾기/바꾸기와 같은 편리한 기능을 제공해준다.
- http://dev.naver.com/projects/smarteditor
- 최신버전 다운
- 프로젝트에 추가
````javascript
<script type="text/javascript" src="se2/js/HuskyEZCreator.js" charset="utf-8"></script>
````
````jquery
$(function(){
    var editor_object = [];
    nhn.husky.EZCreator.createInIFrame({
        oAppRef: editor_object,
        elPlaceHolder: "smarteditor",
        sSkinURI: "se2/SmartEditor2Skin.html", 
        htParams : {
            bUseToolbar : true,             
            bUseVerticalResizer : false,
            bUseModeChanger : false, 
        }
    });

    $("#save").click(function(){
        editor_object.getById["smarteditor"].exec("UPDATE_CONTENTS_FIELD", []);
        $("#form").submit();
    })
````
````html
<form action="url" method="post" id="form">
	<textarea id="smarteditor"></textarea>
	<button id="save" type="submit">save</button>
</form>
````