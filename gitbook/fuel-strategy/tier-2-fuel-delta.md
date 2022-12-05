# Tier 2: Fuel delta

The most basic value that gives you the most information is the fuel delta. It is a calculation showing you the difference between the fuel needed to complete the session and the fuel you have available in the car:&#x20;

* Delta = Current fuel - Fuel needed to get through the session

_This value is particulary useful in a session where you're aiming not to stop for fuel._ For races with two or more pit stops, the delta value becomes very large and impractical.

The delta value can be found here:

* Mini fuel bar
* Pit Screen calculations
* Delta after pitstop on fuel adjustment screen

A <mark style="background-color:red;">negative</mark> fuel delta means you're lacking fuel to finish the sessions, and it looks like you might need to stop for fuel to or ease off the throttle to save some. It is indicated by the red part of the fuel bar.

A <mark style="background-color:green;">positive</mark> fuel delta is surplus fuel.&#x20;

#### Planning your race

You can use the fuel delta to plan the fuel load for your race. Make an AI race with race length matching your race series. Fuel as much as you think you'll need. Start the race and do some proper, representative laps, check the fuel delta. If the delta is +4.3, you can fuel 4.3 liters less for your actuall race. If the delta is -1.4, you should plan with 1.4 liters more in your race.&#x20;

#### Adding a margin

The `fuel & strategy` tab in the plugin menu has the options to add a margin to calculations and commands. More on commands in the next tier. The calculation of fuel delta in itself has no margin by default. It will show you what you need cross the start/finish line on the last lap with <mark style="background-color:orange;">0.2 liters</mark> left on the tank. Those 0.2 liters aren't really a safety margin, since many cars will start stuttering around 0.1 - 0.2 liters, so this is the bare minimum. By adjusting the margin for calculations upwards, you'll see the delta value becomming more negative. So the delta value is now more pessimistic. If your calculation margin is +1.0 liters, and the delta show 0.0 in your race, you'll probably end the race with 1.2 liters on the tank. It gives you a little buffer.
