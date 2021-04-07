
# esp-homekit-fan
ESP8266 HOMEKIT CODE FOR FAN (PWM)

## STEPS TO FOLLOW 

## STEPS TO INSTALL LIBRAY


### 1. First download the library from https://github.com/Mixiaoxiao/Arduino-HomeKit-ESP8266
### 2. Go to Arduino --> Sketch -->  Include library --> Add .ZIP library 
### 3. Select the "Arduino-HomeKit-ESP8266-master" file from the extracted folder.
--------------------------------------------------------------------------------------------------------------------------------

## STEPS TO COMPILE THE CODE AND UPLOAD 

### 1. DOWNLOAD THE CODE FOLDER.
### 2. Open the CODE.ino file.
### 3. Change the ssid and pass in wifi_info.h .
### 4. Compile the code.
--------------------------------------------------------------------------------------------------------------------------------

## Steps for pairing 

```
homekit_accessory_t *accessories[] = {
  HOMEKIT_ACCESSORY(.id = 1, .category = homekit_accessory_category_fan, .services = (homekit_service_t*[]) {
    HOMEKIT_SERVICE(ACCESSORY_INFORMATION, .characteristics = (homekit_characteristic_t*[]) {
      HOMEKIT_CHARACTERISTIC(NAME, "FAN"),
      HOMEKIT_CHARACTERISTIC(MANUFACTURER, "HOMEKIT"),
      HOMEKIT_CHARACTERISTIC(SERIAL_NUMBER, "1234567"),
      HOMEKIT_CHARACTERISTIC(MODEL, "FAN"),
      HOMEKIT_CHARACTERISTIC(FIRMWARE_REVISION, "0.1"),
      HOMEKIT_CHARACTERISTIC(IDENTIFY, my_accessory_identify),
      NULL
    }),
    HOMEKIT_SERVICE(FAN, .primary = true, .characteristics = (homekit_characteristic_t*[]) {
      &fan_on,
      &rotation_speed,
      NULL
    }),
    NULL
  }),
  NULL
};

homekit_server_config_t config = {
  .accessories = accessories,
  .password = "111-11-111"
};
```
--------------------------------------------------------------------------------------------------------------------------------

### In the password section you can change the pass by default its 111-11-111.

