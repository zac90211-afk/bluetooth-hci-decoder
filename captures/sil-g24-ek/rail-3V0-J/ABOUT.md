<h1 align="center">SiLabs EFR32xG24 · Simplicity (RAIL) · 3V0</h1>

<p align="center"><img src="../../../docs/images/uc-banner.svg" alt="Under construction" width="420"></p>

<!-- @emscope-pack:start -->

<!-- *** AUTOMATICALLY GENERATED CONTENT – DO NOT EDIT *** -->  

<p align="right"><sub>captured on 2025-11-01 @ 16:49:08<br>generated on 2025-11-09 @ 13:59:38</sub></p>

## HW/SW Configuration

| Parameter | Value |
|:---|:---|
| Board | [EFR32xG24 Explorer Kit](https://www.silabs.com/development-tools/wireless/efr32xg24-explorer-kit) (BRD2703A) |
| SDK | Simplicity SDK (RAIL) |
| DCDC | disabled |


## EM&bull;Scope results · JS220

### 🟠&ensp;sleep

| supply voltage | &emsp;current (avg)&emsp; | &emsp;current (std)&emsp; | &emsp;average power&emsp;
|:---:|:---:|:---:|:---:|
| 3.0 V |  3.9 µA |  0.6 µA | 11.6 µW |

### 🟠&ensp;1&thinsp;s event period

| &emsp;&emsp;event energy (avg)&emsp;&emsp; | &emsp;&emsp;energy per period&emsp;&emsp; | &emsp;&emsp;energy per day&emsp;&emsp; | &emsp;&emsp;&emsp;**EM&bull;eralds**&emsp;&emsp;&emsp;
|:---:|:---:|:---:|:---:|
| 37.2 µJ | 48.8 µJ |  4.2 J | 18.98 |

### 🟠&ensp;10&thinsp;s event period

| &emsp;&emsp;event energy (avg)&emsp;&emsp; | &emsp;&emsp;energy per period&emsp;&emsp; | &emsp;&emsp;energy per day&emsp;&emsp; | &emsp;&emsp;&emsp;**EM&bull;eralds**&emsp;&emsp;&emsp;
|:---:|:---:|:---:|:---:|
| 37.2 µJ | 153.1 µJ |  1.3 J | 60.49 |

## Typical Event

<p align="center"><img src="event-B.png" alt="Event" width="900"></p>

## Notes

<!-- @emscope-pack:end -->

* sleep current is higher than expected because DCDC is disabled; enabling DCDC should significantly reduce both sleep and active-mode power
