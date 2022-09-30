# FlyController-H743

- [FlyController-H743](#flycontroller-h743)
  - [Before](#before)
    - [Author](#author)
    - [Commit Rules](#commit-rules)
  - [Change Log](#change-log)
  - [Hardware Info](#hardware-info)
  - [GPIO Distribution](#gpio-distribution)
    - [*System Use*](#system-use)
    - [*ADC*](#adc)
    - [*UART(1,2,3,4,7)*](#uart12347)
    - [*SPI(1,2,3)*](#spi123)
    - [*I2C(2,4)*](#i2c24)
    - [*TIMER(1,3,4,15)*](#timer13415)
    - [*I/O or INT*](#io-or-int)


## Before

### Author

> github: github.com/sin1111yi   
> email: sin1111yi@foxmail.com   

### Commit Rules

use tags:

* progress
* fix
* bug
* update
* change

with a hex number   

e.g.   
* fix-1234: commit content
* progress-af12: detailed progress
* bug-a0b0: bug content, match bug id
* modify-efa8: modify info
* ...

-------------------
## Change Log

**09.30.2022**

1. trying to finish PCB design by ***Altuim Designer 22***
2. considering add bluetooth or wifi on board

**09.19.2022**

1. It is too hard to use KiCAD finish 6 layers PCB for me, stop using KiCAD for this project for now.
2. use ***Altuim Designer 22*** to finish project, please be careful!

**09.19.2022**

1. add rssi pin
2. change LED_PWM2 to pwm output backup 
3. add 4 directions LED pads interface

**09.17.2022**

1. add buzz pin & complement readme
2. add LICENSE
3. add info in SCHs

**09.16.2022**   

1. complete first version schematic

**09.11.2022**   

1. create project

-------------------
## Hardware Info

0. MCU: STM32H743VIH6
1. Gyroscope: BMI120
2. Barometer: BMP280
3. Magnetometer: QMC6308
4. OSD: AT7456E
5. Flash: W25Q128JWPIQ
6. DC/DC: TPS54302DDCR
7. LDO: ME6217

-------------------
## GPIO Distribution

### *System Use*   

| GPIO  | Define |    Source     |
| :---: | :----: | :-----------: |
| PA11  |   -    | USB_OTG_FS_DM |
| PA12  |   -    | USB_OTG_FS_DP |
| PA13  |   -    |     SWDIO     |
| PA14  |   -    |     SWCLK     |
|  PH0  |   -    |    OSC_IN     |
|  PH1  |   -    |    OSC_OUT    |

### *ADC*   

| GPIO  |  Define  |   Source   |
| :---: | :------: | :--------: |
|  PA2  | VBAT_ADC | ADC1_INP14 |
|  PA3  | CURR_ADC | ADC1_INP15 |
|  PC5  | RSSI_ADC | ADC1_INP8  |

### *UART(1,2,3,4,7)*   

| GPIO  | Define |  Source   |
| :---: | :----: | :-------: |
|  PA9  |  TX1   | USART1_TX |
| PA10  |  RX1   | USART1_RX |
|  PD5  |  TX2   | USART2_TX |
|  PD6  |  RX2   | USART2_RX |
| PC10  |  TX3   | USART3_TX |
| PC11  |  RX3   | USART3_RX |
|  PA0  |  TX4   | UART4_TX  |
|  PA1  |  RX4   | UART4_RX  |
|  PE8  |  TX7   | UART7_TX  |
|  PE7  |  RX7   | UART7_RX  |

### *SPI(1,2,3)*   

| GPIO  |  Define   |   Source    |
| :---: | :-------: | :---------: |
|  PA4  | SPI1_NSS1 | GPIO_Output |
|  PC4  | SPI1_NSS2 | GPIO_Output |
|  PA5  | SPI1_SCK  |  SPI1_SCK   |
|  PA6  | SPI1_MISO |  SPI1_MISO  |
|  PA7  | SPI1_MOSI |  SPI1_MOSI  |
| PB12  | SPI2_NSS  | GPIO_Output |
| PB13  | SPI2_SCK  |  SPI2_SCK   |
| PB14  | SPI2_MISO |  SPI2_MISO  |
| PB15  | SPI2_MOSI |  SPI2_MOSI  |
| PA15  | SPI3_NCS  | GPIO_Output |
|  PB3  | SPI3_SCK  |  SPI3_SCK   |
|  PB4  | SPI3_MISO |  SPI3_MISO  |
|  PB5  | SPI3_MOSI |  SPI3_MOSI  |

### *I2C(2,4)*   

| GPIO  | Define |  Source  |
| :---: | :----: | :------: |
| PB10  |  SCL2  | I2C2_SCL |
| PB11  |  SDA2  | I2C2_SDA |
|  PB6  |  SCL4  | I2C4_SCL |
|  PB7  |  SDA4  | I2C4_SDA |

### *TIMER(1,3,4,15)*

| GPIO  |  Define  |  Source   |
| :---: | :------: | :-------: |
| PE11  | CAM_CTRL | TIM1_CH2  |
|  PC6  |    M1    | TIM3_CH1  |
|  PC7  |    M2    | TIM3_CH2  |
|  PC8  |    M3    | TIM3_CH3  |
|  PC9  |    M4    | TIM3_CH4  |
| PD12  |    M5    | TIM4_CH1  |
| PD13  |    M6    | TIM4_CH2  |
| PD14  |    M7    | TIM4_CH3  |
| PD15  |    M8    | TIM4_CH4  |
|  PB6  | LED_PWM  | TIM15_CH1 |
|  PB7  | PWM_BKP  | TIM15_CH2 |

### *I/O or INT*

| GPIO  |   Define    | Source |
| :---: | :---------: | :----: |
|  PC0  |    LED0     | Output |
|  PC1  |    LED1     | Output |
|  PD0  |    BUZZ     | Output |
|  PB0  |    INT0     | EXTI0  |
|  PB1  |    INT1     | EXTI1  |
| PE13  | COMPASS_INT | EXTI13 |
|  PE9  |    INT9     | EXTI9  |
| PE12  |    INT12    | EXTI12 |

