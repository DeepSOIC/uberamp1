# Feautures

* output channels: 8 independent(*) single-ended power outputs (TPA3255) + 2 headphone-amplified output channels + 2 non-amplified adau1701 dacs
    * independent 8 single-ended outputs can be arbitrarily combined into btl or even 3-phase-like arrangements.
    * BTL protections of the tpa chip can be enabled with solder bridges on the board
* two tpa3255 amps with full coverage of their supply range and peak output current(**)
* easy-to-program yet flexible adau1701 dsp chip, with self-boot memory on the board
* low-noise AK4454 dacs allow to use the full 113db(***) of dynamic range of the TPA3255
* 2 "feedbass" amplifiers on board, and places for resistors for custom analog mixing of feedbass into outputs.
* capacitor-free analog signal path (except analog inputs) allows to output dc, so uberamp1 can be used to drive motors
* 2 analog input channels
* bluetooth receiver with digital connection to the dsp (firmware = TODO)
* pads for summing inputs for each amp channel to allow adding custom analog feedbacks


(*) there is no place for decoupling capacitors on the board. So you might use one of the outputs as "ground", leaving you with 7 channels. In BTL, there are 4 output channels.

(**) at high supply voltage or high load currents, heatsinking becomes a challenge. It dissipates about 11W total in silence at 48 V.

(***) 113db is for BTL only. In SE mode, or across amps, the dynamic range of TPA3255 is much lower at 101 db.

# known problems (v1):

* power amps don't start exactly in sync, causing large excursion at powerup if a speaker is connected between amps. Seems unfixable.
* i don't have a good heat sink solution yet.
* dacs don't start up if the supply is raised slowly. Can be fixed with a bodge wire connecting "pg" net to "pd" pins of the dac chips
* it is very challenging to solder.

# soldering 

TLDR: manufacturability is screwed up on v1.

While the board was designed for hand-soldering, the footprints for 0603 passives turned out to not work well for hand-soldering.
It is further exacerbated by some bad placements - some pads are unreachable with a reasonable soldering iron. 
It seems that a lot of 0603 footprints can instead be populated with 0402 parts, that should make hand-soldering somewhat easier...

Reflow soldering for passives whould probably work well... but some other foorprints are completely unusable for reflow soldering.