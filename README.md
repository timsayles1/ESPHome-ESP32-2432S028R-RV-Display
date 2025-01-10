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

![IMG_7405](https://github.com/user-attachments/assets/32129d0c-295d-4515-8cb6-4885ce547919)


**Second Screen:**

Displays my current TireLinc TMPS pressures

![IMG_7407](https://github.com/user-attachments/assets/295d0e1f-ffa7-4dc0-8eb6-40c95cfa1e5d)


**Third Screen:**

Displays current and 4 day weather forcast

![IMG_7406](https://github.com/user-attachments/assets/e64a2d67-31b7-44e5-8f60-156db43d736b)


**Items Needed:**

Home assistant device
ESP32-C3 Development Board (for bluetooth)
![esp32-c3-devkitm-1](https://github.com/user-attachments/assets/443c235f-3250-4747-b80d-684a30d5530f)

ESP32-2432S028R
![2432s](https://github.com/user-attachments/assets/948de2d3-8d15-4942-b361-7029f41de4b7)

LCI ESP-01 4 Channel 12 Volt Relay (Optional)
![lci-4ch](https://github.com/user-attachments/assets/30f1ed1b-303c-4b85-96c2-8f4dedeaf7bc)


**Items Integrated:**

Power Watchdog EPO Power Management / Surge Supressor
![hu87fr_11](https://github.com/user-attachments/assets/23e95754-7918-4f00-b113-1255e31b0d75)

TireLinc TPMS Sensors
![tirelinc](https://github.com/user-attachments/assets/60594e8f-3004-42de-9196-458a7e42f593)

Mopeka Standard Check Propane Sensors
![107376_Mopeka_Standard Gas](https://github.com/user-attachments/assets/59be7ba3-2cf2-4ebb-be9a-f0c78c1c2ed8)

Tuya Wifi Temperature / Humidity
![tyua](https://github.com/user-attachments/assets/d8099941-4a2e-4993-aefd-0c33f30b64d3)


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
