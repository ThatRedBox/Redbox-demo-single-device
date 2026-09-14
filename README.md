![Redbox banner](https://raw.githubusercontent.com/ThatRedBox/.github/refs/heads/main/brand/Redbox_banner.png)

Three demo flows for a single [Redbox](https://github.com/ThatRedBox/Redbox-setup) device, showing
what the box does with the sensors and actuators wired to its ports: digital in and out, analog
inputs over the ADC, PWM, and a Dashboard you can open on your phone. Import the flows, wire up
the modules from the table below, and you have something running to take apart and rebuild.

Each demo lives on its own flow tab in the Node-RED editor, with its own page in the
Dashboard. Only the **Motion Detection Demo** tab is enabled after import; enable the
tab of the demo you want to try (double-click the tab → `Enable`) and click `Deploy`.

#### Demo 1: Motion Detector
A motion alarm built around the motion sensor on **D3**. As long as no motion is seen,
the green LED (**D2**) stays on. On motion, the red LED (**D1**) starts blinking, the
Dashboard shows a *"Motion detected!"* notification and plots the event on a chart.
The buzzer (**D4**) only sounds when the alarm is armed with the `Enable alarm` switch
on the Dashboard; that switch can also be toggled with the momentary button on **D5**.

#### Demo 2: Analog Joystick
Reads the analog inputs through the MCP3008 ADC, polled every 150 ms. The joystick on
**A1** (CH0/CH1) is plotted live on a Dashboard chart, and pressing it down lights the
green LED (**D2**). The slider on **A2** (CH2) drives a Dashboard gauge and dims the red
LED (**D1**) through a PWM output; pushed near its maximum, it also starts the buzzer
(**D4**).

#### Demo 3: Smartphone Gamepad
Turns the Dashboard into a gamepad you can open on your phone: a D-pad, an A/B button
pair and a middle section. The left and right arrows switch the red (**D1**) and green
(**D2**) LEDs, and the A button drives the buzzer (**D4**). The other way around, pressing
the physical button on **D5** generates a WAV beep in the flow and plays it through the
phone's speaker. The remaining buttons are left unwired as a starting point for your
own experiments.

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