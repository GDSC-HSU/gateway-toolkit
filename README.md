# gateway-toolkit

Repository will be took in consideration **after (v1.0.0)** to implement toolkit (support app) matter to enhance developemnt life cycle

#### product support software
1. **Firmware uploader** (app) program support oragnization able to customise BLE board build flag & manged their board configureation

```mermaid
sequenceDiagram
    participant BLE_BOARD
    participant FIRMWARE_LOAD
    participant CLOUD
    rect rgb(10, 255, 200)
    Note over FIRMWARE_LOAD,BLE_BOARD: BLE_SECURITY_CODE,...
    FIRMWARE_LOAD->>BLE_BOARD: custom_build_flag
    FIRMWARE_LOAD->>+CLOUD: upload_ble_firmware
    CLOUD->>-FIRMWARE_LOAD: sync
    end
    rect rgb(225, 100,255)
    CLOUD->>+FIRMWARE_LOAD:download_ble_firmware
    FIRMWARE_LOAD->>-BLE_BOARD:firmware_burn
    end
```

2. BLE Emulator suite via serial comunication & web | app | web interface. Developer able to mock BLE value in custom step with delay(ms) and test(stress) gateway app


```mermaid
sequenceDiagram
    participant BLE_BOARD
    participant DEV_PC
    participant MOBILE
    Note left of BLE_BOARD: BOARD_WITHOUT SENSOR
    rect rgb(10, 255, 200)
    DEV_PC->>BLE_BOARD: serial command
    Note over BLE_BOARD,MOBILE: Mock sensor with their ble gatt profile
    BLE_BOARD->>MOBILE: BLE GATT PACKAGES
    end
```
