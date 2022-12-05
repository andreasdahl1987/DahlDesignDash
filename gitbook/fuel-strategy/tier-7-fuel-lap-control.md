# Tier 7: Fuel/lap control

While you can set a fuel/lap target before the race, you can also set a fuel/lap target while racing, and even manipulate the fuel/lap value that calculations are done with.

If you suspect that the situation after pit stop will  be different that it is before:

* Reaching a pack of cars after pit stop, using less fuel because of draft
* Free air after pit stop, using more fuel
* Racing for a position after pit stop, need fuel to be able to race hard/drive in free air
* Last stint of the race, got room in the tank to fuel for fastest possible lap times.
* Adjust fuel/lap to a different driver with different preferences

You can adjust the fuel/lap value by adding an offset. This is done with PitMenu12 + "+"/"-". This offset is added to the fuel calculations. In the Pit Screen, you'll see the offset blinking on top of the fuel/lap box.&#x20;

Pressing PitMenu12 + "OK" will set the fuel/lap target to the current fuel/lap value + the offset.&#x20;

In the plugin menu you can adjust the increments of offset adjustments. Also, by checking `Use target for calculations when set` you will lock fuel calculations to the fuel target automatically when setting a new fuel target. Adjusting the offset or using the CLEAR command (PitMenu1 + "OK") will release the lock. Locking the fuel calculations to the set fuel target can be a good idea, since calculations are based on the floating fuel/lap + static offset unless it is locked to the static target, and can therefore change from lap to lap.

