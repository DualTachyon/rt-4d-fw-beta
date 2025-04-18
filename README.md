# Support

* If you like my work, you can support me through https://ko-fi.com/DualTachyon

# Beta test build of the fully reverse engineered version of RT-4D v3.14 firmware.

The RT-4D v3.14 firmware has been fully reverse engineered and before it can be improved with better features and better user experience, I need help in testing the base firmware.
The build in this repository has feature parity with Radtel's original firmware, but probably has some bugs.
Since there is a lot of code and a lot of ways to trigger every feature/quirk of the firmware, I was not able to test everything.

# Changelog

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

# DISCLAIMER

While efforts have been made to avoid bugs that could corrupt your SPI flash, IT IS IMPERATIVE THAT USERS MAKE A BACKUP OF IT.

# SPI flash backup

The following tools can be used:
* [RT-4D-SPIFlash-CLI](https://github.com/DualTachyon/rt-4d-spiflash-cli)
* [rt890-flash-rs](https://github.com/bricky149/rt890-flash-rs/releases/tag/1.2.96)

How to make a backup:

```
Windows: RT-4D-SPIFlash-CLI.exe -p COMx -r spi.backup
Windows: rt890-flash-rs.exe -4d -p COMx -o spi.backup
Linux: ./rt890-flash-rs -4d -p /dev/ttyUSBx -o spi.backup
```

KEEP THIS BACKUP SAFE SOMEWHERE. It will allow you to recover your SPI flash to a fully working state, no matter what happens to it.

# Requirements

* You must have DMR firmware 1.2.0.6 installed on your RT-4D. 1.2.0.3 may work, but anyone reporting bugs with any older versions will be blocked from this repository.
* Do not request new features or changes, this repository is strictly for testing the reverse engineered firmware against the original. Doing so will get you blocked.
* If you finds bugs, report them on the Issues tab here on GitHub. Make a proper detailed bug report. Reporting your bugs to me on Telegram is a good way to get blocked and ignored.

A good bug report is: "XYZ feature doesn't work. I tested it by doing ABC and used DEF settings. You can see in this video/photo that original firmware works, but not in your beta build".
Also a good report: "The text/bitmap in ABC is corrupted/misaligned/missing when doing DEF".

A bad bug report is: "XYZ doesn't work, plz fix it" and will get you blocked.

# What's different from the original firmware

* If you fitted a 64MBytes SPI flash on your RT-4D, DO NOT USE THIS BUILD. I don't have that type of flash so I couldn't test the new driver for it and didn't want to include it yet.
* Some typos have been fixed.
* A bug that affects address book lookup has been fixed (whether correctly is a different story).
* The Talkaround and Reverse icons match the popup display. In the original, they are reversed.
* DMR screen shows a different UI when Promiscuous is enabled. It is a small taster of what is to come after the current firmware is fully tested.
 * As a result of this change, it is possible the non-promiscuous UI is (slightly) broken. So please go easy on reporting bugs in non-promiscuous mode.
 * The text for Individual/Group/All calls has been shortened to just Private/Group/All to fit with the new UI mode and affects the old UI mode too.

# How to flash the beta build

You can use the many firmware flashing tools:

* [rt890-flash-rs](https://github.com/bricky149/rt890-flash-rs/releases/tag/1.2.96)
* [RT-4D_Flasher](https://github.com/omegatee/RT-4D_Flasher)
* [RT-4D-python-flasher](https://github.com/fagci/RT-4D-python-flasher)
* [rt4d-goflasher](https://github.com/fagci/rt4d-goflasher)

