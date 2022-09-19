# 4.1

```java
import java.util.*;

public class AreaOfPentagon {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read r
        System.out.print("Enter the length from the center to a vertex: ");
        double r = input.nextDouble();

        //compute the area
        double s = 2 * r * Math.sin(Math.PI / 5);
        double area = 5 * Math.pow(s, 2) / (4 * Math.tan(Math.PI / 5));

        //display the result
        System.out.printf("The area of the pentagon is %.2f", area);
    }
}
```

# 4.2

```java
import java.util.*;

public class GreatCircleDistance {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter point 1 (latitude and longitude) in degrees: ");
        double x1 = input.nextDouble();
        double y1 = input.nextDouble();
        System.out.print("Enter point 2 (latitude and longitude) in degrees: ");
        double x2 = input.nextDouble();
        double y2 = input.nextDouble();

        //compute the distance
        final double radius = 6371.01;
        x1 = Math.toRadians(x1);
        y1 = Math.toRadians(y1);
        x2 = Math.toRadians(x2);
        y2 = Math.toRadians(y2);
        double distance = radius * Math.acos(Math.sin(x1) * Math.sin(x2) + Math.cos(x1) * Math.cos(x2) * Math.cos(y1 - y2));

        //display the result
        System.out.println("The distance between the two points is " + distance + " km");
    }
}
```

# 4.4

```java
import java.util.*;

public class AreaOfHexagon {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read the length of a side
        System.out.print("Enter the side: ");
        double s = input.nextDouble();

        //compute the area
        double area = 6 * Math.pow(s, 2) / (4 * Math.tan(Math.PI / 6));

        //display the result
        System.out.println("The area of the hexagon is " + area);
    }
}
```

# 4.5

```java
import java.util.*;

public class AreaOfRegularPolygon {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read n, s
        System.out.print("Enter the number of sides: ");
        int n = input.nextInt();
        System.out.print("Enter the side: ");
        double s = input.nextDouble();

        //compute the area
        double area = n * Math.pow(s, 2) / (4 * Math.tan(Math.PI / n));

        //display the result
        System.out.println("The area of the polygon is " + area);
    }
}
```

# 4.6

```java
import java.util.*;

public class RandomPointsOnCircle {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //generate 3 points
        final double radius = 40;
        double angle1 = Math.random() * 2 * Math.PI;
        double x1 = radius * Math.cos(angle1);
        double y1 = radius * Math.sin(angle1);
        double angle2 = Math.random() * 2 * Math.PI;
        double x2 = radius * Math.cos(angle2);
        double y2 = radius * Math.sin(angle2);
        double angle3 = Math.random() * 2 * Math.PI;
        double x3 = radius * Math.cos(angle3);
        double y3 = radius * Math.sin(angle3);

        // Compute three sides
        double a = Math.sqrt((x2 - x3) * (x2 - x3)
                + (y2 - y3) * (y2 - y3));
        double b = Math.sqrt((x1 - x3) * (x1 - x3)
                + (y1 - y3) * (y1 - y3));
        double c = Math.sqrt((x1 - x2) * (x1 - x2)
                + (y1 - y2) * (y1 - y2));

        // Compute three angles
        double A = Math.toDegrees(Math.acos((a * a - b * b - c * c)
                / (-2 * b * c)));
        double B = Math.toDegrees(Math.acos((b * b - a * a - c * c)
                / (-2 * a * c)));
        double C = Math.toDegrees(Math.acos((c * c - b * b - a * a)
                / (-2 * a * b)));
        
        // Display results
        System.out.println("The three angles are " +
                Math.round(A * 100) / 100.0 + " " +
                Math.round(B * 100) / 100.0 + " " +
                Math.round(C * 100) / 100.0);
    }
}
```

# 4.7

```java
import java.util.*;

public class CornerPoint {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read r
        System.out.print("Enter the radius of the bounding circle: ");
        double r = input.nextDouble();

        //compute
        double angle = Math.toRadians(360.0 / 5);
        double[] x = new double[6];
        double[] y = new double[6];
        x[1] = r * Math.sin(angle);
        y[1] = r * Math.cos(angle);
        x[2] = 0;
        y[2] = r;
        x[3] = -x[1];
        y[3] = y[1];
        x[4] = -r * Math.sin(angle / 2);
        y[4] = -r * Math.cos(angle / 2);
        x[5] = -x[4];
        y[5] = y[4];

        //display the result
        System.out.println("The coordinates of five points on the pentagon are");
        for(int i = 1; i <= 5; i++)
            System.out.printf("(%.2f, %.2f)\n", x[i], y[i]);
    }
}
```

# 4.8

```java
import java.util.*;

public class FindCharacter {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read r
        System.out.print("Enter an ASCII code: ");
        int ascii = input.nextInt();

        //display the result
        System.out.println("The character for ASCII code " + ascii + " is " + (char)ascii);
    }
}
```

# 4.9

```java
import java.util.*;

public class FindUnicode {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter a character: ");
        char ch = input.next().charAt(0);

        //display the result
        System.out.println("The Unicode for the character " + ch + " is " + (int)ch);
    }
}
```

# 4.10

```java
import java.util.*;

public class GuessBirthday {
    public static void main(String[] args) {
        String set1 =
                " 1  3  5  7\n" +
                        " 9 11 13 15\n" +
                        "17 19 21 23\n" +
                        "25 27 29 31";

        String set2 =
                " 2  3  6  7\n" +
                        "10 11 14 15\n" +
                        "18 19 22 23\n" +
                        "26 27 30 31";

        String set3 =
                " 4  5  6  7\n" +
                        "12 13 14 15\n" +
                        "20 21 22 23\n" +
                        "28 29 30 31";

        String set4 =
                " 8  9 10 11\n" +
                        "12 13 14 15\n" +
                        "24 25 26 27\n" +
                        "28 29 30 31";

        String set5 =
                "16 17 18 19\n" +
                        "20 21 22 23\n" +
                        "24 25 26 27\n" +
                        "28 29 30 31";

        int day = 0;

        // Create a Scanner
        Scanner input = new Scanner(System.in);
        char answer = ' ';

        // Prompt the user to answer questions
        System.out.print("Is your birthday in Set1?\n");
        System.out.print(set1);
        System.out.print("\nEnter Y for yes and N for No: ");
        answer = input.next().charAt(0);

        if (answer == 'Y')
            day += 1;

        // Prompt the user to answer questions
        System.out.print("Is your birthday in Set2?\n");
        System.out.print(set2);
        System.out.print("\nEnter Y for yes and N for No: ");
        answer = input.next().charAt(0);

        if (answer == 'Y')
            day += 2;

        // Prompt the user to answer questions
        System.out.print("Is your birthday in Set3?\n");
        System.out.print(set3);
        System.out.print("\nEnter Y for yes and N for No: ");
        answer = input.next().charAt(0);

        if (answer == 'Y')
            day += 4;

        // Prompt the user to answer questions
        System.out.print("Is your birthday in Set4?\n");
        System.out.print(set4);
        System.out.print("\nEnter Y for yes and N for No: ");
        answer = input.next().charAt(0);

        if (answer == 'Y')
            day += 8;

        // Prompt the user to answer questions
        System.out.print("Is your birthday in Set5?\n");
        System.out.print(set5);
        System.out.print("\nEnter Y for yes and N for No: ");
        answer = input.next().charAt(0);

        if (answer == 'Y')
            day += 16;

        System.out.println("\nYour birthday is " + day + "!");
    }
}
```

# 4.11

```java
import java.util.*;

public class DecimalToHex {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a decimal value
        System.out.print("Enter a decimal value (0 to 15): ");
        int decimal = input.nextInt();

        //judge the input
        if (decimal < 0 || decimal > 15)
            System.out.println(decimal + " is an invalid input");
        else if (decimal <= 9)
            System.out.print("The hex value is " + decimal);
        else
            System.out.println("The hex value is " + (char) ('A' + decimal - 10));
    }
}
```

# 4.12

```java
import java.util.*;

public class HexToBinary {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a hex digit
        System.out.print("Enter a hex digit: ");
        char hex = input.next().charAt(0);

        //judge the input
        int decimal = 0;
        if (Character.isLetterOrDigit(hex)) {
            //convert hex to decimal
            if(Character.isLetter(hex))
                if(hex > 'F') {
                    System.out.println(hex + " is an invalid input");
                    System.exit(1);
                }
                else
                    decimal = 10 + hex - 'A';
            else
                decimal = hex;

            //convert decimal to binary
            int binary = 0, i = 0;
            while(decimal > 0) {
                binary += (decimal % 2) * (int)Math.pow(10, i++);
                decimal /= 2;
            }
            System.out.println("The binary value is " + binary);
        }
    }
}
```

# 4.13

```java
import java.util.*;

public class HexToBinary {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a letter
        System.out.print("Enter a letter: ");
        char letter = input.next().charAt(0);

        //judge the input
        if (Character.isLetter(letter)) {
            switch(letter) {
                case 'A': case 'E': case 'I': case 'O': case 'U':
                case 'a': case 'e': case 'i': case 'o': case 'u':
                    System.out.println(letter + " is a vowel");
                    break;
                default: System.out.println(letter + " is a consonant");
            }
        }
        else
            System.out.println(letter + " is an invalid input");
    }
}
```

# 4.15

```java
import java.util.*;

public class PhoneKeyPads {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a letter
        System.out.print("Enter a letter: ");
        char letter = input.next().toLowerCase().charAt(0);

        //judge the input
        int number = 0;
        if (Character.isLetter(letter)) {
            if(letter == 'z')
                number = 9;
            else
                number = (letter - 'a') / 3 + 2;
            System.out.println("The corresponding number is " + number);
        }
        else
            System.out.println(letter + " is an invalid input");
    }
}
```

# 4.16

```java
import java.util.*;

public class PhoneKeyPads {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //generate a letter
        char ch = (char)('A' + (int)(Math.random() * 26));

        //display the result
        System.out.println(ch);
    }
}
```

# 4.17

```java
import java.util.*;

public class DaysOfMonth {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter a year: ");
        int year = input.nextInt();
        System.out.print("Enter a month: ");
        String month = input.next();

        //judge the input
        if(month.equals("Jan")) {
            System.out.println(month + ' ' + year + " has " + 31 + " days");
            System.exit(1);
        }
        if(month.equals("Feb")) {
            if(year % 4 == 0 && year % 100 != 0 || year % 400 == 0)
                System.out.println(month + ' ' + year + " has " + 29 + " days");
            else
                System.out.println(month + ' ' + year + " has " + 28 + " days");
            System.exit(1);
        }
        if(month.equals("Mar")) {
            System.out.println(month + ' ' + year + " has " + 31 + " days");
            System.exit(1);
        }
        if(month.equals("Apr")) {
            System.out.println(month + ' ' + year + " has " + 30 + " days");
            System.exit(1);
        }
        if(month.equals("May")) {
            System.out.println(month + ' ' + year + " has " + 31 + " days");
            System.exit(1);
        }
        if(month.equals("Jun")) {
            System.out.println(month + ' ' + year + " has " + 30 + " days");
            System.exit(1);
        }
        if(month.equals("Jul")) {
            System.out.println(month + ' ' + year + " has " + 31 + " days");
            System.exit(1);
        }
        if(month.equals("Aug")) {
            System.out.println(month + ' ' + year + " has " + 31 + " days");
            System.exit(1);
        }
        if(month.equals("Sep")) {
            System.out.println(month + ' ' + year + " has " + 30 + " days");
            System.exit(1);
        }
        if(month.equals("Oct")) {
            System.out.println(month + ' ' + year + " has " + 31 + " days");
            System.exit(1);
        }
        if(month.equals("Nov")) {
            System.out.println(month + ' ' + year + " has " + 30 + " days");
            System.exit(1);
        }
        if(month.equals("Dec")) {
            System.out.println(month + ' ' + year + " has " + 31 + " days");
            System.exit(1);
        }
        System.out.println(month + " is not a correct month name");
    }
}
```

# 4.18

```java
import java.util.*;

public class MajorStatus {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter two characters: ");
        String str = input.next();
        char chMajor = str.charAt(0);
        char chStatus = str.charAt(1);

        //judge the input
        String strMajor = "";
        String strStatus = "";
        switch(chMajor) {
            case 'M': strMajor = "Mathematics"; break;
            case 'C': strMajor = "Computer Science"; break;
            case 'I': strMajor = "Information Technology"; break;
            default: System.out.println("Invalid input"); System.exit(1);
        }
        switch (chStatus) {
            case '1': strStatus = "Freshman"; break;
            case '2': strStatus = "Sophomore"; break;
            case '3': strStatus = "Junior"; break;
            case '4': strStatus = "Senior"; break;
            default: System.out.println("Invalid input"); System.exit(1);
        }
        System.out.println(strMajor + ' ' + strStatus);
    }
}
```

# 4.19

```java
import java.util.Scanner;

public class ISBN {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read the first 9 digits of an ISBN
        System.out.print("Enter the first 9 digits of an ISBN: ");
        String src = input.next();

        //compute the 10th digit
        int sum = 0;
        for(int i = 0; i < 9; i++)
            sum += (src.charAt(i) - '0') * (i + 1);
        int digit10 = sum % 11;

        //display the result
        System.out.print("The ISBN-10 number is " + src);
        if(digit10 == 10)
            System.out.println('X');
        else
            System.out.println(digit10);
    }
}
```

# 4.20

```java
import java.util.Scanner;

public class ProcessString {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read the input
        System.out.print("Enter a string: ");
        String src = input.nextLine();

        //display the result
        System.out.println("The length of the string is " + src.length());
        System.out.println("The first character of the string is " + src.charAt(0));
    }
}
```

# 4.21

```java
import java.util.*;

public class SSN {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a SSN
        String SSN = input.next();

        //judge the input
        boolean validity = true;
        if(SSN.length() == 11) {
            for(int i = 0; i < 11; i++)
                switch(i) {
                    case 3: case 6:
                        if(SSN.charAt(i) != '-')
                            validity = false;
                        break;
                    default:
                        if(!Character.isDigit(SSN.charAt(i)))
                            validity = false;
                        break;
                }
        }
        else
            validity = false;

        //display the result
        if(validity)
            System.out.println(SSN + " is a valid social security number");
        else
            System.out.println(SSN + " is an invalid social security number");
    }
}
```

# 4.22

```java
import java.util.*;

public class CheckSubstring {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter string s1: ");
        String s1 = input.next();
        System.out.print("Enter string s2: ");
        String s2 = input.next();

        //display the result
        if(s1.contains(s2))
            System.out.println(s2 + " is a substring of " + s1);
        else
            System.out.println(s2 + " is not a substring of " + s1);
    }
}
```

# 4.23

```java
import java.util.*;

public class Payroll {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Employee's name: ");
        String employeeName = input.next();
        System.out.print("Enter number of hours worked in a week: ");
        double workHours = input.nextDouble();
        System.out.print("Enter hourly pay rate: ");
        double hourlyPayRate = input.nextDouble();
        System.out.print("Enter federal tax withholding rate: ");
        double federalTaxWithholdingRate = input.nextDouble();
        System.out.print("Enter state tax withholding rate: ");
        double stateTaxWithholdingRate = input.nextDouble();


        //display the result
        System.out.println("\nEmployee Name: " + employeeName);
        System.out.printf("Hours worked: %.1f\n", workHours);
        System.out.printf("Pay Rate: $%.2f\n", hourlyPayRate);
        System.out.printf("Gross Pay: $%.2f\n", workHours * hourlyPayRate);
        System.out.println("Deductions:");
        System.out.printf("\tFederal Withholding (%.1f%%): $%.2f\n", federalTaxWithholdingRate * 100, workHours * hourlyPayRate * federalTaxWithholdingRate);
        System.out.printf("\tState Withholding (%.1f%%): $%.2f\n", stateTaxWithholdingRate * 100, workHours * hourlyPayRate * stateTaxWithholdingRate);
        System.out.printf("\tTotal Deduction: $%.2f\n", workHours * hourlyPayRate * (federalTaxWithholdingRate + stateTaxWithholdingRate));
        System.out.printf("Net Pay: $%.2f\n", workHours * hourlyPayRate * (1 - federalTaxWithholdingRate - stateTaxWithholdingRate));
    }
}
```

# 4.24

```java
import java.util.*;

public class OrderCities {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter the first city: ");
        String city1 = input.nextLine();
        System.out.print("Enter the second city: ");
        String city2 = input.nextLine();
        System.out.print("Enter the third city: ");
        String city3 = input.nextLine();

        //order cities
        String temp = "";
        if(city1.compareToIgnoreCase(city2) > 0) {
            temp = city1;
            city1 = city2;
            city2 = temp;
        }
        if(city2.compareToIgnoreCase(city3) > 0) {
            temp = city2;
            city2 = city3;
            city3 = temp;
        }
        if(city1.compareToIgnoreCase(city2) > 0) {
            temp = city1;
            city1 = city2;
            city2 = temp;
        }

        //display the result
        System.out.println("The three cities in alphabetical order are " + city1 + ' ' + city2 + ' ' + city3);
    }
}
```

# 4.25

```java
import java.util.*;

public class GenerateVehiclePlateNumbers {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //generate
        char[] vehiclePlateNumber = new char[7];
        for(int i = 0; i < 3; i++)
            vehiclePlateNumber[i] = (char)('A' + Math.random() * 26);
        for(int i = 3; i < 7; i++)
            vehiclePlateNumber[i] = (char)('0' + Math.random() * 10);

        //display the result
        System.out.println(vehiclePlateNumber);
    }
}
```

# 4.26

```java
import java.util.*;

public class ComputeChange {
    public static void main(String[] args) {
        // Create a Scanner
        Scanner input = new Scanner(System.in);

        // Receive the amount
        System.out.print("Enter an amount in double, for example 11.56: ");
        String amount = input.next();

        // Find the number of dollars
        int numberOfOneDollars = Integer.parseInt(amount.substring(0, amount.indexOf('.')));

        //Find the number of cents
        int remainingAmount = Integer.parseInt(amount.substring(amount.indexOf('.') + 1));

        // Find the number of quarters in the remaining amount
        int numberOfQuarters = remainingAmount / 25;
        remainingAmount = remainingAmount % 25;

        // Find the number of dimes in the remaining amount
        int numberOfDimes = remainingAmount / 10;
        remainingAmount = remainingAmount % 10;

        // Find the number of nickels in the remaining amount
        int numberOfNickels = remainingAmount / 5;
        remainingAmount = remainingAmount % 5;

        // Find the number of pennies in the remaining amount
        int numberOfPennies = remainingAmount;

        // Display results
        System.out.println("Your amount " + amount + " consists of");
        System.out.println("    " + numberOfOneDollars + " dollars");
        System.out.println("    " + numberOfQuarters + " quarters ");
        System.out.println("    " + numberOfDimes + " dimes");
        System.out.println("    " + numberOfNickels + " nickels");
        System.out.println("    " + numberOfPennies + " pennies");
    }
}
```



