# 3.1

```java
import java.util.Scanner;

public class QuadraticEquations {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a, b, c
        System.out.println("Enter a, b, c: ");
        double a = input.nextDouble();
        double b = input.nextDouble();
        double c = input.nextDouble();

        //compute the discriminant
        double discriminant = Math.pow(b, 2) - 4 * a * c;
        //judge the discriminant
        if(Math.abs(discriminant - 0) < 1e-14)
            System.out.println("The equation has one root " + (-b / (2 * a)));
        else if(discriminant > 0)
            System.out.println("The equation has two roots " + ((-b + Math.sqrt(discriminant)) / (2 * a)) + " and " + ((-b - Math.sqrt(discriminant)) / (2 * a)));
        else
            System.out.println("The equation has no real roots");
    }
}
```



# 3.2

```java
import java.util.Scanner;

public class AddThreeNumbers {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //generate 3 integers
        int number1 = (int)(Math.random() * 10);
        int number2 = (int)(Math.random() * 10);
        int number3 = (int)(Math.random() * 10);

        //read the sum
        System.out.println("What is " + number1 + " + " + number2 + " + " + number3 + "?");
        int answer = input.nextInt();

        //display the result
        System.out.println(number1 + " + " + number2 + " + " + number3 + " = " + answer + " is " + (number1 + number2 + number3 == answer));
    }
}
```

# 3.3

```java
import java.util.Scanner;

public class LinearEquations {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a, b, c, d, e, f
        System.out.println("Enter a, b, c, d, e, f: ");
        double a = input.nextDouble();
        double b = input.nextDouble();
        double c = input.nextDouble();
        double d = input.nextDouble();
        double e = input.nextDouble();
        double f = input.nextDouble();

        //compute the discriminant
        double discriminant = a * d - b * c;
        //judge the discriminant
        if(Math.abs(discriminant - 0) < 1e-14)
            System.out.println("The equation has no solution");
        else {
            double x = (e * d - b * f) / discriminant;
            double y = (a * f - e * c) / discriminant;
            System.out.println("x is " + x + " and y is " + y);
        }
    }
}
```

# 3.4

```java
import java.util.Scanner;

public class RandomMonth {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //generate an integer
        int month = (int)(Math.random() * 12 + 1);

        System.out.print("Month " + month + " is ");
        //judge the month
        switch(month) {
            case 1: System.out.println("January"); break;
            case 2: System.out.println("February"); break;
            case 3: System.out.println("March"); break;
            case 4: System.out.println("April"); break;
            case 5: System.out.println("May"); break;
            case 6: System.out.println("June"); break;
            case 7: System.out.println("July"); break;
            case 8: System.out.println("August"); break;
            case 9: System.out.println("September"); break;
            case 10: System.out.println("October"); break;
            case 11: System.out.println("November"); break;
            case 12: System.out.println("December"); break;
        }
    }
}
```

# 3.5

```java
import java.util.Scanner;

public class FindFutureDays {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter today's day: ");
        int today = input.nextInt();
        System.out.print("Enter the number of days elapsed since today: ");
        int numberOfDays = input.nextInt();

        System.out.print("Today is ");
        //judge today
        switch(today) {
            case 0: System.out.print("Sunday"); break;
            case 1: System.out.print("Monday"); break;
            case 2: System.out.print("Tuesday"); break;
            case 3: System.out.print("Wednesday"); break;
            case 4: System.out.print("Thursday"); break;
            case 5: System.out.print("Friday"); break;
            case 6: System.out.print("Saturday"); break;
        }

        //compute the future day
        int futureDay = (today + numberOfDays) % 7;

        System.out.print(" and the future day is ");
        //judge the day
        switch(futureDay) {
            case 0: System.out.print("Sunday"); break;
            case 1: System.out.print("Monday"); break;
            case 2: System.out.print("Tuesday"); break;
            case 3: System.out.print("Wednesday"); break;
            case 4: System.out.print("Thursday"); break;
            case 5: System.out.print("Friday"); break;
            case 6: System.out.print("Saturday"); break;
        }
    }
}
```

# 3.6

```java
import java.util.Scanner;

public class BMI {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter weight in pounds: ");
        double weightPounds = input.nextDouble();
        System.out.print("Enter feet: ");
        int feet = input.nextInt();
        System.out.print("Enter inches: ");
        int inches = input.nextInt();

        //compute BMI
        double weightKilos = weightPounds * 0.45359237;
        double heightMeters = (feet * 12 + inches) * 0.0254;
        double bmi = weightKilos / Math.pow(heightMeters, 2);

        //display the result
        System.out.println("BMI is " + bmi);
        if (bmi < 18.5)
            System.out.println("Underweight");
        else if (bmi < 25)
            System.out.println("Normal");
        else if (bmi < 30)
            System.out.println("Overweight");
        else
            System.out.println("Obese");
    }
}
```

# 3.7

```java
import java.util.Scanner;

public class ComputeChange {
    public static void main(String[] args) {
        // Create a Scanner
        Scanner input = new Scanner(System.in);

        // Receive the amount
        System.out.print(
                "Enter an amount in int, for example 1156(for 11 dollars and 56 cents): ");
        int amount = input.nextInt();

        int remainingAmount = amount;

        // Find the number of dollars
        int numberOfDollars = remainingAmount / 100;
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
        System.out.println("Your amount " + amount + " consists of");
        if(numberOfDollars > 0) {
            if(numberOfDollars == 1)
                System.out.println("    " + 1 + " dollar");
            else
                System.out.println("    " + numberOfDollars + " dollars");
        }
        if(numberOfQuarters > 0) {
            if(numberOfQuarters == 1)
                System.out.println("    " + 1 + " quarter");
            else
                System.out.println("    " + numberOfQuarters + " quarters");
        }
        if(numberOfDimes > 0) {
            if(numberOfDimes == 1)
                System.out.println("    " + 1 + " dime");
            else
                System.out.println("    " + numberOfDimes + " dimes");
        }
        if(numberOfNickels > 0) {
            if(numberOfNickels == 1)
                System.out.println("    " + 1 + " nickel");
            else
                System.out.println("    " + numberOfNickels + " nickels");
        }
        if(numberOfPennies > 0) {
            if(numberOfPennies == 1)
                System.out.println("    " + 1 + " penny");
            else
                System.out.println("    " + numberOfPennies + " pennies");
        }
    }
}
```

# 3.8

```java
import java.util.Scanner;

public class SortThreeIntegers {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read 3 integers
        System.out.print("Enter 3 integers: ");
        int num1 = input.nextInt();
        int num2 = input.nextInt();
        int num3 = input.nextInt();

        //sort
        int temp = 0;
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

        //display the result
        System.out.println(num1 + " " + num2 + " " + num3);
    }
}
```

# 3.9

```java
import java.util.Scanner;

public class ISBN {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read the first 9 digits of an ISBN
        System.out.print("Enter the first 9 digits of an ISBN as an integer: ");
        int src = input.nextInt();

        //compute the 10th digit
        int sum = 0;
        int remaining = src;
        for(int i = 9; i > 0; i--) {
            sum += src % 10 * i;
            src /= 10;
        }
        int digit10 = sum % 11;

        //display the result
        System.out.printf("The ISBN-10 number is %09d", remaining);
        if(digit10 == 10)
            System.out.println('X');
        else
            System.out.println(digit10);
    }
}
```

# 3.10

```java
import java.util.Scanner;

public class AdditionQuiz {
    public static void main(String[] args) {
        // 1. Generate two random single-digit integers
        int number1 = (int)(Math.random() * 100);
        int number2 = (int)(Math.random() * 100);

        // 2. Prompt the student to answer "what is number1 + number2?"
        System.out.print
                ("What is " + number1 + " + " + number2 + "? ");
        Scanner input = new Scanner(System.in);
        int answer = input.nextInt();

        // 3. Grade the answer and display the result
        if (number1 + number2 == answer)
            System.out.println("You are correct!");
        else
            System.out.println("Your answer is wrong.\n" + number1 + " + "
                    + number2 + " should be " + (number1 + number2));
    }
}
```

# 3.11

```java
import java.util.Scanner;

public class DaysInMonth {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read the month and year
        System.out.print("Enter the month:");
        int month = input.nextInt();
        System.out.print("Enter the year:");
        int year = input.nextInt();

        //judge the year
        String monthName = "";
        int monthDays = 0;
        if(month == 2) {
            monthName = "February";
            if(year % 4 == 0 && year % 100 != 0 || year % 400 == 0)
                monthDays = 29;
            else
                monthDays = 28;
        }
        else {
            switch(month) {
                case 1: monthName = "January"; monthDays = 31; break;
                case 3: monthName = "March"; monthDays = 31; break;
                case 4: monthName = "April"; monthDays = 30; break;
                case 5: monthName = "May"; monthDays = 31; break;
                case 6: monthName = "June"; monthDays = 30; break;
                case 7: monthName = "July"; monthDays = 31; break;
                case 8: monthName = "August"; monthDays = 31; break;
                case 9: monthName = "September"; monthDays = 30; break;
                case 10: monthName = "October"; monthDays = 31; break;
                case 11: monthName = "November"; monthDays = 30; break;
                case 12: monthName = "December"; monthDays = 31; break;
            }
        }

        //display the result
        System.out.print(monthName + " " + year + " has " + monthDays + " days.");
    }
}
```

# 3.12

```java
import java.util.Scanner;

public class PalindromeInteger {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a three_digit integer
        System.out.print("Enter a three_digit integer:");
        int src = input.nextInt();

        int remaining = src;
        if(remaining < 0)
            remaining = -remaining;
        //compute the reversed number
        int dest = 0;
        int temp = 0;
        for(int i = 2; i >= 0; i--) {
            temp = remaining % 10;
            for(int j = 0; j < i; j++)
                temp *= 10;
            dest += temp;
            remaining /= 10;
        }

        //display the result
        if(src == dest || src == -dest)
            System.out.println(src + " is a palindrome");
        else
            System.out.println(src + " is not a palindrome");
    }
}
```

# 3.14

```java
import java.util.Scanner;

public class Guess {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read the guess
        System.out.print("Enter your guess (0 or 1): ");
        int guess = input.nextInt();

        //generate an integer
        int answer = (int)(Math.random() + 0.5);

        // Display the result
        if(guess == answer)
            System.out.println("your guess is " + guess + ", the answer is " + answer + ", you are right");
        else
            System.out.println("your guess is " + guess + ", the answer is " + answer + ", you are wrong");
    }
}
```

# 3.15

```java
import java.util.Scanner;

public class Lottery {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //generate a lottery
        int lottery = (int)(Math.random() * 1000);
        int temp = lottery;
        int lotteryDigit1 = temp % 10;
        temp /= 10;
        int lotteryDigit2 = temp % 10;
        temp /= 10;
        int lotteryDigit3 = temp % 10;

        //read the guess
        System.out.print("Enter your guess (a three digit integer): ");
        int guess = input.nextInt();
        temp = guess;
        int guessDigit1 = temp % 10;
        temp /= 10;
        int guessDigit2 = temp % 10;
        temp /= 10;
        int guessDigit3 = temp % 10;

        System.out.printf("%d %d %d\n", lotteryDigit1, lotteryDigit2, lotteryDigit3);
        //display the result
        if(guess == lottery)
            System.out.println("Exact match: you win $10,000");
        else if(guessDigit1 == lotteryDigit1 && guessDigit2 == lotteryDigit2 && guessDigit3 == lotteryDigit3 ||
        guessDigit1 == lotteryDigit1 && guessDigit2 == lotteryDigit3 && guessDigit3 == lotteryDigit2 ||
        guessDigit1 == lotteryDigit2 && guessDigit2 == lotteryDigit1 && guessDigit3 == lotteryDigit3 ||
        guessDigit1 == lotteryDigit2 && guessDigit3 == lotteryDigit3 && guessDigit3 == lotteryDigit1 ||
        guessDigit1 == lotteryDigit3 && guessDigit2 == lotteryDigit1 && guessDigit3 == lotteryDigit2 ||
        guessDigit1 == lotteryDigit3 && guessDigit2 == lotteryDigit2 && guessDigit3 == lotteryDigit1)
            System.out.println("Match all digits: you win $3,000");
        else if(guessDigit1 == lotteryDigit1 || guessDigit1 == lotteryDigit2 || guessDigit1 == lotteryDigit3 ||
        guessDigit2 == lotteryDigit1 || guessDigit2 == lotteryDigit2 || guessDigit2 == lotteryDigit3 ||
        guessDigit3 == lotteryDigit1 || guessDigit3 == lotteryDigit2 || guessDigit3 == lotteryDigit3)
            System.out.println("Match at least one digit: you win 1,000");
        else
            System.out.println("Sorry, no match");
    }
}
```

# 3.17

```java
import java.util.Scanner;

public class Game {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //generate a computer move
        int computerMove = (int)(Math.random() * 3);

        //read the player move
        System.out.print("scissor(0), rock(1), paper(2): ");
        int playerMove = input.nextInt();

        //display the result
        String computer = "";
        switch(computerMove) {
            case 0: computer = "scissor"; break;
            case 1: computer = "rock"; break;
            case 2: computer = "paper"; break;
        }
        String player = "";
        switch(playerMove) {
            case 0: player = "scissor"; break;
            case 1: player = "rock"; break;
            case 2: player = "paper"; break;
        }
        if(computerMove == playerMove)
            System.out.println("The computer is " + computer + ". You are " + player + "too. It is a draw");
        else if((playerMove - computerMove) == 1 || (playerMove - computerMove) == -2)
            System.out.println("The computer is " + computer + ", You are " + player + ". You won");
        else
            System.out.println("The computer is " + computer + ", You are " + player + ". You lose");
    }
}
```

# 3.18

```java
import java.util.Scanner;

public class Game {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read the weight
        System.out.print("Enter the weight: ");
        double w = input.nextDouble();

        //judge the input
        if(w < 1e-14)
            System.out.println("Invalid input");
        else if(w > 20)
            System.out.println("The package cannot be shipped");
        else {
            double cost = 0;
            if(w > 10) {
                cost += (w - 10) * 10.5;
                w -= 10;
            }
            if(w > 3) {
                cost += (w - 3) * 8.5;
                w -= 7;
            }
            if(w > 1) {
                cost += (w - 1) * 5.5;
                w -= 2;
            }
            cost += w * 3.5;
            System.out.println("The shipping cost is " + cost);
        }
    }
}
```

# 3.19

```java
import java.util.Scanner;

public class PerimeterTriangle {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read 3 edges
        System.out.print("Enter 3 edges: ");
        double edge1 = input.nextDouble();
        double edge2 = input.nextDouble();
        double edge3 = input.nextDouble();

        //judge the input
        final double epsilon = 1e-14;
        if(edge1 < epsilon || edge2 < epsilon || edge3 < epsilon)
            System.out.println("The input is invalid");
        else {
            if(edge1 + edge2 > edge3 && edge1 + edge3 > edge2 && edge2 +edge3 > edge1)
                System.out.println("The perimeter of the triangle is " + (edge1 + edge2 + edge3));
            else
                System.out.println("The input is invalid");
        }
    }
}
```

# 3.20

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

        //judge the input
        if(ta < -58 || ta > 41 || v < 2) {
            if(ta < -58 || ta > 41)
                System.out.println("The temperature is invalid");
            else 
                System.out.println("The wind speed is invalid");
        }
        else {
            //Compute the wind chill index
            double twc = 35.74 + 0.6215 * ta - 35.75 * Math.pow(v, 0.16) + 0.4275 * ta * Math.pow(v, 0.16);
            
            // Display results
            System.out.println("The wind chill index is " + twc);

        }
    }
}
```

# 3.21

```java
import java.util.*;

public class DayOfWeek {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter year: (e.g., 2012): ");
        int year = input.nextInt();
        System.out.print("Enter month: 1-12: ");
        int month = input.nextInt();
        System.out.print("Enter the day of the month: 1-31: ");
        int dayOfMonth = input.nextInt();

        //judge the input
        if(month <= 2) {
            month += 12;
            year--;
        }

        //compute the day of week
        int k = year % 100;
        int j = year / 100;
        int dayOfWeek = (dayOfMonth + 26 * (month + 1) / 10 + k + k / 4 + j / 4 + 5 * j) % 7;

        //display the result
        String result = "";
        switch(dayOfWeek) {
            case 0: result = "Saturday"; break;
            case 1: result = "Sunday"; break;
            case 2: result = "Monday"; break;
            case 3: result = "Tuesday"; break;
            case 4: result = "Wednesday"; break;
            case 5: result = "Thursday"; break;
            case 6: result = "Friday"; break;
        }
        System.out.print("Day of the week is " + result);
    }
}
```

# 3.22

```java
import java.util.*;

public class PointsInACircle {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a point
        System.out.print("Enter a point with two coordinates: ");
        double x = input.nextDouble();
        double y = input.nextDouble();

        //compute the distance
        double distance = Math.sqrt(Math.pow(x, 2) + Math.pow(y, 2));

        //display the result
        if(distance > 10)
            System.out.print("Point (" + x + ", " + y + ") is not in the circle");
        else
            System.out.print("Point (" + x + ", " + y + ") is in the circle");
    }
}
```

# 3.23

```java
import java.util.*;

public class PointsInARectangle {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a point
        System.out.print("Enter a point with two coordinates: ");
        double x = input.nextDouble();
        double y = input.nextDouble();

        //display the result
        if(x < -5 || x > 5 || y < -2.5 || y > 2.5)
            System.out.print("Point (" + x + ", " + y + ") is not in the rectangle");
        else
            System.out.print("Point (" + x + ", " + y + ") is in the rectangle");
    }
}
```

# 3.24

```java
import java.util.*;

public class PickACard {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //generate the rank and the suit
        int rank = (int)(Math.random() * 13 + 1);
        int suit = (int)(Math.random() * 4);

        //display the result
        String rankName = "";
        switch(rank) {
            case 1: rankName = "Ace"; break;
            case 2: rankName = "2"; break;
            case 3: rankName = "3"; break;
            case 4: rankName = "4"; break;
            case 5: rankName = "5"; break;
            case 6: rankName = "6"; break;
            case 7: rankName = "7"; break;
            case 8: rankName = "8"; break;
            case 9: rankName = "9"; break;
            case 10: rankName = "10"; break;
            case 11: rankName = "Jack"; break;
            case 12: rankName = "Queen"; break;
            case 13: rankName = "King"; break;
        }
        String suitName = "";
        switch(suit) {
            case 0: suitName = "Clubs"; break;
            case 1: suitName = "Diamonds"; break;
            case 2: suitName = "Hearts"; break;
            case 3: suitName = "Spades"; break;
        }
        System.out.print("The card you picked is " + rankName + " of " + suitName);
    }
}
```

# 3.25

```java
import java.util.*;

public class IntersectingPoint {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read four points
        System.out.print("Enter x1, y1, x2, y2, x3, y3, x4, y4: ");
        double x1 = input.nextDouble();
        double y1 = input.nextDouble();
        double x2 = input.nextDouble();
        double y2 = input.nextDouble();
        double x3 = input.nextDouble();
        double y3 = input.nextDouble();
        double x4 = input.nextDouble();
        double y4 = input.nextDouble();

        //compute
        double a = y1 - y2;
        double b = -(x1 - x2);
        double c = y3 - y4;
        double d = -(x3 - x4);
        double e = (y1 - y2) * x1 - (x1 - x2) * y1;
        double f = (y3 - y4) * x3 - (x3 - x4) * y3;

        if(Math.abs(a * d - b * c) < 1e-14)
            System.out.println("The two lines are parallel");
        else {
            double x = (e * d - b * f) / (a * d - b * c);
            double y = (a * f - e * c) / (a * d - b * c);
            System.out.println("The intersecting point is at (" + x + ", " + y);
        }
    }
}
```

# 3.26

```java
import java.util.*;

public class IntersectingPoint {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read an integer
        System.out.print("Enter an integer: ");
        int number = input.nextInt();

        //compute
        Boolean judgeA = number % 5 == 0;
        Boolean judgeB = number % 6 == 0;

        //display the result
        System.out.println("Is " + number + " divisible by 5 and 6? " + (judgeA && judgeB));
        System.out.println("Is " + number + " divisible by 5 or 6? " + (judgeA || judgeB));
        System.out.println("Is " + number + " divisible by 5 or 6, but not both? " + (judgeA ^ judgeB));
    }
}
```

# 3.27

```java
import java.util.*;

public class PointsInTriangle {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a point
        System.out.print("Enter a point's x- and y- coordinates: ");
        double x = input.nextDouble();
        double y = input.nextDouble();

        if(x < 0 || x > 200)
            System.out.println("The point is not in the triangle");
        else {
            double realY = 100 - 0.5 * x;
            if(y > realY || y < 0)
                System.out.println("The point is not in the triangle");
            else
                System.out.println("The point is in the triangle");
        }
    }
}
```

# 3.28

```java
import java.util.*;

public class TwoRectangles {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter r1's x-, y-coordinates, width, and height: ");
        double x1 = input.nextDouble();
        double y1 = input.nextDouble();
        double width1 = input.nextDouble();
        double height1 = input.nextDouble();

        System.out.print("Enter r2's x-, y-coordinates, width, and height: ");
        double x2 = input.nextDouble();
        double y2 = input.nextDouble();
        double width2 = input.nextDouble();
        double height2 = input.nextDouble();

        //compute the limit of 2 rectangles
        double left1 = x1 - width1 / 2;
        double right1 = x1 + width1 / 2;
        double top1 = y1 + height1 / 2;
        double bottom1 = y1 - height1 / 2;
        double left2 = x2 - width2 / 2;
        double right2 = x2 + width2 / 2;
        double top2 = y2 + height2 / 2;
        double bottom2 = y2 - height2 / 2;

        //judgeA: inside or overlap
        //judgeB: overlap or not
        if(left1 <= left2 && right1 >= right2 && bottom1 <= bottom2 && top1 >= top2)
            System.out.println("r2 is inside r1");
        else if(bottom2 >= top1 || left2 >= right1 || top2 <= bottom1 || right2 <= left1)
            System.out.println("r2 does not overlap r1");
        else
            System.out.println("r2 overlaps r1");
    }
}
```

# 3.29

```java
import java.util.*;

public class TwoCircles {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter circle1's x-, y-coordinates, and radius: ");
        double x1 = input.nextDouble();
        double y1 = input.nextDouble();
        double radius1 = input.nextDouble();

        System.out.print("Enter circle2's x-, y-coordinates, and radius: ");
        double x2 = input.nextDouble();
        double y2 = input.nextDouble();
        double radius2 = input.nextDouble();

        //compute the distance
        double distance = Math.sqrt(Math.pow((x2 - x1), 2) + Math.pow((y2 - y1), 2));

        //display the result
        if(distance < Math.abs(radius1 - radius2)) {
            if (radius1 > radius2)
                System.out.println("circle2 is inside circle1");
            else
                System.out.println("circle1 is inside circle2");
        }
        else if(distance > radius2 + radius1)
            System.out.println("circle2 does not overlap circle1");
        else
            System.out.println("circle2 overlaps circle1");
    }
}
```

# 3.30

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
        if(currentHour < 13)
            System.out.println("The current time is " + currentHour + ":" + currentMinute + ":" + currentSecond + " AM");
        else
            System.out.println("The current time is " + (currentHour - 12) + ":" + currentMinute + ":" + currentSecond + " PM");
    }
}
```

# 3.31

```java
import java.util.*;

public class CurrencyExchange {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter the exchange rate from dollars to RMB: ");
        double rate = input.nextDouble();
        System.out.print("Enter 0 to convert dollars to RMB and 1 vice versa: ");
        int conversion = input.nextInt();
        if(conversion == 0) {
            System.out.print("Enter the dollar amount: ");
            double dollar = input.nextDouble();
            System.out.println("$" + dollar + " is " + (dollar * rate) + " yuan");
        }
        else {
            System.out.print("Enter the RMB amount: ");
            double yuan = input.nextDouble();
            System.out.println(yuan + " yuan is $" + (yuan / rate));
        }
    }
}
```

# 3.32

```java
import java.util.*;

public class PointPosition {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter three points for p0, p1, and p2: ");
        double x0 = input.nextDouble();
        double y0 = input.nextDouble();
        double x1 = input.nextDouble();
        double y1 = input.nextDouble();
        double x2 = input.nextDouble();
        double y2 = input.nextDouble();

        //compute
        double result = (x1 - x0) * (y2 - y0) - (x2 - x0) * (y1 - y0);

        //display the result
        if(Math.abs(result) < 1e-14)
            System.out.println("p2 is on the same line");
        else if(result > 0)
            System.out.println("p2 is on the left side of the line");
        else
            System.out.println("p2 is on the right side of the line");
    }
}
```

# 3.33

```java
import java.util.*;

public class PointPosition {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter weight and price for package1: ");
        double weight1 = input.nextDouble();
        double price1 = input.nextDouble();
        System.out.print("Enter weight and price for package2: ");
        double weight2 = input.nextDouble();
        double price2 = input.nextDouble();

        //compute
        double pricePerWeight1 = price1 / weight1;
        double pricePerWeight2 = price2 / weight2;

        //display the result
        if(Math.abs(pricePerWeight1 - pricePerWeight2) < 1e-14)
            System.out.println("Two packages have the same price.");
        else if(pricePerWeight1 > pricePerWeight2)
            System.out.println("Package 2 has a better price.");
        else
            System.out.println("Package 1 has a better price.");
    }
}
```

# 3.34

```java
import java.util.*;

public class PointOnLineSegment {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter three points for p0, p1, and p2: ");
        double x0 = input.nextDouble();
        double y0 = input.nextDouble();
        double x1 = input.nextDouble();
        double y1 = input.nextDouble();
        double x2 = input.nextDouble();
        double y2 = input.nextDouble();

        //compute
        double result = (x1 - x0) * (y2 - y0) - (x2 - x0) * (y1 - y0);

        //display the result
        if(Math.abs(result) < 1e-14 && (x0 <= x2 && x2 <= x1 || x1 <= x2 && x2 <= x0))
            System.out.printf("(%f, %f) is on the line segment from (%f, %f) to (%f, %f)", x2, y2, x0, y0, x1, y1);
        else
            System.out.printf("(%f, %f) is not on the line segment from (%f, %f) to (%f, %f)", x2, y2, x0, y0, x1, y1);
    }
}
```

