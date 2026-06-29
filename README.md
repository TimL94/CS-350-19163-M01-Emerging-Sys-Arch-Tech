# CS 350 Final Project: Smart Thermostat

## Project Summary

This project is a smart thermostat prototype built with a Raspberry Pi. The system reads the current room temperature using an AHT20 temperature sensor through I2C. It uses three buttons for user input, two LEDs to show heating and cooling status, a 16x2 LCD display to show thermostat information, and UART serial communication to simulate sending data to a server.

The problem this project solves is the need for a low-level thermostat prototype that can monitor temperature, respond to user controls, display system status, and send thermostat data for future cloud-connected use. The thermostat has three main states: off, heat, and cool. The mode button cycles between these states. The increase and decrease buttons adjust the temperature set point. The red LED represents heating, and the blue LED represents cooling.

## What I Did Particularly Well

One thing I did well in this project was breaking the system into smaller parts and testing each part before putting everything together. I tested the LEDs, buttons, LCD display, temperature sensor, and serial communication separately so that I could narrow down issues more easily. This was important because problems in embedded systems can come from the wiring, GPIO pin assignments, hardware connections, software logic, or timing.

I also did well using a state machine to organize the thermostat logic. Instead of writing one long section of code with many conditionals, the program separates behavior into off, heat, and cool states. This makes the thermostat easier to understand and easier to debug. The LEDs update based on the current state, the current temperature, and the set point, which helps the system behave like a real thermostat.

## Where I Could Improve

One area where I could improve is making the program more user-friendly and production-ready. The current version works as a prototype, but the user interface could be improved with clearer LCD messages, better formatting, and more obvious feedback when buttons are pressed. I could also improve the shutdown process by making sure every thread and peripheral is closed as cleanly as possible.

Another area for improvement would be adding stronger error handling. For example, if the temperature sensor, LCD, or serial connection fails, the program could display an error message or safely continue in a limited mode. This would make the system more reliable and easier to troubleshoot.

## Tools and Resources Used

The main tools and resources I used were the Raspberry Pi, Python, GPIOZero, the AHT20 temperature sensor, the 16x2 LCD display, UART serial communication, and the python-statemachine library. I also used draw.io to create the state machine diagram and GitHub to store the project files.

The course lab guides were important resources because they explained how to wire the circuit, test the buttons, configure the LEDs, use the LCD display, and work with the Raspberry Pi peripherals. I also used terminal output and debug print statements to confirm that the program was entering the correct state and responding to button presses.

## Transferable Skills

This project helped me develop skills that are useful for other embedded systems and software projects. One major skill is debugging hardware and software together. In web development, many problems are only in the code, but in embedded systems the issue can also be caused by wiring, pin numbers, hardware connections, or communication protocols. Learning to test each piece individually is a skill I can use in future technical projects.

Another transferable skill is using state machines to organize complex behavior. State machines are useful whenever a system has different modes and clear transitions between them. I can apply this idea to embedded systems, application logic, robotics, IoT devices, and even full stack web applications where user actions change the state of an application.

I also gained experience working with common embedded communication methods such as GPIO, I2C, and UART. These skills are useful for future work involving sensors, devices, automation, and Internet of Things systems.

## Maintainability, Readability, and Adaptability

I made this project maintainable by organizing the thermostat behavior into a state machine with clear states and transitions. The off, heat, and cool states each have a specific purpose, which makes the logic easier to follow. The button handlers are also separated by function, so the mode button, increase button, and decrease button each have their own role.

The project is readable because the code includes comments that explain the purpose of the major sections, including the display setup, sensor setup, serial communication, button configuration, and thermostat state logic. The variable names also describe their purpose, such as `setPoint`, `redLight`, `blueLight`, and `processTempStateButton`.

The project is adaptable because the design could be expanded in the future. For example, the thermostat could be modified to send data to a real cloud service over Wi-Fi instead of only simulating server communication through UART. More sensors could also be added, or the LCD display could be updated to show more detailed system information. The state machine structure makes these future changes easier because new states or transitions could be added without rewriting the entire program.

## Portfolio Artifacts

The two artifacts included for this portfolio submission are:

- `Thermostat.py`
- `State Machine.drawio.pdf`

Together, these files show the completed smart thermostat prototype and the state machine design used to control its behavior.
