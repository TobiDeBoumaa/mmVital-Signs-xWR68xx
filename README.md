# mmVital-Signs

> Millimeter-wave vital-signs detection 

<p align="left">
    <a href="https://github.com/KylinC/mmVital-Signs"><img src="https://img.shields.io/badge/Python-3.10-blue" alt="GitHub version"></a>
    <a href="https://github.com/KylinC/mmVital-Signs"><img src="https://img.shields.io/badge/C%2FC%2B%2B-98-yellow" alt="GitHub version"></a>
    <a href="https://github.com/KylinC/mmVital-Signs"><img src="https://img.shields.io/badge/TI%20mmWave%20SDK-3.6.x.x-orange" alt="GitHub version"></a>
    <a href="https://github.com/KylinC/mmVital-Signs"><img src="https://img.shields.io/badge/CCS-12.3.0-lightgrey" alt="GitHub version"></a>
  </p>

The [mmVital-Signs project](https://github.com/KylinC/mmVital-Signs) aims at vital signs detection and provide standard python API from [Texas Instrument](https://www.ti.com.cn/) (TI) mmWave hardware, such as xWR14xx, xWR16xx and xWR68xx.

### Experiment Environment

> Detection range covers the hemicircle area at 0m ~ 8.6m, refers to Part.3

![](http://kylinhub.oss-cn-shanghai.aliyuncs.com/2021-01-17-IMG_8789.jpg)



### Demo

![捕获](http://kylinhub.oss-cn-shanghai.aliyuncs.com/2021-01-17-020515.png)

![image](https://github.com/KylinC/mmVital-Signs/blob/main/docs/VS-2.gif)   



### Theory

- **Biology**

Typical body surface displacement parameters due to breathing and hear-beat are：

<img src="http://kylinhub.oss-cn-shanghai.aliyuncs.com/2021-01-17-%E6%88%AA%E5%B1%8F2021-01-17%20%E4%B8%8A%E5%8D%8810.06.14.png" height="80" />

- **FMCW Basics** 

Periodic linearly-increasing frequency chirps (known as Frequency-Modulated Continuous Wave (FMCW)) are transmitted by radar towards the object：

<img src="http://kylinhub.oss-cn-shanghai.aliyuncs.com/2021-01-17-%E6%88%AA%E5%B1%8F2021-01-17%20%E4%B8%8A%E5%8D%8810.22.56.jpg" height="150" />

Transmitted FMCW signal is given by $$s(t)=e^{j\cdot(2\pi f_ct+\pi \frac{B}{T}t^2)}$$ , it means that we can measure the changes of phase in back waves to predict the movement as $$\Delta \phi = \frac{4\pi\Delta d}{\lambda}$$ 

- **Chirp Configuration for Demo**

>  100 ADC Samples per chirp. Chirp duration is 50 ms based on the IF sampling rate of 2 MHz

Vital signs waveform is sampled along the “slow time axis” hence the vital signs sampling rate is equal to the Frame-rate of system 

<img src="http://kylinhub.oss-cn-shanghai.aliyuncs.com/2021-01-17-%E6%88%AA%E5%B1%8F2021-01-17%20%E4%B8%8A%E5%8D%8810.35.52.jpg" height="300" />

### Requirements

| **Item**     | **Details**                                                  |
| ------------ | ------------------------------------------------------------ |
| Device       | [IWR6843ISK Antenna Module](http://www.ti.com/tool/IWR6843ISK) **OR** [IWR6843ISK_ODS Antenna Module](http://www.ti.com/tool/IWR6843ISK-ODS) **OR** [IWR6843AOPEVM](http://www.ti.com/tool/IWR6843AOPEVM). |
| Power Supply | 5V, 3A with 2.1-mm barrel jack (center positive). The power supply can be wall adapter style or a battery pack with a USB to barrel jack cable. |
| Python 3.10  | All package included in requirements.txt                     |

