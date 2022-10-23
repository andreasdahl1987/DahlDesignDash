<img src="assets/Screen Shot 2022-10-22 at 9.37.05 PM.png" alt="Screen Shot 2022-10-22 at 9.37.05 PM" style="zoom:50%;" />

# Introduction

This is my approach to a universal dashboard for iRacing, as well as advanced LED support for my steering wheel (DahlDesign SW1) and dash (DahlDesign DDU). Though this LED support will work for any 4- or 29-chain of RGB LEDs. The goal was to make a dashboard that looks like it could be in a race car, flooded with features that are useful for simracers. iRacing telemetry can behave strangely, and is lacking a lot of relevant information. To work around/enhance the information available, I’ve made a bunch of new properties, most of which are used in my dashboard.

These properties range from improved accessibility on already available telemetry to new utilities and emulations; such as live updated race positions, actual timed race deltas, traction control activation, optimal shift points and sector timing. I’ve built a framework where I manually map relevant attributes for cars and tracks (about 50 attributes for cars, 15 for tracks) which in return gives me a platform for calculating a lot of things not available in iRacing telemetry. For instance; a pretty accurate estimation of pit stop duration, based on fuel fill rate, which side of the car pit crew is on, how the pit crew works on this particular car, if tire swap and fueling is permitted at the same time, as well as expected time lost from driving through the pit lane, based on car top speed, corner speed, acceleration and brake performance, compared to the race track layout and where the pit lane is on this specific track. Based on this, new properties can be built, such as info on the traffic you’re entering on pit exit.

**There is a lot of testing and manual mapping that goes into each supported car/track. Upon first release, only a few will have full support for all features. I also haven’t got access to all cars and tracks yet. More will follow!**

In order to make my dashboard independent of other plugins, some of the properties are overlapping with other plugins. Most notably Romain’s iRacingExtraProperties plugin.

The dash has some elements with rather small text, and I’d not recommend using a screen with resolution lower than 800 x 480. Vocore 4”/4.3” or China 5”/7” HDMI display is great. Nextion or USBD480 is not optimal.

Big thanks to the SimHub discord community, and Romain Bouteiller (aka Romainrob) in particular, who has kindly held my hand through these coding adventures. He’s helped me solve many code related issues that I wasn’t able to figure out by myself.

# Install

Download the files from the drive folder, place them in the SimHub main folder, generally found under: `C:\Program Files(x86)/SimHub`

* `DahlDesign.dll` and `DahlDesignLED.dll` go directly in the main folder 
* `DahlDesign.js` goes to ../SimHub/JavascriptExtensions 
* `DahlDesign.simhubdash` goes to `../SimHub/DashTemplates`, but you can also just double-click it to install.

Restart SimHub and you should get a prompt that a new plugin has been detected.

# **Getting started**

## Pit Menu Configuration

### Buttons

Many functions/utilities in this dashboard require you to map a button on the plug-in page. Many different ways to map a button are possible.  Experiment with the mapping and button modes (`press` / `release` / `during`). 

<img src="assets/Screen Shot 2022-10-22 at 7.50.10 PM.png" alt="Screen Shot 2022-10-22 at 7.50.10 PM" style="zoom:50%;" />

When you configure this, you really have 2 options - individual, directly accessed values (most commonly used with a multi position switch (MPS), or a simple increment/decrement option (this can work well with a FunkySwitch, up/down toggle or even just 2 buttons).

#### Multi Position Switch

If you have a switch like this (with a minimum of 12 positions that act as individual buttons, **not a simple digital or analog rotary encoder**), you can use this to get direct access to various parts of the control options that make the DahlDesign DDU so unique.

## <img src="assets/Screen Shot 2022-10-22 at 7.57.37 PM.png" alt="Screen Shot 2022-10-22 at 7.57.37 PM" style="zoom:50%;" />

Here you should assign each position to one of the positions shown in the Pit-Menu options above.  This usually works best if you configure your wheel to send a `pulse` of the button each time you turns the wheel.  For Fanatec wheels, this is easily configured in the Fanatac Control Panel.   For SW1 wheels, the can be controlled on wheel itself.  

Set each Pit Menu value to a unique position on your wheel.  For Fanatec wheels like shown, you may have to just 'pretent' that '0' is the 12th position (or maybe make a sticker!).

*If you’re using an encoder to control PitMenu, you need to turn the encoder a single time to engage the menu each time you boot SimHub.*

#### Increment & Rotary

If you don't have a MPS, or you don't want to use it (Andreas uses a FunkySwitch instead, for example), you can also configure the menu's to scroll through simply with a digital encoder or pair of buttons/toggle switch.   Simply configure one button for `Increment` and one for `Decrement`.

### Plus / Minus / OK / Shift

In addition to the rotary / increments, you'll also need to map 3 buttons to control '+', '-' and 'ok' functions to make changes to your pit stop options, as well the buttons you use to shift.<img src="assets/Screen Shot 2022-10-22 at 8.12.09 PM.png" alt="Screen Shot 2022-10-22 at 8.12.09 PM" style="zoom:67%;" />

As with the other options, you can use whichever buttons make sense for you here.   Andreas uses the up/down/press buttons on his FunkySwitch, and other players user an up/down toggle and a dedicated 'OK' button (in this example, yellow as 'OK' and the black toggle for +/-.

<img src="assets/Screen Shot 2022-10-22 at 8.23.35 PM.png" alt="Screen Shot 2022-10-22 at 8.23.35 PM" style="zoom:50%;" />

You should also set your buttons used for shifting here (this really only works with sequential shifting), as they are used in the plugin/dashboard for timing and displaying your shift efficiency.   Most just use the shift paddles on the wheel.

There are other options on this screen that are less commonly used, and discussed in the Appendix.

## In-Car Menu Configuration

### Buttons

*This is the same technique as for the Pit Menu Buttons above, just repeated.  Many users decide they don't need this functionality at all, but it can be useful for certain control of car options like TC & ABS levels, Fuel Maps, etc.*

Many functions/utilities in this dashboard require you to map a button on the plug-in page. Many different ways to map a button are possible.  Experiment with the mapping and button modes (`press` / `release` / `during`). 

<img src="assets/Screen Shot 2022-10-22 at 8.08.11 PM.png" alt="Screen Shot 2022-10-22 at 8.08.11 PM" style="zoom:50%;" />

When you configure this, you really have 2 options - individual, directly accessed values (most commonly used with a multi position switch (MPS), or a simple increment/decrement option (this can work well with a FunkySwitch, up/down toggle or even just 2 buttons).

#### Multi Position Switch

If you have a switch like this (with a minimum of 12 positions that act as individual buttons, **not a simple digital or analog rotary encoder**), you can use this to get direct access to various parts of the control options that make the DahlDesign DDU so unique.

## <img src="assets/Screen Shot 2022-10-22 at 7.57.37 PM.png" alt="Screen Shot 2022-10-22 at 7.57.37 PM" style="zoom:50%;" />

Here you should assign each position to one of the positions shown in the Pit-Menu options above.  This usually works best if you configure your wheel to send a `pulse` of the button each time you turns the wheel.  For Fanatec wheels, this is easily configured in the Fanatac Control Panel.   For SW1 wheels, the can be controlled on wheel itself.  

Set each Pit Menu value to a unique position on your wheel.  For Fanatec wheels like shown, you may have to just 'pretent' that '0' is the 12th position (or maybe make a sticker!).

*If you’re using an encoder to control PitMenu, you need to turn the encoder a single time to engage the menu each time you boot SimHub.*

#### Increment & Rotary

If you don't have a MPS, or you don't want to use it (Andreas uses a FunkySwitch instead, for example), you can also configure the menu's to scroll through simply with a digital encoder or pair of buttons/toggle switch.   Simply configure one button for `Increment` and one for `Decrement`.

## LED Options

If you made yourself a DD SW1 or a DD DDU (congratulations), make sure to enable it and set the starting LED for this unit on the LED page. Choose your reaction time (how long from shift light until you actually shift). Add the effect within the LED editor, the rest is magic.

![Screen Shot 2022-10-22 at 8.28.44 PM](Screen Shot 2022-10-22 at 8.28.44 PM.png)

# Using the Dash

## Overall Color Design

### General tendencies

General colors and color coded values in this dashboard:

Bad/low ![Screen Shot 2022-10-22 at 8.43.38 PM](Screen Shot 2022-10-22 at 8.43.38 PM.png) Good/High

Default state / not enough data: GREY

#### Color coded lap/sector times

#### Overtaking before race end predictions

#### Race position

#### Practice session cars

#### Stint duration

#### Launch screen

#### Pitstop

#### ABS/TC/MAP

For any colors that is not intuitive and I’ve failed to explain, don't hesitate to ask on Discord.

## Dashboard Overview

![Screen Shot 2022-10-22 at 8.52.06 PM](Screen Shot 2022-10-22 at 8.52.06 PM.png)

This is a lot of info!  This is what it could look like, though this dash has many shapes and forms, depending on car model, user input and circumstances. There are no static elements in the entire dash.

Let's break it down into components.

### Delta

You can cycle through the 5 delta modes by ensuring you are on Pit Mode 11 and pressing 'OK'.

#### Color Coding

- Grey: Lap is not valid
- Green: On target to beat session best
- Magenta: On target to beat all-time best

#### Performance Delta Mode

The performance delta screen is pretty much self explanatory. The bars on the bottom show how fast the delta is shifting in either direction. This design is downright stolen from Meekesta.![Screen Shot 2022-10-22 at 8.57.47 PM](Screen Shot 2022-10-22 at 8.57.47 PM.png)

The top section shows the delta and type (compated to Last Lap (LL), Session Best (SB) or Lap Record/Personal Best (LR)).  

The bottom section is unique - the dashboard stores your 'minisector' times (each track is broken in 20 mini sectors) and shows the comparison for each one.  A large red bar indicates you are much slower in that section compared the LL, SB or LR, and a small green bar shows you are a little faster.   Using this quick view, you can understand where you can pick up the most time or consistency.

#### Pit Save Delta Mode

Shows the slowest lap time acceptable if you chose to save a pit stop by conserving fuel or skip changing tires. The delta in the lower right corner is your current delta to this slowest acceptable lap time.![Screen Shot 2022-10-22 at 9.04.37 PM](Screen Shot 2022-10-22 at 9.04.37 PM.png)

The “F +3.87” shows how you’re doing with regards to avoiding pitting for fuel, which also is an important part of the calculation. If you’re driving slow to save fuel and avoid a pit stop, you have to make sure you can actually avoid the pit stop. This value is calculated with the fuel consumption on the previous lap, so you can do a lap with lift/coast and see if you will save enough fuel to avoid pitting, and check if you go fast enough to make it worthwhile. In this case, you’re good on lap time, but still need to save 3.87L more fuel. For the first 30% distance of your lap, the delta will refer to your previous lap time. Then it will go live for the remaining 70%. To get an accurate “acceptable slowest lap time”, you should lock your lapping pace, when you have good pace. This could be smart to do early in the race. Do this with PitMenu11 + “Plus”.

#### Fuel Save Delta Mode

Last is the “fuel saving” delta. It will display your current set target fuel pr. lap (set with PitMenu12 + “OK”, adjusted with PitMenu12 +/-) and your delta to this target on the last lap. On the right, you will see the cumulative fuel saved compared to target on the stint.

![Screen Shot 2022-10-22 at 9.05.15 PM](Screen Shot 2022-10-22 at 9.05.15 PM.png)

### RPM Bar

![Screen Shot 2022-10-22 at 9.05.33 PM](Screen Shot 2022-10-22 at 9.05.33 PM.png)

In test/practice sessions the bar has a pink and a green line showing the optimal shift point and your shift timing for the previous gear shift.   LastlyThis gives you an indication on whether you’re shifting too early or too late. You can also enable the shoft points for races in the DahlDesign options screen, as well as enable the bar to turn orange as a 'shift indicator'.![Screen Shot 2022-10-22 at 9.07.23 PM](Screen Shot 2022-10-22 at 9.07.23 PM.png)

The bar will change colors when using HYS boost, toggling NoBoost, DRS, P2P, etc.

The bar will show all kinds of warnings and messages, as well as some practical features; assisting in safe track entry, hitting pit box, info on radio communication, adjusting to pit lane speed limit, fuel warning, etc. All of this is conditional, not controlled by the user.

Lastly, you can also replace the RPM bar for LEDs (like progressive shift lights).

![Screen Shot 2022-10-22 at 9.07.45 PM](Screen Shot 2022-10-22 at 9.07.45 PM.png)

### Left Multi Function Display (MFD)

You can change the display that appears dynamically by assigning a button on your wheel or keyboard to the SimHub Action 'A' (cycle left) or 'B' (cycle right) to select the display you want to use.

##### Time 1

**TIME1** is basic. Worth noting the session best time is only recorded on valid laps. TIME1 and RACE1-3 have a fuel overview and incident counter at the bottom line. To the left is the remaining fuel, to the right the fuel delta. Blue+green shows fuel on the tank, where green is excess fuel. Red is the amount you’re missing and pink is the amount you’re planning to fill.

<img src="assets/Screen Shot 2022-10-22 at 9.11.58 PM.png" alt="Screen Shot 2022-10-22 at 9.11.58 PM" style="zoom:50%;" />

##### Time 2

**TIME2** is your sector and delta screen. Have a look at sector properties and color coding further up to see how they work. OL is optimal lap time, adding all the best valid sector times together. The value in the lower right corner the maximum brake pressure on your previous brake pedal hit. Deltas on SB and OL refer to personal best.

<img src="assets/Screen Shot 2022-10-22 at 9.12.32 PM.png" alt="Screen Shot 2022-10-22 at 9.12.32 PM" style="zoom:50%;" />

##### TIme 3

**TIME3** is an overview of your previous 8 laps with delta to session best. Laps are color coded according to status.

<img src="assets/Screen Shot 2022-10-22 at 9.12.54 PM.png" alt="Screen Shot 2022-10-22 at 9.12.54 PM" style="zoom:50%;" />

##### Quali

**QUALI** is designed for hot lapping. It shows your current position on fastest lap leaderboard, as well as live position prediction for current lap.

<img src="assets/Screen Shot 2022-10-22 at 9.13.19 PM.png" alt="Screen Shot 2022-10-22 at 9.13.19 PM" style="zoom:50%;" />

##### Race 1

**RACE 1** is extended info on the car ahead and behind on track. Including joker lap count, licence and iRating, as well as last lap delta (comparing yours and his). Color coded for car track position. In this case the car ahead has a blue flag and the car behind is fighting you for your position. For Indycar it will display if P2P is active and the P2P count.

<img src="assets/Screen Shot 2022-10-22 at 9.13.41 PM.png" alt="Screen Shot 2022-10-22 at 9.13.41 PM" style="zoom:50%;" />

##### Race 2

**RACE 2** is pretty straight forward. See color coding for cars ahead/behind on track. Joker status and P2P status will also show up when relevant.

<img src="assets/Screen Shot 2022-10-22 at 9.14.08 PM.png" alt="Screen Shot 2022-10-22 at 9.14.08 PM" style="zoom:50%;" />

##### Race 3

**RACE 3** has a lot of info in a tight space. In comparison to RACE1, it shows the race position ahead and behind, regardless where this driver is on the track compared to you. Color coded with regards to overtake prediction, see color codes above. In the middle is a compressed RACE2. Same class cars will get a black border if they are within 5 seconds of you.

Pace delta and estimated time of overtake is also displayed. Lap 13 + 3 means you’re on lap 13 and will overtake in 3 laps time. FIN + 2 means P5 looks like he will overtake you 2 laps after the race ends, so this is a good thing. The “!” means this driver's last lap was quite slow compared to his best lap time. That might just be a bad lap, but could also mean damaged car or tires degrading. If it was a single bad lap, the overtake predictions might be misleading for this lap.

For Indycar it will display if P2P is active and the P2P count. The properties used in RACE3 will need a few laps to have enough data to display anything.

<img src="assets/Screen Shot 2022-10-22 at 9.14.40 PM.png" alt="Screen Shot 2022-10-22 at 9.14.40 PM" style="zoom:50%;" />

##### Practice 1

**PRAC 1** shows your minimum corner speed for the last corner as well as straight line speed for the last straight. The three boxes on top are your sectors with color coded lap status. The value is the sector score.

Sector score is based on variation in sector times and incidents in this sector. 8 identical sector times in a row, all incident free is max score (10).

<img src="assets/Screen Shot 2022-10-22 at 9.15.16 PM.png" alt="Screen Shot 2022-10-22 at 9.15.16 PM" style="zoom:50%;" />

##### Practice 2

**PRAC 2** shows a 4 second recording of your previous brake input, as well as a 3 second recording of your previous throttle input. The three value boxes are peak brake pressure, area under brake curve and throttle agro (top to bottom).

<img src="assets/Screen Shot 2022-10-22 at 9.16.42 PM.png" alt="Screen Shot 2022-10-22 at 9.16.42 PM" style="zoom:50%;" />

### Right Multi Function Display (MFD)

You can change the display that appears dynamically by assigning a button on your wheel or keyboard to the SimHub Action 'C' (cycle left) or 'D' (cycle right) to select the display you want to use.

##### Practice 1

**PRAC1** is a simple display of your pace, stint duration and amount of valid/invalid laps completed this stint.

<img src="assets/Screen Shot 2022-10-22 at 9.18.20 PM.png" alt="Screen Shot 2022-10-22 at 9.18.20 PM" style="zoom:50%;" />

##### Practice 2

**PRAC2** shows how far you’ve gotten into the stint and how much is left. Ending either on session end or when running out of fuel, whichever happens first. I often use this to structure my practice sessions a bit better. The lap counter will only include hot laps. It might look strange that a 6 minute stint has only 1 lap, but this is because out lap and in lap isn’t counted. There will be only 1 flying lap.

<img src="assets/Screen Shot 2022-10-22 at 9.18.38 PM.png" alt="Screen Shot 2022-10-22 at 9.18.38 PM" style="zoom:50%;" />

##### Qualy 1

**LONE**(Q1) is intended for 2-lap lone qualifying. The bar on the right shows if you’re in danger of running out of time to get your laps done.

<img src="assets/Screen Shot 2022-10-22 at 9.19.07 PM.png" alt="Screen Shot 2022-10-22 at 9.19.07 PM" style="zoom:50%;" />

##### Qualy 2

**OPEN** (Q2) is intended for open qualifying. Shows the car ahead/behind, color coded as left side RACE1/2 in a practice session, as well as laps remaining (including out laps).

<img src="assets/Screen Shot 2022-10-22 at 9.19.28 PM.png" alt="Screen Shot 2022-10-22 at 9.19.28 PM" style="zoom:50%;" />

##### Race 1

**RACE1** is the same as RACE2 but with added information. The race position window is color coded with regards to overtake predictions, and will show estimated lap count until overtake of race position ahead/behind, much like the left side RACE3. The gauge on the lap counter shows how close you are to having one less/more lap. In time limited sessions, a pink line will also appear, this is how close the race leader is to having one less/more lap, which in return can suddenly affect your number of remaining laps.

<img src="assets/Screen Shot 2022-10-22 at 9.19.40 PM.png" alt="Screen Shot 2022-10-22 at 9.19.40 PM" style="zoom:50%;" />

##### Race 2

**RACE2** is your classic position/lap overview.

<img src="assets/Screen Shot 2022-10-22 at 9.20.15 PM.png" alt="Screen Shot 2022-10-22 at 9.20.15 PM" style="zoom:50%;" />

##### RallyX

**RALLY** is your rallycross page, showing joker lap status and laps remaining.

<img src="assets/Screen Shot 2022-10-22 at 9.20.31 PM.png" alt="Screen Shot 2022-10-22 at 9.20.31 PM" style="zoom:50%;" />

##### Track Info

**TRACK** is an overview of weather and track conditions.The gauge in the lower left corner is track usage. Full bar is high, empty bar is fresh track.

I will implement a weather forecast system in the future if it becomes relevant.

<img src="assets/Screen Shot 2022-10-22 at 9.20.49 PM.png" alt="Screen Shot 2022-10-22 at 9.20.49 PM" style="zoom:50%;" />

### Gear box

This part of the dash will change from car to car; the most basic for the Skippy, the most advanced for LMP1 and F1 cars. The info displayed should be fairly intuitive, but some examples are included below.![Screen Shot 2022-10-22 at 9.22.21 PM](Screen Shot 2022-10-22 at 9.22.21 PM.png)

### Menu Bars & Adjustments

#### Pit Menu Bar

 If the car has only a few InCar adjustments, there will only be a PitMenu bar

![Screen Shot 2022-10-22 at 9.25.39 PM](Screen Shot 2022-10-22 at 9.25.39 PM.png)

These correspond to the 12 positions decribed in the Pit Menu Configuration section of this manual.

**Worth mentioning**
P itMenu11 is a mini version of the “Pit Messages” graphic on pit screen. When selected th eadjust box will show the amount of fuel per lap that needs to be saves in order to avoid a single pit stop

#### In Car Menu Bar

If the car has only a few InCar adjustments, there will only be a PitMenu bar. Otherwize, both InCarMenu and PitMenu will be displayed.   The items shown depend on the car.

![Screen Shot 2022-10-22 at 9.27.09 PM](Screen Shot 2022-10-22 at 9.27.09 PM.png)

#### Menu Box

If no menu buttons are mapped, this area will show a brake/throttle bar and fuel strategy.  Otherwise, more detailed information relevant to the selected item (TC level, Fuel Map, Diff Settings, etc).   

<img src="assets/Screen Shot 2022-10-22 at 9.23.53 PM.png" alt="Screen Shot 2022-10-22 at 9.23.53 PM" style="zoom:50%;" />



### Launch screen

Activated with Launch button set in DahlDesign plugin settings or PitMenu2 + Plus-button.

Information on how to achieve the best launch with this car, intended for double clutch systems. Optimal bite point in pink, your set bite point (from the myBitePoint() function), in orange.  Acceleration times are shown for you to work on your launch.<img src="assets/Screen Shot 2022-10-22 at 9.30.59 PM.png" alt="Screen Shot 2022-10-22 at 9.30.59 PM" style="zoom:50%;" />

For high-power cars, where you can’t give 100% throttle from the start, an alternative launch screen is shown. This screen will also automatically appear when on standing start. On all high power cars you release the clutch completely before starting to push the throttle.

<img src="assets/Screen Shot 2022-10-22 at 9.31.21 PM.png" alt="Screen Shot 2022-10-22 at 9.31.21 PM" style="zoom:50%;" />

### Pit screen

Activated with Pit screen button (mapped on plugin options page) or  PitMenu11 + OK![Screen Shot 2022-10-22 at 9.32.00 PM](Screen Shot 2022-10-22 at 9.32.00 PM.png)

This screen might seem flooded at first, let's chop it into elements.

#### Tether

**Tether** - Essential car/race info + temperatures.The two drivers are car ahead and car behind on track, extracted from left side RACE2.

![Screen Shot 2022-10-22 at 9.33.17 PM](Screen Shot 2022-10-22 at 9.33.17 PM.png)

#### Tires

**Tires** - Wear/temp/pressure. Updated only on pit stop (because iRacing doesn't update live). In this case the set pressure for rear/front tires are different from the set you’re currently using, thus marked in blue. Front tires are purple, meaning they are set to be changed. Tire temperatures and wear with color indications.

![Screen Shot 2022-10-22 at 9.33.45 PM](Screen Shot 2022-10-22 at 9.33.45 PM.png)

#### Center

**Center box** - Default view is a traffic report on pit exit, 10 seconds ahead (up) and behind (down). These calculations will require a few laps of data collection to initiate. The number on the cars is race position.  This box will also show many of the things the RPM-bar would show on the main page.

<img src="assets/Screen Shot 2022-10-22 at 9.34.19 PM.png" alt="Screen Shot 2022-10-22 at 9.34.19 PM" style="zoom:50%;" />

#### Fuel Bar

Oversized version of the one seen in left side pages. Total fuel on top, amount planning to fill on bottom. If fueling is checked it will be purple, and a purple gauge indicating the new fuel level will show. Blue+green is the amount of fuel in the tank. Green is excess fuel (positive fuel delta). Fuel missing in red. In this case, the delta is -12.3 L and we’re fueling 9.0 L, so a small bit of red over the purple indicates the 4.3 L missing even after fueling.

<img src="assets/Screen Shot 2022-10-22 at 9.34.41 PM.png" alt="Screen Shot 2022-10-22 at 9.34.41 PM" style="zoom:50%;" />

#### Fuel Calcs

Pit window (opens on lap / closes on lap), amount of pit stops this session, total fuel delta and minimum fuel to fill in descending order. Calculated for average lap fuel use as well as last lap fuel use. Look in the properties page for a complete explanation of these properties.

In this example, 1 pitstop is needed, and we’re quite far from both being able to avoid stopping and having to do 2 stops. About 1.10 here would give a warning to try a fuel save lap. About 1.05 would give a yellow warning, since it would be quite easy to avoid a pit stop with some lift/coast. “OK” in the pit window shows that the pit window is open; there is room on the fuel tank to fill the required amount. Here, a fuel save lap has been attempted (last lap), calculations showing a pit stop is still needed, though with a bit less

to fill and the stint can be extended to lap 39 instead of lap 34 as an absolute last lap to pit. Since only 1 pit stop is required, the minimum amount to fuel (bottom line) is the fuel delta. With 2 or more stops, this would look different. 

![Screen Shot 2022-10-22 at 9.35.08 PM](Screen Shot 2022-10-22 at 9.35.08 PM.png)

#### Pit Services

Selected services on next pit stop and expected time spent, as well as calculated race position on pit exit, or more specifically, position when arriving at the first point at which speed difference of track cars and you is eliminated, typically the braking zone after pit exit. Meaning you might be P12 when exiting the pits, but then easily overtaken on the pit straight, being P14 into turn 1. Bottom line right to left: Total time lost, time spent on car service, time spent on stop+go.

<img src="assets/Screen Shot 2022-10-22 at 9.35.30 PM.png" alt="Screen Shot 2022-10-22 at 9.35.30 PM" style="zoom:50%;" />

#### Pit Messages

A quick summary/recommendation on what to do. If you’ve got 1 second to look at the pit page, look at this:

- OPEN : You have to pit, you’re free to pit now.

- WAIT: You have to pit, window is not open yet.

- BOX: Pit this lap.

- SAVE : There is a chance to avoid a pit stop by saving some fuel.

- NO PIT: You will not have to pit.

  PitMenu11 is a mini version of this.

  <img src="assets/Screen Shot 2022-10-22 at 9.36.13 PM.png" alt="Screen Shot 2022-10-22 at 9.36.13 PM" style="zoom:50%;" />



## Controlling Pit Options

### Commands and Utilities available through PitMenu.

*If* any of the entrys on the In-Car Menu page are mapped, the PitMenu commands will only fire if In-Car Menu is set to position 12.  This can ensure that accidental button presses don't change your pit options, and allow you to double-up the function of some buttons.

##### Quick Reference Table

| Pit Menu Position   | OK Button Action                                             | Plus Button Action                            | Minus Button Action                                      |
| ------------------- | ------------------------------------------------------------ | --------------------------------------------- | :------------------------------------------------------- |
| 1: Clear            | Clear all services (repair, windscreen, refuel, tires) and calculated fuel offset | Fuel for max laps + margin + clear windscreen | Fuel for minimum to end race/stint + margin + windscreen |
| 2: Repair           | Toggle Repairs                                               | Open the Launch Control screen                | Open the Pace screen                                     |
| 3: All Tires        | Toggle replacement of all tires                              | +3 kPA to all tires                           | -3 kPA to all tires                                      |
| 4: Front/Left       | Toggle front/left tires                                      | \+ 3 kPA front/left tires                     | \- 3 kPA front/left tires                                |
| 5: Rear/Right tires | Toggle rear/right tires                                      | \+ 3 kPA rear/right tires                     | \- 3 kPA rear/right tires                                |
| 6: Windscreen       | Toggle windscreen clean                                      | Send private message to car ahead             | Send private message to car behind                       |
| 7: Fuel 2 liter     | Toggle refueling                                             | \+ 2 L fuel                                   | \- 2 L fuel                                              |
| 8:Fuel 10 liter     | Show the full-screen pit screen (described below)            | \+ 10 L fuel                                  | \- 10 L fuel                                             |
| 9:Stopwatch         | Start/stop                                                   | Split                                         | Reset                                                    |
| 10:Temperatures     | Spotter mode                                                 | \+ System volume                              | \- System volume                                         |
| 11: Fuel save       | Cycle through performance and fuel save delta modes          | Snapshot of pace                              | Live pace                                                |
| 12: Strategy        | Set fuel target                                              | +0.1 FuelPerLapOffset                         | -0.1 FuelPerLapOffset                                    |



# Appendix & Less Common Options

## Items Still To Document

* Data Plugin Descriptions
* Color Coding with Colors
* Identification of tracks and cars with specific support

## DahlDesign Data Plugin Descriptions

To Be Added

## Clutch

*This section is highly optional, so unless bite point adjustment and perfectly optimized launches are important to you, its safe to skip.*

If you want your clutch to be visible in the Launch Screen, you need to map the clutch axis to the `myClutch()` function in DahlDesign.js in the Javascript extensions folder. The same goes for clutch bite point, if you have an analog axis to adjust this on your wheel.

<img src="assets/Screen Shot 2022-10-22 at 7.51.27 PM.png" alt="Screen Shot 2022-10-22 at 7.51.27 PM" style="zoom:50%;" />

