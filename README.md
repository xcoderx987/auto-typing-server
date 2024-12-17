**Auto-Typing Server:**

The Auto-Typing Server is a utility that allows seamless integration between your smartphone and laptop for automated typing. Using the Copy Cat app (link to be updated soon), you can send text from your smartphone to your laptop, where it will be automatically typed into any text editor.


**Features:**

Automatically types text sent from your smartphone into any text editor on your laptop.

Connects your app and laptop over the same Wi-Fi network for easy setup.

Simple and automated server setup.

**Instructions:**

**Prerequisites:**

Ensure your laptop and smartphone are connected to the same Wi-Fi network.

Download the Copy Cat app (link to be provided soon).


**Step 1: Download and Set Up the Server**

**Copy the script below:**

@echo off

setlocal

REM Set the file name and URL

set "file=auto_typing_server"

set "url=https://github.com/sumit91221/auto-typing-server/raw/main/auto_typing_server.exe"

REM Check if the file already exists

if not exist "%file%" (

    echo File '%file%' not found. Downloading...
    
    REM Download the server executable using PowerShell
    
    powershell -Command "Invoke-WebRequest -Uri '%url%' -OutFile '%file%'"
    
    if %errorlevel% neq 0 (
    
        echo Failed to download the server executable. Please check your internet connection and try again.
        
        pause
        
        exit /b 1
        
    )
    
) else (

    echo File '%file%' already exists. Skipping download.
    
)


REM Unblock the downloaded executable

echo Unblocking the server executable...

powershell -Command "Unblock-File -Path .\%file%"

if %errorlevel% neq 0 (

    echo Failed to unblock the server executable. Please ensure you have the necessary permissions.
    
    pause
    
    exit /b 1
    
)


REM Run the server executable and wait for it to complete

echo Running the server executable...

"%file%"

if %errorlevel% neq 0 (

    echo Failed to run the server executable. Please ensure all dependencies are installed and try again.
    
    pause
    
    exit /b 1
    
)


echo Press any key to exit...

pause

endlocal

Paste the script into Notepad.


**Save the file as server.bat (ensure the file extension is .bat and not .txt).**

**Step 2: Run the Server**

Double-click on the server.bat file.

This will automatically download, unblock, and set up the server on your laptop.

Once the setup is complete, the server will run and wait for connections.

**Step 3: Connect the App to the Server**

Open the Copy Cat app on your smartphone.

Enter the IP address of your laptop in the app’s connection settings.

Press Connect.

Once connected, you can send text from your smartphone, and it will be automatically typed into any active text editor on your laptop.


**Notes**

Ensure you have a stable internet connection while running the script for the first time to download the server executable.

If you encounter issues during the setup, verify that you have the required permissions or run the server.bat file as an administrator.

This script unblocks the downloaded file to ensure smooth execution. If additional dependencies are required, follow the on-screen prompts.

**Troubleshooting**

Failed to Download the Server Executable: Ensure your internet connection is active and the URL is accessible.

Permissions Issues: Run the script as an administrator.

Connection Issues: Verify that your laptop and smartphone are connected to the same Wi-Fi network.

With these simple steps, your Auto-Typing Server is ready to use!
