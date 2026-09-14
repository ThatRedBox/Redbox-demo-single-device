![Redbox banner](https://raw.githubusercontent.com/ThatRedBox/.github/refs/heads/main/brand/Redbox_banner.png)

Redbox demo project lorem ipsum dolores si amet ...

## Wiring the sensors and actuators
| Port     | Raspberry Pi GPIO      | Module              |
|----------|------------------------|---------------------|
| **D1**   | GPIO12 <br/>GPIO20     | LED red             |
| **D2**   | GPIO21 <br/>GPIO16     | LED green           |
| **D3**   | GPIO13 <br/>GPIO24     | Motion Sensor       |
| **D4**   | GPIO25 <br/>GPIO22     | Buzzer              |
| **D5**   | GPIO23 <br/>GPIO27     | Switch (momentary)  |
| **A1**   | *ADC* CH0 <br/>*ADC* CH1  | Joystick         |
| **A2**   | *ADC* CH2 <br/>*ADC* CH3  | Slider           |
| **I2C**  | I2C SDA <br/>I2C SDL   |          /          |
| **UART** | UART RX <br/>UART TX   |          /          |


## Installing the flows
For each Redbox Device, install its respective flows

1. Open [Redbox_flows.json](Redbox-one/Redbox_flows.json) file here on GitHub, and click the `Copy raw file` button.
2. Open the web editor on the box (usually http://[ip address]).
3. In the top-right menu, select `≡ → Import → Clipboard`.
4. Paste the copied content into the dialog and click `Import`.
5. Click `Deploy` to activate the flow. Check the Debug sidebar or your configured outputs to verify everything is running.
6. Open the `Dashboard` at http://[ip address]?view=dashboard

## License & Collaboration

**Copyright© 2026 Sanne 'SpuQ' Santens**. Redbox is licensed under the
**[MIT License](LICENSE.txt)**. Trademark rules and guidlines apply.