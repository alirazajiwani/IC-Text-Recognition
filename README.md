# IC-Text-Recognition

## System Architecture
The system comprises two principal components communicating via a TCP/IP socket connection, with each playing distinct roles:
### Client: PYNQ Board
Data acquisition and preprocessing unit.

Functionalities:
•	Initializes and streams live video using the onboard camera.
•	Monitors BTN0 as a user-trigger mechanism.
•	Captures frames upon user input.
•	Applies a multi-stage image preprocessing pipeline to enhance OCR readiness.
•	Serializes and transmits the processed frame to the server.

### Server: Host PC
Central processing and OCR analysis unit.

Functionalities:
•	Initializes a TCP server socket to accept client connections.
•	Deserializes the incoming image data.
•	Feeds the image into the PaddleOCR engine for text extraction.
•	Displays results with confidence scores in the terminal.
•	Appends output to a persistent file ocr_results.txt.


## Code Execution Guide:
1.	Run `PaddleOCR_PC.pynb`.
2.	Output: `Listening on 5002...`.
3.	Open and execute all cells in the PYNQ Jupyter notebook `PaddleOCR_PYNQ`.
4.	View the live camera feed in the notebook.
5.	Press `BTN0` on the board to capture a frame from the live video feed.
6.	Processing of the image will begun and it will be sent to Host PC.
7.	OCR results are shown on the PC and saved to a `ocr_results.txt` file.

### Free port identification:

Open Command Prompt and run,

`netstat -aon | findstr :5000`	//replace 5000 with a port number you want to check

If it returns nothing, that port is likely free.
If it shows a line, the port is in use.
