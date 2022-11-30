# Tier 2: Using PitMenu

Follow the steps under [setup](../introduction/plugin-menu.md) to bind switches to the PitMenu. The PitMenu will let you control many aspects of the fuel strategy system. The more advance features are covered in later tiers.

First of all, you can order your fuel, tire, windscreen and repairs with this menu. For fuel there are two sizes of increments, and the size of these increments can be adjusted in the plugin menu.&#x20;

There are also two **fuel commands** available:

* PitMenu1 + "+": Fuel to go as many laps as possible, given the size of the fuel tank and current fuel consumption. This is not the same as full tank, but will be close to it. Full tank will not give more laps, you'll just have a bit more weight for the whole stint.
  * For a race with a single pit stop, you'll likely take on too much fuel with this command. For a race with two or more stints, this is will give you the longest next stint possible.&#x20;
* PitMenu1 + "-": Fuel the amount you need to finish the session.&#x20;
  * For a race with a single pit stop, this is a good option. For a race with two or more stints this option will give you the least amount of fuel that will get you through the whole race without adding an extra pit stop - meaning your following pit stops will be with more or less full tank, and you'll be using all your margins on this stop.&#x20;

You can add a margin to these commands, the same way you can add it to calculations - in the plugin menu. That will just add a little extra fuel on top. Adding margins to both calculations and commands will cumulate. The advantage of adding margins to commands instead of calculations is that you wont affect the accuracy of the calculations - "what you see is what you get". Margins on calculations can mask or create a problem that isn't really there.&#x20;
