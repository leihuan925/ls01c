# FTDI tools: prepare your USB port to talk with roch

DUDE=$(USER)

help:
	@echo ""
	@echo "Valid targets are: "
	@echo "  udev  : copy udev rules for /dev/roch"
	@echo "  utils : create ftdi utilities."
	@echo ""
	@echo "There is no make target for actually flashing the device."
	@echo "Because this is dangerous, be sure to read doxygen/mainpage.dox"
	@echo "for detailed info on how to do this by hand (./bin/ftdi_roch)."
	@echo ""

utils: all

udev:
	@echo ""
	@echo "Copying 57-roch.rules -> to /etc/udev/rules.d"
	@echo ""
	@sudo addgroup $(DUDE) dialout
	@sudo cp 57-roch.rules /etc/udev/rules.d
	@sudo service udev reload
	@sudo service udev restart
	@echo ""
	@echo "Logout and log back in to make sure the dialout group permissions take affect."
	@echo ""

# Doxygen documentation: make sure you sudo apt-get install ros-indigo-rosdoc-lite first.
doxygen:
	@rm -rf doc
	rosdoc_lite -o doc ./

.PHONY: doxygen
