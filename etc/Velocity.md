#Velocity

###VTL(Velocity Template Language) 장점
- UI 디자이너와 개발자의 병렬 개발 가능
- 각각의 영역에 집중가능
- 유지보수 용의
- JSP,PHP 대체방안 제시

###문법
- VTL 문장은 # 으로 시작하며  변수명은 $ 로 표시한다.
- VTL 문장의 시작은 #으로 시작한다.
- 변수의 시작은 $로 시작한다.
- 주석
 - 한줄 ##
 - 여러줄 #* *#
````
# set( $foo = "Velocity")
````
````
<html>
	<body>
		#set($color = "blue")
		좋아하는 색깔은 $color 입니다.
	</body>
</html>
````
- 객체 사용
````
$ custom.Address
$ custom.getAddress()
````
````
#if($velocityCount <= 3)
   $item
#end
````
````
<ul> 
#foreach( $product in $allProducts ) 
<li>$product.id , $product.name</li> 
#end 
</ul>
````
