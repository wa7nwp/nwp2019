# Sound Card Radio

## Radios

### IC-7100
+ http://www.n4rfc.com/?p=1419
+ https://www.icomamerica.com/en/products/amateur/hf/rsba1/default.aspx

### FSQ Bellingham

The main FSQ event around Bellingham, including Ferndale , Blaine, Birch Bay, and Linden, and beyond, Is the Sunday morning ragchew on 145.580 wide band FM Symplex. It starts around nine and goes until everyone runs out of steam. Start fldigi, select FSQ 6 or 4.5, ensure the “FSQ-ON” button is on, and send “allcall *”. If you get any replies, you’re good to go. Adjust the gray squelch bar at the bottom right so that it’s just above the bouncing green bar with no signal being received.

Reach out to this group if you have more questions -  Google Groups "Northwest Washington Digital Amateur Radio" group.

Chris KC9AD.

### FX.25

#### UZ7HO

Here is beta-version of FX.25 mode: http://uz7.ho.ua/fx25.zip
SM requires "fx25.dll" for FX.25 operation. This is optional DLL and you may not use it then FX.25 feature will not active.
By default SM configured for "FX.25 RX-ONLY". If you are going to use FX.25 mode for TX then you need to enable this option:
Go to "Modems" - "FX.25 Mode" there you find: "NONE" "RX-ONLY" or "RX-TX"
The "RX-TX" mode includes such FEC parameters:
Block size - RS parity size
32 - 16
64 - 16
128 - 32
191 - 64
221 - 32
239 - 16
PS: I found out that the best Paclen for direct link is 35 or 100 for the minimal RS block padding. It would be good to add 96 bytes block for Paclen 50-60, since there is a lot of unused FX.25 tags for that but it requires coordination.
    
