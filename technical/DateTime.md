 List<String> list = new ArrayList<>() {
            {
                add("1000-01-01 00:00:00");
                add("1100-01-01 00:00:00");
                add("1200-01-01 00:00:00");
                add("1300-01-01 00:00:00");
                add("1400-01-01 00:00:00");
                add("1500-01-01 00:00:00");
                add("1600-01-01 00:00:00");
                add("1700-01-01 00:00:00");
                add("1800-01-01 00:00:00");
                add("1900-01-01 00:00:00");
                add("2000-01-01 00:00:00");
                add("2100-01-01 00:00:00");
                /*-30610245208000
-27454571608000
-24298898008000
-21143138008000
-17987464408000
-14831790808000
-11676117208000
-8520357208000
-5364683608000
-2209008070000
946665000000
4102425000000*/
            }
        };

         for (String s : list) {
            LocalDateTime localDateTime = LocalDateTime.parse(s, DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss"));
            System.out.println(localDateTime.atZone(ZoneId.systemDefault()).toInstant().toEpochMilli());
        }

# 

 add("1950-01-01 00:00:00");
                add("1960-01-01 00:00:00");
                add("1970-01-01 00:00:00");
                add("1980-01-01 00:00:00");
                add("1990-01-01 00:00:00");

                -631171800000
-315639000000
-19800000
315513000000
631132200000
-14831790808000

# 

add("1970-01-01 00:00:00");
                add("1971-01-01 00:00:00");
                add("1972-01-01 00:00:00");
                add("1973-01-01 00:00:00");
                add("1974-01-01 00:00:00");
                add("1975-01-01 00:00:00");
                add("1976-01-01 00:00:00");
                add("1977-01-01 00:00:00");
                add("1978-01-01 00:00:00");
                add("1979-01-01 00:00:00");
                add("1980-01-01 00:00:00");
                add("1981-01-01 00:00:00");
                add("1982-01-01 00:00:00");

-19800000
31516200000
63052200000
94674600000
126210600000
157746600000
189282600000
220905000000
252441000000
283977000000
315513000000
347135400000
378671400000

# 

add("1970-01-01 00:00:00");//19800000
                add("1970-01-02 00:00:00");//66600000
                add("1970-01-03 00:00:00");
                add("1970-01-04 00:00:00");
                add("1970-01-05 00:00:00");
                add("1970-01-06 00:00:00");
                add("1970-01-07 00:00:00");
                add("1970-01-08 00:00:00");
                add("1970-01-09 00:00:00");
                add("1970-01-10 00:00:00");
                add("1970-01-11 00:00:00");
                add("1970-01-12 00:00:00");
                add("1970-01-13 00:00:00");

-19800000
66600000
153000000
239400000
325800000
412200000
498600000
585000000
671400000
757800000
844200000
930600000
1017000000

# 

add("1970-01-01 00:00:00");//-19800000
                add("1970-01-01 01:00:00");
                add("1970-01-01 02:00:00");
                add("1970-01-01 03:00:00");
                add("1970-01-01 04:00:00");
                add("1970-01-01 05:00:00");
                add("1970-01-01 06:00:00");
                add("1970-01-01 07:00:00");
                add("1970-01-01 08:00:00");
                add("1970-01-01 09:00:00");
                add("1970-01-01 10:00:00");
                add("1970-01-01 11:00:00");
                add("1970-01-01 12:00:00");

-19800000
-16200000
-12600000
-9000000
-5400000
-1800000
1800000
5400000
9000000
12600000
16200000
19800000
23400000

# GOT THE 0 value of long millisecond

package com.yahoo.mail.cmds.gateway;

import java.time.LocalDateTime;
import java.time.ZoneId;
import java.time.format.DateTimeFormatter;
import java.util.ArrayList;
import java.util.List;

public class SampleMain {
    public static void main(String[] args) {
        System.out.println("TYY");

        /*try {
            LocalDateTime localDateTimeMin = LocalDateTime.MIN;//-999999999-01-01T00:00
            System.out.println(localDateTimeMin);
            LocalDateTime localDateTimeMax = LocalDateTime.MAX;//-999999999-01-01T00:00
            System.out.println(localDateTimeMax);

            System.out.println(localDateTimeMin.atZone(ZoneId.systemDefault()).toInstant().toEpochMilli());//long overflow
            System.out.println(localDateTimeMax.atZone(ZoneId.systemDefault()).toInstant().toEpochMilli());//long overflow

        } catch (Exception e) {
            System.out.println(e.getMessage());
        }*/

        List<String> list = new ArrayList<>() {
            {
                add("1970-01-01 05:00:00");//-1800000
                add("1970-01-01 05:10:00");// -1200000
                add("1970-01-01 05:20:00");// -600000
                add("1970-01-01 05:30:00");// 0 may be based on timezone.
                add("1970-01-01 05:40:00");// 600000 --> 1 minute=60 seconds=60000 milliseconds; 10 minutes=600000 milliseconds;
                add("1970-01-01 05:50:00");// 1200000
                add("1970-01-01 05:00:00");// -1800000
            }
        };

        for (String s : list) {
            LocalDateTime localDateTime = LocalDateTime.parse(s, DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss"));
            System.out.println(localDateTime.atZone(ZoneId.systemDefault()).toInstant().toEpochMilli());
            // 1970-01-01T00:10:00.000Z
        }


    }
}

# 