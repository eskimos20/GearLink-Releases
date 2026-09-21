# GearLink Releases

Public APK releases for **GearLink** — an Android app that bridges smart
trainers, power meters, heart-rate sensors and wireless controllers to
cycling apps such as Zwift, Rouvy and MyWhoosh, over Bluetooth and
LAN/Wi-Fi.

## What GearLink does

- Bridges a smart trainer (FTMS, Tacx and others) so apps see a
  standard controllable fitness machine over Bluetooth or LAN
- Forwards power, cadence, speed and heart-rate telemetry to connected
  apps
- Relays controller input (shift buttons, steering and brake paddles)
  to the app
- Offers virtual drivetrain emulation — selectable real-world cassette
  and chainring setups with per-gear resistance shaping
- Sim / ERG / grade and resistance control pass-through to the trainer
- Supports multiple simultaneous app connections and multiple sensors

## Install

This repository only hosts downloadable builds. Install the latest APK
from the [Releases](../../releases) page on an Android phone. Once
installed, the app notifies you under the logo when a newer build is
available and can download and install it directly.

## How GearLink works

### The bridge

GearLink sits between your devices and your training app. Your
trainer, heart-rate band, power meter and Zwift Click/Play connect to
the phone over Bluetooth. The app then presents one combined trainer
to your game as `GearLink-BT-Bridge` over Bluetooth and
`GearLink-IP-Bridge` over Wi-Fi.

### 1 · Connect your devices

Devices → Scan for devices → tap Connect on each one you want to use.
Connected devices are saved and re-connect automatically on the next
start (auto-connect can be turned off in Settings).

### 2 · Start the bridge

Home → Start. The phone now advertises `GearLink-BT-Bridge` over
Bluetooth and `GearLink-IP-Bridge` on your local network. With
auto-start on, the bridge comes up by itself once your devices are
connected.

### 3 · Pair in your app

- **Zwift** — pair `GearLink-BT-Bridge` (Bluetooth) or
  `GearLink-IP-Bridge` (Wi-Fi; the PC running Zwift must be on the
  same network). Select it as trainer, power source and — if a band
  is connected — heart rate.
- **Rouvy** — pair `GearLink-BT-Bridge` over Bluetooth as your
  trainer.
- **MyWhoosh** — pair the trainer over Bluetooth as
  `GearLink-BT-Bridge`. A Click/Play connected to GearLink also shows
  up as `GearLink-Controller` in MyWhoosh's controller pairing.

### Controllers — two ways

- **Via GearLink** — pair the Click or Play under Devices. Button
  presses are forwarded through the bridge, which gives shifting to
  apps without native controller support (e.g. MyWhoosh) and lets the
  virtual drivetrain shape every gear.
- **Direct to the app** — pair the controller in the app's own
  pairing screen instead and the app handles the buttons natively.

The drivetrain selected in Settings applies either way.

### Compare / Calibrate (C/C)

Compares two power sources against each other — typically your
trainer and a standalone power meter.

- Requires two connected sources that both report cadence.
- The session arms once both report at least 50 rpm — "Ready" pulses
  until then.
- While armed, the clock runs and running averages build up.
- Cadence below 20 rpm — or a source going quiet for about
  3 seconds — pauses the session. Readings sent after the last
  healthy pedal stroke are discarded, so coasting never pollutes the
  averages.
- With exactly two sources the Difference card shows how far apart
  their averages sit, in W and %.
- Reset clears the session; the next pedal stroke starts a new one.

### Settings

**Drivetrain** picks which gearing your shifts emulate. **Trainer
difficulty** scales the terrain resistance sent to the trainer (not
used by Zwift). **Rider weight** feeds trainers that use it.
**Debug** enables diagnostics — Download saves the log to
`Download/GearLink-log.txt`.

## Disclaimer

This is experimental, untested software provided as-is, intended for
private use. Use it at your own risk — the author takes no
responsibility for any damage, data loss or compatibility issues.

## License

Released under the [MIT License](LICENSE).
