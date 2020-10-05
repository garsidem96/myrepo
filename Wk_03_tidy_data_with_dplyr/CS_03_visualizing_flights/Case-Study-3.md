---
title: "Case Study 3"
output: 
   html_document:
     keep_md: true
---

# Question 1:
If I am leaving before noon, which two airlines do you recommend at each airport (JFK, LGA, EWR) that will have the lowest delay time at the 75th percentile?





![](Case-Study-3_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

Note: The "OO" airline was removed from the data because of the extremely small sample size.
![](Case-Study-3_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

![](Case-Study-3_files/figure-html/unnamed-chunk-5-1.png)<!-- -->

Results are as follows: If I want to leave from EWR, the best airlines at the 75th percentile are AS and WN. For LGA, the best are F9 and WN. For JFK, the best are HA and VX.

# Question 2:
Which origin airport has the lowest probability of a late arrival when I am using Delta Airlines?


### Origin: EWR

----------------------
 arr_delay > 0    n   
--------------- ------
     FALSE       2570 

     TRUE        1725 

      NA          47  
----------------------
Here we have EWR, with 2,570 out of the 4,295 total flights arriving on time, giving us a 59.8% success rate.

### Origin: LGA

-----------------------
 arr_delay > 0     n   
--------------- -------
     FALSE       14469 

     TRUE        8335  

      NA          263  
-----------------------
Here we have LGA, with 14,469 out of the 22,804 total flights arriving on time, giving us a 63.4% success rate.

### Origin: JFK

-----------------------
 arr_delay > 0     n   
--------------- -------
     FALSE       14206 

     TRUE        6353  

      NA          142  
-----------------------
Here we have JFK, with 14,206 out of the 20,559 total flights arriving on time, giving us a 69.1% success rate.

As the data shows, the airport that has the highest chance of arriving on time when using Delta Airlines is JFK, with 69.1 % of flights arriving on time or early.
