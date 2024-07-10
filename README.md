# 👋About the MistBuddy Project
This project builds a MistBuddy.  MistBuddy consists of a humidifier and two Tasmotized smart plugs. 
>Note: The term "Tasmotized" is often used in the hobbyist community to refer to a device that has been flashed or reprogrammed with the [Tasmota firmware](https://tasmota.github.io/docs/). This is often done to extend the capabilities of the device or to make it compatible with a wider range of home automation software. In this case the tasmotized device is a [Sonoff S31 wifi smart plug](https://amzn.to/4eT2SJJ).

MistBuddy spews out mist for a number of seconds each minute based on MistBuddy software that sends its power switches ON / OFF messages. The scenario is an indoor grow environment whose humidity is too low.
>Note: Too low humidity can be determined by measuring the environment's VPD (Vapor Pressure Deficit).  VPD is a measure of the difference between the actual and saturation water vapor pressure at a certain temperature. It directly influences a plant's rate of transpiration. High VPD results in increased transpiration, leading to potential plant stress from excessive water loss. This can manifest as wilted leaves, slowed growth, reduced crop yield, and in extreme cases, plants dry up and die. High VPD conditions can deter certain pests preferring moist environments but can encourage others like spider mites and thrips that thrive in hot, dry conditions. Low VPD can lead to reduced transpiration, affecting nutrient transport within the plant and causing lower rates of photosynthesis due to stomatal closure. This condition also increases the risk of diseases such as powdery mildew and botrytis, as well as other pathogens that thrive in high humidity.

Different plant types will prefer different ideal vpd levels. Some plants, like cacti and other succulents, are adapted to arid environments with potentially high VPD levels. They have evolved various mechanisms to conserve water, such as reduced leaf surface area and the ability to store water in their tissues. On the other hand, plants native to humid, tropical environments, like orchids, may prefer lower VPD levels. These plants have evolved to thrive in conditions of high humidity and are typically more sensitive to water loss through transpiration.

I found this YouTube video best explained (at least to the way I see things) water vapor, temperature's relationship to Relative Humidity and VPD.

The humidifier is an evolution of the one in the YouTube video [How to Build a Homemade Humidifier Using Ultrasonic Misters / fogger](https://www.youtube.com/watch?v=vmiO6Z_HLCE).

The current software that sends ON / OFF messages to a MistBuddy device can be found in the [mistbuddy_lite github repo](https://github.com/solarslurpi/mistbuddy_lite).

# Build the Humidifier
**CAVEAT: I have been using a build using these parts.  As in "it works for me."  I am not a professional.  I am sharing with in hopes it can benefit others.  I am not responsible for any damages to your home or property.


## BoM

The supplies needed to build this component of MistBuddy include:

| Component | Cost | Description |
|-----------|------|--------|
| Storage Tote |$10.50 | I used this [Storage Tote from Home Depot](https://www.homedepot.com/p/HDX-14-Gal-Tough-Storage-Tote-in-Black-with-Yellow-Lid-SW111/314468098).
| 2" PVC Pipe | $17.75 | Another [Home Depot purchase](https://www.homedepot.com/p/Charlotte-Pipe-2-in-x-10-ft-PVC-Schedule-40-DWV-Pipe-PVC-07200-0600/100348475).
| 2" PVC 90° elbow| $2.60  | [Home Depot](https://www.homedepot.com/p/Charlotte-Pipe-2-in-PVC-DWV-90-Degree-Hub-x-Hub-Elbow-PVC003001000HD/203393418).
| Waterproof IP67 12v Fan | $18 | I got [this fan from Amazon](https://amzn.to/3WgADKK).  It is powerful and waterproof.  It also has a nice, solid connector connecting the power source to the fan.
| Power source for the fan | $8 | [This is a very compact power source](https://amzn.to/3VT9pKp) that has the right connector to connect the fan.
| Mist maker | $34.10 | I bought the [Mist maker I use from Aliexpress](https://www.aliexpress.com/item/3256803543458943.html?spm=a2g0o.order_list.0.0.57dd1802LzMQr6).  I did not do any measurements to determine the ideal amount of misters.  Perhaps less can be used.
| Power source for the mist maker. | $40 | [The meanwell LRS-350-48 power supply(https://www.digikey.com/en/products/detail/mean-well-usa-inc/LRS-350-48/7705033).
| Float Valve | $10 | [Float Valve](https://amzn.to/43NemIL) to stop the constantly running water line from filling the tub.
| Water Source Connector | $15 (for 4) | [1/2" Barb to 1/2 " NPT female connector](https://amzn.to/3yzxlsG) _Note: The _connector fittings _assume_ 1/2"_ PEX connector to incoming water_ (see image below)

<!-- 2 cols for xtra small, 3 for small, 3 for medium, and 3 for large screens -->