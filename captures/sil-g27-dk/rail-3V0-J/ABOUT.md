<h1 align="center">SiLabs EFR32xG27 · Simplicity (RAIL) · 3V0</h1>

<p align="center"><img src="../../../docs/images/uc-banner.svg" alt="Under construction" width="420"></p>

<!-- @emscope-pack:start -->

<!-- *** AUTOMATICALLY GENERATED CONTENT – DO NOT EDIT *** -->  

<p align="right"><sub>captured on 2025-11-01 @ 23:39:00<br>generated on 2025-11-09 @ 13:59:39</sub></p>

## HW/SW Configuration

| Parameter | Value |
|:---|:---|
| Board | [EFR32xG27 Development Kit](https://www.silabs.com/development-tools/wireless/efr32xg27-development-kit) (BRD2602A) |
| SDK | Simplicity SDK (RAIL) |
| DCDC | disabled |


## EM&bull;Scope results · JS220

### 🟠&ensp;sleep

| supply voltage | &emsp;current (avg)&emsp; | &emsp;current (std)&emsp; | &emsp;average power&emsp;
|:---:|:---:|:---:|:---:|
| 3.0 V |  2.5 µA |  0.7 µA |  7.5 µW |

### 🟠&ensp;1&thinsp;s event period

| &emsp;&emsp;event energy (avg)&emsp;&emsp; | &emsp;&emsp;energy per period&emsp;&emsp; | &emsp;&emsp;energy per day&emsp;&emsp; | &emsp;&emsp;&emsp;**EM&bull;eralds**&emsp;&emsp;&emsp;
|:---:|:---:|:---:|:---:|
| 26.0 µJ | 33.5 µJ |  2.9 J | 27.61 |

### 🟠&ensp;10&thinsp;s event period

| &emsp;&emsp;event energy (avg)&emsp;&emsp; | &emsp;&emsp;energy per period&emsp;&emsp; | &emsp;&emsp;energy per day&emsp;&emsp; | &emsp;&emsp;&emsp;**EM&bull;eralds**&emsp;&emsp;&emsp;
|:---:|:---:|:---:|:---:|
| 26.0 µJ | 101.4 µJ |  0.9 J | 91.28 |

## Typical Event

<p align="center"><img src="event-B.png" alt="Event" width="900"></p>

## Notes

<!-- @emscope-pack:end -->

* sleep current is higher than expected because DCDC is disabled; enabling DCDC should significantly reduce both sleep and active-mode power
