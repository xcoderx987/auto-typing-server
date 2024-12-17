# auto-typing-server
A server that will automatically type the text sent from your smartphone through the Copy Cat app (link to the app will be updated soon) on the any text editor in your laptop.
Connect your app and your laptop over the same Wi-Fi network.

**Copy the following script:**
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

**Paste it in notepad and save as server.bat file.**

Open the bat file, it will do the required setup automatically and will run the server on your laptop.

Now enter the IP address of your laptop in the app and press connect.

Your app is connected with your laptop and you are able to send data from your phone to your laptop for automatic typing.
