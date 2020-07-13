	  ______                              _
	 / _____)             _              | |
	( (____  _____ ____ _| |_ _____  ____| |__
	 \____ \| ___ |    (_   _) ___ |/ ___)  _ \
	 _____) ) ____| | | || |_| ____( (___| | | |
	(______/|_____)_|_|_| \__)_____)\____)_| |_|
	  (C)2020 Semtech

Spectral Scan Utility
=====================


## 1. Introduction

This software allows to scan the spectral band using the additional sx1261 radio
of the Semtech Corecell reference design.
It computes a RSSI histogram on several frequencies, that will help to detect
occupied bands and get interferer profiles.
It logs the histogram in a .csv file.

## 2. Command line options

### 2.1. General options ###

`-h`
will display a short help and version informations.

### 2.2. SPI options ###

`-d spidev_path`
specifies the spi_dev path to be used to acces the sx1261 radio.

### 2.2. USB options ###

`-u -d tty_path`
specifies the tty path to be used to acces the STM32 which will redirect commands
to the sx1261 radio.

## 3. Usage

This utility is autonomous and will perform a full initialization of the
concentrator. So it cannot be run in parallel of the packet forwarder.

It will scan channels as specified on the command line, the first channel being
the given frequency (-f argument) and the other channels (number given with -n
argument) shifted by 200kHz from the previous one.

It then generates a CSV file with the RSSI histogram for each channel.

## 4. Legal notice

The information presented in this project documentation does not form part of
any quotation or contract, is believed to be accurate and reliable and may be
changed without notice. No liability will be accepted by the publisher for any
consequence of its use. Publication thereof does not convey nor imply any
license under patent or other industrial or intellectual property rights.
Semtech assumes no responsibility or liability whatsoever for any failure or
unexpected operation resulting from misuse, neglect improper installation,
repair or improper handling or unusual physical or electrical stress
including, but not limited to, exposure to parameters beyond the specified
maximum ratings or operation outside the specified range.

SEMTECH PRODUCTS ARE NOT DESIGNED, INTENDED, AUTHORIZED OR WARRANTED TO BE
SUITABLE FOR USE IN LIFE-SUPPORT APPLICATIONS, DEVICES OR SYSTEMS OR OTHER
CRITICAL APPLICATIONS. INCLUSION OF SEMTECH PRODUCTS IN SUCH APPLICATIONS IS
UNDERSTOOD TO BE UNDERTAKEN SOLELY AT THE CUSTOMER'S OWN RISK. Should a
customer purchase or use Semtech products for any such unauthorized
application, the customer shall indemnify and hold Semtech and its officers,
employees, subsidiaries, affiliates, and distributors harmless against all
claims, costs damages and attorney fees which could arise.

*EOF*