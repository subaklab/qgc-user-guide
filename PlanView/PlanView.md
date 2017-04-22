# Plan View

![](PlanView.jpg)

Plan View는 비행체의 자동 미션을 계획하는데 사용합니다. 일단 미션을 계획하고 비행체로 보내면, [Fly View](FlyView.md)를 미션 비행으로 변경합니다.

비행체가 [GeoFence](PlanGeoFence.md)나 [Rally Points](PlanRallyPoints.md)을 지원한다면, Plan View에서 설정이 가능합니다.

위 이미지는 이륙(takeoff), 2개 waypoint 비행 후 착륙의 단순한 미션을 보여주고 있습니다.

미션을 생성하는 단계는 :

1. Plan View로 변경 (Change to Plan View)
2. 명령을 미션에 추가하고 필요하면 수정 (Add commands to the mission and edit as needed)
3. 미션을 비행체로 전송 (Send the mission to the vehicle)
4. Fly View로 변경하고 미션 비행 (Change to Fly View and fly your mission)

## Plan 도구들
화면의 왼쪽 모퉁이에 Plan Tools가 있습니다. 이 툴의 위에서 부터 아래로 :

* Add Commands
* [Survey](Survey.md)
* Sync
* Center map
* Map Type
* Zoom In/Out

### Add Commands
Add Commands 툴을 활성화시키기 위해 클릭합니다. 활성화시키는 동안 지도를 클릭하면 새로운 미션 명령을 클릭한 위치에 추가됩니다. 이 툴은 다시 클릭할 때까지 활성화 상태로 남아 있습니다.

### Sync
Sync 툴로 GeoFence를 비행체나 파일로 보낼 수 있습니다. *비행전에 GeoFence를 비행체로 전송했는지 확인하세요.* 툴이 "!"로 표시되는 것은 GeoFence가 변경 후에 비행체로 전송하지 않았다는 것을 뜻합니다.

Sync 툴은 다음과 같은 기능을 제공합니다 :

* 비행체로 전송 (Send to Vehicle)
* 비행체로부터 로드 (Load from Vehicle)
* 파일에 저장 (Save to File)
* 파일로부터 로드 (Load from File)
* 전체 삭제 (Remove All)

### Survey

[Survey](Survey.md)는 polygonal area 상에서 격자패턴으로 비행할 수 있습니다.

## Mission Command List
화면의 오른쪽 모서리에 미션 명령의 목록이 있습니다. 해당 아이템에 대해서 값을 수정하고 싶다면 클릭합니다. 위에서 미션, Geofence, 렐리 포인트 사이를 전환하는 옵션의 집합입니다.

### Mission Command Editors

미션 editor를 보기 위해서 미션 명령을 클릭합니다. editor로 명령의 값을 지정할 수 있습니다. 명령 이름을 클릭하면 명령의 타입도 변경가능합니다. 이렇게 하면 미션을 만들기 위해서 설정 가능한 명령들 중에 선택이 가능합니다 명령 이름의 오른쪽에 메튜를 클릭해서 열 수 있습니다. 이 메뉴로 Insert와 Delete 같은 추가 옵션에 접근할 수 있습니다.

### Planned Home Position
미션은 항상 관련된 "Planned Home Position"을 가지고 있습니다. 비행체의 home position을 시뮬레이션하는데 사용됩니다. waypoint 라인들이 첫번째 waypoint에 올바르게 연결되어 그려지는지를 봅니다. 미션의 실제 home position은 비행체가 설정하며 "planned" home position과 다를 수 있다는 것을 명심하세요. 미션을 시작한 위치가 "planned"의 위치와 다른 경우입니다.

## Mission Display
지도의 중앙에 현재 미션을 시각화해서 보여줍니다. 인디케이터를 클릭해서 선택하고, 드래그해서 움직일 수 있습니다.

## Mission Height Display
지도의 아래부분에서 미션 명령들 사이에 높이 차이를 보여줍니다. 이의 왼쪽에서 이전 명령과 관련한 현재 선택한 명령에 대한 정보가 있습니다. 예를 들면: 이전 waypoint와의 거리
