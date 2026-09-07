---
title: Guides
---

# Creating custom IO puzzles
**You need the RustEdit extension installed on your server for IO to work.**

Before you get started, make sure you have either *Show IO Connections* or *Show selected IO Connections** toggled on in the *View* menu on the toolbar
![io_show_connections](https://attachments.rusthq.com/7bdee8ca9c4cdb9c3b77b66556a007294391f5698c8a9b4b64cf5d902753aa07 =150x)

All IO circuits require power. Make sure you have some kind of power source in your circuit.

You can create connections by selecting the IO prefab, in the bottom of the `Transform Tool` you will have a section titled `IO Tools`.
The `IO Tools` section contains both `Output Connections` and `Input Connections`. From these sections you can connection and disconnect connections.

IO connections are made by connecting a output slot of one IO entity to the input slot of another IO entity.
To make a connection, select one of the output slots on the selected IO entity, and simply click on a different IO entity.
When making a connection you can cancel by pressing the `Right Mouse Button`
![io_power_line](https://attachments.rusthq.com/8c8c0ebbbfad973488f15fc9f811b4a3fcd494acbedc73c8d3e684a02ab3b18e =400x)

## Creating a simple security door puzzle
In this short tutorial we are going to create a simple security door circuit using a fuse box and a card reader on one side of the door, and a push button on the other.

**NOTE** Doors are not IO entities. But we can control a door using a `Door Manipulator` which when powered will open a door in its proximity.

To setup this circuit we will need to add the following prefabs to our map;
- Generator
- Fusebox
- Card Reader
- Press Button
- Or Switch
- Door Manipulator
- Security Door 

Here I have arranged them for this demonstration
![io_securitydoorex_front](https://attachments.rusthq.com/7c0c7cfb291c09acf707ce4603a562a43bcff7ffd75068179d06798a9407a29f =400x)![io_securitydoorex_back](https://attachments.rusthq.com/5c0c2474dfcbd188a901a69c59c79fbc73d6e6a6cf7578ea1abfd3063128ed80 =450x)

On the front side we have the `Card Reader` and a `Fuse Box`
On the back side we have the `Generator`, `Or Switch`, `Door Manipulator` and `Press Button`

How we want this circuit to work is
- The card reader and the push button open the door
- The card reader will only have power when there is a fuse in the fuse box
- The push button will always work to open the door (so players aren't trapped inside)

**Step 1**
We want to connect the generator to both the fuse box and the press button. Click on the generator and then press 'Connect IO Output To...'. This will draw a line that will follow your mouse.
Move your mouse over to the fuse box and click on it.
This will show you a prompt to select which input slot you want to connect to. The fuse box only has 1 input slot so select 'Power In'
Lets do the same for the press button.
![io_gentofuse](https://attachments.rusthq.com/a3056bfed6b4870bb1801c02255d180a31476be52490304878707e7d2d0b4f66 =400x)

**Step 2**
Now lets connect the fuse box to the card reader the exact same way. Now if we select the card reader we will see a couple of extra options in the IO section of the transform tool.
![io_cardreader](https://attachments.rusthq.com/5f5697b43f838f5e649d1da46f9b108a841736f6292fa3bcd2a53b7c59c3a80a)
*Access Level* - Sets which color keycard is required to use the card reader
*Access Duration* - Sets the amount of time the door will stay open for after using the card reader.
You can set these options to what ever you like

** Step 3**
Now lets connect the card reader to the ORSwitch, and then also connect the press button to the ORSwitch. 
We are going to use both input slots on the ORSwitch so it doesn't matter which way we connect them.

**Step 4**
Finally connect the ORSwitch to the door manipulator. 
**NOTE** Be aware that the placement of the door manipulator is critical to it detecting the door once ingame. It is best placed on the hinge side of the door within 1m of it. The help with this when you select the door manipulator it will show you with whether it is a valid placement.
You also have 3 actions to choose between for a door manipulator;
*Open* - Opens the door when there is power and closes it when there is no power
*Close* - Does the opposite of Open
*Toggle* - Opens if closed when power is supplied, Closes is open when power is supplied.
We just need to set it to Open for this circuit
![io_doormanipulator](https://attachments.rusthq.com/3b1beed6834eacc014e9dde42847892126aafc2c3acc77fe12ae41d6b8b39bba)

**Step 5**
Crack open a beer and congratulate yourself on a job well done

Here is a video demonstrating this circuit when the IO tools were first implemented
!media(https://www.youtube.com/watch?v=wnhH6Cww7bo)

Here is the circuit diagram
![io_diagram](https://attachments.rusthq.com/fb4e8cb58ff624107de8d94b2512aaff48c63eb4fcddc64a7bd14250a352a46d)
