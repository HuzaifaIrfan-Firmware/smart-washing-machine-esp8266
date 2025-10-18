<div align="center">
  <h1>Smart Washing Machine Controller ESP8266</h1>
  <p><h3 align="center">Firmware for ESP8266 Controller 🚀</h3></p>
</div>

[Hardware Design](https://github.com/HuzaifaIrfan-IoT/smart-washing-machine)
&nbsp;&nbsp;•&nbsp;&nbsp;
[Android App](https://github.com/HuzaifaIrfan-Mobile/smart-washing-machine-app)

<hr>

[![Android Controlled Washing Machine](https://ytcards.demolab.com/?id=oTMUrj1S7qQ&title=Android+Controlled+Washing+Machine&lang=en&timestamp=1698796800&background_color=%230d1117&title_color=%23ffffff&stats_color=%23dedede&max_title_lines=1&width=300&border_radius=5&duration=0)](https://www.youtube.com/shorts/oTMUrj1S7qQ)

## Features
- [x] CPU Task Scheduler (Task Manager IO) for Running CPU Tasks
- [x] 16x Machine Tasks can be set in the Tasks Sequence
- [x] REST API Server for Remote Control
- [x] Watch Dog Timer to Restart if the CPU is out of Control
- [x] Rising Interrupt (if Lid is Opened) and Pause if Drying
- [ ] Water Level Sensor
- [ ] Maximum Water Inlet Motor Time
- [ ] Minimum Time to Drain Water before New Filling and Spinning
- [ ] Water Level Switch to be added Later

## REST API Server (Postman Documentation)
https://documenter.getpostman.com/view/6684754/2s9YXmWfAG


## Install
- VS Code
- PlatfornIO


## Flash to ESP8266 Controller
- Change Your WIFI SSID and Password in [rest_api_server](smart_washing_machine_esp8266/src/rest_api_server/rest_api_server.cpp)

## Overview

![Overview](overview.drawio.png)

### Washing Machine Tasks

| ID | Description             | Minimum (s) | Countdown (s) | Maximum (s) |
|----|-------------------------|-------------|----------------|--------------|
| 0  | MACHINE_WAITING_TASK    | 1           | 5              | 60           |
| 1  | WATER_FILLING_TASK      | 30          | 60             | 1200         |
| 2  | WASHER_SPINNING_TASK    | 30          | 300            | 600          |
| 3  | CLOTHES_SOAKING_TASK    | 60          | 300            | 1800         |
| 4  | WATER_DRAINING_TASK     | 120         | 120            | 1200         |
| 5  | DRYER_TASK              | 60          | 120            | 300          |
| 6  | SEQUENCE_END_TASK       | 20          | 20             | 30           |


### Lid Switch Truth Table

| Lid Closed | Dryer Vibration Safety Switch (NC) | Line Connected | Pulled Up Pin | Code Check     |
|------------|-------------------------------------|----------------|----------------|----------------|
| 0          | 0                                   | 0              | 5V             | digitalRead    |
| 1          | 0                                   | 0              | 5V             | RISING Interrupt |
| 0          | 1                                   | 0              | 5V             | digitalRead    |
| 1          | 1                                   | 1              | GND            | digitalRead    |

- NC = Normally Closed



# 📝 Documentation

# 📚 References


# 🤝🏻 Connect with Me

## Huzaifa Irfan

- 💬 Just want to say hi?
- 🚀 Have a project to discuss?
- 📧 Email me @: [hi@huzaifairfan.com](mailto:hi@huzaifairfan.com)
- 📞 Visit my Profile for other channels:

[![GitHub](https://img.shields.io/badge/Github-%23222.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/HuzaifaIrfan/)
[![Website](https://img.shields.io/badge/Website-%23222.svg?style=for-the-badge&logo=google-chrome&logoColor==%234285F4)](https://www.huzaifairfan.com)
# 📜 License

Licensed under the GPL3 License, Copyright 2025 Huzaifa Irfan. [LICENSE](LICENSE)
<hr />
Last Updated on 2023-11-22
