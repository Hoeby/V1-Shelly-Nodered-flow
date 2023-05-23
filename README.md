# V1-Shelly-Nodered-flow

To let this flow work correctly, nodered must be version 3.x.x
If not, then the flow will not work.

Which palette modules need to be installed in nodered:
- node-red-dashboard
- node-red-node-ui-table

<a href="https://nodered.org/docs/user-guide/editor/palette/manager">How to install these modules in nodered, click on this link.</a>

The flow saves data on you device. This is needed in case of a deploy or update, to prevent that the config is gone.
The flow tries to make the needed directories, but to help the flow it is better to make these en give the the writting/reading rights
For the PI with domoticz, make the directory: /home/pi/domoticz/plugins/shelly
For nodered in docker, make the directory: /data/saved-files/shelly  (remember, that this needs to be a volume, that the config is not gone when something happens with the container)
