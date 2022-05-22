# USB uses NRZI encoding:
1 : no change
0 : change in level.
If you hook it up on an oscilloscope, first thing is to decode J and K into 0 and 1s. 

# USB DP and DM are differential instead of CLK/Data
This offers several advantages:
1. Less interferecen from environment. Any EMI received is likely to be cancelled out by the two wires 180 out of phase.
2. Less EMI emission from USB. Something running half a GB/s acts like antenna. The two wires have magnetic field that cancel out. 

But the clocks have to be inferred. 

# USB effective range
  5 meter

# USB endianess
	lsb first 
	while I2C and SPI are msb first.

# Bit Stuffing:
A zero is inserted after every six consecutive ones to force transition in NRZI data stream. 
