# Android-specific instructions (draft)

Apply only to authorised native Android work and its Android platform integrations.

  * For changes using Android APIs, check availability across the project's supported runtime versions, not just `compileSdk`. Preserve `minSdk` compatibility through supported alternatives or runtime guards. Account for behaviour changes tied to the running Android version and `targetSdk`.
  * When work must continue after the user leaves the screen or app, choose a supported Android execution mechanism for its duration, urgency, and user visibility. Account for background limits and interruption; do not assume an ordinary thread, timer, or foreground service guarantees uninterrupted execution.
  * Use emulators for behaviour they can reproduce. Use physical devices when hardware, manufacturer-specific behaviour, or real-world performance claims cannot be established through emulation. State the tested configuration and any remaining device-specific gaps; one emulator or device does not prove all supported configurations.
