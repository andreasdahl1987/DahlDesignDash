# Setup

### Setup

#### Dashboard settings

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

Have a look at the dashboard settings tab, note the options. There are none you have to check, but you might want to set up your session specific screens and preferred delta screen.

#### Dashboard controls

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p> </p></figcaption></figure>

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

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

If you control the menu with an encoder (increment/decrement bindings), the pitmenu will always start in position 12 on boot, and there is no use in labeling it.&#x20;

You might also notice the **+**, **-** and **OK** buttons on the wheel above. They are bound to the respective mappings at the top of the pit menu tab. These 3 buttons gives you the 3 options on each of the 12 pages. All 36 options are explained [here.](https://dahl-design.gitbook.io/properties/pit-menu)

The graphical elements of the pit menu in the dashboard are covered [here.](../dashboard/menu-bars/pit-menu.md)

#### InCar Menu

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

The **InCar Menu** is mapped the same way as the Pit Menu. The purpose of this menu is to give visual feedback on in-car adjustments. iRacing supports simultaneous button presses, so a multiposition switch together with a "+" and a "-" button can be used to adjust a lot of settings up/down. Up to 12 positions are supported by the plugin.&#x20;

The InCar menu in the dashboard is only there for supported cars, and even not all of them have the menu. Typically, cars that have a lot of in-car adjustments available will have this menu. The graphical elements of the InCar menu are covered[ here](plugin-menu.md#incar-menu).&#x20;

The idea is that you make key bidings in iRacing that match the layout of the InCar menu. You can use the same "+" and "-" buttons as with the Pit menu. In that case, the InCar menu must be in position 12 to unlock the Pit menu, in order to avoid pushing actions from the Pit menu and InCar menu at the same time. You can also use seperate buttons for in-car adjustments up/down, in that case uncheck _"Disable PitMenu Controls unless In-Car Rotary unused or in 12th/Pit position"_ in the  **Plugin setup** tab.&#x20;

You can use either a multiposition switch or an encoder to control the menu. An important **difference** to the pit menu is that iRacing requires a true multiposition switch in order to set up several in-car adjustments to the same rotary switch. You will not be able to sync the iRacing bindings with the dashboard if using a rotary encoder, so it has limited use. With the encoder you'd only be able to use the switch to look at the dashboard elements. Though, that could be useful even so.&#x20;

#### Fuel & Strategy

In this tab you'll find settings that affect how you add fuel with the Pit Menu as well as margins for fuel calculation and fuel adding. It is explained in detail [here.](https://app.gitbook.com/s/d2E1GdYd97jTQlTu0Drn/properties/fuel-and-strategy)

