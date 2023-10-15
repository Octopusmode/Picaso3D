# Как поменять значения  EEPROM в прошивке PRO250

0. Открыть репетир хост.
0. В нём соединиться с принтером по бодрейту 230400.
0. Вбить *M205* чтобы получить текущий конфиг в EEPROM.
0. Открыть документ https://www.repetier.com/documentation/repetier-firmware/rf-installation/.
0. Там написано как через *M206 T<type> P<position> X<new_value>* менять значения.
0. Поменять нужный параметр.


Считанный исходный конфиг:
```
21:48:37.416 : EPR:2 75 230400 Baudrate
21:48:37.416 : EPR:3 129 11602.28 Filament printed [m]
21:48:37.416 : EPR:2 125 8605906 Printer active [s]
21:48:37.416 : EPR:3 3 170.67 X-axis steps per mm
21:48:37.416 : EPR:3 7 170.67 Y-axis steps per mm
21:48:37.416 : EPR:3 11 800.00 Z-axis steps per mm
21:48:37.416 : EPR:3 15 300.00 X-axis max. feedrate [mm/s]
21:48:37.416 : EPR:3 19 300.00 Y-axis max. feedrate [mm/s]
21:48:37.416 : EPR:3 23 10.00 Z-axis max. feedrate [mm/s]
21:48:37.416 : EPR:3 27 80.00 X-axis homing feedrate [mm/s]
21:48:37.417 : EPR:3 31 80.00 Y-axis homing feedrate [mm/s]
21:48:37.417 : EPR:3 35 10.00 Z-axis homing feedrate [mm/s]
21:48:37.417 : EPR:3 39 20.00 Max. jerk [mm/s]
21:48:37.417 : EPR:3 47 0.40 Max. Z-jerk [mm/s]
21:48:37.417 : EPR:3 133 -15.20 X home pos [mm]
21:48:37.417 : EPR:3 137 -0.90 Y home pos [mm]
21:48:37.417 : EPR:3 141 -0.38 Z home pos [mm]
21:48:37.417 : EPR:3 145 200.00 X max length [mm]
21:48:37.417 : EPR:3 149 200.00 Y max length [mm]
21:48:37.417 : EPR:3 153 210.60 Z max length [mm]
21:48:37.417 : EPR:3 169 0.00 Z correction [mm]
21:48:37.417 : EPR:3 173 213.10 X sopli 2 [mm]
21:48:37.418 : EPR:3 177 -0.10 Y sopli 2 [mm]
21:48:37.422 : EPR:3 51 2000.00 X-axis acceleration [mm/s^2]
21:48:37.422 : EPR:3 55 2000.00 Y-axis acceleration [mm/s^2]
21:48:37.423 : EPR:3 59 10000.00 Z-axis acceleration [mm/s^2]
21:48:37.423 : EPR:3 63 2000.00 X-axis travel acceleration [mm/s^2]
21:48:37.423 : EPR:3 67 2000.00 Y-axis travel acceleration [mm/s^2]
21:48:37.423 : EPR:3 71 10000.00 Z-axis travel acceleration [mm/s^2]
21:48:37.423 : EPR:0 103 0 OPS operation mode [0=Off,1=Classic,2=Fast]
21:48:37.423 : EPR:3 99 50.00 OPS move after x% retract [%]
21:48:37.423 : EPR:3 43 0.80 OPS min. distance for fil. retraction [mm]
21:48:37.424 : EPR:3 87 1.50 OPS retraction length [mm]
21:48:37.424 : EPR:3 91 0.00 OPS retraction backlash [mm]
21:48:37.424 : EPR:0 106 0 Bed Heat Manager [0-2]
21:48:37.424 : EPR:0 107 255 Bed PID drive max
21:48:37.424 : EPR:0 124 80 Bed PID drive min
21:48:37.424 : EPR:3 108 196.00 Bed PID P-gain
21:48:37.424 : EPR:3 112 33.02 Bed PID I-gain
21:48:37.424 : EPR:3 116 290.00 Bed PID D-gain
21:48:37.424 : EPR:0 120 255 Bed PID max value [0-255]
21:48:37.425 : EPR:3 200 452.33 Extr.1 steps per mm
21:48:37.425 : EPR:3 204 2000.00 Extr.1 max. feedrate [mm/s]
21:48:37.425 : EPR:3 208 5.00 Extr.1 start feedrate [mm/s]
21:48:37.425 : EPR:3 212 3000.00 Extr.1 acceleration [mm/s^2]
21:48:37.425 : EPR:0 216 1 Extr.1 heat manager [0-1]
21:48:37.425 : EPR:0 217 140 Extr.1 PID drive max
21:48:37.425 : EPR:0 245 60 Extr.1 PID drive min
21:48:37.425 : EPR:3 218 24.00 Extr.1 PID P-gain
21:48:37.425 : EPR:3 222 0.88 Extr.1 PID I-gain
21:48:37.425 : EPR:3 226 80.00 Extr.1 PID D-gain
21:48:37.426 : EPR:0 230 255 Extr.1 PID max value [0-255]
21:48:37.426 : EPR:2 231 0 Extr.1 X-offset [steps]
21:48:37.426 : EPR:2 235 0 Extr.1 Y-offset [steps]
21:48:37.426 : EPR:1 239 1 Extr.1 temp. stabilize time [s]
21:48:37.426 : EPR:1 250 150 Extr.1 temp. for retraction when heating [C]
21:48:37.426 : EPR:1 252 0 Extr.1 distance to retract when heating [mm]
21:48:37.426 : EPR:0 254 255 Extr.1 extruder cooler speed [0-255]
21:48:37.426 : EPR:3 246 0.00 Extr.1 advance L [0=off]
21:48:37.427 : EPR:3 300 452.33 Extr.2 steps per mm
21:48:37.427 : EPR:3 304 2000.00 Extr.2 max. feedrate [mm/s]
21:48:37.427 : EPR:3 308 5.00 Extr.2 start feedrate [mm/s]
21:48:37.427 : EPR:3 312 3000.00 Extr.2 acceleration [mm/s^2]
21:48:37.427 : EPR:0 316 1 Extr.2 heat manager [0-1]
21:48:37.427 : EPR:0 317 140 Extr.2 PID drive max
21:48:37.427 : EPR:0 345 60 Extr.2 PID drive min
21:48:37.427 : EPR:3 318 24.00 Extr.2 PID P-gain
21:48:37.427 : EPR:3 322 0.88 Extr.2 PID I-gain
21:48:37.427 : EPR:3 326 80.00 Extr.2 PID D-gain
21:48:37.427 : EPR:0 330 255 Extr.2 PID max value [0-255]
21:48:37.428 : EPR:2 331 2705 Extr.2 X-offset [steps]
21:48:37.428 : EPR:2 335 -145 Extr.2 Y-offset [steps]
21:48:37.428 : EPR:1 339 1 Extr.2 temp. stabilize time [s]
21:48:37.428 : EPR:1 350 150 Extr.2 temp. for retraction when heating [C]

```

<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/telegram/white"> <source media="(prefers-color-scheme: light)" srcset="https://cdn.simpleicons.org/telegram/black"> <img src="https://cdn.simpleicons.org/telegram/.svg" alt="Telegram" alight=left height="20" width="20"></picture> [Источник](https://t.me/Picaso3dUnofficial/97759)




