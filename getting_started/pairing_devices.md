**IMPORTANT:** Before you start, make sure that `permit_join: true` is set in your `configuration.yaml`. Otherwise new devices cannot join the network!
It's equally important that `permit_join: false` is set in your `configuration.yaml` after initial setup is done to keep your Zigbee network safe and to avoid accidental joining of other Zigbee devices.

Start by checking if your Zigbee device is supported, see  [Supported devices](../information/supported_devices.md).

Once you see something similar to `New device with address 0x00159d00016da0c8 connected!` in the log your device is paired.

## Xiaomi
Different devices require different pairing methods. In case you get an `Error [ERR_UNHANDLED_ERROR]: Unhandled error. (Cannot get the Node Descriptor of the Device: 0x00158d0001720111)` you should try a different pairing method. See [Supported devices](../information/supported_devices.md) to figure out if your device is MiJia or Aqara.
* Most MiJia devices: press and hold the reset button on the device for +- 5 seconds (until the blue light starts blinking). **IMPORTANT**: Release and start pressing the reset button every second. This keeps the device awake, otherwise pairing will **fail!**.
* Most Aqara devices: press and hold reset button on the device for +- 5 seconds until the blue light blinks three times, release the reset button (the blue light will blink once more) and wait.
* Most Aqara wall switches: press and hold the button on the device for +- 10 seconds (until the blue light starts blinking and stops blinking), release and wait.
* [Video: Pairing Xiaomi Aqara Cube MFKZQ01LM](https://www.youtube.com/watch?v=uhMrcIAdGxg&feature=youtu.be)

*NOTE: When you fail to pair a device, try replacing the battery, this could solve the problem.*

## Belkin WeMo smart LED bulb
[Resetting or Restoring the Wemo® Smart LED Bulb, F7C033](http://www.belkin.com/us/support-article?articleNum=116178)

## IKEA TRADFRI
The factory reset procedure differs between TRADFRI components:

* Factory reset the light bulb ([video](https://www.youtube.com/watch?v=npxOrPxVfe0)). After resetting the bulb will automatically connect. While pairing, keep the bulb close the the CC2531 USB sniffer.
What works for me every time is using (very) short “on’s” and a little bit longer “off’s”…
I start with bulb on, then off, and then 6 “on’s”, where I kill the light as soon as the bulb shows signs of turning on… Hope that make sense…?

* To factory reset the TRADFRI wireless dimmer (ICTC-G-1) press the button 4 times (so the red lights starts blinking).

* To factory reset the TRADFRI control outlet, press and hold the reset button (pinhole underneath the light, located at the top of the outlet) with a paperclip until the white light starts fading. Hold onto the button for a few more seconds, then release. After this, the outlet will automatically connect.

* To factory reset the TRADFRI drivers (ICPSHC24-10EU-IL-1 and ICPSHC24-30EU-IL-1) use a small pin or paperclip to push the reset button once.

### IKEA TRADFRI signal repeater (E1746)
Push the reset button of the device with a paperclip for 5 seconds. While pairing the LED is flashing/dimming slowly. Once the pairing is finished, the LED stays on.

### IKEA TRADFRI remote control (E1524)
Pair the remote to Zigbee2mqtt by holding it close to the coordinator and pressing the button next to the battery 4 times. The red light on the remote will now flash a few times.

## Müller Licht 
### Tint remote control (MLI-404011)
Remove the battery cover and use the cover to press the button above the batteries. Press and hold this button for 10-20 seconds and release the button. After that the remote should show up as a paired device.

### Tint LED bulb GU10/E14/E27 350/470/806 lumen, dimmable, color, opal white (404000/404005/404012)
Turn the light bulb five times on and off. After turning it on the sixth time, it will indicate with colors that the bulb is pairing.

## Philips Hue
Factory reset the light bulb see [HOWTO: Factory reset a Hue bulb](https://www.youtube.com/watch?v=qvlEAELiJKs). After resetting the bulb will automatically connect.

* This is also possible with the [Tradfri Remote Control](https://www.ikea.com/us/en/images/products/tradfri-remote-control__0489469_PE623665_S4.JPG) by pressing and holding the reset button on the bottom of the remote (next to the battery). [This may not always work](https://github.com/Koenkk/zigbee2mqtt/issues/296#issuecomment-416923751).
* Philips Hue Lightstrip Plus V2 have been successfully reset using the [Hue Dimmer Switch](https://www2.meethue.com/en-us/support/dimmer-switch) by holding the On and Off buttons at the same time for 10 seconds while holding next to the Lightstrip controller, afterwards the Lightstrips can join Zigbee2MQTT.
* For the 7146060PH (Philips Hue Go), **the power cord has to be connected**, after the blinking light (**INSTEAD** of step four in the video), press and keep holding the button on the bottom until the device is paired (+- 60 seconds). While holding the button the Hue Go will give you a nice light show :smile:.

### Philips LivingColors (Friends of HUE)
Philips LivingColors IRIS and Philips LivingColors Bloom Devices that comes with Philips (HUE) Remote Gen 2 (Touch Wheel) or Gen 3 (Round Click Wheel) can be paired via Zigbee. Devices with Gen 1 Remote don't use Zigbee and can not be paired.
The Philips LivingColors Remote can not be paired via Zigbee because it only support ZigBee Light Link (ZLL).

To Pair hold Button ON and Bottom Left Key (Favorite 1) on the Remote in Front of the Device until the Device Light blinks and lights Orange. If connection was succesfull the Device Light will light Green.

**WARNING**: If you pair your Device to a Zigbee Network which is not using a ZLL Channel you can't reset the Device with the Philips LivingColors Remote Gen 3. The Gen 3 Remote will only try ZLL Channels to find the Device! Maybe it's possible to reset the Device with a Philips LivingColors Remote Gen 2 as it should try all Zigbee Channels to find the Device.

[Philips LivingColors Bloom Manual](https://www.download.p4c.philips.com/files/7/7099760pu/7099760pu_dfu_eng.pdf)

[Philips LivingColors Iris Manual](https://www.download.p4c.philips.com/files/7/7099930ph/7099930ph_dfu_eng.pdf)

## Innr
Factory reset using [Innr manual reset instructions](https://www.youtube.com/watch?v=4zkpZSv84H4). After resetting the bulb will automatically connect.

## Hive
Follow instructions from [How do I reset my Hive Active Light?](https://www.hivehome.com/ca/support/Help_installing_Hive/HIH_Hive_Active_Light/How-do-I-reset-my-Hive-Active-Light). After resetting the bulb will automatically connect.

## OSRAM
### OSRAM Light Bulb
Follow instruction from [Manual reset](http://belkin.force.com/Articles/articles/en_US/Troubleshooting_and_Tutorials/Resetting-the-OSRAM-LIGHTIFY-Tunable-White-60-Bulb#a). After resetting the bulb will automatically connect.
### OSRAM Smart+ Plug
For the OSRAM Smart+ plug (AB3257001NJ) hold the on/off button until your hear a click (+- 10 seconds).
### OSRAM Smart+ Switch Mini
For the OSRAM Smart+ Switch Mini (AC0251100NJ) hold the Middle and Arrow Down Buttons for 10 Seconds to Reset the Device. Hold the Middle and Arrow Up Buttons for 3 Seconds to connect. If the Switch is connected hold Middle and Arrow Up Buttons for 3 Seconds to disconnect.
### OSRAM Switch 4x-LIGHTIFY
For the OSRAM Switch 4x-LIGHTIFY (AB371860055) hold the Bottom Left and Top Right Button for 3 Seconds to connect.

## PLUG EDP RE:DY
Factory reset the plug (hold the switch button for >10sec). After resetting the switch will automatically connect.

## Netvox power socket
Factory reset by:
- Press and hold the Binding Key for 15 seconds. The network indicator will flash green 3 times
(at the 3rd, the 10th, and the 15th second).
- After releasing the Binding Key, press the Switch Key within 2 seconds. The network indicator
will rapidly flash green.
- After fast flashes, Z809A will reboot, and the restore is completed. The socket will automatically connect now.

## Gledopto
Some of the Gledopto devices are not providing a `modelID`, in that case the modelID `undefined` is shown. Sometimes it helps to repair the device while keeping it close to the coordinator (less than one meter).

If this fails, the `modelID` has to be set manually in `data/database.db`. First find out the `modelID` of your devices from the [Supported devices page](../information/supported_devices.md). Then open `data/database.db` and add the `modelId` as highlighted in **bold** below.

*{"id":50,"type":"Router","ieeeAddr":"0x00124b0019c606cd","nwkAddr":10828,"manufId":0,"manufName":"GLEDOPTO","powerSource":"Mains (single phase)",**"modelId":"GL-S-007Z"**,"epList":[11,13],"status":"offline","joinTime":null,"endpoints":{"11":{"profId":49246,"epId":11,"devId":528,"inClusterList":[0,3,4,5,6,8,768],"outClusterList":[],"clusters":{"genBasic":{"dir":{"value":1},"attrs":{}},"genIdentify":{"dir":{"value":1},"attrs":{}},"genGroups":{"dir":{"value":1},"attrs":{}},"genScenes":{"dir":{"value":1},"attrs":{}},"genOnOff":{"dir":{"value":1},"attrs":{}},"genLevelCtrl":{"dir":{"value":1},"attrs":{}},"lightingColorCtrl":{"dir":{"value":1},"attrs":{}}}},"13":{"profId":49246,"epId":13,"devId":57694,"inClusterList":[4096],"outClusterList":[4096],"clusters":{"lightLink":{"dir":{"value":3},"attrs":{}}}}},"_id":"geCEMkRqlaMe6muE"}*

## SecuriFi
### Peanut Smart Plug (PP-WHT-US)
Additional steps are required because the Peanut Smart Plug does not provide a `ModelId` in its database entry, and thus zigbee2mqtt cannot identify the product or how to handle it.

Reset the device and initiate pairing mode by holding the pairing button (the small button next to the on/off button) for ten seconds, releasing the button, and unplugging the device.  When plugged back in, the front LED will be blinking red and ready to receive a pairing request.  When paired successfully, the red LED on the plug will stop blinking.

After pairing, you must stop zigbee2mqtt and manually edit the zigbee2mqtt `database.db` file with a text editor (note that the file may be owned by root).  Find each line where the Peanut Smart Plug is listed (look for "SecuriFi Ltd." in the `ManufName` field) and **add** `"ModelId":"PP-WHT-US",` between two existing fields.

*For example,* change `..."manufId":4098,"manufName":"Securifi Ltd....` to `..."manufId":4098,"ModelId":"PP-WHT-US","manufName":"Securifi Ltd....` on each line for the device.

Save the file and restart zigbee2mqtt.

## Trust
### Trust Remote control (ZYCT-202)
Factory reset the remote by holding the 0 (off) button for +-20 seconds.
To establish a connection keep the remote within 2 meters from the hub. Press and hold the smart group button (button with two bulbs) and wait until the lights, below the channels, flash.
### Trust Wireless contact sensor (ZCTS-808)
When pairing the sensor with Zigbee2MQTT, keep opening and closing the sensor (pull/insert the sensor parts next to eachother) for 10 seconds, otherwise device will fall asleep before it gets fully configured and will not send state changes.
