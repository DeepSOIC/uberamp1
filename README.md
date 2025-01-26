# Feautures

* output channels: 8 independent(*) single-ended power outputs (TPA3255) + 2 headphone-amplified output channels + 2 non-amplified adau1701 dacs
    * independent 8 single-ended outputs can be arbitrarily combined into btl or even 3-phase-like arrangements.
    * BTL protections of the tpa chip can be enabled with solder bridges on the board
    * headphone amplifier output 9 Vpp.
* two tpa3255 amps, with power up to 54 V and output current trip at 17 A per channel (**)
* easy-to-program yet flexible adau1701 dsp chip, with self-boot memory on the board
* low-noise AK4454 dacs
* SNR 111 dB in BTL and 101 db in SE (theoretical, unverified so far).
* 2 "feedbass" amplifiers on board, and places for resistors for custom analog mixing of feedbass into outputs.
* capacitor-free (***) analog signal path (except analog inputs) allows to output dc, so uberamp1 can be used to drive motors
* 2 analog input channels (2.5Vpp) (AC-coupled ground-referenced; DC coupling possible with an addon board)
* bluetooth receiver with digital connection to the dsp (firmware = TODO)
* pads for summing inputs for each amp channel to allow adding custom analog feedbacks
* fan control circuit

(*) there is no place for decoupling capacitors on the board. So you might use one of the outputs as "ground", leaving you with 7 channels. In BTL, there are 4 output channels.

(**) not fully tested yet. At high supply voltage or high load currents, heatsinking becomes a challenge. It dissipates about 11W total in silence at 48 V. It was really not designed to push out the full power continuously, it was designed so to handle transients well.

(***) there are footprints for dc blocking caps. Install jumpers if DC coupling is desired.

# known problems (v1.1):

* power amps don't start exactly in sync, causing large excursion at powerup if a speaker is connected between amps (it does so quietly, so it's not too bad). Seems unfixable.
* it is challenging to solder.
* i was unable to program the bluetooth chip to work with this amplifier so far.
* a fan is required at 48V supply voltage. It can work fanless if only one amplifier chip is active, or if the supply voltage is lower. 

# soldering 

Manufacturability is still slightly screwed up on v1.1.

While the board was designed for hand-soldering, but it also works with reflow soldering.
But footprints for 10uf bypass caps are now a little too large, they are prone to shifts to one pad during reflow.
And the rows of resistors next to dacs are placed too dense, and are prone to shorting together.

Top side can be reflow-soldered. 
Bottom side must be done by hand. 

