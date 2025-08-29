# IC-Text-Recognition


## System Architecture
The system comprises two principal components communicating via a TCP/IP socket connection, with each playing distinct roles:


<img width="2286" height="747" alt="image" src="https://github.com/user-attachments/assets/c5e1cd89-7728-4948-8abb-75c7072de969" />


## Internet Access to the Board

1.	Power up the board with PYNQ image.
2.	Press `Windows+R` on the HOST PC and type `ncpa.cpl` and Enter.
3.	If there is no connection to the PC/Laptop other than Internet connection and Ethernet (PYNQ board) then allow `mobile hotspot` on the PC to enable the drop-down menu in the `sharing section` in properties menu.
4.	Right click on the the connection from you have internet access. Go to:
Properties-> Sharing -> Check the `Allow other network users to connect through the computer's internet connection`, And press `OK`.
6.	Check the ethernet (connected to board) ipv4 address through properties. It should be `192.168.137.1`.

**NOW THE BOARD HAS INTERNET ACCESS**

### To Check the new IP Address of the board: 
Normally, when the board is used locally with no internet access, the default ip address of the board is `192.168.99.2`. But, due to the new ipv4 address alotted to the HOST PC, a new ip address is given to the board by the PC. 

1.	Download the `ipaddress.bat` file into the PC.
2.	Run the `.bat` file and wait for it to detect the ipaddress of the PYNQ board. 
3.	Type the detected ipaddress on your web browser and access the jupyter notebook. 
4.	Verify the internet access by typing `ping goolge.com` in terminal.

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
