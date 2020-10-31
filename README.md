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

#### DecimalToText function

    public static String decimalToText(BigInteger integer) {
        boolean isZero = integer.compareTo(BigInteger.ZERO) == 0; 
        return isZero ? FULLY_TH : toText(integer).concat(SATANG_TH);
    }
