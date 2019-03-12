# [whereis.contolini.com](https://whereis.contolini.com/)

An easy, battery-efficient way to share your location on a map while you wander aimlessly through life.
Your location will be logged in the background and uploaded whenever a data connection is available.

Uses ThingSpeak, MapBox and the [GPSLogger](https://github.com/mendhak/gpslogger/) mobile app.

## Set up ThingSpeak

1. Create a [ThingSpeak](https://thingspeak.com) account.
1. Create a [new channel](https://thingspeak.com/channels/new) with the following properties:
    - Name: gps
    - Field 1: time
    - Field 2: lat
    - Field 3: lon
    - Field 4: satellites
    - Field 5: altitude
    - Field 6: speed
    - Field 7: direction
    - Field 8: battery
1. Set the channel's sharing setting to "Share channel view with everyone"

## Set up mobile app

1. Install [gpslogger](https://github.com/mendhak/gpslogger) on your Android device.
1. Go into setting and "Log to custom URL".
1. Enter `https://api.thingspeak.com/update?api_key=XXXXXXXXX&field1=%TIME&field2=%LAT&field3=%LON&field4=%SAT&field5=%ALT&field6=%SPD&field7=%DIR&field8=%BATT` where `XXXXXXXXX` is your ThingSpeak channel's API key (available in your channel's settings)
1. Adjust logging intervals and whatever else you want under settings.

There are probably iPhone apps that do similar logging. LMK if you find one.

## Set up your website

1. Fork this repo. Edit your forked repo's settings to serve GitHub Pages from [master](https://help.github.com/en/articles/configuring-a-publishing-source-for-github-pages).
1. Edit a [couple variables](https://github.com/contolini/whereis/blob/master/index.html#L40-L48) in index.html.
1. Edit the [CNAME file](https://github.com/contolini/whereis/blob/master/CNAME) with your proper URL (or delete it).

Log a few requests and see if they appear on the map that hopefully renders. Board a plane and set the app to record your position once every 15 minutes. Have a nice trip and stay safe.
