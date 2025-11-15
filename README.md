# Support

* If you like my work, you can support me through https://ko-fi.com/DualTachyon

# Common courtesy

Don't be an entitled user like "fe8769". Asking for help and then refusing it because "I have 40 years of experience with SW dev, it won't work.".
If you know the firmware / RT-4D better than me, then don't ask for my help or use my firmware.
Scare tactics like fake threats of calling law enforcement using bogus laws you don't understand is also not it.
Fake accusations of harassment also won't work. Still waiting for your public apology, dude...

Congratulation to those who felt the need to publicly spread hate in a public chat group, and those that defended it.
Development will now happen whenever I feel like it.

# Forewarning

- **If you don't know what this firmware is about, just go visit somewhere else.**
- **If you need a ready made codeplug to get started, just go visit somewhere else.**
- **This firmware is not for newbies to radios or DMR. Go visit somewhere else if you are a newbie.**
- **If you need to tell everyone on github that you have 40 years of computer and radio experience, go somewhere else.**
- **If you double click a file and nothing happens, go visit somewhere else.**
- **If you can't find a download for flashers, go visit somewhere else.**
- **If you think I'm annoying, then don't use my firmware! I never forced you to use my stuff. Go and use the official firmware.**

If you fit in any of the above points, stick to Official Radtel firmware as this firmware is not for you.

# Changelog

You find more friendly documentation at [wiki](https://github.com/jcalado/rt-4d-fw-beta/wiki) by [Joel](https://github.com/jcalado). Be aware that the documentation can sometimes lag behind the releases.

- From beta 38 onwards, the minimum DMR firmware suported will be 1.2.0.16. Any bug reports with b38+ that use older versions will be ignored.

- <img src="Zzz.png">Let's have a look I guess.</a>

- Beta 40
  - Fixed a bug with receiving group SMS.
  - As a result, RX group list now only support 32 IDs.
    - If you have more than 32 IDs in a group, only up to 32 will be used. The rest will be ignored.
    - If you need more than 32 IDs per group, you're probably doing it wrong anyway.
    - "But Dual! My OGD77 radio supports more than 32 IDs!". Great, then go use your OGD77 radio. This is not OGD77 firmware.
  - Fixed the scanner being interrupted by pressing a key when the key lock was in effect.
  - Fixed a bug where the TX LED could stay on after a very short transmission.

- Beta 39
  - Added DMR group name resolution in "Extra" menu.
    - If a group ID exists in your contacts list, it will be resolved and displayed instead of "GID:xxxx".
  - When a caller ID is not in the address book, "ID not found" will be displayed.

- Beta 38
  - Added "STICKY" mode to the DMR dial screen (green key).
    - In sticky mode, the entered ID will be used as the default contact for PTT when on the main screen.
    - This let's you change a TG temporarily without needing to input it over and over again.
    - Press * to activate sticky mode.
    - A small inverted S will appear on the bottom right of the screen.
    - Press * again to de-activate sticky mode to restore "default contact" functionality.
  - Press the side 2 key while in the DMR dial screen to save the entered ID as a new contact.
  - The instructions option in "Basic Set" has been removed.

- Beta 37 - Small and simple changes.
  - Fixed incorrect display of DCS subtones when captured with the spectrum or frequency monitor.
  - Spectrum no longer renders columns of non existing frequencies.
    - If your spectrum range does not align to the width of the spectrum (= 121 steps), you will see a partial spectrum only.
  - The LCD contrast is updated in real time when scrolling through the possible values in "Basic Set" -> "LCD Contrast".
    - Cancelling, pressing PTT or allow the exit timer to kick in will restore the contrast to the original setting.
    - A reboot is no longer required to take effect.
  - Long press the red key to exit to the main screen from any menu, deep level or otherwise.
  - The red LED will blink when attempting a DMR transmission to indicate progress contacting a DMR repeater.
    - The LED will then stay on as previously if a connection was made while PTT is still held.
    - The LED will turn off when PTT is released or if connection to the repeater failed.

- WIP
  - DCS codes are now correctly displayed in the capture list.
  - Spectrum no longer renders or processes frequencies beyond the "To:" limit in Scan Range.
    - Fixed display bug introduced by this feature when not in scan range mode.
  - In non promiscuous, calls coming from self ID are now ignored.

- Beta 36
  - Added "Show Zone Ch" to "Extra 06" menu, to select whether the bottom left channel number reflects the global channel or the number within the zone.
  - Fixed bug with a clear screen when changing SMS format.
  - Fixed a bug with analogue scrambling.
  - Added new spectrum features. Other than any bug fixes, no new spectrum features for a few betas.
    - Selecting the modulation has moved to the * key, like the step, noise, bandwidth fields.
    - The menu key now controls alternate screens for new features.
    - Press the menu key to alternate between the spectrum display, Scan Settings, Capture List and Blocked List.
    - Spectrum display
      - When in "Scan Mode", you can press the side 2 key to open squelch on any selected frequency.
      - When in "Range Scan" (see below for details), you can press the red key to exit this mode.
        - Traditional monitor mode will take effect.
    - Scan Settings
      - Press the up and down keys to select various options.
      - Press the green key on any option to activate them.
      - The "Start range scan" allows the spectrum to scan a wider range than fits on the screen.
        - Press the green key to activate it.
        - The frequency range can be modified with the "From:" and "To:" options.
          - These 2 can only be edited with the keys 0 to 9.
          - Press the menu key to auto complete a frequency (e.g. 144 MENU -> 144.000).
      - When set to ON, the capture option will add detected frequencies to the capture list.
      - When set to OFF, the replay option will skip detected frequencies from opening squelch.
        - This is not a block and is meant to give an audible cue when a given range has been "fully" scanned.
        - The replay option is only meaningful when capture is ON. When capture is OFF, replay is always ON.
      - When set to a value other than INF(nite), the max dwell timer puts a limit to how long the squelch remains open.
      - When set to a value other than NONE, the min dwell timer determines the minimum time an open signal must play before it is captured.
    - Capture list
      - Captured frequencies are shared with the frequency monitor.
      - The storage list has been increased to 256.
      - Like the frequency monitor, you can press the green key to alternate between frequency and subtone details.
      - Long press side 1 key to delete a single frequency.
      - Long press side 2 key (longer than normal) to delete all frequencies.
      - Long press the menu button to go to VFO mode at a selected frequency.
      - Press the red key to exit back to the main spectrum screen.
    - Blocked list
      - Same key usage as Capture List but no subtone information.

- Beta 35
  - Fixes to original firmware:
    - When sending an SMS fails, no longer get kicked out to the main screen.
    - Check the sending ID is valid before sending.
  - Added "PTT Lock" to "Extra 06" to disable PTT during key lock / always.
  - Long pressing the red key in the dial and DTMF screen will erase the entire input field.
  - Fixed a bug with saving SMS.
  - The spectrum has been revamped.
    - Noise suppression logic has been refactored.
      - 3 new controls have been added to allow finer control for opening squelch.
        - Noise suppression threshold.
        - Noise floor.
        - Noise register check.
      - You can find more details below about their usage.
      - It is also best understood by trying to use it. I'm no technical writer and my explanations will often suck.
    - The top of the screen shows settings that can be edited. From left to right:
      - Step with a fixed list of values: 1.0, 2.5, 5.0, 6.25, 8.33, 10.0, 12.5, 25.0, 50.0, 100.0 kHz.
      - Nxx: This is the noise suppression threshold and is accompanied by a slider on each side of the spectrum.
      - Fxx: This allows you to raise/lower the noise floor and affects the Nxx value.
      - Bandwidth: Narrow, Wide.
      - Modulation: FM, AM, SSB.
      - A "#" that represents the BK4819 Noise Register.
        - When this is on, noise quality is checked by BK4819 before opening squelch, even if the signal is above Nxx threshold.
        - Press side 2 key to toggle this setting on / off.
      - A "J" that represents "jump mode" and lets you move the frequency range by 60 steps. Read below for instructions.
    - The bottom of the screen shows 3 frequencies:
      - Left value is the starting frequency.
      - Middle value is the frequency of the last signal detected.
      - Right value is the end frequency.
    - Just under the spectrum are displayed an arrow pointing to the last frequency detected and the subtone, if available.
    - Both sides of the spectrum show a small slider that represents the noise suppression threshold.
    - Most settings at the top, and the left frequency can be edited via the * and up/down keys.
    - Key usage:
      - Press the * key to change the current field.
        - When selected, the left frequency will have a small arrow to its right.
        - When selected, the step, noise suppression, floor and bandwidth will be in inverted colors.
      - Press the up/down key to modify the selected field.
        - In frequency mode, this moves the frequency band by one step.
          - Press the green key to activate "jump mode" change to move in 60 steps instead.
          - Press it again to revert to one step mode.
      - Press 0 to 9 to edit the start frequency, from any field.
        - You can press the menu key to auto complete a frequency (e.g. press 144 MENU, for 144.000).
      - Press the menu key to change the modulation.
      - Press the # key to switch between monitor and scan mode.
        - Scan mode lets you move the cursor around the spectrum without a signal taking over.
      - Press side 1 to block an open signal.
        - An empty vertical line will be displayed in the spectrum.
      - Long press side 1 to clear the block list.
      - Press side 2 key to skip an open signal.
        - This is not a block and will be played again if found.
      - Long press the side 2 key to turn on/off the noise register check.

- Beta 34.1 minor hotfix
  - Clear the screen after entering the boot password.
  - Fixed Radtel bug where the scanner in VFO mode may not enter the selected scan range.
  - Note there is no indicator anywhere that you are running 34.1 vs 34.

- Beta 34
  - This beta uses the 3.16 baseline but excludes the following:
    - The "Carrier LED" is very buggy and latches on Tier 3 data transmissions.
    - DMR logic that made DMR scanning next to useless and increased latency for RX calls.
  - This beta assumes you have previous upgraded to either a beta 32 and above, or official firmware 3.15 and above.
    - If you didn't, check the beta 32 changelog.
  - Mitigations added to reduce / prevent the Radtel "silent RX" DMR bug where the RT-4D would be in a call but no audio would be playing.
  - An "INVALID!" is displayed when an invalid DMR ID is received.
    - An invalid ID is sometimes returned by the DMR firmware and it is currently unknown why that is.
    - When this occurred, garbled text could appear on the DMR screen.
  - A new "Frequency Monitor" has been added to the hotkey list.
    - This is based on the existing "Frequency Detect" feature but will capture frequencies autonomously into a list.
    - Press the menu key to exit the monitor and enter VFO mode at the last detected frequency.
    - Press the * key to change the time spent on a frequency before moving on.
    - Press the # key to select between 136-174 MHz and 400-480 MHz bands.
    - Long press the # key to select narrower bands.
    - Press the red key to exit this feature.
    - Press the green key to enter the list of captured frequencies, along with a counter of occurences.
      - Press the green key to swap between displaying frequencies and subtones detected.
      - Press the menu key on a frequency to stop monitoring and go into VFO mode at that frequency.
      - Press the red key to exit the list.
      - Press the * key to refresh the list with newly captured frequencies.
      - Long press side 1 key to delete a captured frequency.
      - Long press side 2 key to delete all frequencies.
    - Long press of the red key will force exit the monitor from any screen mode.
    - The list of frequencies is only saved to SPI flash when exiting the monitor.
    - Long press * is supported to enable the key lock and prevent accidental cancellation of the monitor.
    - The PTT button is prevented from cancelling the frequency monitor.
  - Press * in the "Call log" to switch the display between the DMR ID and the callsign.
  - Reintroduced DMR scan speed for those who don't like Radtel's 400ms default.
    - Go to "Extra Set 10" -> "DMR Scan Speed 06".
  - Improved handling of PTT when used outside the main screen.
    - Respects the "Main PTT TX" and "Secondary PTT" settings.

- Beta 33
  - Support for parity with Radtel 3.16 is targeting Beta 34 or 35.
  - Fixed Radtel bug with PTT within the address book. It now works.
  - Fixed Radtel bug where the current channel might change if an invalid TX frequency was present.
  - Fixed Radtel bug introduced in 3.15 with some visual corruption.
  - Fixed a bug with DCS decoding in the CTCSS/DCS scanner.
  - The backlight will turn on when your RT-4D is being probed by "Online Check" and "Remote Stun/Kill/Wake/Monitor".
  - When in the DMR dial screen, press # to activate the remote features being usable from that screen.
    - You only need to press # once per session, it will persist until you power off / restart.
    - Press # multiple times to cycle through the different features.
    - The selected feature is remembered every time you invoke the dial screen.
    - Long press the green key to activate the selected feature.
    - This only works when the ID is the private type.
  - "Live CTCSS" has been renamed to "Live SubTone" since it now supports DCS.
  - Renamed various typos, short names and some non sensical text.

- Beta 32
  - WARNING: BACKUP YOUR SETTINGS WITH CPS 1.21 IF YOU HAVEN'T INSTALLED OR USED 3.15 YET!
  - This beta is based on the v3.15 baseline from Radtel. This means a few things:
    - Not all official v3.15 changes have been implemented. Mainly, the spectrum update and "green LED" on DMR activity are not present in beta 32.
    - If you already upgraded to official 3.15 and are still using it, you can flash the beta directly and skip the following 2 comments. Otherwise read on.
      - Please follow the Radtel instructions in setting up a new code plug to prevent loss of data.
      - The biggest change is that RX groups have been expanded from 16 contacts to 128. This means if you don't have a backup, all but the first group in your RT-4D will be corrupted.
      - You can use CPS 1.22 to reload your groups, but make sure you follow Radtel instructions about CPS usage.
  - Improved CPS compatibility by moving new Scan Return setting.
    - If you have previously used the "Last CH" setting, please update the setting via the radio.
    - The setting in CPS is effectively ignored by this firmware moving forward.
    - CPS 1.22 and earlier will give an error if you read from the RT-4D with keys defined with non official features.
      - You can unbind those keys temporarily to be able to read+modify+write with CPS.
      - This will be improved in a future version.
  - Fixed Radtel bug where the incorrect CC is sometimes displayed.
  - Fixed Radtel bug where the wrong CC would play in non-promiscuous mode.
  - Fixed Radtel bug with zone channel editing where wrong channels would toggle and some duplicates appeared.
  - You can press the Menu key in the DMR Dial screen for a quick key-in without having to reach for PTT.
  - The green key long press now inherits all feature options of the other keys.
    - PLEASE REBIND THIS KEY with your preferred action as beta32 will interpret the previous setting as a different one.
  - Scanner supports a block list, similar to the spectrum.
    - Short press side 1 key to block a frequency / channel. Up to 256 are supported.
    - Long  press side 1 key to clear the block list
    - Block list is cleared when scanning ends.
  - Added a new hotkey option "Next Zone". Activating this feature will load the next zone that has channels.
  - Added a new hotkey option "Send DTMF" to bring up the "DTMF Select" menu with the 16 DTMF strings.
  - You can press the green key in the "DTMF Select" to quickly transmit that string.
  - You can press the green key in the scanner to exit to the last found channel/frequency.
  - When editing zone channels, empty channels and channels with empty names will now be populated with "Empty-XXXX" and "No Alias" respectively.
  - Fixed DMR tones not playing when entering/exiting a call.

- Beta 31
  - Support for display foreign characters has been fixed.
  - A small key icon is now displayed at the bottom if the current channel is configured with a DMR key.
  - Antenna icon has little use or meaning, so it has been replaced with the dual standby indicator.
  - Fixed some visual corruption when scanning DMR in channel/zone mode.
  - Fixed a few bugs with SMS reception and transmission.
  - Fixes / improvements on official firmware
    - Improved Radtel experience with changing channels by number.
      - You can now enter for example "33" and then press enter to go to 0033.
    - Now keeps track of the frequency offset in Frequency / VFO mode.
    - Modulation is no longer reset in Frequency/VFO mode when changing frequency by key up/down or by activating scanning.
      - The exception is that going into Airband will force the modulation to be AM.


- Beta 30
  - Fixed Radtel bug where the * character in the Sub Tone screen was corrupted when scrolling down.
  - Increased the minimum scan speed to 60ms as screen updates introduces some RFI that prevents weaker signals from being detected.
    - A reminder that a scan speed of less than 200ms is not recommended by Radtel engineers.
  - Added a simple "scan range" feature to the scanner. Edit your desired frequency start and end at "Extra 10" -> "Scan Range LO/HI".
    - LO has to be less than HI or the frequency will be rejected. You may need to adjust HI first in some situations.
  - Improved the scanner user interface.
  - Fixed the Scan Dwell timer for DMR (it was missing).
  - Added "Last CH" option to "Scan Return". When exiting the scanner and a signal was previously found, the frequency/channel will be selected on the main screen.
  - Changed the scanner to scan both DMR TS. Due to DMR firmware restrictions, dual TS in Promiscuous is not yet available.
  - Added 2 extra ranges to the Frequency Detect feature.
    - "<240 MHz" will cover 18..240 MHz.
    - ">240 MHz" will cover 240..999 MHz.
    - 240 Mhz was chosen as that is the cut off point at which the radio switches the antennas between VHF and UHF.
  - Added a potential fix / workaround for the "Silent RX" DMR bug.
  - Added a "DMR Scan Speed" option in "Extra 10". This lets you reduce the scan speed to 400ms.
    - Please not that this is not advised and may miss channels or have side effects with the DMR firmware.

- Beta 29
  - Switching to DMR in Frequency/VFO mode will now default to Promiscuous mode.
  - Added a new feature in "Key Define" to allow switching the DMR TS with a long press (only in Frequency/VFO mode).
  - You can now jump to a channel/key/zone by number when in select screens (e.g. Zone list, Channel list , Keys list).
    - Enter a digit to start edit mode, press the menu key to jump.
  - You can now erase the last entered digit with the red key, when editing a frequency in Frequency/VFO mode.
  - Setting the same zone in A and B will no longer copy the channel number from one into the other when changing screens.
    - Each zone now keeps track the channel for each area (A and B) and saves it to flash.
    - Warning: when using Radtel CPS, the current zone channel for area B will be reset.
  - Fixed a Radtel bug when editing the zone name and it happened to be in the active area. The name will now be updated immediately.
  - Upgraded frequency scanner feature.
    - The Scan options in "Basic Set 01" have been changed.
      - Scan Duration and Scan Return are unchanged.
      - Scan End is its own menu and independent of TO/CO modes.
      - Scan Mode has been replaced by Scan Continue.
        - Scan Continue defines the time before the scanner resumes when the signal goes away during RX.
        - Scan Continue of 0 will make the scanner stay at the found frequency, even when the signal is gone and until the user presses the up/down key.
      - Scan Dwell is permanently on, terminates RX after the specified timeout and resumes scanning.
        - Scan Dwell of 0 will let RX play until the signal goes away. You can press up/down key to skip.
      - More explanations and details can be found (here)[https://github.com/DualTachyon/rt-4d-fw-beta/discussions/10#discussioncomment-12892323]. Warning: long thread!

- Beta 28
  - Improved spectrum feature.
    - Press PTT to exit the spectrum info Frequency Mode with the same frequency selected by the cursor.
    - Press up/down keys to skip a "stuck in RX" frequency.
    - Long press up/down to move the cursor faster.
    - Press Side 1 key to add the current frequency to a blacklist
    - Long press Side 1 key to clear the blacklist
    - Exiting the spectrum will clear the blacklist
  - Fixed Radtel bug where starting scanning while RX is active will stop at the next frequency with the green LED turned on.
  - Press up/down key during frequency scan to skip "stuck in RX".
  - Fixed bug that would wipe the calibration when using the Radtel Tuning software.

- Beta 27
  - Replaced the Dual Standby icon from a "D" to a "DW".
  - Added a "Pre TOT Warning". When enabled via "Extra 10", you will receive a double beep sound when you are close to the TOT limit.
    - If the TOT is between 10 and 60 seconds, the warning sound will come 5 seconds before TOT.
    - If the TOT is greater than 60 seconds, the warning sound will come 10 seconds before TOT.
    - If the TOT is 5 seconds, there is no warning sound.
  - Added an area indicator on the left side of screen, when in Single VFO display.
  - When selecting channels in a zone, press # to alternate between the channel number and its alias.
  - Fixed bug in the spectrum where the cursor was one pixel ahead of the RX frequency.
    - Both a bug in my decompilation and a bug in Radtel's official firmare.

- Beta 26
  - Fixed bug with address book lookup introduced in Beta 23.
  - Battery voltage displayed now shows the 'v'.
  - Save mode setting is now displayed on the top status bar.
    - This will help those users that do not know save mode 1:3 does not enable the backlight during RX / TX.
    - Due to lack of contiguous space, the Alert Voice / Beep indicator has been shifted to left to make way.

- Beta 25
  - Fixed bug with saving/deleting Contacts, Call Log and SMS.

- Beta 24
  - Fixed the IDs from Promiscuous calls into the call log.
  - Fixed type of call triggered by PTT during the call back (call hold) period.
  - Add new option to "Extra 10" to enable using PTT in the Sub Tone screen.
    - You can now test sub tones with a repeater by selecting a code, then pressing PTT to check if a repeater accepts it.
  - Fixed logic bug with spectrum that was showing fewer peaks.
  - Added option to fix the Radtel RSSI thresholds in the spectrum.
    - Due to screen layout issues, the new "TH" field is written over the "DEC" field.
    - The "DEC" field is still accessible by cycling through with the star key.
    - The spectrum UI will be revamped at a later date.
    - You may want to try setting a value of 25 and go up/down until you find the sweet spot.
    - The firmware remembers your previous threshold setting.
    - Please note that the RSSI thresholds vary between squelch levels, so a threshold reduction for SQ1 may or may not work for SQ2, SQ3, etc.

- Beta 23
  - Fixed the DMR UI in the "extra" firmware when RX happens on the alternate VFO.
  - No changes to "original" other than the version increase.

- Beta 22
  - Fixed Radtel bug when changing the frequency step
  - Block TX with local ID as the DMR firmware refuses to dial it anyway.

- Beta 21
  - Updated allowed DMR range in the 400MHz to match official 3.14.

- Beta 20
  - It is now possible to update the DMR with this firmware instead of reverting to the official one.

- Beta 19
  - Fixed Channel ID corruption on input
  - Added Live CTCSS scanner to the "Extra 10" menu.

- Beta 18
  - The original.bin is a version of the firmware that is largely unmodified from the original excepted for some bug fixes. No UI changes or extra features.
  - The extra.bin is a version that has extra changes and features:
    - A modified DMR screen that works with both promiscuous and non promiscuous modes.
    - Toggling promiscuous mode displays correctly on the screen.
    - A small P is displayed on the bottom of the screen when Promiscuous mode is enabled.
    - New menu "Extra 10" with TX Backlight and Voltage Show.
      - The backlight can be turned off after 5 seconds of TX'ing.
      - The battery voltage can be displayed instead of a meter.
    - Scan Direction replaced with Scan Duration (duration of time spent on a single frequency before moving on)
    - The address book and contacts functions can be bound to the side keys and the long press keys.
    - The green key long press behaviour can also be modified to invoke the contacts instead.
    - When editing a text or number field, the editor will place the cursor at the end of the field.
    - The default for a new ID is now 0 instead of 1, so that the editor starts with an empty field.
    - Some measurement units were chaned to lower case.
    - The call log now shows "From" and "To" IDs, which is useful for promiscuous mode. In addition, leading zeroes are trimmed.

# Flashing tools

* [rt890-flash-rs](https://github.com/bricky149/rt890-flash-rs/releases/)
* [RT-4D_Flasher](https://github.com/omegatee/RT-4D_Flasher)

