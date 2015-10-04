# Zway-LightMotion

Trigger lights with motion and other security sensors

# Configuration

## lights

Multiple devices that should be triggered. Trigger will not be fired when any 
of these devices is already turned on.

## extraLights

Extra devices that should be checked. Trigger will not be fired when any of
these devices is already turned on.

## securitySensors

Security sensors that trigger lights

## luminositySensor

Optional luminosity sensor.

## luminosity

Only triggers if luminosity is above threshold.

## duration

Trigger duration after the last security sensor has been untripped.

# Virtual Devices

This module creates a virtual binary switch device to turn on/off random devices.

# Events

No events are emitted

# License

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or any 
later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.