# ML Fitness Tracker
<!--- Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails! -->

<!--- ("Add a Hook Here* Something like: Ever wish you could track your fitness progress? Want a friend/device to count your never-ending reps? (Well,) Look no further. ). An Arduino powered, BLE (Bluetooth Low Energy) based fitness tracker that detects numerous exercises and records the number of repetitions on a user interface (Insert Name Here). -->

Ever wish you could track your fitness progress? Want a friendly device to count your never-ending reps? Well, Look no further. GetFit is an Arduino powered, BLE (Bluetooth Low Energy) based fitness tracker that detects numerous exercises and records the number of repetitions on a user interface (Insert Name Here).

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Sumire T | Homestead High School | Electrical Engineering | Incoming Senior

<!--- **Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.** -->

![Headstone Image](Sumire-Headshot.png){:height="50%" width="50%"}
  
# Final Milestone
<!--- For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe> -->
The goal for this milestone was to use my own machine learning model and upload it into the user interface with the working features (with the working counter).

For my third milestone, I first uploaded the code for my machine learning model built through Edge Impulse on the Arduino and installed my own library from my Edge Impulse ZIP files.

To get BLE features in my code, I pasted parts of the original code that included BLE function calls. After (Successfully) uploading the modified code to the Arduino Nano, the Arduino was successfully able to recognize the key features of the tracker: recognize each exercise and count the number of repetitions. It was apparent that the Arduino was able to recognize each exercise (side raises and lateral raises) after observing the given accuracy score for each exercise on the serial monitor when doing a certain exercise. For scores greater than 0.8, it indicated that the Arduino had recognized that one specific exercise. On the other hand, output scores less than 0.5 indicated that the Arduino did not recognize that specific exercise, and that one was most likely doing another exercise instead. The number of repetitions was displayed on the serial monitor and recorded in 2-second intervals.

I then created a new project on Firebase to establish a hosting site for my Arduino code and added the Firebase configuration to the srcript.js file to connect the files on my computer required for the user interface. (Ex: html files, css files, js files).

To set up the user interface, I modified the original source code so that it would accurately display only the necessary components of my project (Two exercises: side raises and arm circles) by removing the unused components in the index.html files. (The code for sit ups, planks, etc., as my version only counts side exercises and arm circles.)

However, while making these changes, the format of the user interface became disorganized, which led me to adjust the positions of the components in the user interface through editing the style.css file (Ex: place the button for arm circles down two columns, the button for side raises to the right 1 column, etc.).

I deployed my updated user interface through the command "firebase deploy" and opened the (generated) Firebase project link, "ml-fitness-tracker.web.app", which successfully displayed the features relevant to my machine learning model. (Only two exercises on main menu). After connecting the Arduino to the user interface through BLE, the counter accurately displayed the name of the exercises and recorded the number of repetitions, which meant that my own model was able to execute the features of the original file.

For my next milestone, I would like to make a juggling counter (instead of a fitness counter) by setting up an entirely new project and recreating the steps of the three milestones. 
 
Demo Video:


https://github.com/sumiretakeya/Sumire_Bluestamp_Portfolio/assets/107578593/f6969769-0264-4eab-8673-bed45a49b241


# Second Milestone
<!--- For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone --> 

For my second milestone, I trained my machine learning model from my collected data from two exercises on Edge Impulse, an embedded machine learning operations platform, and was able to get an accuracy of 96.64%, which I then proceeded to deploy into an Arduino zip library. (An automatically generated neural network with the best settings for the model)

I then made a new project in Firebase, an app development platform, to create a hosting site between the user interface and the Arduino bluetooth connection. I initialized the newly created project by running the command, "firebase init".

Additionally, I uploaded the original source code of the model library, to understand how the user interface establishes a Bluetooth Low Energy connection with the Arduino and works like a counter. I worked with the original source code and library, which I knew would upload without external errors, before uploading my own code and library into the Arduino Nano, (which I wasn't sure...). After uploading both the original source code and library zip file to the IDE, I uploaded it to the Arduino Nano.

I added the Firebase configuration to the script.js file of the original source file.

I then opened the website created through Firebase and enabled "Experimental Web Platform Features" by going to "chrome://flags" to access Bluetooth using Chrome.

When accessing the webpage "https://ml-fitness-tracker.web.app", which I created through Firebase, the user interface worked seamlessly, as I 
was able to successfully connect the Arduino Nano with a Bluetooth connection (the feature), and the counter of exercises worked, meaning that if one holding the Arduino Nano were to do one arm circle, the counter on the user interface would display an additional arm circle.

For my next milestone, I will use my own code and library from my machine learning model to set up the user interface and exercise counter.

<!--- **Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://youtu.be/xJzyyJrNCDw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe> -->

# First Milestone
<!--- For your first milestone, describe what your project is and how you plan to build it. You can include:
- An explanation about the different components of your project and how they will all integrate together
- Technical progress you've made so far
- Challenges you're facing and solving in your future milestones
- What your plan is to complete your project

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.** -->
 
My project is the machine-learning fitness tracker, a device one attaches to their arm that is powered by an Arduino through BLE (Bluetooth Low Energy) connection that detects different exercises (Ex: jumping jacks, squats, etc.) and ultimately records the number of repetitions on a user interface. 
For my first milestone, I first set up the Arduino (a microcontroller) by connecting it to Edge Impulse, a platform that uses embedded machine learning. I got the Arduino to be recognized by running the command "edge-impulse-daemon" on the terminal. 

To collect data in a similar manner to the actual armband, I made a prototype case by gluing cardboard pieces together. 
For the placement of the armband, I placed it in the middle of the lower part of the arm to accurately record the movements of the exercises. 
I collected data on two exercises: arm circles and lateral rises. I recorded the exercises on the Arduino at 30 second intervals. I repeated this four times for a total of 2 minutes of data per exercise then went around collecting data from two other people besides myself.
A challenge that I faced was finding a way to take accurate data with the armband, as I initially attached the armband too loosely on the upper part of the arm, which caused the Arduino unable to detect accurate movement. To solve this, I attached the armband on the middle of the lower part of the arm. 

Another challenge that I faced was initially only recording data from myself, which resulted in the model having a 100% accuracy, which meant that it was overtrained with my movements, and would not be able to detect the same exercise if another person were to try it. To solve this, I collected data from more people. 

For the next milestone, I will train the machine learning model on Edge Impulse and test it until I get good accuracy. 
<iframe width="560" height="315" src="https://www.youtube.com/embed/xJzyyJrNCDw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Schematics 
<!--- Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. -->

# Code
<!--- Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. -->
Here is the code that I used for this project. 

Arduino Code:
```c++
/* Edge Impulse ingestion SDK
 * Copyright (c) 2022 EdgeImpulse Inc.
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 * http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 *
 */

/* Includes ---------------------------------------------------------------- */
#include <stakeya-project-3_inferencing.h>
#include <Arduino_LSM9DS1.h> //Click here to get the library: http://librarymanager/All#Arduino_LSM9DS1
#include <Arduino_LPS22HB.h> //Click here to get the library: http://librarymanager/All#Arduino_LPS22HB
#include <Arduino_HTS221.h> //Click here to get the library: http://librarymanager/All#Arduino_HTS221
#include <Arduino_APDS9960.h> //Click here to get the library: http://librarymanager/All#Arduino_APDS9960
#include <ArduinoBLE.h>

// Global Variables

float threshold = 10;
float confidence = 0.8;
bool flag = false;
String Label;

//Blutooth service activating

BLEService fitness_service("e267751a-ae76-11eb-8529-0242ac130003");

BLEIntCharacteristic exercise("2A19", BLERead | BLENotify); 
BLEByteCharacteristic start("19b10012-e8f2-537e-4f6c-d104768a1214", BLERead | BLEWrite);
BLEByteCharacteristic pause("6995b940-b6f4-11eb-8529-0242ac130003", BLERead | BLEWrite);

BLEDevice central;

enum sensor_status { //Unique to this code
    NOT_USED = -1,
    NOT_INIT,
    INIT,
    SAMPLED
};

/** Struct to link sensor axis name to sensor value function */
typedef struct{ //Unique to this code
    const char *name;
    float *value;
    uint8_t (*poll_sensor)(void);
    bool (*init_sensor)(void);    
    sensor_status status;
} eiSensors;

/* Constant defines -------------------------------------------------------- */
#define CONVERT_G_TO_MS2    9.80665f
#define MAX_ACCEPTED_RANGE  2.0f        // starting 03/2022, models are generated setting range to +-2,
                                        // but this example use Arudino library which set range to +-4g. 
                                        // If you are using an older model, ignore this value and use 4.0f instead
/** Number sensor axes used */
#define N_SENSORS     18

/* Forward declarations ------------------------------------------------------- */
float ei_get_sign(float number);

bool init_IMU(void);
bool init_HTS(void);
bool init_BARO(void);
bool init_APDS(void);

uint8_t poll_acc(void);
uint8_t poll_gyr(void);
uint8_t poll_mag(void);
uint8_t poll_HTS(void);
uint8_t poll_BARO(void);
uint8_t poll_APDS_color(void);
uint8_t poll_APDS_proximity(void);
uint8_t poll_APDS_gesture(void);

/* Private variables ------------------------------------------------------- */
static const bool debug_nn = false; // Set this to true to see e.g. features generated from the raw signal

static float data[N_SENSORS];
static bool ei_connect_fusion_list(const char *input_list);

static int8_t fusion_sensors[N_SENSORS];
static int fusion_ix = 0;

/** Used sensors value function connected to label name */
eiSensors sensors[] =
{
    "accX", &data[0], &poll_acc, &init_IMU, NOT_USED,
    "accY", &data[1], &poll_acc, &init_IMU, NOT_USED,
    "accZ", &data[2], &poll_acc, &init_IMU, NOT_USED,
    "gyrX", &data[3], &poll_gyr, &init_IMU, NOT_USED,
    "gyrY", &data[4], &poll_gyr, &init_IMU, NOT_USED,
    "gyrZ", &data[5], &poll_gyr, &init_IMU, NOT_USED,
    "magX", &data[6], &poll_mag, &init_IMU, NOT_USED,
    "magY", &data[7], &poll_mag, &init_IMU, NOT_USED,
    "magZ", &data[8], &poll_mag, &init_IMU, NOT_USED,

    "temperature", &data[9], &poll_HTS, &init_HTS, NOT_USED,
    "humidity", &data[10], &poll_HTS, &init_HTS, NOT_USED,

    "pressure", &data[11], &poll_BARO, &init_BARO, NOT_USED,

    "red", &data[12], &poll_APDS_color, &init_APDS, NOT_USED,
    "green", &data[13], &poll_APDS_color, &init_APDS, NOT_USED,
    "blue", &data[14], &poll_APDS_color, &init_APDS, NOT_USED,
    "brightness", &data[15], &poll_APDS_color, &init_APDS, NOT_USED,
    "proximity", &data[16], &poll_APDS_proximity, &init_APDS, NOT_USED,
    "gesture", &data[17], &poll_APDS_gesture,&init_APDS, NOT_USED,
};

/**
* @brief      Arduino setup function
*/
void setup()
{
    /* Init serial */
    Serial.begin(115200);
    // comment out the below line to cancel the wait for USB connection (needed for native USB)
    //while (!Serial);
    Serial.println("Edge Impulse Sensor Fusion Inference\r\n");

    /* Connect used sensors */
    if(ei_connect_fusion_list(EI_CLASSIFIER_FUSION_AXES_STRING) == false) {
        ei_printf("ERR: Errors in sensor list detected\r\n");
        return;
    }
if (!BLE.begin()) {
      Serial.println("starting BLE failed!");

      while (1);
    }

    // BLE spremenljivke

    BLE.setLocalName("Get-Fit");
    
    BLE.setAdvertisedService(fitness_service);

    //Karakteristike
    
    start.setValue(0);
    pause.setValue(0);

    
    fitness_service.addCharacteristic(exercise); 
    fitness_service.addCharacteristic(start);
    fitness_service.addCharacteristic(pause);



    BLE.addService(fitness_service);

    BLE.advertise();

    Serial.println("Bluetooth device active, waiting for connections...");

    while(1) {
      Serial.println("HELLO");
      central = BLE.central();
      // if First negotiation with arduino and ble (via app) goes well then runs this loop that flashes LED, then breaks
      if (central) {
        Serial.print("Connected to central: ");
        // print the central's BT address:
        Serial.println(central.address());
        // turn on the LED to indicate the connection:
        digitalWrite(LED_BUILTIN, HIGH);

        break;
      }
    }
    /* Init & start sensors */

    for(int i = 0; i < fusion_ix; i++) {
        if (sensors[fusion_sensors[i]].status == NOT_INIT) {
            sensors[fusion_sensors[i]].status = (sensor_status)sensors[fusion_sensors[i]].init_sensor();
            if (!sensors[fusion_sensors[i]].status) {
              ei_printf("%s axis sensor initialization failed.\r\n", sensors[fusion_sensors[i]].name);             
            }
            else {
              ei_printf("%s axis sensor initialization successful.\r\n", sensors[fusion_sensors[i]].name);
            }
        }
    }
}

/**
* @brief      Get data and run inferencing
*/
void loop()
{
    if (central.connected()) 
    {
        start.read();
        pause.read();
    }
    if (start.value()) 
    {
        flag = true;
        //Serial.println("Started");
        start.setValue(0);
    }
    if(pause.value()) 
    {
         flag = false;
         //Serial.println("Stopped");
         pause.setValue(0);
    }
    ei_printf("\nStarting inferencing in 2 seconds...\r\n");
    
    if(flag == false)
    {
      return;
    }

    delay(2000);
  
    if (EI_CLASSIFIER_RAW_SAMPLES_PER_FRAME != fusion_ix) {
        ei_printf("ERR: Sensors don't match the sensors required in the model\r\n"
        "Following sensors are required: %s\r\n", EI_CLASSIFIER_FUSION_AXES_STRING);
        return;
    }

    ei_printf("Sampling...\r\n");

    // Allocate a buffer here for the values we'll read from the sensor
    float buffer[EI_CLASSIFIER_DSP_INPUT_FRAME_SIZE] = { 0 };

    for (size_t ix = 0; ix < EI_CLASSIFIER_DSP_INPUT_FRAME_SIZE; ix += EI_CLASSIFIER_RAW_SAMPLES_PER_FRAME) {
        // Determine the next tick (and then sleep later)
        int64_t next_tick = (int64_t)micros() + ((int64_t)EI_CLASSIFIER_INTERVAL_MS * 1000);

        for(int i = 0; i < fusion_ix; i++) {
            if (sensors[fusion_sensors[i]].status == INIT) {
                sensors[fusion_sensors[i]].poll_sensor();
                sensors[fusion_sensors[i]].status = SAMPLED;
            }
            if (sensors[fusion_sensors[i]].status == SAMPLED) {
                buffer[ix + i] = *sensors[fusion_sensors[i]].value;
                sensors[fusion_sensors[i]].status = INIT;
            }
        }

        int64_t wait_time = next_tick - (int64_t)micros();

        if(wait_time > 0) {
            delayMicroseconds(wait_time);
        }
    }

    // Turn the raw buffer in a signal which we can the classify
    signal_t signal;
    int err = numpy::signal_from_buffer(buffer, EI_CLASSIFIER_DSP_INPUT_FRAME_SIZE, &signal);
    if (err != 0) {
        ei_printf("ERR:(%d)\r\n", err);
        return;
    }

    // Run the classifier
    ei_impulse_result_t result = { 0 };

    err = run_classifier(&signal, &result, debug_nn);
    if (err != EI_IMPULSE_OK) {
        ei_printf("ERR:(%d)\r\n", err);
        return;
    }

    // print the predictions
    ei_printf("Predictions (DSP: %d ms., Classification: %d ms., Anomaly: %d ms.):\r\n",
        result.timing.dsp, result.timing.classification, result.timing.anomaly);
    for (size_t ix = 0; ix < EI_CLASSIFIER_LABEL_COUNT; ix++) {
        ei_printf("%s: %.5f\r\n", result.classification[ix].label, result.classification[ix].value);
    }
#if EI_CLASSIFIER_HAS_ANOMALY == 1
    ei_printf("    anomaly score: %.3f\r\n", result.anomaly);
    if(result.anomaly < threshold)
        {
            for (size_t ix = 0; ix < EI_CLASSIFIER_LABEL_COUNT; ix++)  
              {      
                 ei_printf("    %s: %.5f\n", result.classification[ix].label, result.classification[ix].value); 
                 //ei_printf("Test");
                 if(result.classification[ix].value > confidence )
                 {
                     Label = String(result.classification[ix].label);
                     Serial.println(Label);
                     if (Label == "ArmCircles")
                     {
                      //  Serial.println("Counter One Incremented");
                      //  counterOne += 1;
                       if (central.connected()) exercise.writeValue(0);
                       Serial.println("Data sent");
                     }
                     else if (Label == "LateralRaises")
                     {
                      //  Serial.println("Counter Two Incremented");
                      // counterTwo += 1;
                       if (central.connected()) exercise.writeValue(2);
                       Serial.println("Data sent");
                     }
                  }
               }
         }        
#endif
}


#if !defined(EI_CLASSIFIER_SENSOR) || (EI_CLASSIFIER_SENSOR != EI_CLASSIFIER_SENSOR_FUSION && EI_CLASSIFIER_SENSOR != EI_CLASSIFIER_SENSOR_ACCELEROMETER)
#error "Invalid model for current sensor"
#endif


/**
 * @brief Go through sensor list to find matching axis name
 *
 * @param axis_name
 * @return int8_t index in sensor list, -1 if axis name is not found
 */
static int8_t ei_find_axis(char *axis_name)
{
    int ix;
    for(ix = 0; ix < N_SENSORS; ix++) {
        if(strstr(axis_name, sensors[ix].name)) {
            return ix;
        }
    }
    return -1;
}

/**
 * @brief Check if requested input list is valid sensor fusion, create sensor buffer
 *
 * @param[in]  input_list      Axes list to sample (ie. "accX + gyrY + magZ")
 * @retval  false if invalid sensor_list
 */
static bool ei_connect_fusion_list(const char *input_list)
{
    char *buff;
    bool is_fusion = false;

    /* Copy const string in heap mem */
    char *input_string = (char *)ei_malloc(strlen(input_list) + 1);
    if (input_string == NULL) {
        return false;
    }
    memset(input_string, 0, strlen(input_list) + 1);
    strncpy(input_string, input_list, strlen(input_list));

    /* Clear fusion sensor list */
    memset(fusion_sensors, 0, N_SENSORS);
    fusion_ix = 0;

    buff = strtok(input_string, "+");

    while (buff != NULL) { /* Run through buffer */
        int8_t found_axis = 0;

        is_fusion = false;
        found_axis = ei_find_axis(buff);

        if(found_axis >= 0) {
            if(fusion_ix < N_SENSORS) {
                fusion_sensors[fusion_ix++] = found_axis;
                sensors[found_axis].status = NOT_INIT;
            }
            is_fusion = true;
        }

        buff = strtok(NULL, "+ ");
    }

    ei_free(input_string);

    return is_fusion;
}

/**
 * @brief Return the sign of the number
 * 
 * @param number 
 * @return int 1 if positive (or 0) -1 if negative
 */
float ei_get_sign(float number) {
    return (number >= 0.0) ? 1.0 : -1.0;
}

bool init_IMU(void) {
  static bool init_status = false;
  if (!init_status) {
    init_status = IMU.begin();
  }
  return init_status;
}

bool init_HTS(void) {
  static bool init_status = false;
  if (!init_status) {
    init_status = HTS.begin();
  }
  return init_status;
}

bool init_BARO(void) {
  static bool init_status = false;
  if (!init_status) {
    init_status = BARO.begin();
  }
  return init_status;
}

bool init_APDS(void) {
  static bool init_status = false;
  if (!init_status) {
    init_status = APDS.begin();
  }
  return init_status;
}

uint8_t poll_acc(void) {
  
    if (IMU.accelerationAvailable()) {

    IMU.readAcceleration(data[0], data[1], data[2]);

    for (int i = 0; i < 3; i++) {
        if (fabs(data[i]) > MAX_ACCEPTED_RANGE) {
            data[i] = ei_get_sign(data[i]) * MAX_ACCEPTED_RANGE;
        }
    }

    data[0] *= CONVERT_G_TO_MS2;
    data[1] *= CONVERT_G_TO_MS2;
    data[2] *= CONVERT_G_TO_MS2;
    }

    return 0;
}

uint8_t poll_gyr(void) {
  
    if (IMU.gyroscopeAvailable()) {
        IMU.readGyroscope(data[3], data[4], data[5]);
    }
    return 0;
}

uint8_t poll_mag(void) {
  
    if (IMU.magneticFieldAvailable()) {
        IMU.readMagneticField(data[6], data[7], data[8]);
    }
    return 0;
}

uint8_t poll_HTS(void) {
  
    data[9] = HTS.readTemperature();
    data[10] = HTS.readHumidity();
    return 0;
}

uint8_t poll_BARO(void) {
  
    data[11] = BARO.readPressure(); // (PSI/MILLIBAR/KILOPASCAL) default kPa
    return 0;
}

uint8_t poll_APDS_color(void) {
  
    int temp_data[4];
    if (APDS.colorAvailable()) {
        APDS.readColor(temp_data[0], temp_data[1], temp_data[2], temp_data[3]);

        data[12] = temp_data[0];
        data[13] = temp_data[1];
        data[14] = temp_data[2];
        data[15] = temp_data[3];
    }
}

uint8_t poll_APDS_proximity(void) {

    if (APDS.proximityAvailable()) {
        data[16] = (float)APDS.readProximity();
    }
    return 0;
}

uint8_t poll_APDS_gesture(void) {
    if (APDS.gestureAvailable()) {
        data[17] = (float)APDS.readGesture();
    }
    return 0;
}
```
UI Code:
```c++
*Code Here*
```
GitHub Link to Source Code:
https://github.com/CodersCafeTech/GetFit

GitHub Link to My Arduino Library:
(https://github.com/sumiretakeya/MlLibrary)

GitHub Link to My UI Files:
(https://github.com/sumiretakeya/htmlFile)

<!--- ```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
``` -->

# Bill of Materials
<!---- Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. -->
Here is the list of materials that I used for my project. One can either choose to make their own DIY case or 3D print it out. The cost breakdown of both options are listed below:

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Arduino Nano 33 BLE Sense with Headers | What the item is used for | $43.50 | <a href="https://store-usa.arduino.cc/products/arduino-nano-33-ble-sense-with-headers"> Link </a> |
| Anker PowerCore 5000 Portable Charger | Hardware, What the item is used for | $17.99 | <a href="https://a.co/d/bzSM61g"> Link </a> |
| 18" x 2" Cinch Strap | What the item is used for | $18.53 | <a href="https://a.co/d/isdqSpr"> Link </a> |
| Cardboard | Build a relatively sturdy case if 3D case is not an option |$0 - $9.81 | <a href="https://www.staples.com/Corrugated-Sheet-24-x-48-5-Bundle-SP2448/product_946708?cid=PS:GS:SBD:PLA:MS&gclid=CjwKCAjw-b-kBhB-EiwA4fvKrGfs_8eTA5h1a_B92vL9k0gwqHrUV5KCjFd3ZyT2keSoWiSbKTE8qhoCt64QAvD_BwE"> Link </a> |
| 3D Case | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

<!--- # Dimensions of 3D Case -->


<!--- # Dimensions of DIY Case -->

# Other Resources

Link to Helpful Websites Used to Complete this Project:
(https://docs.google.com/document/d/1gp4OPdYfRvL58Zp1qBMSvtmFS1bA3fpqKweGuT3sNpk/edit?usp=sharing)

Other:


<!--- # Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here. -->
