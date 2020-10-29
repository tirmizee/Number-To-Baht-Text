# Number-To-Baht-Text

### Algorithm design

- <b>ToText </b> : function to convert number to text between 0-9,999,999 . 

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/97610581-a9e09500-1a47-11eb-9dc1-b545d43fd121.png" width="650">
</p>

#### NumberToText function

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
