# Number-To-Baht-Text

### Algorithm design

- <b>ToText </b> : function to convert number to text between 0 and 9,999,999 . 

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/97611483-d47f1d80-1a48-11eb-9c82-0719b39f002e.png" width="650">
</p>

#### NumberToText function (Main)

    public static String numberToText(BigDecimal bigDecimal) {

        bigDecimal = bigDecimal.setScale(2, RoundingMode.HALF_UP);

        String plain = bigDecimal.toPlainString();
        String plains[] = plain.split("\\.");

        BigInteger integer = new BigInteger(plains[0]);
        BigInteger decimal = new BigInteger(plains[1]);

        String integerText = integerToText(integer);
        String decimalText = decimalToText(decimal);

        return integerText + decimalText;
    }

#### IntegerToText function

#### DecimalToText function

    public static String decimalToText(BigInteger integer) {
        boolean isZero = integer.compareTo(BigInteger.ZERO) == 0; 
        return isZero ? FULLY_TH : toText(integer).concat(SATANG_TH);
    }
    
#### Demo

    public static void main(String[] args) {
        System.out.println(numberToText(new BigDecimal(0.21)));
        System.out.println(numberToText(new BigDecimal(0)));
        System.out.println(numberToText(new BigDecimal(1.0)));
        System.out.println(numberToText(new BigDecimal(11.67)));
        System.out.println(numberToText(new BigDecimal(11)));
        System.out.println(numberToText(new BigDecimal(201.99)));
        System.out.println(numberToText(new BigDecimal(11_311)));
        System.out.println(numberToText(new BigDecimal(200_000)));
        System.out.println(numberToText(new BigDecimal(8_999_902.88)));
        System.out.println(numberToText(new BigDecimal(123_456_789.10)));
        System.out.println(numberToText(new BigDecimal(90_999_123_456_789.20)));
        System.out.println(numberToText(new BigDecimal("300987654321123456541.90")));
    }
    
    ศูนย์บาทยี่สิบเอ็ดสตางค์
    ศูนย์บาทถ้วน
    หนึ่งบาทถ้วน
    สิบเอ็ดบาทหกสิบเจ็ดสตางค์
    สิบเอ็ดบาทถ้วน
    สองร้อยหนึ่งบาทเก้าสิบเก้าสตางค์
    หนึ่งหมื่นหนึ่งพันสามร้อยสิบเอ็ดบาทถ้วน
    สองแสนบาทถ้วน
    แปดล้านเก้าแสนเก้าหมื่นเก้าพันเก้าร้อยสองบาทแปดสิบแปดสตางค์
    หนึ่งร้อยยี่สิบสามล้านสี่แสนห้าหมื่นหกพันเจ็ดร้อยแปดสิบเก้าบาทสิบสตางค์
    เก้าสิบล้านล้านเก้าแสนเก้าหมื่นเก้าพันหนึ่งร้อยยี่สิบสามล้านสี่แสนห้าหมื่นหกพันเจ็ดร้อยแปดสิบเก้าบาทยี่สิบสตางค์
    สามร้อยล้านล้านล้านเก้าแสนแปดหมื่นเจ็ดพันหกร้อยห้าสิบสี่ล้านล้านสามแสนสองหมื่นหนึ่งพันหนึ่งร้อยยี่สิบสามล้านสี่แสนห้าหมื่นหกพันห้าร้อยสี่สิบเอ็ดบาทเก้าสิบสตางค์

