## Zephyr & West

### Compiling
* Start by sourcing zephyr-env.sh
`source ~/ncs/v3.1.1/zephyr/zephyr-env.sh`

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
