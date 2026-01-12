To control multiple servo motors we need to make use of a servo driver. We used Adafruit PCA9685. They can be chained together and adressed individually. 

The motors connect to each driver on the pins on the bottom of the board. Each motor requires a voltage-in pin, a ground pin and a signal pin. Follow the labels on the board.

To address each servo driver separately, solder must be applied to the contact pads in the top right portion of the board. The pin combinations increment on a binary basis. The boards can be accessed based on their binary designation.

The drivers communicate with the raspberry pi via the SCL and SDA (Serial Clock, Serial Data) 12C GPIO Pins. Each additional driver is chained to the last through the pins on either side of the board.

Working out the correct power for the drivers.

Each driver needs access to a power supply outside the raspberry pi. Use a voltmeter and connect the electrodes between the ground and voltage pins of the driver. First determine the voltage running through driver when the device is at rest. Then find the voltage when all the motors are in motion. If you can test when all the motors are under stress. 

When you have worked out the maximum voltage required, find a power supply that will cover the voltage required. The power supply is attached to the driver through the connectors at the top of the board.

Once the motors are connected and powered, run the following script on the raspberry pi to activate the motors.The sample script can be found here
https://docs.circuitpython.org/projects/pca9685/en/latest/examples.html#servo-example

The dependencies required can be found here
https://docs.circuitpython.org/projects/pca9685/en/latest/
