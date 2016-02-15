# Zway-MotionTrigger

Trigger switches based on security sensors like motion or door sensors if 
certain preconditions are met (eg. luminosity below a certain level). Lets you 
specify  multiple devices to trigger and check, a delay for turning off lights 
and multiple preconditions to check. This module will ensure that devices are 
not triggered if any of the selected devices is already turned on.

# Configuration

## lights

Multiple devices that should be triggered. Trigger will not be fired if any 
of these devices is already turned on.

## securitySensors

Security sensors that trigger lights. It is sufficient for one security 
sensor to be triggered.

## timeout

Trigger timeout duration after the last security sensor has been untripped.
(in seconds)

## preconditions

Multiple optional conditions to check before a switch will be triggered. 
Luminosity sensors, and the Astronomy module from 
https://github.com/maros/Zway-Astronomy are particularly well suited to 
be included in such condition checks. Can also to prevent triggering lights
if any other light is already switched on.

## preconditions.time.timeFrom, preconditions.time.timeTo, preconditions.time.dayofweek

Multiple time periods when the motion trigger should be active. 
Time in HH:MM format

## preconditions.binary.device, preconditions.multilevel.device

Multiple devices to check. Must be either a binar or multilevel sensor.

## preconditions.multilevel.device

Operators to be used for the multilevel checks

## preconditions.binary.value, preconditions.multilevel.value

Values to be used for the precondition checks

## preconditions.recheck

If this option is checked, all preconditions will be rechecked regularly.
Otherwise preconditions will be only checked once when the light is about
to be triggered

## dimmer.mode, dimmer.static, dimmer.code, dimmer.dynamic

Sets how the dimmer level sould be determined. 

* Full: Sets dimmers to 100% (default)
* Static: Sets the dimmer level to a user-defined value
* Code: Executes a user-provided JavaScript code to calculate the dimmer level
* Dynamic: Calculate dimmer based on luminosity

# Virtual Devices

This module creates a virtual binary switch device to turn on/off the trigger.
Current operation mode (triggered, on, off) is indicated by the icon color.
metrics:level stores the mode of the trigger, and metrics:triggered weather
a device is currently triggered or not.

# Events


## light.on, light.off

Emits an event whenever a light is switched on or off. ie. Allows other 
motion triggers, to act immediately after one trigger has been switched
off.

# Installation

Install the BaseModule from https://github.com/maros/Zway-BaseModule first

```shell
cd /opt/z-way-server/automation/modules
git clone https://github.com/maros/Zway-MotionTrigger.git MotionTrigger --branch latest
```

To update or install a specific version
```shell
cd /opt/z-way-server/automation/modules/MotionTrigger
git fetch --tags
# For latest released version
git checkout tags/latest
# For a specific version
git checkout tags/1.02
# For development version
git checkout -b master --track origin/master
```

Alternatively this module can be installed via the Z-Wave.me app store. Just
go to Management > App Store Access and add 'k1_beta' access token.

# License

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or any 
later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.
