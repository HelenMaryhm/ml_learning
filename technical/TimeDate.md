-----------
long milliseconds = 123456789L; // replace with your milliseconds
        double seconds = (double) milliseconds / 1000;
        System.out.println(seconds);//123456.789
----------
long milliseconds = 999L; // replace with your milliseconds
        BigDecimal seconds = new BigDecimal(milliseconds).divide(new BigDecimal(1000), 10, RoundingMode.HALF_UP);
        System.out.println(seconds);
-----------
long milliseconds = 999L; // replace with your milliseconds
        long seconds = TimeUnit.MILLISECONDS.toSeconds(milliseconds);
        System.out.println(seconds);
        System.out.println(milliseconds/1000);
------------
long ms = 1;
        long seconds = TimeUnit.MILLISECONDS.toSeconds(ms);
        System.out.println(seconds); //0
------------
 System.out.println(System.currentTimeMillis());//1714659457869
        long hours = 476294L;
        Duration duration = Duration.ofHours(hours);

        long days = duration.toDays();
        duration = duration.minusDays(days);

        long hoursRemaining = duration.toHours();
        duration = duration.minusHours(hoursRemaining);

        long minutes = duration.toMinutes();
        duration = duration.minusMinutes(minutes);

        long seconds = duration.getSeconds();

        System.out.println(days + " days " + hoursRemaining + " hours " + minutes + " minutes " + seconds + " seconds");
//19845 days 14 hours 0 minutes 0 seconds
------------
long milliseconds = 1714659299006L;
        long hours = TimeUnit.MILLISECONDS.toHours(milliseconds);
        System.out.println(hours);

-------------
(1714659118)/(60*60) 476294

System.out.println(TimeUnit.MILLISECONDS.toSeconds(System.currentTimeMillis()));
-------------
        LocalTime timeAtOneAM = LocalTime.of(1, 0); // 1:00 AM
        System.out.println(TimeUnit.MILLISECONDS.toSeconds(timeAtOneAM.toNanoOfDay()));
-------------
YamlToObject.readYamlAndConvertToSaintsDto();
RoughMain(List<SaintsDto> saintsDtos) {
        // private constructor
        saintsDtoList = saintsDtos;
    }

 */
/*
 long milliseconds = 998L;
 System.out.println((double) milliseconds / 1000); // 0.998
 System.out.println(milliseconds / 1000); // 0
 System.out.println(TimeUnit.MILLISECONDS.toSeconds(milliseconds)); //0
*/