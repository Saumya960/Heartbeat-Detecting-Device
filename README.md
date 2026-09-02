# Heartbeat-Detecting-Device
Heartbeat_Monitoring-device
1st year group project
The program was implemented to run as a standalone system. It receives signals from the sensor and is analysed by the algorithm. The algorithm follows a set of logical conditions which help to detect accurate human heartbeats.
Here is the logical flow of the algorithm.
1) The program starts when the user presses the rotary encoder button.
2) The algorithm is split into two sections: Determining the mean threshold and Peak detection.
3) First two seconds of data will be read to determine the mean threshold. The peak detection program starts once the mean threshold is available.
4) The mean threshold program continuously provides a new value every two seconds.
5) The peak is determined by the slope deflection method. I.e. The peak is identified when the slope of the tangent line is zero.
6) Once the first peak is identified the program checks whether the signal value is less than the mean threshold. At this point, the signal value is saved as max value and sample count was saved temporarily.
7) If the previous logic is unsatisfied, it checks whether the signal value is greater than the previously identified peak value (max value).
8) If the signal value exceeds the max value, the max value and sample count will be updated with the latest values.
9) If the signal value goes below the mean threshold level, the peak is confirmed, and sample count is saved permanently, and the max value is set to zero.
10)This process will run continuously until the user presses the button again to stop the program.
This is the process of the algorithm, and it filters the noisiness of the signal by avoiding fake peaks. Heartbeat (BPM) is calculated based on the sample count between two peaks. BPM is set to calculate every 5 seconds and it is displayed on the LED display.
