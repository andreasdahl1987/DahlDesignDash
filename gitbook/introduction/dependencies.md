# Dependencies

The dashboard is 1/4th of a complete dashboard/controller system, including RGB LED control and controller firmware. It is totally dependent on the properties plugin, and some features are dependent on the LED plugin. Both of these should be installed.&#x20;

<figure><img src="../.gitbook/assets/Dependencies.png" alt=""><figcaption></figcaption></figure>

* [Properties plugin](https://github.com/andreasdahl1987/DahlDesignProperties) -> Generates new properties for iRacing and controls the LED plugin
  * No dependencies
* [LED plugin](https://github.com/andreasdahl1987/DahlDesignLED) -> LED control for Dahl Design DDU and SW1
  * Dependent on Properties plugin
* [Dashboard](https://github.com/andreasdahl1987/DahlDesignDash) -> iRacing specific dashboard template
  * Dependent on Properties plugin
  * Dependent on LED plugin to very little extent, only if using the simulated LEDs in the dash. It is advicable to have both installed though.
* [DDC](https://github.com/andreasdahl1987/DahlDesignDDC) -> Universal controller firmware builder
  * DDC has no dependencies. It is installed on a controller, not a computer. It will work on any system, even if SimHub is not installed. Though it can send information to the Properties plugin.
