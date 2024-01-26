The thermostat I am using (RCS zwave thermostat model TBZ48A - rebranded GoControl TBZ48) requires special mode mappingings to work with google assistant in OpenHAB:
    
    heat=1:Heat,heatcool=3:Auto,off=0:Off,cool=2:Cool

tuya binding is from smarthomej and install is as simple as add https://download.smarthomej.org/addons.json as JSON 3rd Party Addon Service in the settings

As I Write Rules dring my reset I will copy the code here so I can set them back up after any crash and can debug if needed
