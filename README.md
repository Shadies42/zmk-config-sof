# Sof 
In early 2024, i went on a keyboard kit building bonansa. On one of these I killed Pin 11 of the Super Mini NRF52840-BLE, however, Pin 22 was free and so I have re-assigned Pin 14 (super mini's Pin 11) to Pro Micro Pin 4 (super mini's Pin 22).

I call this fixed up Sofle with a dead pin, simply, Sof.

I'll add pictures of the pin outs here.

In order to physically do this, I double checked the dead pin and straight up cut it off so there was no connection at all between the board and the socket ( i hear rewiring a pin to another pin, even a dead one, caun lead to issues ) and then used some spare copper wire, that i fashioned into a hook, to wrap around the dead pins socket and the new pins socket. 
This bridges the gap and allowed the software to scan pin 11's column. Yes, i could have splashed out the whole £12 ( inc. postage) for a new MCU, but, I get to feel smug by fixing it my self and teasing out a problem.

Again, reminder to add photos of terrible soldering and wiring...

The programming was the most arduous. I couldn't find how to best configure the files to update the switch matrix, but found that I would need to modify a dtsi and overlay file from these posts, the first of which which was very on the nose:

[Reddit Post](https://www.reddit.com/r/ErgoMechKeyboards/comments/19ekxvx/wireless_soflenicenano_help_dead_column_pin_can/)

[Reddut Post 2](https://www.reddit.com/r/ErgoMechKeyboards/comments/12hjcdh/workaround_for_pin_not_working_with_nicenano/)

[Reddit Post](https://www.reddit.com/r/ErgoMechKeyboards/comments/zwdwkg/comment/j1vimxx/)

[GitHub](https://github.com/romones/zmk-config-sweep/blob/main/config/boards/shields/cradio/cradio_right.overlay) < This detailed the file structure, how ever this came about after I figured it out with trial and error but it is here for anyone needing it as reference.

## Main Issues
It was alot of trial and error to figure out the file structure needed for these new files.

It also took a while for it to click that i needed to look at the Pro Micro pin out rather than the pin out of my actual board to re-write these files. So keep that in mind.

It was an absolute pain to force these sausage fingers into controlling a soldering iron into such a small space. I was soldering under the socker header... smart move...

## Final Notes
If you are searching for the same thing, then it is simpler than it sounds, you'll be fine. Have a look in the overlay file you can see where I changed the pin from 14 to 4, e.g., 11 to 22. All of those extra files your probably confused about where they came from. Check in the ZMK repo and look under shields, there should be the folders containing all the files for the default shields like Sofle or Corne. These are the files you are looking for. If your working on a whole new shielf (e.g. keyboard) then follow the instructions for making a new shield on the ZMK wiki.

Have Fun!
