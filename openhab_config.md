This is an unorganized list of links and settings for my openhab setup that may or may not be useful to others.
It is for reference in restoring after a server crash or remembering how I set things up for troubleshooting

The thermostat I am using (RCS zwave thermostat model TBZ48A - rebranded GoControl TBZ48) requires special mode mappings to work with Google Assistant in OpenHAB:
    
    heat=1:Heat,heatcool=3:Auto,off=0:Off,cool=2:Cool

tuya binding is from smarthomej and installation is as simple as adding https://download.smarthomej.org/addons.json to JSON 3rd Party Addon Service in the settings

As I Write Rules during my reset I will copy the code here so I can set them back up after any crash and can debug if needed

https://github.com/openhab/org.openhab.binding.zwave/blob/main/doc/linear/wa00z1_0_0.md

https://docs.smarthomej.org/3.2.9/org.smarthomej.binding.tuya.html

Pantry light rules
closed/off

        configuration: {}
triggers:
  - id: "1"
    configuration:
      itemName: pantry_door_sensor_Contact_Portal_1
      state: CLOSED
      previousState: OPEN
    type: core.ItemStateChangeTrigger
conditions: []
actions:
  - inputs: {}
    id: "2"
    configuration:
      itemName: Morgan_Lamp_pantry
      command: "0"
    type: core.ItemCommandAction

    open/on

        configuration: {}
triggers:
  - id: "1"
    configuration:
      itemName: pantry_door_sensor_Contact_Portal_1
      state: OPEN
      previousState: CLOSED
    type: core.ItemStateChangeTrigger
conditions: []
actions:
  - inputs: {}
    id: "2"
    configuration:
      itemName: Morgan_Lamp_pantry
      command: "100"
    type: core.ItemCommandAction


