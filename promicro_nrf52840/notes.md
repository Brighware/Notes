# Promicro nRF52840
## Pins
### LEDs
Blue LED: `BLED = P0.15`

## Schematic
https://chat.nologo.tech/d/80/14#responsive



## Zephyr & West

### Topology
```
west-workspace/
│
├── application/         # .git/     │
│   ├── CMakeLists.txt               │
│   ├── prj.conf                     │  never modified by west
│   ├── src/                         │
│   │   └── main.c                   │
│   └── west.yml         # main manifest with optional import(s) and override(s)
│                                    │
├── modules/
│   └── lib/
│       └── zcbor/       # .git/ project from either the main manifest or some import.
│
└── zephyr/              # .git/ project
    └── west.yml         # This can be partially imported with lower precedence or ignored.
                         # Only the 'manifest-rev' version can be imported.
```


### Setup
Install `nrfutil` and use it to install a zephyr toolchain and a sdk to `~/ncs` (this can take a while).


### Compiling
* Start by sourcing zephyr-env.sh from the appropriate toolchain.
`source ~/ncs/$TOOLCHAIN/zephyr/zephyr-env.sh`

* Confirm environment using west:
`west topdir`

* Compile command:
`west build -p -b promicro_nrf52840/nrf52840/uf2 $PROJECT_DIR`


### Boards
* promicro_nrf52840
* promicro_nrf52840/nrf52840/uf2

### Creating a project
#### Workspace application
1. Initialize the workspace
`west init -m https://github.com/username/$PROJECT_NAME`
2. Change to the workspace directory
`cd $PROJECT_NAME`
3. Update west environment
`west update`

##### Structure
```west
<home>/
└─── <_west-workspace_>/
   ├─── .west/
   ├─── nrf/
   ├─── zephyr/
   ├─── ...
   └─── <app>/
      ├── src/
      ├── ...
      └── west.yml
```


##### freestanding application

```west
<home>/
├─── <west-workspace>/
│  ├─── .west/
│  ├─── nrf/
│  ├─── zephyr/
│  └─── ...
└─── <app>/
   ├─── src/
   └─── ...
```


## Links
### ot-usb-br
https://primalcortex.wordpress.com/2022/05/21/building-an-openthread-border-router-with-the-esp32-and-the-nrf52840-dongle/

