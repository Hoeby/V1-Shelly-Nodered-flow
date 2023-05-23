# V1-Shelly-Nodered-flow

To let this flow work correctly, nodered must be version 3.x.x
If not, then the flow will not work.

These shelly devices are supported in this flow:
- Shelly Plus Plug S

Which palette modules need to be installed in nodered:
- node-red-dashboard
- node-red-node-ui-table

<a href="https://nodered.org/docs/user-guide/editor/palette/manager">How to install these modules in nodered, click on this link.</a>

The flow saves data on you device. This is needed in case of a deploy or update, to prevent that the config is gone.
The flow tries to make the needed directories, but to help the flow it is better to make these en give the the writting/reading rights <br>
For the PI with domoticz, make the directory: /home/pi/domoticz/plugins/shelly <br>
For nodered in docker, make the directory: /data/saved-files/shelly  (remember, that this needs to be a volume, that the config is not gone when something happens with the container) <br>

Import the flow in your nodred environment.
Copy the JSON flow with, open the next link and copy all data <br>
<a href="https://raw.githubusercontent.com/Hoeby/V1-Shelly-Nodered-flow/main/flows.json">JSON flow data.</a><br>
Import this data in nodered

When the directories where to config is saved need to be different, these can be changed in the flow.
Search for this part in the flow. Double click on the correct environment and make your changes.
For docker, remember that the location needs to be inside your container, otherwise nodered can't store the config <br>
<img src="assets/save_location.png" width="500" >

There are 2 mqtt nodes in the flow. Set the correct mqtt server in these nodes.
After deploy, check that they are connected <br>
<img src="assets/mqtt.png" width="500" >

Go to you nodered web UI page <br>
Replace "nodered IP" with the ip address from your environment <br> 
Replace "nodered number" with the port number from your environment <br>
http://nodered IP:nodered Port/ui <br>

When correct, you see this page in the web UI <br>
The flow will test your directory. When correct working, the directory location is shown at the top. <br><br>
If it stays on: please wait, loading config <br>
Then the directory can't be written by nodered. check your directory and writting/reading rights <br>
<img src="assets/ui.png" width="1000" >

To get the devices in the list. <br>
Switch your shelly plugin (manually or with the shelly app). If your shelly device has the correct mqtt settings, it will appear in the IDX table. <br>
To setup the idx settings. Choose the device, select the device type and click on "set settings". <br>
Click on "How setup device in domoticz", which dummy devices manual need to be made in domoticz. This flow doens't automatically make devices in domoticz <br>

you are ready to go

