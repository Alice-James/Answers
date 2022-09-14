# 1.1

```java
public class Welcome {
    public static void main(String[] args) {
         System.out.println("Welcome to Java\n" + "Welcome to Computer Science\n" + "Programming is fun");
    }
}
```

# 1.2

```java
public class Welcome {
    public static void main(String[] args) {
        for(int i = 1;i <= 5; i++)
            System.out.println("Welcome to Java");
    }
}
```

# 1.3

```java
public class Welcome {
    public static void main(String[] args) {
            System.out.println("      J     A     V     V     A\n" +
                               "      J    A A     V   V     A A\n" +
                               "  J   J   AAAAA     V V     AAAAA\n" +
                               "   J J   A     A     V     A     A");
    }
}
```

# 1.4

```java
public class PrintATable {
    public static void main(String[] args) {
        System.out.println("a      a^2    a^3\n" +
                           "1      1      1\n" +
                           "2      4      8\n" +
                           "3      9      27\n" +
                           "4      16     64");
    }
}
```

# 1.5

```java
public class ComputeExpressions {
    public static void main(String[] args) {
        System.out.println((9.5 * 4.5 - 2.5 * 3) / (45.5 - 3.5));
    }
}
```

# 1.6

```java
public class SummationSeries {
    public static void main(String[] args) {
        System.out.println(1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9);
    }
}
```

# 1.7

```java
public class ApproximatePI {
    public static void main(String[] args) {
        System.out.println(4 * (1.0 - 1.0 / 3 + 1.0 / 5 - 1.0 / 7 + 1.0 / 9 - 1.0 / 11));
        System.out.println(4 * (1.0 - 1.0 / 3 + 1.0 / 5 - 1.0 / 7 + 1.0 / 9 - 1.0 / 11 + 1.0 / 13));
    }
}
```

# 1.8

```java
public class AreaPerimeterCircle {
    public static void main(String[] args) {
        double radius = 5.5;
        double PI = 3.1415926;

        System.out.println(radius * radius * PI);
        System.out.println(2 * radius * PI);
    }
}
```

# 1.9

```java
public class AreaPerimeterRectangle {
    public static void main(String[] args) {
        double width = 4.5;
        double height = 7.9;

        // print area
        System.out.println(width * height);
        // print perimeter
        System.out.println(2 * (width + height));
    }
}
```

# 1.10

```java
public class AverageSpeed {
    public static void main(String[] args) {
        // compute length in miles
        double length_mile = 14.0 / 1.6;
        // compute time in hours
        double time_hour = (30.0 / 60 + 45.0) / 60.0;

        System.out.println(length_mile / time_hour);
    }
}
```

# 1.11

```java
public class PopulationProjection {
    public static void main(String[] args) {
        // compute how many seconds are there in a year
        int seconds = 365 * 24 * 60 * 60;
        // compute population growth per year
        double population_growth = seconds / 7.0 + seconds / 45.0 - seconds / 13.0;

        for(int i = 1; i <= 5; i++)
            System.out.println(312032486 + i * population_growth);
    }
}
```

# 1.12

```java
public class AverageSpeed {
    public static void main(String[] args) {
        System.out.println(24 * 1.6 / (1 + (40.0 + 35.0 / 60) / 60));
    }
}
```

# 1.13

```java
public class Algebra {
    public static void main(String[] args) {
        double a = 3.4, b = 50.2, c = 2.1, d = 0.55, e = 44.5, f = 5.9;

        System.out.println((e * d - b * f) / (a * d - b * c));
        System.out.println((a * f - e * c) / (a * d - b * c));
    }
}
```

