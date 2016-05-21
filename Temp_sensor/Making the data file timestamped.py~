# Copyright (c) 2012 Matthew Kirk
# Licensed under MIT License, see 
# http://www.cl.cam.ac.uk/freshers/raspberrypi/tutorials/temperature/LICENSE

import RPi.GPIO as GPIO
import time

GPIO.setmode(GPIO.BCM)
GPIO.setup(17, GPIO.IN)
GPIO.setup(18, GPIO.OUT)
GPIO.setup(25, GPIO.OUT)

GPIO.output(18, GPIO.HIGH)

while True:
	if GPIO.input(17):
		break

while GPIO.input(17):
	pass

GPIO.output(18, GPIO.LOW)
GPIO.output(25, GPIO.HIGH)

timestamp = time.strftime("%Y-%m-%d-%H-%M-%S")
filename = "".join(["temperaturedata", timestamp, ".log"])
datafile = open(filename, "w", 1)

while True:
	tfile = open("/sys/bus/w1/devices/10-000802824e58/w1_slave")
	text = tfile.read()
	tfile.close()
	temperature_data = text.split()[-1]
	temperature = float(temperature_data[2:])
	temperature = temperature / 1000
	datafile.write(str(temperature) + "\n")
	if GPIO.input(17):
		break

datafile.close()
GPIO.output(25, GPIO.LOW)

