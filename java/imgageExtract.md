#imgage extract
````java
public void imgExtract(String text) {
	Pattern nonValidPattern = Pattern.compile("<img[^>]*src=[\"']?([^>\"']+)[\"']?[^>]*>");
	List<String> result = new ArrayList<String>();
	Matcher matcher = nonValidPattern.matcher(text);
	while (matcher.find()) {
		result.add(matcher.group(1));
	}
}
````