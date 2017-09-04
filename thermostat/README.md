# openHAB HVAC - Thermostat
This is a software thermostat that implements the features found in most hardware thermostats.

## Scope
This component only provides core thermostat functions. Interface items are used to coordinate with other components and functions, such as mode scheduling and controlling physical heating and air conditioning equipment.

## Internationalization
This component is intended to support any language, number format, and temperature unit.
* The user interface can be set to display in Celsius or Fahrenheit.
* A language conversion list can be used to control most on the runtime displays. Configuration and troubleshooting information is only in English.

## User Interface
### Screen Widget
![Widget](/thermostat/docs/widget.png?raw=true)

### Main Popup
![Main Popup - Manual Mode](/thermostat/docs/main_popup-manual_mode.png?raw=true)
![Main Popup - Preset Mode](/thermostat/docs/main_popup-preset_mode.png?raw=true)

### Advanced Popup
![Advanced Popup](/thermostat/docs/advanced_popup.png?raw=true)

## Setup
### Framework Groups
The following group items must be created for the component to function. These groups must be named in English exactly as shown below. All groups should have the "Base type" set to "None".
* HVAC_Framework_Thermostat_ActiveMode
* HVAC_Framework_Thermostat_AvailableMode
* HVAC_Framework_Thermostat_ConstantFan
* HVAC_Framework_Thermostat_CoolCall
* HVAC_Framework_Thermostat_Cooling
* HVAC_Framework_Thermostat_CoolSP
* HVAC_Framework_Thermostat_CoolSupplied
* HVAC_Framework_Thermostat_CurrentTemp
* HVAC_Framework_Thermostat_Deadband
* HVAC_Framework_Thermostat_EnableRemoteMode
* HVAC_Framework_Thermostat_HeatCall
* HVAC_Framework_Thermostat_Heating
* HVAC_Framework_Thermostat_HeatSP
* HVAC_Framework_Thermostat_HeatSupplied
* HVAC_Framework_Thermostat_SimThermostat
* HVAC_Framework_Thermostat_Status
* HVAC_Framework_Thermostat_System
* HVAC_Framework_Thermostat_Thermostat

### Individual Thermostats
A number of items must exist for each thermostat that will operate. Some items can be shared between multiple thermostats, such as preset modes. Some items should be shared with other components, such as controlling a physical furnace.

The following table shows an example item list for a room named "Kitchen".

|Data Point|Type|Name|Parent Groups|Notes|
|---|---|---|---|---|
|Thermostat Identifier|Group<br/>Base type: None|Kitchen_Thermostat|HVAC_Framework_Thermostat_Thermostat<br/>Optional: HVAC_Framework_Thermostat_SimThermostat|The optional sim group is used to have the system update the current temperature when not bound to an input.|
|Active Mode|String|Kitchen_Thermostat_Mode|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_ActiveMode||
|Constant Fan|Switch|Kitchen_Thermostat_ConstantFan|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_ConstantFan||
|Cool Call|Switch|Kitchen_Thermostat_CoolCall|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_CoolCall||
|Cooling|Switch|Kitchen_Thermostat_Cooling|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_Cooling||
|Cool Setpoint|Number|Kitchen_Thermostat_CoolSP|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_CoolSP||
|Cool Supplied|Switch|House_HVAC_Cooling|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_CoolSupplied||
|Current Temperature|Number|Kitchen_CurrentTemp|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_CurrentTemp||
|Deadband|Number|Kitchen_Thermostat_Deadband|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_Deadband||
|Enable Remote Mode|Switch|Kitchen_Thermostat_EnableRemoteMode|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_EnableRemoteMode||
|Heat Call|Switch|Kitchen_Thermostat_HeatCall|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_HeatCall||
|Heating|Switch|Kitchen_Thermostat_Heating|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_Heating||
|Heat Setpoint|Number|Kitchen_Thermostat_HeatSP|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_HeatSP||
|Heat Supplied|Switch|House_HVAC_Heating|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_HeatSupplied||
|Status|String|Kitchen_Thermostat_Status|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_Status||
|System|String|Kitchen_Thermostat_System|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_System||
|Remote Mode Request|String|Kitchen_Thermostat_RemoteModeRequest|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_RemoteModeRequest||
|Available Mode|String|StandardHVACMode_Occupied_ACOnly|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_AvailableMode||
|Available Mode|String|StandardHVACMode_Occupied_FanThenAC|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_AvailableMode||
|Available Mode|String|StandardHVACMode_Unoccupied|Kitchen_Thermostat<br/>HVAC_Framework_Thermostat_AvailableMode||
