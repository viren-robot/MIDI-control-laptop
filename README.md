MIDI/CTRL

A browser-based MIDI controller. Play it with your laptop keyboard or the on-screen keys, and it sends real MIDI out to a connected USB-MIDI device (tested against a Casio CT-X870IN).

Requirements
Browser: Chrome, Edge, or Brave. Safari and Firefox do not support the Web MIDI API and will show an "unsupported browser" message.
Hardware: a class-compliant USB-MIDI device (keyboard, synth, or interface) connected via USB. A standard USB-A to USB-B cable works — the same type used for printers, scanners, or an Arduino Uno.
Setup
Plug the USB-B end into the device's MIDI/USB TO HOST port, USB-A end into your laptop.
Power on the device. Do this before or right after connecting the cable so it enumerates correctly.
Open midi-controller.html in Chrome, Edge, or Brave.
Allow the "use MIDI devices" permission prompt when it appears.
If you miss it: click the padlock icon in the address bar → Site settings → MIDI devices → Allow → reload the page.
Select your device from the OUTPUT dropdown at the top. The status LED should turn on and read LIVE.

If your device doesn't appear at all, check Windows Device Manager (or macOS Audio MIDI Setup) to confirm the OS sees it as a USB Audio/MIDI device — unplug, wait a few seconds, and replug with the device already powered on if it's missing.

Playing
Laptop keyboard:
Low octave: Z X C V B N M (white keys), S D G H J (black keys)
High octave: Q W E R T Y U I O P (white keys), 2 3 5 6 7 9 0 (black keys)
On-screen keys: click or tap. Vertical click position sets velocity (top = soft, bottom = hard).
Octave shift: the − / + buttons, range ±2 octaves.
Controls
Control	Sends	Behavior
Pitch wheel	Pitch Bend	Springs back to center on release
Mod wheel	CC1	Holds position
Volume knob	CC7	Drag vertically to turn
Cutoff knob	CC74	Drag vertically to turn
Channel

The CHANNEL dropdown defaults to AUTO (scan):

While scanning, every message is broadcast on all 16 MIDI channels, so the receiving device responds regardless of what channel it's set to.
Press a key directly on the physical device once, and the page detects the channel from its incoming MIDI and locks onto it — switching from broadcast to that single channel.
To re-scan (e.g. after changing the device's channel setting), reselect AUTO (scan) from the dropdown.
You can also set a channel manually from the dropdown at any time, which disables scanning.
Monitor

The readout panel at the bottom logs the last ~40 MIDI events sent or detected (note on/off, channel detection), with timestamps.

Troubleshooting
No sound, but the LED is LIVE and notes are logged: check the keyboard's Local Control setting — if it's off, the keyboard won't produce sound from its own key presses, but this shouldn't affect notes triggered externally. Also check the keyboard's own volume and that its local tone/mode isn't muted.
Device doesn't show in OUTPUT: confirm the browser has MIDI permission (see Setup step 4), and that the OS recognizes the USB connection.
Wrong notes / silence on specific channels: leave CHANNEL on AUTO (scan) and press a physical key once to auto-detec
