# Tier 4: Main Screen info

There are several other elements in the main dashboard screen that can tell you something about your fuel situation. These become more useful if you're in a race where one or more pit stops are required.

### One-word advice

The box for PitMenu11 one-word advice about your strategy.

* NONE: This session will be finished without any pit stops for fuel.
* WAIT: You'll have to fuel, but it is too early to come in.
* OPEN: You can pit now.
* BOX: You should come in now, or you'll be running out of fuel on the next lap.
* SAVE: It looks like there is not much fuel missing, you might make it with some fuel saving.

### Calculation accuracy

The box for PitMenu12 and the fuel/lap value in the Pit Screen will change colors according to accuracy of fuel and remaining laps (in case of timed session) calculations.&#x20;

<mark style="background-color:red;">Red</mark> if fuel calculations are very crude.&#x20;

<mark style="background-color:yellow;">Yellow</mark> if the calculations have decent data to work with.

<mark style="background-color:blue;">Blue</mark> if there is a good data collection.

<mark style="background-color:green;">Green</mark> if the calculations are based on a large amount of accurate data.&#x20;

You should not be trusting fuel/strategy calculations when the color is <mark style="background-color:red;">red.</mark>

### Pit Menu 12

The small strategy screen visible when in PitMenu12 has a few other relevant values.&#x20;

* Pit window open: When you have enough room in the tank for the fuel to need.&#x20;
  * \<Number>: The lap number when you can come in
  * "-": No pit window because no pit stop
  * "OK": You can go pit now if you want
  * "<mark style="background-color:yellow;">OK</mark>": Pit within 3 laps
  * "<mark style="background-color:red;">PIT</mark>": Pit this lap
* Pit window close: The latest lap to pit without running out of fuel.&#x20;
  * \<Number>: The lap number when you can come in
  * "-": No pit window because no pit stop
  * "<mark style="background-color:red;">PIT</mark>": Pit this lap

### Pit Menu 11

The small strategy screen visible when in PitMenu11 has information on how much you need to reduce your fuel consumption in order to avoid a pit stop. Depending on the track, car and race situation (avaliable draft or free air) the amount you can save by lifting/coasting may very a lot. But in extreme cases up to 15% reduced fuel consumption per lap can be reached without completely throwing your pace away. If you are close to a positive delta, you can have a look here what is needed. Also, the calculations are made for the dynamic fuel/lap as well as previous lap fuel/lap, which means you can do a single lap of fuel saving and how this affected the calculation.&#x20;
