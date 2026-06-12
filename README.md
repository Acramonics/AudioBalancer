AudioBalancer
=============

Andrew Martin, acramonics, 2026
-------------------------------

AudioBalancer is a balanced line receiver to unbalanced and an unbalanced to balanced driver on a single board. This could be used as a standalone device or as an add on to another circuit - the baord has been designed to be as small as possible while using through-hole components.

The circuit uses the SSM2141P receiver and SSM2142P receiver. These are now end-of-life, but still quite easy to find quite cheaply.

Both receiver and driver contain capacitors for decoupling 48V phantom
power on the balanced connection protection for the chips if these are
charged and the inputs are accidentally shorted to earth. See the
[Phantom Menace](./docs/AES5335_48V_Phantom_Menace.pdf) document.

| Components                   | Function            | Options              |
| :--------------------------- | :------------------ | :------------------- |
| (1) C3,C4,C13,C14            | HF coupling         | Omit if not needed   |
| (2) C1,C2,C11,C12            | Phantom protection  | Bridge if not needed |
| (3) D1,D2,D3,D4, D5,D6,D7,D8 | Short protection    | Omit if not needed   |
| (4) R4,R5,R6,R7              | Short protection    | Omit if not needed   |

1. The 10nF capacitors across the decoupling capacitors are to ensure
   a good high frequency response. Depending on your application these
   may not be needed.

2. These prevent the 48V phantom power reaching the ICs. If you are
   confident that this is not a problem in your application, they may
   be bridged out.

3. If the 47uF capacitors are charged by phantom power and the signal
   pins are accidentally shorted to ground these provide protection to
   the chips by shunting the voltage to the power rail. Normal 1N4148
   diodes may also be used, but they will not provide the same degree
   of protection.

4. These allow the 47uF capacitors to discharge in the event of a short.

Consequently, if you are confident of no problems with phantom power,
you can omit the eight Schottky diodes, and the four 10K resistors and
replace the four 47uF coupling capacitors with links.





