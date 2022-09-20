# 5.1

```java
import java.util.Scanner;

public class Average {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter an integer, the input ends if it is 0: ");
        int positive = 0, negative = 0, sum = 0, i = 0;
        double total = 0;
        while (true) {
            i = input.nextInt();
            if (i == 0)
                break;
            else {
                sum++;
                total += i;
                if (i > 0)
                    positive++;
                else
                    negative++;
            }
        }

        //display the result
        if (sum == 0)
            System.out.println("No numbers are entered except 0");
        else {
            System.out.println("The number of positives is " + positive);
            System.out.println("The number of negatives is " + negative);
            System.out.printf("The total is %.1f\n", total);
            System.out.printf("The average is %.2f\n", total / sum);
        }
    }
}
```

# 5.2

```java
import java.util.Scanner;

public class AdditionQuizLoop {
    public static void main(String[] args) {
        final int NUMBER_OF_QUESTIONS = 10; // Number of questions
        int correctCount = 0; // Count the number of correct answers
        int count = 0; // Count the number of questions
        long startTime = System.currentTimeMillis();
        String output = ""; // output string is initially empty
        Scanner input = new Scanner(System.in);

        while (count < NUMBER_OF_QUESTIONS) {
            //Generate two random integers
            int number1 = (int)(Math.random() * 15 + 1);
            int number2 = (int)(Math.random() * 15 + 1);

            //Prompt the student to answer "What is number1 + number2?"
            System.out.print(
                    "What is " + number1 + " + " + number2 + "? ");
            int answer = input.nextInt();

            //Grade the answer and display the result
            if (number1 + number2 == answer) {
                System.out.println("You are correct!");
                correctCount++;
            }
            else
                System.out.println("Your answer is wrong.\n" + number1
                        + " + " + number2 + " should be " + (number1 + number2));

            // Increase the count
            count++;

            output += "\n" + number1 + "+" + number2 + "=" + answer +
                    ((number1 + number2 == answer) ? " correct" : " wrong");
        }

        long endTime = System.currentTimeMillis();
        long testTime = endTime - startTime;

        System.out.println("Correct count is " + correctCount +
                "\nTest time is " + testTime / 1000.0 + " seconds\n" + output);
    }
}
```

# 5.3

```java
import java.util.Scanner;

public class Conversion {
    public static void main(String[] args) {
        System.out.println("Kilograms     Pounds");
        for(int i = 1; i <= 199; i += 2)
            System.out.printf("%-9d     %6.1f\n", i, i * 2.2);
    }
}
```

# 5.5

```java
import java.util.Scanner;

public class Conversion {
    public static void main(String[] args) {
        System.out.println("Kilograms        Pounds     |    Pounds        Kilograms");
        for(int i = 1, j = 20; i <= 199; i += 2, j += 5)
            System.out.printf("%-9d        %5.1f      |    %-6d        %6.2f\n", i, i * 2.2, j, j / 2.2);
    }
}
```

# 5.7

```java
public class FutureTuition {
    public static void main(String[] args) {
        final int tuitionThisYear = 10000;
        final double tuitionIncrease = 0.05;
        double tuitionAYear = tuitionThisYear, sum = 0;

        for(int i = 0; i < 10; i++)
            tuitionAYear *= 1 + tuitionIncrease;
        System.out.println("The tuition in 10 years is $" + tuitionAYear);
        for(int i = 0; i < 4; i++) {
            sum += tuitionAYear;
            tuitionAYear *= 1 + tuitionIncrease;
        }
        System.out.println("The total cost of four years' worth of tuition starting after the tenth year is $" + sum);
    }
}
```

# 5.8

```java
import java.util.*;

public class HighestScore {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter the number of students: ");
        int number = input.nextInt();
        String name = "", highestName = "";
        int score = 0, highestScore = 0;
        for(int i = 0; i < number; i++) {
            System.out.print("Enter a name and a score: ");
            name = input.next();
            score = input.nextInt();
            if(score > highestScore) {
                highestScore = score;
                highestName = name;
            }
        }
        System.out.println("The highest score is " + highestName + "'s " + highestScore);
    }
}
```

# 5.9

```java
import java.util.*;

public class HighestScore {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter the number of students: ");
        int number = input.nextInt();
        String name = "", highestName = "", secondName = "";
        int score = 0, highestScore = 0, secondScore = 0;

        //initialize the second highest
        System.out.print("Enter a name and a score: ");
        name = input.next();
        score = input.nextInt();
        highestScore = score;
        highestName = name;
        secondScore = score;
        secondName = name;

        for(int i = 0; i < number - 1; i++) {
            System.out.print("Enter a name and a score: ");
            name = input.next();
            score = input.nextInt();
            if(score > highestScore) {
                secondScore = highestScore;
                secondName = highestName;
                highestScore = score;
                highestName = name;
            }
            else if(score > secondScore) {
                secondScore = score;
                secondName = name;
            }
        }
        System.out.println("The highest score is " + highestName + "'s " + highestScore);
        System.out.println("The second highest score is " + secondName + "'s " + secondScore);
    }
}
```

# 5.14

```java
import java.util.*;

public class GCD {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read
        System.out.print("Enter 2 numbers: ");
        int n1 = input.nextInt();
        int n2 = input.nextInt();
        int d = (n1 < n2)? n1 : n2;
        int i = 0;
        for(i = d; i > 0; i--)
            if(n1 % i == 0 && n2 % i == 0)
                break;
        System.out.printf("The gcd is: " + i);
    }
}
```

# 5.15

```java
public class DisplayASCII {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        for(int i = 0; i <= '~' - '!'; i++) {
            System.out.print((char)('!' + i));
            System.out.print((i % 10 == 9)? '\n' : ' ');
        }
    }
}
```

# 5.16

```java
import java.util.*;

public class DisplayASCII {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read an integer
        System.out.print("Enter an integer: ");
        int src = input.nextInt();
        int remaining = src;
        String output = "";

        //find the factors
        for(int i = 2; i <= remaining; i++) {
            if(remaining % i == 0) {
                remaining /= i;
                if(remaining == 1) {
                    output += i + ".";
                    break;
                }
                output += i + ", ";
                i = 1;
                continue;
            }
        }

        //display the result
        System.out.println("The factors of " + src + " is: " + output);
    }
}
```

# 5.17

```java
import java.util.*;

public class DisplayPyramid {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read an integer
        System.out.print("Enter the number of lines: ");
        int lines = input.nextInt();

        //loop for each line
        for(int lineIndex = 1; lineIndex <= lines; lineIndex++) {
            //display the former half
            //display spaces
            for(int spaces = 0; spaces < lines - lineIndex; spaces++)
                System.out.printf("    ");
            for(int numberIndex = lineIndex; numberIndex > 1; numberIndex--)
                System.out.printf("%3d ", numberIndex);

            System.out.printf("%3d", 1);

            //display the latter half
            for(int numberIndex = 2; numberIndex <= lineIndex; numberIndex++)
                System.out.printf(" %3d", numberIndex);
            System.out.printf("\n");
        }
    }
}
```

# 5.18

```java
import java.util.*;

public class DisplayPatterns {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        final int length = 6;

        System.out.println("Pattern A");
        for(int i = 1; i <= length; i++) {
            for (int j = 1; j <= i; j++)
                System.out.printf("%-2d", j);
            System.out.println();
        }

        System.out.println("Pattern B");
        for(int i = length; i >= 1; i--) {
            for (int j = 1; j <= i; j++)
                System.out.printf("%-2d", j);
            System.out.println();
        }

        System.out.println("Pattern C");
        for(int i = 1; i <= length; i++) {
            for(int k = 0; k < length - i; k++)
                System.out.print("  ");
            for (int j = i; j >= 1; j--)
                System.out.printf("%-2d", j);
            System.out.println();
        }

        System.out.println("Pattern D");
        for(int i = length; i >= 1; i--) {
            for(int k = 0; k < length - i; k++)
                System.out.print("  ");
            for (int j = 1; j <= i; j++)
                System.out.printf("%-2d", j);
            System.out.println();
        }
    }
}
```

# 5.19

```java
import java.util.*;

public class DisplayPyramid {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        final int lines = 8;
        int result = 1;
        for(int lineIndex = 1; lineIndex <= lines; lineIndex++) {
            //display the spaces
            for(int spaces = 0; spaces < lines - lineIndex; spaces++)
                System.out.print("    ");
            
            //display the former
            System.out.printf("1");
            for(int i = 1; i < lineIndex; i++) {
                result *= 2;
                System.out.printf("%4d", result);
            }
            
            //display the latter
            for(int i = 1; i < lineIndex; i++) {
                result /= 2;
                System.out.printf("%4d", result);
            }
            result = 1;
            System.out.println();
        }
    }
}
```

# 5.21

```java
import java.util.*;

public class Loan {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read
        System.out.print("Loan Amount: ");
        int loanAmount = input.nextInt();
        System.out.print("Number of Years: ");
        int year = input.nextInt();
        System.out.println();

        //display the result
        double annualInterestRate = 5, totalPayment = 0, monthlyPayment = 0;
        double monthlyInterestRate = annualInterestRate / 1200;
        System.out.println("Interest Rate     Monthly Payment     Total Payment");
        for(int i = 0; i <= 24; i++) {
            monthlyPayment = loanAmount * monthlyInterestRate / (1 - (1 / Math.pow(1 + monthlyInterestRate, year * 12)));
            totalPayment = monthlyPayment * year * 12;
            System.out.printf("%-5.3f%%            %-6.2f              %-8.2f\n", annualInterestRate, monthlyPayment, totalPayment);
            annualInterestRate += 0.125;
            monthlyInterestRate = annualInterestRate / 1200;
        }
    }
}
```

# 5.22

```java
import java.util.*;

public class LoanAmortizationSchedule {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read
        System.out.print("Loan Amount: ");
        int loanAmount = input.nextInt();
        System.out.print("Number of Years: ");
        int numberOfYears = input.nextInt();
        System.out.print("Annual Interest Rate: ");
        double annualInterestRate = input.nextDouble();
        System.out.println();

        //compute
        double monthlyInterestRate = annualInterestRate / 1200;
        double monthlyPayment = loanAmount * monthlyInterestRate / (1 - 1 / (Math.pow((1 + monthlyInterestRate), numberOfYears * 12)));
        double totalPayment = monthlyPayment * numberOfYears * 12;
        double balance = 10000, monthlyInterest = 0, principal = 0;

        //display the result
        System.out.printf("%-20s%-20s%-20s%-20s\n", "Payment#", "Interest", "Principal", "Balance");
        for(int i = 1; i <= 12; i++) {
            monthlyInterest = monthlyInterestRate * balance;
            principal = monthlyPayment - monthlyInterest;
            balance -= principal;
            System.out.printf("%-20d%8.2f%21.2f%19.2f\n", i, monthlyInterest, principal, balance);
        }
    }
}
```

# 5.23

```java
import java.util.*;

public class CancellationError {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        final int n = 5000;
        double leftToRight = 0, rightToLeft = 0;

        //compute left to right
        for(int i = 1; i <= n; i++)
            leftToRight += 1.0 / i;

        //compute right to left
        for(int i = n; i >= 1; i--)
            rightToLeft += 1.0 / i;

        //display the result
        System.out.printf("left to right = %.20f\nright to left = %.20f\nthe difference is: %.20f\n", leftToRight, rightToLeft, leftToRight - rightToLeft);
    }
}
```

# 5.24

```java
import java.util.*;

public class SumSeries {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        final int start = 1, end = 99;
        double sum = 0;
        int dividend = start, divisor = dividend + 2;

        //compute
        for(int i = divisor; i <= end; i += 2) {
            sum += (double)dividend / divisor;
            dividend += 2;
            divisor += 2;
        }

        //display the result
        System.out.printf("%f", sum);
    }
}
```

# 5.25

```java
import java.util.*;

public class SumSeries {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //compute pi
        double sum = 0;
        String output = "";
        for(int i = 10000; i <= 100000; i += 10000) {
            for(int j = i; j >= 1; j--) {
                sum += Math.pow(-1, j + 1) / (2 * j - 1);
            }
            output += "for i = " + i + ", pi = " + (sum * 4) + "\n";
            sum = 0;
        }

        //display the result
        System.out.print(output);
    }
}
```

# 5.26

```java
import java.util.*;

public class ComputeE {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //compute e
        double e = 1;
        int item = 1;
        String output = "";
        for(int i = 1; i <= 20; i++) {
            for(int j = 1; j <= i; j++) {
                item *= j;
                e += 1.0 / item;
            }
            output += "for i = " + i + ", e = " + e + "\n";
            e = 1;
            item = 1;
        }

        //display the result
        System.out.print(output);
    }
}
```

# 5.28

```java
import java.util.*;

public class DisplayMonth {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read
        System.out.print("Enter the year: ");
        int year = input.nextInt();
        System.out.print("Enter the first weekday: ");
        int firstWeekday = input.nextInt();
        int month = 1, monthDay = 1, monthDayTotal = 0, day = firstWeekday;
        String output = "", monthName = "", weekdayName = "";

        for(month = 1; month <= 12; month++) {
            switch (month) {
                case 1: monthName = "January"; monthDayTotal = 31; break;
                case 2: monthName = "February"; monthDayTotal = (year % 4 == 0 && year % 100 != 0 || year % 400 == 0)? 29 : 28; break;
                case 3: monthName = "March"; monthDayTotal = 31; break;
                case 4: monthName = "April"; monthDayTotal = 30; break;
                case 5: monthName = "May"; monthDayTotal = 31; break;
                case 6: monthName = "June"; monthDayTotal = 30; break;
                case 7: monthName = "July"; monthDayTotal = 31; break;
                case 8: monthName = "August"; monthDayTotal = 31; break;
                case 9: monthName = "September"; monthDayTotal = 30; break;
                case 10: monthName = "October"; monthDayTotal = 31; break;
                case 11: monthName = "November"; monthDayTotal = 30; break;
                case 12: monthName = "December"; monthDayTotal = 31; break;
            }
            for(int i = 1; i <= monthDayTotal; i++) {
                switch (day % 7) {
                    case 0: weekdayName = "Sunday"; break;
                    case 1: weekdayName = "Monday"; break;
                    case 2: weekdayName = "Tuesday"; break;
                    case 3: weekdayName = "Wednesday"; break;
                    case 4: weekdayName = "Thursday"; break;
                    case 5: weekdayName = "Friday"; break;
                    case 6: weekdayName = "Saturday"; break;
                }
                output += monthName + " " + i + ", " + year + " is " + weekdayName + "\n";
                day++;
            }
        }

        //display the result
        System.out.print(output);
    }
}
```

# 5.29

```java
import java.util.*;

public class DisplayCalendar {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read
        System.out.print("Enter the year: ");
        int year = input.nextInt();
        System.out.print("Enter the first weekday: ");
        int firstWeekday = input.nextInt();
        int month = 1, monthDay = 1, monthDayTotal = 0, day = firstWeekday;
        String output = "", monthName = "", weekdayName = "";

        for(month = 1; month <= 12; month++) {
            //get the month name
            switch (month) {
                case 1: monthName = "January"; monthDayTotal = 31; break;
                case 2: monthName = "February"; monthDayTotal = (year % 4 == 0 && year % 100 != 0 || year % 400 == 0)? 29 : 28; break;
                case 3: monthName = "March"; monthDayTotal = 31; break;
                case 4: monthName = "April"; monthDayTotal = 30; break;
                case 5: monthName = "May"; monthDayTotal = 31; break;
                case 6: monthName = "June"; monthDayTotal = 30; break;
                case 7: monthName = "July"; monthDayTotal = 31; break;
                case 8: monthName = "August"; monthDayTotal = 31; break;
                case 9: monthName = "September"; monthDayTotal = 30; break;
                case 10: monthName = "October"; monthDayTotal = 31; break;
                case 11: monthName = "November"; monthDayTotal = 30; break;
                case 12: monthName = "December"; monthDayTotal = 31; break;
            }

            //print the head of a month calendar
            for(int j = 0; j < 7 * 3; j++)
                System.out.print(' ');
            System.out.println(monthName + " " + year);
            for(int j = 0; j < 7 * 7; j++)
                System.out.print('-');
            System.out.println();
            System.out.println("  Sun    Mon    Tue    Wed    Thu    Fri    Sat  ");

            //print the calendar
            for(int i = 1; i <= monthDayTotal; i++) {
                //look for the start point
                if(i == 1) {
                    for(int j = 0; j < day % 7; j++)
                        for(int k = 0; k < 7; k++)
                            System.out.print(' ');
                }

                //print each day
                System.out.printf("  %3d  ", i);

                //print the next line
                if(day % 7 == 6 || i == monthDayTotal)
                    System.out.println();
                day++;
            }

            //print an empty line after printing a month
            System.out.println();
        }
    }
}
```

# 5.30

```java
import java.util.*;

public class CompoundValue {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read
        System.out.print("Enter an amount: ");
        double amount = input.nextDouble();
        System.out.print("Enter the annual interest rate: ");
        double annualInterestRate = input.nextDouble();
        double monthlyInterestRate = annualInterestRate / 1200;
        System.out.print("Enter the number of months: ");
        int numberOfMonths = input.nextInt();

        //display the result
        double value = 0;
        String output = "";
        for(int i = 1; i <= numberOfMonths; i++) {
            value = (100 + value) * (1 + monthlyInterestRate);
            output += "After month " + i + ", the value in the account becomes " + value + "\n";
        }

        //display the result
        System.out.println(output);
    }
}
```

# 5.33

```java
import java.util.*;

public class PerfectNumber {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        int iDivisor = 0;
        for(int i = 2; i <= 10000; i++) {
            for (int j = 1; j <= i / 2; j++) {
                if (i % j == 0)
                    iDivisor += j;
            }
            if(i == iDivisor)
                System.out.println(i);
            iDivisor = 0;
        }
    }
}
```

# 5.34

```java
import java.util.Scanner;

public class Game {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        int computerMove = 0, playerMove = 0, playerScore = 0, computerScore = 0;
        while(-2 <= (computerScore - playerScore) && (computerScore - playerScore) <= 2) {
            //generate a computer move
            computerMove = (int) (Math.random() * 3);

            //read the player move
            System.out.print("scissor(0), rock(1), paper(2): ");
            playerMove = input.nextInt();

            //display the result
            String computer = "";
            switch (computerMove) {
                case 0:
                    computer = "scissor";
                    break;
                case 1:
                    computer = "rock";
                    break;
                case 2:
                    computer = "paper";
                    break;
            }
            String player = "";
            switch (playerMove) {
                case 0:
                    player = "scissor";
                    break;
                case 1:
                    player = "rock";
                    break;
                case 2:
                    player = "paper";
                    break;
            }
            if (computerMove == playerMove)
                System.out.println("The computer is " + computer + ". You are " + player + " too. It is a draw");
            else if ((playerMove - computerMove) == 1 || (playerMove - computerMove) == -2) {
                System.out.println("The computer is " + computer + ", You are " + player + ". You won");
                playerScore++;
            }
            else {
                System.out.println("The computer is " + computer + ", You are " + player + ". You lose");
                computerScore++;
            }
        }
    }
}
```

# 5.37

```java
import java.util.Scanner;

public class DecimalToBinary {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a decimal integer
        System.out.print("Enter a decimal integer: ");
        int decimal = input.nextInt();

        //convert
        int remaining = decimal, binary = 0, digitIndex = 0, digitNumber = 0, incrementation = 1;
        while(incrementation != 0 || remaining != 0) {
            digitNumber = remaining % 2;
            incrementation = digitNumber;
            for(int i = 0; i < digitIndex; i++)
                incrementation *= 10;
            binary += incrementation;
            digitIndex++;
            remaining /= 2;
        }

        //display the result
        System.out.println(binary);
    }
}
```

# 5.38

```java
import java.util.Scanner;

public class DecimalToOctal {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //read a decimal integer
        System.out.print("Enter a decimal integer: ");
        int decimal = input.nextInt();

        //convert
        String octal = "";
        int digit = 0;
        while(digit != 0 || decimal != 0) {
            digit = decimal % 8;
            octal = digit + octal;
            decimal /= 8;
        }

        //display the result
        System.out.println(octal);
    }
}
```

# 5.39

```java
import java.util.Scanner;

public class SalesAmount {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        final double goal = 30000;
        double amount = 0;
        if(goal <= 400)
            amount = goal / 0.08;
        else if(goal <= 900)
            amount = 5000 + (goal - 400) / 0.1;
        else
            amount = 10000 + (goal - 900) / 0.12;

        //display the result
        System.out.println(amount);
    }
}
```

# 5.40

```java
import java.util.Scanner;

public class HeadsTails {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        final int simulationTimes = 1000000;
        int heads = 0, tails = 0;
        for(int i = 0; i < simulationTimes; i++) {
            if((int)(Math.random() + 0.5) == 1)
                heads++;
            else
                tails++;
        }

        System.out.printf("heads = %d\ntails = %d\n", heads, tails);
    }
}
```

# 5.41

```java
import java.util.Scanner;

public class MaxNumbers {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter numbers: ");
        int number = input.nextInt(), max = number, count = 0;
        while(number != 0) {
            if(number > max) {
                max = number;
                count = 1;
            }
            else if(number == max)
                count++;
            number = input.nextInt();
        }

        //display the result
        System.out.printf("The largest number is %d\n", max);
        System.out.printf("The occurrence count of the largest number is %d\n", count);
    }
}
```

# 5.43

```java
import java.util.Scanner;

public class Combinations {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        int combinations = 0;
        for(int i = 1; i <= 6; i++) {
            for(int j = i + 1; j <= 7; j++) {
                System.out.printf("%d %d\n", i, j);
                combinations++;
            }
        }
        System.out.printf("The total number of all combinations is %d\n", combinations);
    }
}
```

# 5.44

```java
import java.util.Scanner;

public class BitLevelOperations {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read an integer
        System.out.print("Enter an integer: ");
        int decimal = input.nextInt();

        //convert
        if(decimal >= 0) {
            String binary = "";
            int digit = 0;
            for(int i = 0; i < 16; i++) {
                digit = decimal % 2;
                binary = digit + binary;
                decimal /= 2;
            }
            System.out.println("the bits are " + binary);
        }
        else {
            //compute Math.pow(2, 16)
            long negative = 1;
            for(int i = 0; i < 16; i++)
                negative *= 2;
            decimal += negative;
            String binary = "";
            int digit = 0;
            for(int i = 0; i < 16; i++) {
                digit = decimal % 2;
                binary = digit + binary;
                decimal /= 2;
            }
            System.out.println("the bits are " + binary);
        }
    }
}
```

# 5.45

```java
import java.util.Scanner;

public class StandardDeviation {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read
        final int n = 10;
        System.out.printf("Enter %d numbers: ", n);
        double summation1 = 0, summation2 = 0;
        double number = 0;
        for(int i = 0; i < n; i++) {
            number = input.nextDouble();
            summation1 += number;
            summation2 += number * number;
        }

        //compute
        double mean = summation1 / n;
        double deviation = Math.sqrt((summation2 - Math.pow(summation1, 2) / n) / (n - 1));

        //display the result
        System.out.printf("The mean is %f\n", mean);
        System.out.printf("The standard deviation is %f\n", deviation);
    }
}
```

# 5.46

```java
import java.util.Scanner;

public class ReverseString {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        //read
        System.out.print("Enter a string: ");
        String str = input.nextLine();

        //reverse the string
        String output = "";
        int length = str.length();
        for(int i = length - 1; i >= 0; i--)
            output += str.charAt(i);

        //display the reversed string
        System.out.printf("The reversed string is %s\n", output);
    }
}
```

