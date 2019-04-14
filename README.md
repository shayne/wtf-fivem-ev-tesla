# wtf-fivem-ev-tesla

FiveM Electric Vehicle / Tesla Resources

## Caveats

These resources were created for demonstration purposes. Some features are basic, like `demogarages`, and all scripts are client side.

In the future these may be integrated into frameworks and/or include their own server side/persistence logic.

## Requirements
None

## Overview

### Resources

There are three resources in this repository, meant to work together but not strictly dependant on eachother.

**wtf_teslax**

- Tesla Model X
    - 3D model from https://www.gta5-mods.com/vehicles/tesla-model-x-p90d
    - Custom handling, mimicking real-life expectations
        - Best in class acceleration: 0-60 ~4sec, 0-100 ~7sec
        - Limited top end due to increased drag: ~160mph
        - Better than average handling
        - Low center of gravity, limited roll-over

**wtf_tesla_supercharger**

- Tesla Supercharger
    - High quality 3D model of Tesla Supercharger
    - Custom for placing superchargers in convenient locations

**wtf_ev**

- EV HUD
    - EV vehicles display Whr (watt-hours) energy use
    - This figure is based on "RPMs" and Whr effects battery range
- EV Battery
    - EV vehicles have batteries instead of fuel
    - The battery discharge loosely follows real-life heuristics
        - A HUD is rendered on the minimap showing charge level %
        - Discharging uses a stepping function based on "RPM"
            - High RPMs (e.g. racing) will negatively effect range
            - Low RPMs benefit from less energy use
- EV Charger
    - Featuring the Tesla Supercharger 3D model
        - Via an included custom map: `wtf_tesla_supercharger`
    - Charging uses a quadratic Bezier curve
        - 0-60% takes ~30% of total charge time
        - &gt;61% takes the remaining time to reach full charge
    - Supports custom charging rates via `config.lua`
- Garage Demo
    - Mostly for demonstration purposes
    - Adds the concept of charging while your vehicle is stored in a garage
    - Supports custom charging rates via `config.lua`
        - Example: parking-garages charge faster than parking lots, which are faster than house-garages

## Screenshots

![photo_2019-04-14_00-43-29 (5)](https://user-images.githubusercontent.com/79330/56089919-310eed80-5e4f-11e9-9fd1-fa0eb3027122.jpg)

![photo_2019-04-14_00-43-29 (6)](https://user-images.githubusercontent.com/79330/56089925-3a985580-5e4f-11e9-9ff3-eb9430e0fbaf.jpg)

![photo_2019-04-14_00-43-29 (4)](https://user-images.githubusercontent.com/79330/56089926-3f5d0980-5e4f-11e9-8809-cf90160ba203.jpg)

![photo_2019-04-14_00-43-29 (3)](https://user-images.githubusercontent.com/79330/56089928-41bf6380-5e4f-11e9-95c1-5727de1d4326.jpg)

![photo_2019-04-14_00-43-29 (2)](https://user-images.githubusercontent.com/79330/56089930-4552ea80-5e4f-11e9-8ac3-8dbdf466dc5a.jpg)

![photo_2019-04-14_00-43-29 (1)](https://user-images.githubusercontent.com/79330/56089931-47b54480-5e4f-11e9-9bdf-5183bf6a9ec6.jpg)


## Download & Installation

### Using Git
```
cd resources
git clone https://github.com/shayne/wtf-fivem-ev-tesla [wtf-ev-tesla]/
```

### Manually
- Download https://github.com/shayne/wtf-fivem-ev-tesla/archive/master.zip
- Create and place in in `[wtf-ev-tesla]` directory

## Installation
- Add this in your `server.cfg`:

```
start wtf_ev
start wtf_teslax
start wtf_tesla_supercharger
```

## Debug
- Debug commands available when `Config.Debug = True`
- `/teslax` spawns and places you in the Tesla Model X
- `/fuel 40` will set fuel to specified amount (40 as an example)