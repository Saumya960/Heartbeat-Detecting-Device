# Heartbeat Monitoring Device

This project was developed as a 1st-year group assignment. The system runs as a standalone device that receives signals from a heartbeat sensor and processes them using a custom algorithm. The algorithm filters noise, detects accurate peaks, and calculates human heartbeats in BPM.

## 🔧 How the Algorithm Works

1. The program starts when the user presses the rotary encoder button.
2. The algorithm is divided into two main parts:
   - Determining the mean threshold
   - Peak detection
3. The first two seconds of sensor data are used to calculate the initial mean threshold. Peak detection begins once this threshold is available.
4. The mean threshold is continuously updated every two seconds.
5. Peaks are detected using the slope deflection method — a peak is identified when the slope of the tangent line becomes zero.
6. After detecting the first peak, the algorithm checks if the signal value drops below the mean threshold. If so, the current signal value is saved as the max value and the sample count is stored temporarily.
7. If the signal does not drop below the threshold, the algorithm checks whether the signal value exceeds the previously saved max value.
8. If the signal exceeds the max value, both the max value and sample count are updated.
9. When the signal finally drops below the mean threshold, the peak is confirmed. The sample count is saved permanently and the max value is reset to zero.
10. This process repeats continuously until the user presses the button again to stop the program.

## ❤️ BPM Calculation

The algorithm avoids false peaks by applying logical filtering conditions.  
BPM is calculated based on the number of samples between two confirmed peaks.  
The BPM value is updated every 5 seconds and displayed on the LED display.

## 📷 Device Image

![Device Image](Heartbeat%20Monitoring%20Device.jpg)

