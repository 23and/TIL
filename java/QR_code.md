#QR code

- zxing library
 - 자바로 구현된 1D/2D 바코드 이미지 처리 오픈소스
- https://github.com/zxing/zxing
- core: The core image decoding library, and test code
- javase: J2SE-specific client code

````
public class QRCode {
    public static void main(String[] args) {
        QRCodeWriter q = new QRCodeWriter();
        try {
            String text = "url";
            text = new String(text.getBytes("UTF-8"), "ISO-8859-1");
            BitMatrix bitMatrix = q.encode(text, BarcodeFormat.QR_CODE,200,200);
            MatrixToImageWriter.writeToStream(bitMatrix, "png",
                    new FileOutputStream(new File("qrcode.png")));
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
````