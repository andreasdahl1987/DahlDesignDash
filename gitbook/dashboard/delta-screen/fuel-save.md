# Fuel save

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

The purpose of this screen is to help you decide if you should try to avoid a pit stop or not. This can be used for both fuel and tire strategy.

On top it shows the slowest lap time acceptable if you chose to save a pit stop by conserving fuel or skip changing tires. The value in the lower right corner is your current delta to this slowest acceptable lap time. The value in the lower left corner is your current fuel save delta; how much more fuel you need to save to avoid the pit stop. Both values need to be <mark style="background-color:green;">green</mark> to make the pit stop skip worth it.&#x20;

In the example above, you've got 2.2 seconds headroom, and can slow down more to save more fuel. You're also not saving enough fuel, need to save 3.87 liters more to be able to extend the stint.  So the message here is you should try slow down even more. If you can bring down the fuel delta below 0, and still keep the lap time, you're good.&#x20;

The fuel delta is calculated from the last lap consumption, so it will be updated from lap to lap. A single lap of coast/lifting will give you some answers.&#x20;

For the first 30% distance of your lap, the delta will refer to your previous lap time, so you'll get time to evaluate the situation. Then it will go live for the remaining 70%.  For these first 30 % of the lap the background color will change to <mark style="background-color:orange;">gray.</mark>

An **essential** part of using this delta is to **lock the pace** used for calculations. The algorithm need to compare your current lap times to the theoretical lap times you'd have if you'd done the pit stop. If you dont lock the pace for calculations, and you start slowing down to save fuel, your calculated race pace will be much slower that what you'd expect after the pit stop, and the minium accepted lap time will also be much slower than it actually is.&#x20;

* Lock the current race pace at a time in the race where the pace is representative of the situation right after pit stop. You can see that using this delta requires a bit of planning.&#x20;
* Locking pace is done by pressing "+" button in PitMenu11.&#x20;
* To release and go back to live pace calculations press "-" button in PitMenu11.
* When pace is locked, the color of the lap time in the delta screen turns <mark style="background-color:blue;">blue</mark>.



