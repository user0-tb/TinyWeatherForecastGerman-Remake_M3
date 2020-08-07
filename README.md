Tiny Weather Forecast Germany
=================================

An android app with a widget that presents a 24 hours weather forecast based on open data from the Deutscher Wetterdienst (DWD).

Screenshots
--------

![Screenshot #1](fastlane/metadata/android/en-US/images/phoneScreenshots/1.png)
![Screenshot #2](fastlane/metadata/android/en-US/images/phoneScreenshots/2.png)
![Screenshot #3](fastlane/metadata/android/en-US/images/phoneScreenshots/3.png)


How to get the app
------------------

This app is currently in a beta state, current official builds are not available yet - but this will shortly change.

You get builds for testing here: <https://kaffeemitkoffein.de/nextcloud/index.php/s/NxjPfLNfAfYB9PN>

License
-------

 Copyright (c) 2020 Pawel Dube

 This program is free software: you can redistribute it and/or modify it
 under the terms of the GNU General Public License as published by the
 Free Software Foundation, either version 3 of the License, or (at
 your option) any later version.

 Tiny 24h Weather Forecast Germany is distributed in the hope that it will be useful, but
 WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
 General Public License for more details.

 You should have received a copy of the GNU General Public License
 along with Imagepipe. If not, see <http://www.gnu.org/licenses/>.

Credits
-------

 The Material Design icons are Copyright (c) by Google Inc., licensed 
 under the Apache License Version 2.0.
 
 This app uses gradle and the gradle wrapper, Copyright by Gradle Inc,
 licensed under the Apache 2.0 license.
 
 Data source: Deutscher Wetterdienst, own elements added, some data 
 averaged over individual values.
 
 This program uses the WeatherSpec class of Gadgetbridge,
 Copyright (C) 2016-2020 Andreas Shimokawa, Carsten Pfeiffer,
 Daniele Gobbetti, licensed under the GNU AFFRERO GENERAL PUBLIC LICENSE,
 Version 3, 19 November 2007. 
 
 Contributors:
 - Andreas Shimokawa (bugfixes & support for the Gadgetbridge API)
 
 Privacy
 -------
 
 For the privacy statement, see [here](https://codeberg.org/Starfish/TinyWeatherForecastGermany/wiki/Home).

 Concept
 -------
 
 When installing [lineageos](https://lineageos.org/) on your device, you will perhaps miss the out of the box functionality of the cLock stock app to display a weather forecast. 
 To do so, you need to install a third-party weather provider service. The first idea was to code a weather forecast provider that uses the open data from the Deutscher Wetterdienst (DWD).
 
 However, although some basic functionality could be established in a test version, the lineageos classes to integrate a [weather provider service](https://lineageos.github.io/android_lineage-sdk/reference/lineageos/weatherservice/WeatherProviderService.html) turned out to be quite inflexible (e.g. you need to provide a forecast for exactly 7 days to achieve full functionality, some additional data available form the DWD could not be displayed, etc.).
 
 Therefore, this idea was dropped in favour of a widget that could be placed comfortably on the home screen and adjusted to the needs of the user, displaying more detailed weather data that would have been possible using a weather provider service.
 
 Furthermore, this approach makes this app also available to anyone, not requiring lineageos to be installed on the device.
 
 Please also note that the DWD presents huge amounts of open weather data. The scope of this app is to poll a simple, 24 hours weather forecast from the DWD, and not more at the present time. 
 
 FAQ
 ---
 *For locations in a different time zone the day/night icons seem incorrect.*
 
 The app always displays the date & time of your device (and locale). Example: you are in Berlin and have selected the weater for Cuba. The app shows you the weather in Cuba at the corresponding Berlin time and uses the day/night-icons corresponding to the Berlin time. Once you have travelled to Cuba and your device switched to the local time in Cuba, the app will display the weather in Cuba at the Cuba time.   
 
 *How to read the widget?*
 
 The widget icon, the weather description text and the current temperature refer to the weather forecast that can be expected until the next full hour. The low and high temperatures refer to the values that can be expected to occur from now to midnight.
 
 *How often does the app update the weather forecast?*
 
 The weather forecast data from the Deutscher Wetterdienst that is used by Tiny Weather Forecast Germany gets updated every 6 hours. Therefore, it does not make sense to pull weather data more frequently than this from the DWD API. However, a manual data update triggered by the user's selection in the main app always forces an update of forecast data. When changing sensors/locations, the data always gets updated, too. The app does not store forecast data for multiple locations.
 
 The forecast data covers the next ten days. So it is pretty feasible to present a weather forecast for some time without polling new data.
 
 *How often does the GadgetBridge app gets updated (when this feature is enabled)?*
 
  When GadgetBridge support is enabled, the app will, in the best case, update GadgetBridge every 30 minutes using forecast data that is already in place, meaning that the DWD API will not be called for this. However, on devices with API 23 or higher, such updates might not occur that regularly when the device goes in doze mode, but should be launched in the so-called “maintenance window”, and it is difficult to say what this really means in manners of time. This will likely mean very different things depending on the device and/or ROM.
  
 Contributing
 ------------

 Please leave comments, bug reports, issues and feature requests at
 the app repository at codeberg.org:
 
 https://codeberg.org/Starfish/TinyWeatherForecastGermany
 
 Alternatively, for suggestions and bug reports, you can contact me
 by email: pawel (at) kaffeemitkoffein.de 
