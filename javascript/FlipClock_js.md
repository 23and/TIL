#FlipClock js
````html
<html>
	<head>
		<link rel="stylesheet" href="/assets/css/flipclock.css">
	</head>
	<body>
		<div class="your-clock"></div>
		
		<script src="/assets/js/libs/jquery.js"></script>
		<script src="/assets/js/flipclock/flipclock.min.js"></script>
	</body>
</html>
````
````javascript
var clock = $('.your-clock').FlipClock({
});

var clock = new FlipClock($('.your-clock'), {
});
````
- http://flipclockjs.com/