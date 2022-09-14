# 2.1

```java
import java.util.*;

public class ConvertTemperature {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a degree in Celsius: ");
        double celsius = input.nextDouble();
        double fahrenheit = (9.0 / 5) * celsius + 32;
        System.out.print(celsius + " Celsius is " + fahrenheit + " Fahrenheit");
    }
}
```

# 2.2

```java
import java.util.*;
import static java.lang.Math.PI;

public class CylinderVolume {
    //Main method
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Enter the radius and length
        System.out.print("Enter the radius and length of a cylinder: ");
        double radius = input.nextDouble();
        double length = input.nextDouble();

        //Compute the area and volume
        double area = radius * radius * PI;
        double volume = area * length;
        System.out.println("The area is " + area);
        System.out.println("The volume is " + volume);
    }
}
```

# 2.3

```java
import java.util.*;

public class ConvertLength {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Enter a length in feet
        System.out.print("Enter a value for feet: ");
        double feet = input.nextDouble();

        //Convert feet into meters
        double meters = feet * 0.305;
        
        //Display the result
        System.out.println(feet + " feet is " + meters + " meters");
    }
}
```

# 2.4

```java
import java.util.*;

public class ConvertMass {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Enter a mass in pounds
        System.out.print("Enter a number in pounds: ");
        double pounds = input.nextDouble();

        //Convert pounds into kilograms
        double kilograms = pounds * 0.454;

        //Display the result
        System.out.println(pounds + " pounds is " + kilograms + " kilograms");
    }
}
```

# 2.5

```java
import java.util.*;

public class ConvertMass {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Enter the subtotal and a gratuity rate
        System.out.print("Enter the subtotal and a gratuity rate: ");
        double subtotal = input.nextDouble();
        double gratuityRate = input.nextDouble() / 100;

        //Compute the gratuity and total
        double gratuity = subtotal * gratuityRate;
        double total = subtotal + gratuity;

        //Display the result
        System.out.println("The gratuity is $" + gratuity + " and total is $" + total);
    }
}
```

# 2.6

```java
import java.util.*;

public class SumDigits {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Enter the number
        System.out.print("Enter a number between 0 and 1000: ");
        int source = input.nextInt();

        //Adds all the digits
        int remaining = source;
        int sum = 0;
        int next_digit = 0;
        while(remaining != 0) {
            next_digit = remaining % 10;
            sum += next_digit;
            remaining /= 10;
        }

        //Display the result
        System.out.println("The sum of the digits is " + sum);
    }
}
```

# 2.7

```java
import java.util.*;

public class SumDigits {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Enter the number of minutes
        System.out.print("Enter the number of minutes: ");
        int minutes = input.nextInt();

        //Compute years and days
        int days = minutes / 60 / 24;
        int years = days / 365;
        days %= 365;

        //Display the result
        System.out.println(minutes + " minutes is approximately " + years + " years and " + days + " days");
    }
}
```

# 2.8

```java
import java.util.*;

public class ShowCurrentTime {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read the time zone
        System.out.print("Enter the time zone offset to GMT: ");
        int timeZone = input.nextInt();

        //Compute the current time
            // Obtain the total milliseconds since midnight, Jan 1, 1970
            long totalMilliseconds = System.currentTimeMillis();

            // Obtain the total seconds since midnight, Jan 1, 1970
            long totalSeconds = totalMilliseconds / 1000;

            // Compute the current second in the minute in the hour
            long currentSecond = totalSeconds % 60;

            // Obtain the total minutes
            long totalMinutes = totalSeconds / 60;

            // Compute the current minute in the hour
            long currentMinute = totalMinutes % 60;

            // Obtain the total hours
            long totalHours = totalMinutes / 60 + timeZone;

            // Compute the current hour
            long currentHour = totalHours % 24;

        // Display results
        System.out.println("The current time is " + currentHour + ":"
                + currentMinute + ":" + currentSecond + " GMT");
    }
}
```

# 2.9

```java
import java.util.*;

public class ShowCurrentTime {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read v0, v1 and t
        System.out.print("Enter v0, v1, and t: ");
        double v0 = input.nextDouble();
        double v1 = input.nextDouble();
        double t = input.nextDouble();

        //Compute the average acceleration
        double a = (v1 - v0) / t;

        // Display results
        System.out.println("The average acceleration is " + a);
    }
}
```

# 2.10

```java
import java.util.*;

public class CalculatingEnergy {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read M, finalTemperature, and initialTemperature
        System.out.print("Enter the amount of water in kilograms: ");
        double M = input.nextDouble();
        System.out.print("Enter the initial temperature: ");
        double initialTemperature = input.nextDouble();
        System.out.print("Enter the final temperature: ");
        double finalTemperature = input.nextDouble();

        //Compute Q
        double Q = M * (finalTemperature - initialTemperature) * 4184;

        // Display results
        System.out.println("The energy needed is " + Q);
    }
}
```

# 2.11

```java
import java.util.*;

public class PopulationProjection {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read the number of years
        System.out.print("Enter the number of years: ");
        int years = input.nextInt();

        //Compute the population
        long currentPopulation = 312032486;
        int secondsInAYear = 365 * 24 * 60 * 60;
        double growthInAYear = secondsInAYear / 7.0 + secondsInAYear / 45.0 - secondsInAYear / 13.0;
        long population = (long)(currentPopulation + growthInAYear * years);

        // Display results
        System.out.println("The population in " + years + " years is " + population);
    }
}
```

# 2.12

```java
import java.util.*;

public class PopulationProjection {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read the speed and acceleration
        System.out.print("Enter speed and acceleration: ");
        double v = input.nextDouble();
        double a = input.nextDouble();

        //Compute the length
        double length = v * v / (2 * a);

        // Display results
        System.out.println("The minimum runway length for this airplane is " + length);
    }
}
```

# 2.13

```java
import java.util.*;

public class CompoundValue {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read the monthly saving amount
        System.out.print("Enter the monthly saving amount: ");
        double msa = input.nextDouble();

        //Compute the length
        double accountValue = 0;
        for(int i = 0; i < 6; i++)
            accountValue = (msa + accountValue) * (1 + 0.00417);

        // Display results
        System.out.println("After the sixth month, the account value is $" + accountValue);
    }
}
```

# 2.14

```java
import java.util.*;

public class BMI {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read the weight and height
        System.out.print("Enter weight in pounds: ");
        double weightPounds = input.nextDouble();
        System.out.print("Enter height in inches: ");
        double heightInches = input.nextDouble();

        //convert weight and height
        double weightKilos = weightPounds * 0.45359237;
        double heightMeters = heightInches * 0.0254;
        //Compute BMI
        double bmi = weightKilos / (heightMeters * heightMeters);

        // Display results
        System.out.println("BMI is " + bmi);
    }
}
```

# 2.15

```java
import java.util.*;

public class DistanceOfTwoPoints {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read points
        System.out.print("Enter x1 and y1: ");
        double x1 = input.nextDouble();
        double y1 = input.nextDouble();
        System.out.print("Enter x2 and y2: ");
        double x2 = input.nextDouble();
        double y2 = input.nextDouble();

        //Compute the distance
        double distance = Math.pow((Math.pow((x2 - x1), 2) + Math.pow((y2 - y1), 2)), 0.5);

        // Display results
        System.out.println("The distance between the two points is " + distance);
    }
}
```

# 2.16

```java
import java.util.*;

public class AreaHexagon {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read the length of a side
        System.out.print("Enter the length of the side: ");
        double length = input.nextDouble();

        //Compute the area
        double area = 3 * Math.pow(3, 0.5) / 2 * Math.pow(length, 2);

        // Display results
        System.out.println("The area of the hexagon is " + area);
    }
}
```

# 2.17

```java
import java.util.*;

public class WindChillTemperature {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read the temperature and wind speed
        System.out.print("Enter the temperature in Fahrenheit between -58F and 41F: ");
        double ta = input.nextDouble();
        System.out.print("Enter the wind speed (>= 2) in miles per hour: ");
        double v = input.nextDouble();

        //Compute the wind chill index
        double twc = 35.74 + 0.6215 * ta - 35.75 * Math.pow(v, 0.16) + 0.4275 * ta * Math.pow(v, 0.16);

        // Display results
        System.out.println("The wind chill index is " + twc);
    }
}
```

# 2.18

```javascript
public class WindChillTemperature {
    public static void main(String[] args) {
        System.out.println("a    b    pow(a, b)");
        for(int i = 1; i <= 5; i++)
            System.out.println(i + "    " + (i + 1) + "    " + (int)(Math.pow(i, i + 1)));
    }
}
```

# 2.19

```java
import java.util.*;

public class AreaTriangle {
    public static void main(String[] args) {
        Scanner gym = new Scanner(System.in);
        //Read three points
        System.out.print("Enter the coordinates of three points separated by spaces like x1 y1 x2 y2 x3 y3: ");
        double x1 = gym.nextDouble();
        double y1 = gym.nextDouble();
        double x2 = gym.nextDouble();
        double y2 = gym.nextDouble();
        double x3 = gym.nextDouble();
        double y3 = gym.nextDouble();

        //Compute the area
        double side1 = Math.pow((Math.pow((x2 - x1), 2) + Math.pow((y2 - y1), 2)), 0.5);
        double side2 = Math.pow((Math.pow((x3 - x1), 2) + Math.pow((y3 - y1), 2)), 0.5);
        double side3 = Math.pow((Math.pow((x2 - x3), 2) + Math.pow((y2 - y3), 2)), 0.5);
        double s = (side1 + side2 + side3) / 2;
        double area = Math.pow((s * (s - side1) * (s - side2) * (s - side3)), 0.5);

        //Display the result
        System.out.println("The area of the triangle is " + area);
    }
}
```

# 2.20

```java
import java.util.*;

public class AreaTriangle {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read balance and interest rate
        System.out.print("Enter balance and interest rate (e.g., 3 for 3%): ");
        double balance = input.nextDouble();
        double annualInterestRate = input.nextDouble();

        //Compute the interest
        double interest = balance * (annualInterestRate / 1200);

        //Display the result
        System.out.println("The interest is " + interest);
    }
}
```

# 2.21

```java
import java.util.*;

public class FutureInvestmentValue {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //Read investment amount, annual interest rate, and number of years
        System.out.print("Enter investment amount: ");
        double investmentAmount = input.nextDouble();
        System.out.print("Enter annual interest rate in percentage: ");
        double annualInterestRate = input.nextDouble() / 100;
        System.out.print("Enter number of years: ");
        double numberOfYears = input.nextDouble();

        //Compute the interest
        double monthlyInterestRate = annualInterestRate / 12;
        double futureInvestmentValue = investmentAmount * Math.pow((1 + monthlyInterestRate), numberOfYears * 12);

        //Display the result
        System.out.println("Future value is $" + futureInvestmentValue);
    }
}
```

# 2.22

```java
import java.util.Scanner;

public class ComputeChange {
    public static void main(String[] args) {
        // Create a Scanner
        Scanner input = new Scanner(System.in);

        // Receive the amount
        System.out.print(
                "Enter an amount in int, for example 1156: ");
        int amount = input.nextInt();

        int remainingAmount = amount;

        // Find the number of one dollars
        int numberOfOneDollars = remainingAmount / 100;
        remainingAmount = remainingAmount % 100;

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
        System.out.println("Your amount " + amount / 100.0 + " consists of");
        System.out.println("    " + numberOfOneDollars + " dollars");
        System.out.println("    " + numberOfQuarters + " quarters ");
        System.out.println("    " + numberOfDimes + " dimes");
        System.out.println("    " + numberOfNickels + " nickels");
        System.out.println("    " + numberOfPennies + " pennies");
    }
}
```

# 2.23

```java
import java.util.Scanner;

public class ComputeChange {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        // Read the distance, fuel efficiency and the price per gallon
        System.out.print("Enter the driving distance: ");
        double distance = input.nextDouble();
        System.out.print("Enter miles per gallon: ");
        double milesPerGallon = input.nextDouble();
        System.out.print("Enter price per gallon: ");
        double pricePerGallon = input.nextDouble();

        // Compute the cost
        double cost = distance / milesPerGallon * pricePerGallon;

        // Display the result
        System.out.println("The cost of driving is $" + cost);
    }
}
```

