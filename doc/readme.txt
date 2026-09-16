AlifeDiegetic: In-world volume control for STALKER Anomaly, by Damian
Version: next (xlibs 1.8.4, demonized 20250908)
GitHub: https://github.com/damiansirbu-stalker/AlifeDiegetic
Changelog: https://github.com/damiansirbu-stalker/AlifeDiegetic/blob/main/doc/changelog
Russian / На русском: https://github.com/damiansirbu-stalker/AlifeDiegetic/blob/main/doc/readme_ru.txt
Bugs, suggestions: https://github.com/damiansirbu-stalker/AlifeDiegetic/issues

Alife Collection:
AlifeAmbience: https://github.com/damiansirbu-stalker/AlifeAmbience
AlifeBalance: https://www.moddb.com/mods/stalker-anomaly/addons/alifebalance
AlifeCompanions: https://github.com/damiansirbu-stalker/AlifeCompanions
AlifeDiegetic: https://www.moddb.com/mods/stalker-anomaly/addons/diegetic-audio-control-100
AlifeGuard: https://www.moddb.com/mods/stalker-anomaly/addons/alifeguard-1001
AlifePlus: https://www.moddb.com/mods/stalker-anomaly/addons/alifeplus-v1-0-01
AlifeSpooks: https://github.com/damiansirbu-stalker/AlifeSpooks
AlifeTactics: https://www.moddb.com/mods/stalker-anomaly/addons/alifetactics
FurnitureFuel: https://github.com/damiansirbu-stalker/FurnitureFuel
JitProfiler: https://github.com/damiansirbu-stalker/JitProfiler
TestZone: https://github.com/damiansirbu-stalker/TestZone
xlibs: https://www.moddb.com/mods/stalker-anomaly/addons/xlibs-1001

Anomaly has no way to control the volume of radios, megaphones, guitars, and harmonicas independently from the game's audio sliders. You can't turn down Duty propaganda without killing ambient sounds. AlifeDiegetic fixes this.

The mod hooks directly into the audio subsystems that play in-world sound: ph_sound for radios and megaphones, guitar_anim for campfire guitar, harmonica_anim for harmonica. Each source gets its own volume slider, enable/disable toggle, and where applicable a pause multiplier that controls silence between tracks or announcements.

A master volume multiplier sits on top of everything. All changes apply immediately through MCM.

Missing dependencies are handled gracefully. If you don't have the guitar or harmonica mods installed, those controls simply do nothing.

Features:

Radios:
  Volume control for faction base radios and music
  Pause multiplier between tracks (longer silence or shorter)
  Enable/disable toggle

Megaphones:
  Volume control for Duty propaganda, Arena announcer, alarms
  Pause multiplier between announcements
  Enable/disable toggle

Guitar:
  Volume control for campfire guitar (requires Guitar Animation mod)
  Enable/disable toggle

Harmonica:
  Volume control for harmonica (requires Harmonica mod)
  Enable/disable toggle

Master volume multiplier applied to all sources

Requirements:
Anomaly 1.5.3
Modded exes: themrdemonized or AOEngine v0.55 or newer. The full feature set needs the latest demonized build; a feature that needs a newer one stays inactive on older exes.
xlibs (https://www.moddb.com/mods/stalker-anomaly/addons/xlibs-1001)
MCM
Radio_Remastered or similar (for radio/megaphone control)
Guitar Animation by Daiviey (optional, for guitar control)
Harmonica by Daiviey (optional, for harmonica control)

Install (MO2):
1. Install xlibs
2. Install AlifeDiegetic
3. Load order does not matter
4. Configure via MCM

Uninstall (MO2):
Disable or remove in MO2.

Configuration:
All settings in MCM under AlifeDiegetic. All defaults are 1.0 (unchanged from game behavior).

Compatibility:
Coexists with the mods it controls. It hooks ph_sound, guitar_anim, and harmonica_anim, and a control is inactive when its mod is absent.
Tested with Anomaly 1.5.3, GAMMA, and Forgotten Zone.

Performance and Infrastructure:
Performance comes first, ahead of any feature. When a feature cannot fit the budget it is reworked, replaced, or removed with an X-Ray engine modification rather than allowed to slow the game.
Built from the X-Ray engine source by reverse engineering, with targeted engine changes of my own for performance, precision, and accuracy.
Heavy work spreads across frames, paced by rate limiters and staggered, deferred queues, with the math to keep cost bounded at any entity count.
A layered validator runs on every change, locally and in CI, and blocks the build on any crash, unsafe engine call, performance regression, style break, failed smoke load, or leaked secret.
Profiled with JitProfiler, an engine-native, scientific profiler.
Timings are worst-case, from a build with no multithreading or optimizations, so yours runs faster.
Project Health: https://damiansirbu-stalker.github.io/AlifeDiegetic/
[JitProfiler: AlifeDiegetic under CPU and allocation capture]

Credits:
Altogolik - support, ideas, source materials

Usage and License:
  Modpacks: allowed and encouraged. Keep the readme and license files.
  Addons, patches, integrations: allowed. Credit "AlifeDiegetic by Damian Sirbu" visibly on your mod page.
  Reproducing the implementation in other software: not allowed, even with credit.
  Full license in LICENSE file and on GitHub.

Diagnostics and reporting:
Debug mode: turn on in MCM, reproduce, then off. Writes alifediegetic.log.
Report at https://github.com/damiansirbu-stalker/AlifeDiegetic/issues/new/choose or the EFP, Anomaly, and Zona Discord. Include repro steps, engine build, modlist, load order, xray.log, and alifediegetic.log.
