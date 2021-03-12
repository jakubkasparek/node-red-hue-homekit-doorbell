# node-red-hue-homekit-doorbell
my simple flow to have Apple Homekit native doorbell, by Philips Hue Smart Button.

video:<br>
https://youtu.be/CpSQrBIdOHY

<img width="790" alt="Snímek obrazovky 2021-03-12 v 16 12 09" src="https://user-images.githubusercontent.com/49455498/110959179-bb1ea400-834d-11eb-9de8-92df382809a3.png">

<b>my node-red flow:</b>

```
[{"id":"703c0240.785004","type":"homekit-service","z":"3d0701aa.5fe506","isParent":true,"bridge":"b51ae49c.1f963","parentService":"","name":"Doorbell","serviceName":"Doorbell","topic":"","filter":false,"manufacturer":"MADE by  jakubkasparek.cz","model":"1.0","serialNo":"4815162342","firmwareRev":"1.0","hardwareRev":"1.0","softwareRev":"1.0","cameraConfigVideoProcessor":"","cameraConfigSource":"","cameraConfigStillImageSource":"","cameraConfigMaxStreams":"","cameraConfigMaxWidth":"","cameraConfigMaxHeight":"","cameraConfigMaxFPS":"","cameraConfigMaxBitrate":"","cameraConfigVideoCodec":"","cameraConfigAudioCodec":"","cameraConfigAudio":false,"cameraConfigPacketSize":"","cameraConfigVerticalFlip":false,"cameraConfigHorizontalFlip":false,"cameraConfigMapVideo":"","cameraConfigMapAudio":"","cameraConfigVideoFilter":"","cameraConfigAdditionalCommandLine":"","cameraConfigDebug":false,"cameraConfigSnapshotOutput":"disabled","cameraConfigInterfaceName":"","characteristicProperties":"{ \"Name\" : \"Doorbell on Entry\"}","waitForSetupMsg":false,"outputs":2,"x":420,"y":300,"wires":[["9d921ed1.323ca"],[]]},{"id":"9d921ed1.323ca","type":"debug","z":"3d0701aa.5fe506","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"payload","targetType":"msg","statusVal":"","statusType":"auto","x":610,"y":300,"wires":[]},{"id":"fc559ddc.585d78","type":"inject","z":"3d0701aa.5fe506","name":"0","props":[{"p":"payload"},{"p":"topic","vt":"str"}],"repeat":"","crontab":"","once":false,"onceDelay":0.1,"topic":"","payload":"{\"ProgrammableSwitchEvent\":0}","payloadType":"json","x":210,"y":280,"wires":[["703c0240.785004"]]},{"id":"fefa7c62.f38408","type":"inject","z":"3d0701aa.5fe506","name":"1","props":[{"p":"payload"},{"p":"topic","vt":"str"}],"repeat":"","crontab":"","once":false,"onceDelay":0.1,"topic":"","payload":"{\"ProgrammableSwitchEvent\":1}","payloadType":"json","x":210,"y":340,"wires":[["703c0240.785004"]]},{"id":"2794913b.47da76","type":"hue-bridge-node","z":"3d0701aa.5fe506","name":"Hue Bridge New","bridge":"afdd2b03.6cee9","autoupdates":true,"skipglobalevents":false,"x":160,"y":500,"wires":[["bca38ee9.0265b8"]]},{"id":"bca38ee9.0265b8","type":"hue-button","z":"3d0701aa.5fe506","name":"Doorbell","bridge":"afdd2b03.6cee9","sensorid":"52","skipevents":false,"universalevents":false,"x":360,"y":500,"wires":[["fde47d1c.f2cac"]]},{"id":"fde47d1c.f2cac","type":"change","z":"3d0701aa.5fe506","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"{\"ProgrammableSwitchEvent\":1}","tot":"json"},{"t":"set","p":"topic","pt":"msg","to":"","tot":"str"}],"action":"","property":"","from":"","to":"","reg":false,"x":420,"y":400,"wires":[["703c0240.785004"]]},{"id":"2901ed6e.2b3892","type":"comment","z":"3d0701aa.5fe506","name":"Hue Doorbell","info":"","x":390,"y":200,"wires":[]},{"id":"b51ae49c.1f963","type":"homekit-bridge","bridgeName":"Node-RED","pinCode":"826-38-554","port":"","allowInsecureRequest":true,"manufacturer":"NRCHKB","model":"1.2.0","serialNo":"Default Serial Number","firmwareRev":"1.2.0","hardwareRev":"1.2.0","softwareRev":"1.2.0","customMdnsConfig":false,"mdnsMulticast":true,"mdnsInterface":"","mdnsPort":"","mdnsIp":"","mdnsTtl":"","mdnsLoopback":true,"mdnsReuseAddr":true,"allowMessagePassthrough":true},{"id":"afdd2b03.6cee9","type":"hue-bridge","name":"Philips hue","bridge":"192.168.197.XX","key":"xxxxxxxyourHueTokenxxxxx","interval":"3000","disableupdates":false}]

```


requered node-red plugin:<br>
https://github.com/Foddy/node-red-contrib-huemagic


<p align="center">
  
  <img src="https://user-images.githubusercontent.com/49455498/110950782-8f4af080-8344-11eb-8dc3-dc572080740a.jpg" width="350" alt="Philips Hue Smart Button">
  <img src="https://user-images.githubusercontent.com/49455498/110950761-8a863c80-8344-11eb-81a0-24e12d0fe322.jpg" width="350" title="any HomePod">
</p>


