# Creating Hello World APK with Kivy on Android


# Prerequisites

Android device (Android 5.0 or higher)
Internet connection for downloading apps


Method: Using Pydroid 3
Step 1: Install Pydroid 3
Open Google Play Store
Search for "Pydroid 3"
Install the app

Open Pydroid 3
Step 2: Install Kivy Library
Open Pydroid 3
Tap the menu icon (☰) in the top-left
Select "Pip"
In the search box, type: kivy
Tap "INSTALL"
Wait for installation to complete (may take 5-10 minutes)

Step 3: Create the Hello World App
In Pydroid 3, tap the "+" button or go to File → New
Name the file: main.py
Copy and paste the following code:
python

```
from kivy.app import App
from kivy.uix.label import Label
from kivy.uix.boxlayout import BoxLayout
from kivy.core.window import Window

class HelloWorldApp(App):
    def build(self):
        # Set window background color
        Window.clearcolor = (0.1, 0.1, 0.1, 1)
        
        # Create a layout
        layout = BoxLayout(orientation='vertical', padding=20, spacing=10)
        
        # Create a label with Hello World text
        label = Label(
            text='Hello World!',
            font_size='40sp',
            bold=True,
            color=(1, 1, 1, 1)
        )
        
        # Add label to layout
        layout.add_widget(label)
        
        return layout

if __name__ == '__main__':
    HelloWorldApp().run()

```

Save the file: Tap the save icon or go to File → Save

Step 4: Run the Application
Tap the yellow play button (▶) at the bottom-right
The app will compile and run

You should see a black screen with "Hello World!" displayed in white text
Step 5: Stop the Application
Tap the stop button (■) or press the back button to exit



# Creating a Standalone APK (Requires Computer)

To create an actual installable APK file, you need to use a computer with Linux/WSL:

Requirements
Linux or Windows with WSL (Windows Subsystem for Linux)
Python 3.7+
Steps on Computer
Install Buildozer:

```
pip install buildozer
```

Create project folder and add main.py with the code above
Initialize Buildozer:

```bash

buildozer init
```

Edit buildozer.spec file:
ini
```
title = Hello World
package.name = helloworld
package.domain = org.example
source.include_exts = py,png,jpg,kv,atlas
requirements = python3,kivy
android.permissions = INTERNET
```
Build the APK:
```bash
buildozer -v android debug
```

Find your APK: The APK will be in the bin/ folder. Transfer it to your Android device and install.

Troubleshooting
Kivy Installation Fails in Pydroid 3
Ensure you have stable internet connection
Try installing dependencies first: pip install cython
Restart Pydroid 3 and try again
App Doesn't Run
Check if Kivy installed 


Permission Errors
Grant Pydroid 3 storage permissions in Android settings



# Summary
You've successfully created a Hello World Kivy application on Android! While Pydroid 3 doesn't create standalone APK files, it allows you to develop and run Kivy apps directly on your device. For production APKs, use Buildozer on a computer.

Content is user-generated and unverified.
