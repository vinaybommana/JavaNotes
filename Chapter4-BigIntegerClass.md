#BigNumbers

##BigInteger Class

`public class BigInteger extends Number implements Comparable<BigInteger>`

* BigInteger class is used for mathematical operation which involves very **big** integer calculations.
* which are outside the limit of all available primitive data types.
* BigIntegers are `Immutable` arbitrary-precision integers.
* Additional to that of the `java.lang.Math`, BigInteger provides operations for
    - modular arithmetic
    - GCD calcualtion
    - primality testing
    - prime generation
    - bit manipulation
    - and a few other miscellanous operations.

####Example
```java
import java.math.BigInteger;

public class MainClass {
    public static void main(String[] args) {
        System.out.println("Here's a Long.MAX_VALUE: " + Long.MAX_VALUE); // 9223372036854775807
        BigInteger bInt = new BigInteger("999999999999999999999999999999");
    }
}
```

#### Adding to BigInteger values.

```java
import java.math.BigInteger;

public class AddingTwoNum {
    public static void main(String[] args) {
        BigInteger a = new BigInteger("999999999999999");
        BigInteger b = new BigInteger.valueOf(1);
        a = a.add(b);
        System.out.println(a);
    }
}
```
For subtracting two `BigInteger` numbers use `a.sub(b)` regarding the former eg.,\
For multiplying two `BigInteger` numbers use `a.multiply(b)` regarding the former eg.,\
For dividing  two `BigInteger` numbers use `a.divide(b)` regarding the former eg.,\

$~$

* Other methods common that can be applied to the BigInteger class
    - `gcd()`
    - `max()`
    - `min()`
    - `mod()`
    - `remainder()`
    - `pow(_exponent_)`

####Comparison between two BigIntegers

* In order to compare two `BigInteger` numbers we need to use `compareTo` method.
* The method declaration for `compareTo`
```java
public int compareTo(BigInteger val)
```
* for example we need to write a while loop to until a `BigInteger` is less than `BigInteger.ZERO` then

```java
while(a.compareTo(b) > 0) {
    // do something
}
```

* `compareTo` method returns -1 for less than, 0 for equal to, 1 for greater than the number.

##BigDecimal Class

`public class BigInteger extends Number implements Comparable<BigInteger>`

* Immutable, arbitrary-precision signed decimal numbers.
* A `BigDecimal` consists of an arbitrary precision integer _unscaled_ value and a 32 bit integer-scale.

* The `java.math.BigDecimal` class provides operations for:
    - arithmetic
    - scale manipulation
    - rounding
    - comparison
    - hashing
    - format conversion

* Two types of operations are provided for manipulating the scale of a Decimal number:
    - scaling / rounding operations
    - decimal point motion operations
* These are used for monetary values.

####Example for BigDecimal and Monetary values

```java
import java.math.BigDecimal;
import java.math.RoundingMode;

public class MonetaryExample {
    public static void main(String[] args) {
        BigDecimal total = new BigDecimal("123.45");
        BigDecimal discountPercent = new BigDecimal("0.10");
        BigDecimal discount = total.multiply(discountPercent);
        BigDecimal beforeTax = total.subtract(discount);
        beforeTax = beforeTax.setScale(2, RoundingMode.HALF_UP);
        BigDecimal salesTaxPercent = new BigDecimal("0.05");
        BigDecimal salesTax = beforeTax.multiply(salesTaxPercent);
        salesTax = salesTax.setScale(2, RoundingMode.HALF_UP);
        BigDecimal result = beforeTax.add(salesTax);
        result = result.setScale(2, RoundingMode.HALF_UP);
        System.out.println("Subtotal: " + total);
        System.out.println("Discount: " + discount);
        System.out.println("SubTotal after discount: " + beforeTax);
        System.out.println("Sales Tax: " + salesTax);
        System.out.println("Total: " + result);
    }
}
```

`java.math.BigDecimal.setScale(int newScale, RoundingMode roundingMode)`

####for example:
    - new BigDecimal("2.5467").setScale(3, RoundingMode.HALF_UP) 
    - results in 2.547

```java
BigDecimal smallNumber = new BigDecimal("0.01234");
smallNumber.round(new MathContext(2, RoundingMode.HALF_UP)));
// Result   = 0.012
smallNumber.setScale(2, RoundingMode.HALF_UP));
// Result   = 0.01
```

```java
BigDecimal number = new BigDecimal("1.01234");
number.round(new MathContext(2, RoundingMode.HALF_UP))); 
// Result   = 1.0
number.setScale(2, RoundingMode.HALF_UP));
// Result   = 1.01
```
$~$

In general the rounding modes and precision setting determine how operations return results\
with a limited number of digits when the exact result has more digits (perhaps infinitely many in the case of division) than the number of digits returned.\
First, the total number of digits to return is specified by the MathContext's precision setting;\
this determines the result's precision.\
_The digit count starts from the leftmost nonzero digit of the exact result._\
The rounding mode determines how any discarded trailing digits affect the returned result. 
