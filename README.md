# V1-Shelly-Nodered-flow

To let this flow work correctly, nodered must be version 3.x.x
If not, then the flow will not work.

Which palette modules need to be installed in nodered:
- node-red-dashboard
- node-red-node-ui-table

<a href="https://nodered.org/docs/user-guide/editor/palette/manager">How to install these modules in nodered, click on this link.</a>

The flow saves data on you device. This is needed in case of a deploy or update, to prevent that the config is gone.
The flow tries to make the needed directories, but to help the flow it is better to make these en give the the writting/reading rights <br>
For the PI with domoticz, make the directory: /home/pi/domoticz/plugins/shelly <br>
For nodered in docker, make the directory: /data/saved-files/shelly  (remember, that this needs to be a volume, that the config is not gone when something happens with the container) <br>

When the directories need to be different, the can be changed in the flow.
Search for this part in the flow. Double click on the correct environment and make your changes.
For docker, remember that the location needs to be inside your container, otherwise nodered can't store the config
<img src="assets/save_location.png" width="300" >
