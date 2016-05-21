
# import the RPi.GPIO module:
import RPi.GPIO as GPIO

# There are two ways of numbering the IO pins on a Raspberry Pi within RPi.GPIO. The first is using the BOARD numbering system and second numbering system is the BCM numbers.
# BOARD numbering system refers to the pin numbers on the P1 header of the Raspberry Pi board.
# BCM numbers system refers to the channel numbers on the Broadcom SOC.

# To specify BCM numbers system you are using
GPIO.setmode(GPIO.BCM)

# To detect which pin numbering system has been set
# mode = GPIO.getmode()

# You need to set up every channel you are using as an input or an output.
# To configure a channel as an input:
GPIO.setup(17, GPIO.IN)


while True:
	if GPIO.input(17):
		tfile = open("/sys/bus/w1/devices/10-000802824e58/w1_slave")
		text = tfile.read()
		tfile.close()
		temperature_data = text.split()[-1]
		temperature = float(temperature_data[2:])
		temperature = temperature / 1000
		print temperature
	while GPIO.input(17):
		pass

