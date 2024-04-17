# Soil-Moisture-Air-Quality-Code
int air_quality_sensor_pin = A0;
int soil_moisture_sensor_pin = A1;
void setup() {
 Serial.begin(9600);
 pinMode(air_quality_sensor_pin, INPUT);
 pinMode(soil_moisture_sensor_pin, INPUT);
}
void loop() {
 // Reading air quality sensor data
 int air_quality_sensor_data = analogRead(air_quality_sensor_pin);
 Serial.print("Air Quaality Sensor Data: ");
 Serial.println(air_quality_sensor_data);
 // Reading soil moisture sensor data
 int soil_moisture_data = analogRead(soil_moisture_sensor_pin);
 Serial.print("Soil Moisture Sensor Data: ");
 Serial.println(soil_moisture_data);
 // Analyzing Air quality sensor data (example thresholds)
 if (air_quality_sensor_data > 800) {
 Serial.println("Bad Air Quality!");
 } else if (air_quality_sensor_data >= 500 && air_quality_sensor_data <= 
800) {
 Serial.println("Minimal Air Quality");
 } else {
 Serial.println("Best Air Quality");
 }
 // Analyzing soil moisture data (example thresholds)
 if (soil_moisture_data > 950) {
 Serial.println("No moisture, Soil is dry");
 } else if (soil_moisture_data >= 400 && soil_moisture_data <= 950) {
 Serial.println("There is some moisture, Soil is medium");
 } else {
 Serial.println("Soil is wet");
 }
delay(2000); // Delay for 2 second between readings
}
