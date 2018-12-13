# Example using the Modular Sensors Library to Save Data to an SD card and Send data to the EnviroDIY Data Portal

This shows the use of an "EnviroDIY logger" object for an AVR board.  It takes the simple_logging example one step farther in creating a modem object that is used to send data to the EnviroDIY data portal.  Before using this example, you must register a site and sensors at the data portal (http://data.envirodiy.org/).  After you have registered the site and sensors, the portal will generate a registration token and universally unique identifier (UUID) for each site and further UUID's for each variable.  You will need to copy all of those UUID values into your sketch to replace the "12345678-abcd-1234-efgh-1234567890ab" place holders in this example.  Please do not try to run the example exactly as written, but delete the chunks of code pertaining to sensors that you do not have attached.

const char *REGISTRATION_TOKEN = "127c29cd-d5ff-49a4-8183-21b46d612116";   // Device registration token
const char *SAMPLING_FEATURE = "33e8837a-afea-4c0f-b702-d127919657d2";     // Sampling feature UUID
const char *UUIDs[] =                                                      // UUID array for device sensors
{
    "baa55568-e4ad-4114-aa70-5d4a41652ddd",   // Battery voltage (EnviroDIY_Mayfly_Batt)
    "2fb1f21c-c8b4-43f1-a87e-c06196cf951f",   // Temperature (Maxim_DS3231_Temp)
    "6432c166-3ba0-4b59-9597-c9bb1558fdc4",   // Barometric pressure (Bosch_BME280_Pressure)
    "ce5756f1-224d-46f2-b18e-815ff4e0feb2"    // Relative humidity (Bosch_BME280_Humidity)
};