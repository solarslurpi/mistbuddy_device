# 👋About the MistBuddy Project
This project builds a MistBuddy.  MistBuddy consists of a humidifier and two Tasmotized smart plugs. 
>Note: The term "Tasmotized" is often used in the hobbyist community to refer to a device that has been flashed or reprogrammed with the [Tasmota firmware](https://tasmota.github.io/docs/). This is often done to extend the capabilities of the device or to make it compatible with a wider range of home automation software. In this case the tasmotized device is a [Sonoff S31 wifi smart plug](https://amzn.to/4eT2SJJ).

MistBuddy spews out mist for a number of seconds each minute based on MistBuddy software that sends its power switches ON / OFF messages. The scenario is an indoor grow environment whose humidity is too low.
>Note: Too low humidity can be determined by measuring the environment's VPD (Vapor Pressure Deficit).  VPD is a measure of the difference between the actual and saturation water vapor pressure at a certain temperature. It directly influences a plant's rate of transpiration. High VPD results in increased transpiration, leading to potential plant stress from excessive water loss. This can manifest as wilted leaves, slowed growth, reduced crop yield, and in extreme cases, plants dry up and die. High VPD conditions can deter certain pests preferring moist environments but can encourage others like spider mites and thrips that thrive in hot, dry conditions. Low VPD can lead to reduced transpiration, affecting nutrient transport within the plant and causing lower rates of photosynthesis due to stomatal closure. This condition also increases the risk of diseases such as powdery mildew and botrytis, as well as other pathogens that thrive in high humidity.

Different plant types will prefer different ideal vpd levels. Some plants, like cacti and other succulents, are adapted to arid environments with potentially high VPD levels. They have evolved various mechanisms to conserve water, such as reduced leaf surface area and the ability to store water in their tissues. On the other hand, plants native to humid, tropical environments, like orchids, may prefer lower VPD levels. These plants have evolved to thrive in conditions of high humidity and are typically more sensitive to water loss through transpiration.

I found this YouTube video best explained (at least to the way I see things) water vapor, temperature's relationship to Relative Humidity and VPD.

The humidifier is an evolution of the one in the YouTube video [How to Build a Homemade Humidifier Using Ultrasonic Misters / fogger](https://www.youtube.com/watch?v=vmiO6Z_HLCE).

The current software that sends ON / OFF messages to a MistBuddy device can be found in the [mistbuddy_lite github repo](https://github.com/solarslurpi/mistbuddy_lite).

# 🙏 Thanks to Those That Went Before
- **THANK YOU Theo Arends**. [Tasmota](https://tasmota.github.io/docs/), created by Theo Arends in 2016, was developed to solve key pain points in smart home devices, particularly the need for local control and open communication protocols like MQTT. The project has grown significantly, with its main GitHub repository now boasting over 21,700 stars and 4,700 forks, indicating its widespread adoption in the open-source community for ESP8266 and ESP32 based devices. Tasmota's integration with MQTT allows for efficient device control and monitoring without relying on proprietary cloud services.
- **THANK YOU Oak and Spore Mushroom Farm** for the video on [How to Build a Homemade Humidifier Using Ultrasonic Misters / fogger](https://www.youtube.com/watch?v=vmiO6Z_HLCE).  The directions were clear, easy to follow, and easy to customize.
- **THANK YOU mostlychris** for the video on [Tasmota on Sonoff. Flash the S31 plug with Tasmota firmware for local control](https://www.youtube.com/watch?v=9N58uy3ezvA).  Your directions were clear and made the process seem far less intimidating.


# Build the Humidifier
>**CAVEAT**: I have been using a build using these parts.  As in "it works for me."  I am not a professional.  I am sharing with in hopes it can benefit others.  I am not responsible for any damages to your home or property.

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

# Tasmotize Power Switches
In order to send mqtt messages to a power switch, the easiest way is to use a Tasmotized device.  The easiest way to do this is to reflash the [SONOFF S31 Lite plugs](https://amzn.to/3xnPWYc) with Tasmota.

The reasons for the S31 plug include:
- it uses the ESP8266 microcontroller with accessible flash memory and exposed programming pins, making it amenable to custom firmware.
- the S31 Lite doesn't incorporate hardware-level restrictions like dedicated encryption chips that would prevent firmware modifications.
- it is community supported.

## Buy Two S31 Lite Plugs
These directions assumed you have two [Sonoff S31 plugs](https://amzn.to/3xnPWYc) smart plugs.
## Flash the Smart Plugs
The Sonoff S31 (or S31 Lite) can be flashed so that Tasmota is running on the local wifi. [This YouTube video gives instructions on how to flash Tasmota](https://www.youtube.com/watch?v=9N58uy3ezvA).
ooh! Extra care when soldering.  If not, well...it is way too easy to rip off one of the pads...
>If soldering, it is easy to rip off the pads.  I found using [clamp fixture with pogo pins/ 2.54mm Single row 6P](https://www.aliexpress.us/item/3256804682713003.html?spm=a2g0o.order_list.order_list_main.15.4b181802cPkXRI&gatewayAdapt=glo2usa) from aliexpress to be the best way to flash without soldering.
