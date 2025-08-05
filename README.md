# IC-Text-Recognition

## How to run the code:

1. Run 'PaddleOCR_PC'.
2. It will show 'Listenining on 5002...'
3. After that, run the 'PaddleOCR_PYNQ' notebook.
4. Serial connection will be build and OCR will begin in 'PaddleOCR_PC' after frame capturing.

### Free port identification:

Open Command Prompt and run,

'netstat -aon | findstr :5000'	//replace 5000 with a port number you want to check

If it returns nothing, that port is likely free.
If it shows a line, the port is in use.
