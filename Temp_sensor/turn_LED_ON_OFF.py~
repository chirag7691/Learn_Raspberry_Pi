
# Open the export file and write GPIO pin number we want to use to connect LED to it, hence "w"
export_file = open("/sys/class/gpio/export", "w")

# write pin the LED is connected to:
export_file.write("18")

# Close the file now that the text has been read.
export_file.close()
#==========================================================================

# Open the direction file and write to it, hence "w"
direction_file = open("/sys/class/gpio/gpio18/direction", "w")

# Writing the "out" to the direction file makes the pin to be an output pin
direction_file.write("out")

# Close the file now that the text has been read.
direction_file.close()
#==========================================================================

# Open the value file and write to it, hence "w"
value_file = open("/sys/class/gpio/gpio18/value", "w")

# Writing the number "1" to the value file makes the pin turn on
value_file.write("1")

# Close the file now that the text has been read.
value_file.close()

value_file = open("/sys/class/gpio/gpio18/value", "w")

# Writing the number "0" to the value file makes the pin turn off
value_file.write("0")

# Close the file now that the text has been read.
value_file.close()
#==========================================================================

# Open the unexport file and write GPIO pin number we have useed to connect LED to it to be free, hence "w"
unexport_file = open("/sys/class/gpio/unexport", "w")

# write pin the LED is connected to:
unexport_file.write("18")

# Close the file now that the text has been read.
unexport_file.close()
