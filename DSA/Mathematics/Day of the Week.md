```java
class Solution {
    public String dayOfTheWeek(int day, int month, int year) {
        Map<Integer, Integer> months = new HashMap<>();
        months.put(1, 31);
        months.put(3, 31);
        months.put(4, 30);
        months.put(5, 31);
        months.put(6, 30);
        months.put(7, 31);
        months.put(8, 31);
        months.put(9, 30);
        months.put(10, 31);
        months.put(11, 30);
        months.put(12, 31);
        Map<Integer, String> weekDays = new HashMap<>();
        weekDays.put(0, "Thursday");
        weekDays.put(1, "Friday");
        weekDays.put(2, "Saturday");
        weekDays.put(3, "Sunday");
        weekDays.put(4, "Monday");
        weekDays.put(5, "Tuesday");
        weekDays.put(6, "Wednesday");

        int daysInYears = 0;
        for(int i=1971;i<year;i++) {
            daysInYears += isLeapYear(i) ? 366 : 365;
        }
        int daysInMonths = 0;
        for(int i=1;i<month;i++) {
            if(i==2) daysInMonths += isLeapYear(year) ? 29 : 28;
            else daysInMonths += months.get(i);
        }
        int totalDays = daysInYears + daysInMonths + day;
        return weekDays.get(totalDays%7);
    }
    boolean isLeapYear(int i) {
        return (i%400==0 || (i%4==0 && i%100!=0));
    }
}
```

## Better solution, because of using array.

```java
class Solution {
    public boolean isLeapYear(int n)
    {
        if(n % 400 == 0)
        {
            return true;
        }
        if(n % 100 == 0)
        {
            return false;
        }
        if(n % 4 ==0)
        {
            return true;
        }

        return false;
    }

    public String dayOfTheWeek(int day, int month, int year) {
        String days[]  = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};
        int months[] = {31,28,31,30,31,30,31,31,30,31,30,31};


        int totalPassedDays = 0;

        // years
        for(int i = 1971; i < year ; i++)
        {
            if(isLeapYear(i))
            {
                totalPassedDays += 366;
            }
            else
            {
                totalPassedDays += 365;
            }
        }

        // months
        for(int i = 1 ; i < month ; i++)
        {
            if(i==2 && isLeapYear(year))
            {
                totalPassedDays += 29;
            }
            else
            {
                totalPassedDays += months[i-1];
            }
        }

        // curr date
        totalPassedDays += day - 1;

        int idx = (5 + totalPassedDays) % 7;
        return days[idx];
    }
}
```
