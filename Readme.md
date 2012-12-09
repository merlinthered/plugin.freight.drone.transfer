# Transfer Freight via Drones: Remake

![Freight drone](http://img3.imagebanana.com/img/d9ibkjf/frachtdrohne.jpg)

This script allows the working transfer of freight via drones.
The command is located in the trade commands and differs from the EGO script by its yellow color.

Usage is equal to the EGOSOFT script. However, the behaviour is a little different.

Corresponding thread on the Egosoft forums: [[Script][Mar/17/2009] Transfer Freight via Drones - working](http://forum.egosoft.com/viewtopic.php?t=239069)

## Description:
This command allows you to transfer freight to and from a station or ship over large distances. Intergalactic Trade Software Standards now make it possible for the drones to trade with foreign stations. Due to their size freight drones can only be used by big ships.

## Requirements:
* Ship of class big ship (except M8) - Using drones on a ship that is smaller than the drone makes no sense...
* Trade Command Software Mk2
* Freight Drone

## Installation/Update:
* Copy the contents of the "t" folder into the X3 TC\t folder
* Copy the contents of the "scripts" folder into the X3 TC\scripts folder
* If ChemODur's string library is already installed, the t files of it can be overwritten with the ones contained in this package. They contain minor fixes for german letters.

## Deinstallation:
* Cancel all running transfers (collect the drones or give them another command)
* Save
* Quit X3 and remove the scripts' files from the "scripts" folder (see "Used Files")
* Remove the language file from the "t" folder (see "Used Files")

## Behaviour:
If more wares than a single drone can carry are selected more drones are used and the selected wares are distributed between them.
A drone loads as much selected ware as possible from the starting ship and moves to its destination. Then it unloads the wares. If the target doesn't have enough free cargo space the drone waits until more space is available. When it's empty it starts loading the wares to transport back from the destination. If the target doesn't have enough of them the drone waits until the stock is refilled! That's why the target's stock is not regarded when selecting the wares to transport back from the destination.
When the selected amount of wares has been loaded the drone starts back to it's starting ship. Then it starts unloading the wares and follows the starting ship within transporter range until everything has been unloaded. If there is not enough space in the starting ship's cargo bay the drone waits until more space is cleared. Then it flies to the ship to be collected. This now happens automatically. M2 owners now no longer have to collect the drones manually.

## Known Problems:
It's possible that the drones don't transport all wares that have been selected. This is due to the fact that while selecting the wares it is ignored that they have to be distibuted between multiple drones.
E.g. if you have three drones, they have a total cargo bay of 2400 units. If you want to transport 4 units of a ware with a volume of 600, selecting these is no problem in the UI, because 4*600 fits exactly into the 2400 cargo bay of the drones. However, only 3 of them can be transported, because a drone can hold only one of them at a time and the remaining one can not be split to be transported partly in different drones. If something like this happens, the script will not alert you that some of the selected wares could not be transported. A little thinking is needed here ;)
_This case has not yet been tested properly_

## Used Files:

* `t\8222-L044.xml`
* `t\8222-L049.xml`
* `t\8910-L007.xml` <-------String Library by ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
* `t\8910-L044.xml` <-------String Library by ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
* `t\8910-L049.xml` <-------String Library by ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377

* `scripts\lib.chem.strings.xml` <-------String Library by ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
* `scripts\plugin.freight.drone.delivery.xml`
* `scripts\plugin.freight.drone.gui.xml`
* `scripts\setup.freight.drone.move.xml`
* `scripts\plugin.freight.drone.target.xml`
* `scripts\plugin.freight.drone.transfer.xml`
* `scripts\plugin.freight.drone.wares.xml`
* `scripts\setup.freight.drone.transfer.xml`

## Used Resources:

### Command Slot
`COMMAND_TYPE_TRADE_22 (422)` ->"COMMAND_DRONE_WARE_EXCHANGE"

### Language Files 
`8222-L044.xml (page id=8222)`
`8222-L049.xml (page id=8222)`
`8910-L007.xml (page id=8910)` <-------String Library by ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
`8910-L044.xml (page id=8910)` <-------String Library by ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
`8910-L049.xml (page id=8910)` <-------String Library by ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377

## Changelog:

### 2009-03-17: v beta 07

- Executing the command no longer terminates any other commands on the ship.
- In the ware selection menu the current stock, transport class and volume of each ware is now displayed
- Used ChemODurs String Library for formatting.

### 2009-03-13: v beta 06

- Freight drones no longer load installed wares.

### 2009-03-13: v beta 05

- The script version is now displayed in the upper right corner of the main transfer window. (Yes, I'm bored...)


### 2009-03-11: v beta 04

- When the drone is sent to buy wares at a foreign station it now waits until the player has enough money instead of loading all the wares and only paying as much as the player can afford.


### 2009-03-09: v beta 03

- Initial English Release
