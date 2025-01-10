# ESPHome-ESP32-2432S028R-RV-Display
RV Specific display panel for the CYD ESP32-2432S028R LCD

The "ESP32-2432S028R", an ESP32 with a built in 320 x 240 2.8" LCD display with touch screen, is colloquially known as the "Cheap Yellow Display" or CYD. It's about $15 delivered and offers an easy, no-solder touch display to control your smart home. It is supported in ESPHome and can be used to easily visualize Home Assistant entities and control Home Assistant itself, straight out of the box. 

In order to gather bluetooth data, you will need a separate ESP32 device (basic no display one) as enabling BLE tracking on the CYD will cause the display to crash.


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


**Second Screen:**

Displays my current TireLinc TMPS pressures


**Third Screen:**

Displays current and 4 day weather forcast


**Items Needed:**

Home assistant device
ESP32-C3 Development Board (for bluetooth)
ESP32-2432S028R
LCI ESP-01 4 Channel 12 Volt Relay (Optional)


**Items Integrated:**

Power Watchdog EPO Power Management / Surge Supressor

TireLinc TPMS Sensors

Mopeka Standard Check Propane Sensors

Tuya Wifi Temperature / Humidity


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
