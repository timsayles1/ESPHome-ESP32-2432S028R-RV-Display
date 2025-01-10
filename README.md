# ESPHome-ESP32-2432S028R-RV-Display
RV Specific display panel for the CYD ESP32-2432S028R LCD

The "ESP32-2432S028R", an ESP32 with a built in 320 x 240 2.8" LCD display with touch screen, is colloquially known as the "Cheap Yellow Display" or CYD. It's about $15 delivered and offers an easy, no-solder touch display to control your smart home. It is supported in ESPHome and can be used to easily visualize Home Assistant entities and control Home Assistant itself, straight out of the box. 

In order to gather bluetooth data, you will need a separate ESP32 device (basic no display one) as enabling BLE tracking on the CYD will cause the display to crash.

I have tried several TPMS monitors for my RV and I have found the TireLinc to be the most reliable (although most expensive) monitors. 


**Files:**

templates.yaml - Accumulates all the data from various sensors to send to the LCD display. Not 100% needed as you can code the sensors directly into the ESPHome code instead.

sensors.yaml - Settings for Google Geocode integration to pull from Starlink.

automations.yaml - Automations to update longitude and latitude for Home Assistant and ARVEE from Starlink location.

esp-32-ble.yaml - EspHome code for the ESP32-C3 Dev Board as bluetooth receiver and proxy.

esp-32-display.yaml - EspHome code for the CYD LCD display.

lci-4ch-relay.yaml - EspHome code for the LCI 4 Channel 12 Volt ESP-01 Relay. After initial programming you will need to press the S1 button.

/fonts/ - Fonts you need to upload to EspHome for LCD Display.


**The display performs the following functionality:**

Using my Starlink satellite, I am able to obtain the GPS Longitude and Latitude for my exact location. I am able to feed the coordinates to geocode my location as well as update weather information.


**Main Screen:**
The display allows 3 button controls at the top of the main screen. I am controlling two LED lights via a ESP-01 4 channel relay as well as arming my Blink security camers.

The middle of the display shows my power usage and propane tank levels.

The bottom of the main display shows current inside and outside temperatures.

![IMG_7405](https://github.com/user-attachments/assets/8bf408c5-6fdf-4618-94d2-2ed6c29ca7c8)



**Second Screen:**

Displays my current TireLinc TMPS pressures

![IMG_7407](https://github.com/user-attachments/assets/a21dfff6-c1f3-4159-9713-64c535e80df8)



**Third Screen:**

Displays current and 4 day weather forcast

![IMG_7406](https://github.com/user-attachments/assets/64957465-87f1-45f0-b31c-aa1e3af11b97)



**Items Needed:**

Home assistant device
ESP32-C3 Development Board (for bluetooth)

![esp32-c3-devkitm-1](https://github.com/user-attachments/assets/516e3863-e476-4962-9d3c-00f6c93e7a04)

ESP32-2432S028R

![2432s](https://github.com/user-attachments/assets/57d84bd8-06b5-45b9-ac06-d82c7f45426a)


LCI ESP-01 4 Channel 12 Volt Relay (Optional)

![lci-4ch](https://github.com/user-attachments/assets/ec4de490-5324-4654-ac92-51b990f24b45)


**Items Integrated:**

Power Watchdog EPO Power Management / Surge Supressor

![hu87fr_11](https://github.com/user-attachments/assets/996e5353-9bb8-4d2e-9860-f8f7e5edb54d)

TireLinc TPMS Sensors

![tirelinc](https://github.com/user-attachments/assets/8aa58d1a-8bad-4acb-ad42-d7332d56a793)

Mopeka Standard Check Propane Sensors

![107376_Mopeka_Standard Gas](https://github.com/user-attachments/assets/ff91f4cc-75e8-44cb-a29b-9a60e55be185)

Tuya Wifi Temperature / Humidity

![tyua](https://github.com/user-attachments/assets/f1589158-1044-4f94-82a0-ce956198b0fb)


**Home Assistant Integrations Needed:**


HACS - TireLinc integration (TireLinc TMPS Integration)
  https://github.com/k3vmcd/tirelinc


HACS - ARVEE (Timezone Geolocation via long/lat)
  https://github.com/mikegoubeaux/hass-arvee-timezonefinderL


HACS - Google Geocode (Location Geocode via long/lat)
  https://github.com/gregoryduckworth/GoogleGeocode-HASS


Home Assistant Integration - StarLink


Home Assistant Integration - Tuya


Home Assistant Integration - Met.No


Home Assistant Add-on - EspHome
