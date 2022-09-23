# 6.1

```java
public class PentagonalNumbers {
    public static void main(String[] args) {
        for(int i = 1; i <= 100; i++) {
            System.out.printf("%7d", getPentagonalNumber(i));
            if(i % 10 == 0)
                System.out.println();
        }
    }

    public static int getPentagonalNumber(int n) {
        return n * (3 * n - 1) / 2;
    }
}
```

# 6.2

```java
import java.util.*;

public class SumDigits {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read an integer
        System.out.printf("Enter an integer: ");
        int src = input.nextInt();

        //display the result
        System.out.printf("The sum digits of %d is : %d", src, sumDigits(src));
    }

    public static int sumDigits(int n) {
        int sum = 0, remaining = n;
        while(remaining != 0) {
            sum += remaining % 10;
            remaining /= 10;
        }

        return sum;
    }
}
```

# 6.3

```java
import java.util.*;

public class PalindromeInteger {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read an integer
        System.out.printf("Enter an integer: ");
        int src = input.nextInt();

        //display the result
        if(isPalindrome(src))
            System.out.printf("The integer is palindrome\n");
        else
            System.out.printf("The integer is not a palindrome\n");
    }

    public static boolean isPalindrome(int n) {
        return n == reverse(n);
    }

    public static int reverse(int n) {
        String src = n + "";
        int reversal = 0;

        for(int i = src.length() - 1; i >= 0; i--)
            reversal = reversal * 10 + src.charAt(i) - '0';

        return reversal;
    }
}
```

# 6.4

```java
import java.util.*;

public class DisplayReversal {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read an integer
        System.out.printf("Enter an integer: ");
        int src = input.nextInt();

        //display the result
        reverse(src);
    }

    public static void reverse(int n) {
        String src = n + "";
        int reversal = 0;

        //compute the reversal
        for(int i = src.length() - 1; i >= 0; i--)
            reversal = reversal * 10 + src.charAt(i) - '0';

        //display the reversal
        System.out.printf("The reversal of %d is: %d\n", n, reversal);
    }
}
```

# 6.5

```java
import java.util.*;

public class SortThreeNumbers {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read 3 numbers
        System.out.printf("Enter 3 numbers: ");
        double num1 = input.nextDouble(), num2 = input.nextDouble(), num3 = input.nextDouble();

        //display the result
        displaySortedNumbers(num1, num2, num3);
    }

    public static void displaySortedNumbers(double num1, double num2, double num3) {
        //sort the numbers
        double temp = 0;
        if(num1 > num2) {
            temp = num1;
            num1 = num2;
            num2 = temp;
        }
        if(num2 > num3) {
            temp = num2;
            num2 = num3;
            num3 = temp;
        }
        if(num1 > num2) {
            temp = num1;
            num1 = num2;
            num2 = temp;
        }

        //display the numbers in increasing order
        System.out.printf("The increasing order of the numbers is:\n%f\n%f\n%f\n", num1, num2, num3);
    }
}
```

# 6.6

```java
import java.util.*;

public class DisplayPatterns {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read an integer
        System.out.printf("Enter an integer: ");
        int lines = input.nextInt();

        //display the result
        displayPatterns(lines);
    }

    public static void displayPatterns(int lines) {
        for(int i = 1; i <= lines; i++) {
            //print spaces
            for(int j = lines - i; j >= 1; j--)
                System.out.printf("   ");

            //print numbers before '1'
            for(int k = i; k > 1; k--)
                System.out.printf("%-3d", k);

            //print '1' and change the line
            System.out.printf("1\n");
        }
    }
}
```

# 6.18

```java
import java.util.*;

public class CheckPasswords {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read a password
        System.out.printf("Enter a password: ");
        String password = input.nextLine();

        //display the result
        if(isValidPassword(password))
            System.out.println("Valid password");
        else
            System.out.println("Invalid password");
    }

    public static boolean isValidPassword(String password) {
        //check point1
        if(password.length() < 8)
            return false;

        //check point2
        int digitsNumbers = 0;
        char temp = ' ';
        for(int index = password.length() - 1; index >= 0; index--) {
            temp = password.charAt(index);
            if(Character.isDigit(temp)) {
                digitsNumbers++;
                continue;
            }
            else if(!Character.isLetter(temp))
                return false;
        }

        //check point3
        if(digitsNumbers < 2)
            return false;
        else
            return true;
    }
}
```

# 6.22

```java
import java.util.*;

public class SquareRoot {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read a number
        System.out.printf("Enter a number: ");
        double number = input.nextDouble();

        //display the result
        System.out.printf("The square root of %f is: %f\n", number, sqrt(number));
    }

    public static double sqrt(double n) {
        double lastGuess = 1, nextGuess = 1;
        do {
            lastGuess = nextGuess;
            nextGuess = (lastGuess + n / lastGuess) / 2;
        } while(Math.abs(nextGuess - lastGuess) >= 0.0001);

        return  nextGuess;
    }
}
```