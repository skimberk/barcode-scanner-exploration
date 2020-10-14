# Barcode scanner exploration

I just got my hands on a barcode scanner from an old Point of Sales system. Since my brushless motor/self-balancing robot project is on hold since I fried all my DRV8305 gate drivers (and I'm just waiting for a bunch of other stuff from Digikey), I decided to take apart the scanner!

The thing looks flimsy on the outside but seems sturdy on the inside. There are three separate PCBs: the actual barcode scanning module, a phone connector with some diodes (seems to just be doing USB with phone connectors), and an intermediary PCB which connects the two.

The barcode scanning module seems to be made by Symbol Technologies, Inc. This is what it says on the label:

```
Symbol Technologies, Inc. Made in Mexico
(barcode)
(S)SN: M1L74D00F SW: NBRWDAAJ
P/N: SE-3223-I100AR SBRE
See integration guide for patent info
```

The barcode scanning module is itself composed of three PCBs soldered together. The main PCB, along with a smaller PCB soldered at 90 degrees on one edge with a big chip, and a very small PCB at the corner (also soldered at 90 degrees) which is attached to the laser diode. A metal block is screwed onto the main PCB, cradled on one side by the medium PCB and on one corner by the laser PCB. There are two magnets with mirrors on springs (there's a word for them, they're used for resin 3D printers and laser lightshows, but it escapes me) and the laser diode, all of which seem glued to the metal block. I removed the metal block by removing all the screws, desoldering the PCBs, and using my soldering iron to push out the pins for the magnet-mirror-things. The whole assembly slid off, revealing a photo diode still attached to the main PCB.

My guess as to how it works is that the laser diode is scanned back and forth by the magnet-mirror-things, bounces off the whites of the barcode (and is absorbed by the blacks) and returns to the scanner. The returning light somehow (some fancy angle stuff is going on) gets redirected to the photodiode. The photodiode is protected by a greenish-bluish mirror thing, which I'm guessing only lets through the wavelength of the laser. That way all 
