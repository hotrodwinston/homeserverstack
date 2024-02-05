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

https://community.openhab.org/t/getting-gocontrol-wa00z-1-to-controlzooz-zen52-double-relay/153235/14

Setting up rules to have scene controllers turn items on and off is more complicated than it should be in some cases so this guide is helpful. Per the above link, you need to trigger on state update, not state change. An example rule for turning lights off is below. In this example, one relay of a double relay switch is being turned off when a button is pressed UPDATING the state of the scene controller to 2. If the item being controlled only had one relay I would just use association to make the buttons act as on/off. That has the advantage of working even if the hub is down. But in this case that's not an option.

light off on scene remote button press

    configuration: {}
    triggers:
      - id: "1"
    configuration:
      itemName: WA00Z1_Remote_2_Scene_Number
      state: "2.0"
    type: core.ItemStateUpdateTrigger
    conditions: []
    actions:
      - id: "2"
    configuration:
      itemName: Living_Room_Ceiling_Switch_1
      command: OFF
    type: core.ItemCommandAction
