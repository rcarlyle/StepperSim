# StepperSim
Ryan Carlyle

This is an Excel spreadsheet model of an open-loop stepper motor and stepper driver system. It is intended to facilitate drivetrain design for light CNC machinery such as 3D printers. 

## How to use:
1. Select the appropriate spreadsheet for your stepper driver chip.
2. Input the highlighted parameters for your motor, power supply, driver chip, and drivetrain.
3. Look at the output charts and interpret what you see. Hint: you want the coil current to closely track the target current.

Unfortunately, each driver chip has its own special control logic and features, so each spreadsheet is highly customized for a particular driver chip. Additional drivers may be added over time. Currently supported drivers:
- Allegro A4988

## Basic model methodology:
3. Calculate the instantaneous state parameters (such as microstep target and back-emf voltage)
4. Calculate how long until the driver's PWM chopper will next change state
4. Calculate coil current at that time via a simple first-order RL circuit model
5. Increment time to the next state and repeat

There's also a lot of logic to determine how the driver will act at each state change and to output some useful calculations. But that's details. 
