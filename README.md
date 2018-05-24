# Controlling-Mouse-Pointer-through-face-movements
Controlling mouse events such as movement, single click, double click, right click, etc using face movement througImpo
#install all necessary packages like numpy,opencv, win32api, pyautogui

Importing all necessary packages like opencv, win32api, pyautogui
Loading face HaarCasscade xml file
Loading live video
Getting initial cursor position
#For single click we wish to gaze at point for 2 sec, based on frame rate of your webcam initialize the array of that size*2 (since 
#framerate is persecond and we need gaze for 2 seconds), Similarly for right click we wish to gaze for nearly 3.5secs so initial array for the required

Now read each frame using .read() function
Convert the frame into GrayScale #HaarCasscade works best on grayScale
In the frame look for face
For simplicity draw rectangle around the face
#Now our face on screen is represented in just small part of it, so face movement in that part won't cover the complete screen
#Thus scaling the movement based on screen size (my laptop screen is 1365*767px and hence I scaled X-coordinate to 3 and Y-coordinate to 4 
#and to keep them within screen boundary I found the mod of those numbers).

Now set the cursor postion with this new position
For each new frame add the position coordinated in array and incrementr array index
#Checking for right click- (If all the coordinates of last 3.5 secs are in range of 30*30px its a long gaze hence invovke righr click function)
#If its not right click check for click in same way

If long gaze invoke right click
If small gaze invoke left click

Space Key can be used to terminate the process
Fianlly relaese video
