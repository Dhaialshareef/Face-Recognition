# Face-Recognition
This code uses the HUSKYLENS sensor for face recognition with Arduino. Here’s an explanation of the important parts:

1. HUSKYLENS.h Library:
The HUSKYLENS library is included to interact with the HUSKYLENS sensor via I2C communication.

3. huskylens Object:
An object huskylens of type HUSKYLENS is created, which is used to communicate with the sensor.

5. ID Definitions:
Variables ID0, ID1, and ID2 are defined to represent the "learned results" stored in HUSKYLENS. For example, ID1 corresponds to the first learned face.

7. Setup Function:
Wire.begin() is used to initialize the I2C communication.
The code checks if HUSKYLENS is connected properly.
The face recognition algorithm is selected using huskylens.writeAlgorithm(ALGORITHM_FACE_RECOGNITION).

9. Main Function loop():
The code checks if "learned faces" or "objects" are stored in HUSKYLENS using huskylens.requestLearned() and huskylens.requestBlocksLearned().
If learned faces are available, it checks the number of detected learned faces (huskylens.count(ID1)) and prints the result to the Serial Monitor. If a learned face is detected, it prints "Learned face detected"; otherwise, it prints "Learned face not detected".

11. Result Checking:
If the number of detected learned faces (arj) is different from the previous value (arjprevious), it prints an appropriate message based on whether a learned face is detected or not.
