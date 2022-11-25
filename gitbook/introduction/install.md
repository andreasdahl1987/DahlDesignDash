# Install

### Download DahlDesignDDU.simhubdash

{% embed url="https://github.com/andreasdahl1987/DahlDesignDash/releases" %}

* Get the latest release from GitHub repository page. You'll only need the `DahlDesignDDU.simhubdash` file.
* Open the file to install the dashboard template. If this doesn't work, then move the file to the DashTemplate folder. Typically C:\Program Files(x86)\SimHub\DashTemplates
* Restart SimHub

### Download plugin .dll files

{% embed url="https://github.com/andreasdahl1987/DahlDesignProperties/releases" %}

{% embed url="https://github.com/andreasdahl1987/DahlDesignLED/releases" %}

* The files goes into your SimHub main folder. Typically C:\Program Files(x86)\SimHub
* Restart SimHub and you'll get a prompt that a new plugin has been found.
* Follow the steps for [setting up the properties plugin](https://dahl-design.gitbook.io/properties/introduction/install).

### Setup

#### Dashboard settings

Have a look at the dashboard settings tab, note the options. There are none you have to check, but you might want to set up your session specific screens and preferred delta screen.

#### Dashboard controls

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p> </p></figcaption></figure>

Here you can map buttons for controlling elements of the dashboard. None of these are absolutely necessary to map, since the PitMenu can do much of the same, but **Radio** should be mapped if you use  push-to-talk. Just map the same button you use for push-to-talk.

The option to set a binding to **Pressed** and **Released** is there to enable using momentary and latching buttons/toggles for these actions. For regular momentary buttons you only need to map **Pressed**, but for toggles or latching buttons you need to map both. In that case, you need to set the button press type to "pressed" and "released" accordingly.&#x20;

#### Car controls

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Here are some car specific controls where the plugin needs to monitor your actions in order to start some calculations or show dashboard elements. The TC Off bindings are there to start a stopwatch and show a countdown in the dashboard. It is relevant for a few cars that only deactivate TC for 5 seconds when you hit the TC toggle button. There is no in-game visualization of this, but the dashboard can show you. The same goes for "No Boost" for the Porsche 919. It can be activated, but there is no in-game visual feedback. Mapping this to your No Boost-button will give you some feedback in the dashboard.

#### Pit Menu

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

The Pit Menu is a great tool that offers a way to control your pit stop, fuel strategy and dashboard elements with a few buttons. I highly recommend setting it up, or at least learning what it does, since it will be mentioned more than a few times in this manual.&#x20;

It is simply pit a menu with 12 positions, each positions have 3 possible actions. In total 36 commands can be produced. The position in the menu can be controlled by a multiposition switch or an encoder.

A multiposition switch (with a minimum of 12 positions ) gives direct access to whichever menu position the switch points to, and allows you to label the switch accordingly, like the left rotary switch on the 1st generation Dahl Design SW1 below.&#x20;

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

If you control the menu with an encoder (increment/decrement bindings), the pitmenu will always start in position 12 on boot, and there is no use in labeling it.&#x20;

You might also notice the **+**, **-** and **OK** buttons on the wheel above. They are bound to the respective mappings at the top of the pit menu tab. These 3 buttons gives you the 3 options on each of the 12 pages. All 36 options are explained [here.](https://dahl-design.gitbook.io/properties/pit-menu)

The graphical elements of the pit menu in the dashboard are covered here

### &#x20;
