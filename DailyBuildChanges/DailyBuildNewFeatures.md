# Daily Build 주요 변경사항

## Plan View - Mission Settings
미션을 생성할 때, 화면 오른쪽에 있는 미션 목록 중에서 첫번째 아이템이 Mission Settings입니다. 비행체 정보를 지정하는 것 이외에 home position을 지정할 수 있습니다.

<img src="MissionSettings.jpg" style="width: 150px;"/>

### Planned Home Position
planned home position을 통해 미션을 만드는 동안 비행체의 home position을 시뮬레이션이 가능합니다. 이륙부터 미션 완료까지 waypoint trajectory를 볼 수 있습니다. 이것은 "planned" home position라는 것을 명심하세요. 그리고 비행체를 구성시키기 위해서   
The planned home position allows you to simulate the vehicle's home position while planning a mission. This way you see that waypoint trajectory for your vehicle from takeoff to mission completion. Keep in mind that this is the "planned" home position and you should place it where you plan to start the vehicle from. The actual home position of a vehicle is set by the vehicle itself when arming.

### Vehicle Info
When planning a mission the firmware being run on the vehicle as well as the vehicle type must be known in order for QGroundControl to show you the mission items appropriate for you vehicle.

If you are planning a mission while you are connected to your vehicle the Firmware and Vehicle Type will be determined from the vehicle connection. If you are planning a mission while not connected to a vehicle you will need to specify this information yourself.

The additional value which can be specified when planning a mission is the vehicle flight speed. By specifying this value total mission or survey times can be approximated.

## Multi-Vehicle View (Work In Progress)

There is a new view available when you have multiple vehicles connected to QGC. It will only show up when more than one vehicle is connected. When that happens you will see an additional set of radio button at the top right of the Plan view.

<img src="MultiVehicleRadios.jpg" style="width: 150px;"/>

Click the Multi-Vehicle radio button to replace the instrument panel with the multi-vehicle list:

<img src="MultiVehicleList.jpg" style="width: 150px;"/>

The example above shows three vehicles. The numbers are the vehicle id. In the large font is the current flight mode. You can click the flight mode name to chnage to a different flight mode. To the right are small version of the instruments for each vehicle. You can command the vehicle to do the following actions from the control panel:

* Arm/Disarm
* Start/Stop a mission
* Return to Launch
* Take Control back of the vehicle by returning to manual control from a mission.

Coming soon:

* See mission progress as a linear display (green line)

### Multi-Vehicle Gotchas

#### Unique vehicle ids
Each vehicle connected to QGC must have a unique id. Otherwise QGC will think the vehicles are actually the same vehicle. The symptom of this is the Plan view jerking around as it try to position itself to one vehicle and then the next. For PX4 Pro firmwares this is the ```MAV_SYS_ID``` parameter. For ArduPilot firmwares it is the ```SYSID_THISMAV``` parameter.

### Using SITL to simulate multiple vehicles

#### ArduPilot SITL
The ArduPilot SITL simulator does support it but you cannot use the variant which has MAVProxy in the middle of the connection. There are bugs in MAVProxy which cause the routing of mavlink messages to individual vehicles to not work correctly. Also you must have a separate directory for each vehicle.

So for example say your main repo directory is ```arduppilot```. You can have a directory for each vehicle:

* ```arduppilot/ArduCopter/v1```
* ```arduppilot/ArduCopter/v2```

You then launch the SITL instance for vehicle 1 from the ```v1``` directory using the following command:
```../../build/sitl/bin/arducopter-quad --model quad --defaults ../../Tools/autotest/default_params/copter.parm --instance 1```

Launch the second vehicle from the ```v2``` directory and change the command line to ```--instance 2```.

#### PX4 Pro SITL
The PX4 Pro SITL simulator does not support this. Although it may be possible with some internal hacking of the simulator itself.

## AutoLoad Mission on Vehicle Connect (WIP)

In the Settings / General page there is a new item for "AutoLoad mission directory:". By checking this item and specifying a directory, when QGC connects to a vehicle it will automatically upload a mission to the vehicle. The mission file must be named "AutoLoad#.mission" where the # is replaced with the vehicle id.

## Default Mission Item Altitude

When you add the first new waypoint to a mission the altitude for that item was previously hardcoded to 50 meters. You can now choose a default value for that from the Settings/General page.

If you change the altitude on a waypoint, subsequent items will continue to use that new altitude. This is an existing feature that has not changed. That new altitude entered from he Plan view does not affect the default altitude stored in settings.

## Plan - Mission Settings

## Plan - Camera Section on Waypoints

## Plan/Fly - Camera/Gimbal direction shown on waypoints
