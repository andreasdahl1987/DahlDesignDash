# Tier 8: Fuel save analysis

The dashboard has a tool for determining whether fuel saving is worth it or not.&#x20;

You might lose 25 seconds on a pit stop, but you can drive at max pace for the rest of the race, with fresh tires on the last stint. If you need to go 2 seconds slower pr. lap to save enough fuel to skip the pit stop, the pit stop will only be worth it if the race has more than 12 laps remaining.

As your race pace might be falling off due to worn tires, or you're already in the process of fuel saving - you need a race pace to compare to. Something that represets the pace in case of going for the pit stop. This pace should be dialed in when you actually have it. Meaning that in order to use this feature you need to be a bit ahead of the game. You can make a habit of locking in the pace a few laps into the race, when you've gotten into the "flow". Locking the pace for fuel saving analysis is done by PitMenu11 + "+". Go back to using live pace with PitMenu11 + "-".&#x20;

The analysis will look at the potential race pace, your current pace, laps remaining in the race and the predicted time lost on a pit stop. To get the correct numbers for the pit stop duration, you actually have to order a pit stop with the fuel needed to end the session (PitMenu1 + "-", and add tire change if relevant). When all this is set up, you can use the Fuel Save Delta Screen.

![](<../.gitbook/assets/image (5).png>)



The lap time displayed is the lap time you need to beat while still saving fuel. You always need to be faster than this lap time. If you go faster, this lap time will gradually increase, and it will be easier to beat. The opposite is true if you go slower. This lap time is colored <mark style="background-color:blue;">blue</mark> if you have locked in a pace.

The value in the lower right corner is your current delta to this slowest acceptable lap time. The value in the lower left corner is your current fuel save delta; how much more fuel you need to save to avoid the pit stop. Both values need to be <mark style="background-color:green;">green</mark> to make the pit stop skip worth it.

In the example above, you've got 2.2 seconds headroom, and can slow down more to save more fuel. You're also not saving enough fuel, need to save 3.87 liters more to be able to extend the stint. So the message here is you should try slow down even more. If you can bring down the fuel delta below 0, and still keep the lap time, you're good.

The fuel delta is calculated from the _**last lap consumption**_, so it will be updated from lap to lap. A single lap of coast/lifting will give you some answers.

For the first 30% distance of your lap, the lap time delta will refer to your previous lap time, so you'll get time to evaluate the situation. Then it will go live for the remaining 70%. For these first 30 % of the lap the background color will change to gray to illustrate this.&#x20;
