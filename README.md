# ST-Vacation-Manager
Vacation Manager SmartApp for SmartThings

# Summary
Automatically puts home in a vacation mode after you're gone and manages a visiting house sitter

This app allows you to extend SmartThings to effectively create a vacation mode that is automatically triggered after a selected sway time.  For instance, you might want to turn off the water or gas when you're on vacation but you might not want to do that all the time when you're in and out of the house.  Vacation Manager also allows you to have a house sitter, dog walker, pet feeder, plant waterer or whathaveyou stop by for a visit and turns on devices for their visit.

# Required Devices
None.  It is also suggested to use the app in conjunction with a water or gas valve but that is by no means required.

However, there are a few suggestions:
1. It is highly suggested to create a vacation mode that is different than the default Away mode.  Additionally, to avoid an unexpected transition out of the vacation mode, inspect other routines such as Good Morning! and Goodnight! to ensure that they don't execute mode changes during a vacation (plus they would be largely unnecessary since no one is there anyhow).  

2. It is highly suggested to create a vacation routine such as "I'm on Vacation!".  This will allow you to pick and choose how devices are turned off for vacation (either in the app or via the routine that the app invokes).  Duplication isn't an issue (turning off a light or valve in both places) and it gives you some insurance on the off chance that the device does not receive the command the first time.  Another reason is that the app does not implement controls of HVAC, locks or other things that are well taken care of by a routine where duplication is unnecessary.

3. For the House Sitter, it is suggested to use a device like the SmartThings Arrival fob or similar but any presence sensor can be used.  It is advisable to have the app execute your "Goodbye!" or similar routine after the House Sitter leaves so as to ensure that everything is secure.

# Installation

The SmartApp is installed as a custom app in the SmartThings mobile app via the "My Apps" section.  Therefore, the app must first be installed into your SmartThings SmartApps repository.

## Installation via GitHub Integration
1. Open SmartThings IDE in your web browser and log into your account.
2. Click on the "My SmartApps" section in the navigation bar.
3. Click on "Settings"
4. Click "Add New Repository"
5. Enter "LLWarrenP" as the namespace
6. Enter "ST-Vacation-Manager" as the repository
7. Hit "Save"
8. Select "Update from Repo" and select "ST-Vacation-Manager"
9. Select "smartapps/vacation-manager.src/vacation-manager.groovy"
10. Check "Publish" and hit "Execute Update"

## Manual Installation
1. Open SmartThings IDE in your web browser and log into your account.
2. Click on the "My SmartApps" section in the navigation bar.
3. On your Device Handlers page, click on the "+ Create New SmartApp" button on the right.
4. On the "New SmartApp" page, Select the Tab "From Code", Copy the "vacation-manager.groovy" source code from GitHub and paste it into the IDE editor window.
5. Click the blue "Create" button at the bottom of the page. An IDE editor window containing the SmartApp code should now open.
6. Click the blue "Save" button above the editor window.
7. Click the "Publish" button next to it and select "For Me". You have now self-published your SmartApp.

# App Settings
All settings are well documented in the app but here are a few highlights:

**Change to this mode for vacation - After how many hours?** The intent of the app is to move to vacation mode after you're gone for a period of time longer than normal, such as 18+ hours.  If you want the mode to be activated sooner, you can set it to a lower tolerance, but keep in mind that this is designed to work *after* the SHM sets you as "Away" and arms the system so that is why it is advisable to set the time to what you would consider to be a vacation time.

**Turn them back on when I return?** and **Turn them off when they leave?** These are designed to simply toggle whatever was turned on manually in the app and does not undo/redo any routine.  Also keep in mind that when you return from vacation your SHM (typically) will transition from the vacation mode to Home and will (typically) also execute "I'm Back!" for you automatically.

# App Logging
The app will log some basic goings on (visible in the IDE Live Logging) such as when the vacation mode is being activated and when a house sitter arrives and departs (which are also possible via push or SMS).  Additionally, if you use any routines, the SHM will log those for you independently (visible in the app).
