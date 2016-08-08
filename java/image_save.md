#image save

- 이미지 위에 글자 쓰고, 다시 이미지로 저장

````java
String path="위치"; 
BufferedImage img = ImageIO.read(new File(path));
BufferedImage image = new BufferedImage(width, height, BufferedImage.TYPE_INT_RGB);
Graphics2D g = image.createGraphics(); 
g.drawImage(img, 0, 0, width, height, null);
g.setColor(Color.GRAY);
g.setFont(new Font("고딕체",Font.BOLD,30));
g.drawString("글자", 50, 50);
ImageIO.write(image,"jpg",new File("저장 위치"));
````