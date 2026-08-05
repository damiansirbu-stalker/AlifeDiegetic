AlifeDiegetic: In-world volume control for STALKER Anomaly, by Damian
Version: next (xlibs 1.5.1)
GitHub: https://github.com/damiansirbu-stalker/AlifeDiegetic
Changelog: https://github.com/damiansirbu-stalker/AlifeDiegetic/blob/main/doc/changelog
Russian / На русском: https://github.com/damiansirbu-stalker/AlifeDiegetic/blob/main/doc/readme_ru.txt
Bugs, suggestions: https://github.com/damiansirbu-stalker/AlifeDiegetic/issues

Alife Collection:
AlifePlus: https://www.moddb.com/mods/stalker-anomaly/addons/alifeplus-v1-0-01
AlifeBalance: https://www.moddb.com/mods/stalker-anomaly/addons/alifebalance
AlifeGuard: https://www.moddb.com/mods/stalker-anomaly/addons/alifeguard-1001
AlifeTactics: https://www.moddb.com/mods/stalker-anomaly/addons/alifetactics
AlifeDiegetic: https://www.moddb.com/mods/stalker-anomaly/addons/diegetic-audio-control-100
AlifeSpooks: https://github.com/damiansirbu-stalker/AlifeSpooks

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
Requires xlibs.
Runs on themrdemonized modded exes 2025.9.10 or newer, or AOEngine v0.55 or newer.
The full feature set needs the latest demonized build. A feature that needs a newer build stays inactive on older exes.
Tested with GAMMA. Hooks into ph_sound, guitar_anim, and harmonica_anim. If those mods are not present the relevant controls are inactive. No base script modifications.

Development:
Written against X-Ray Monolith engine source, Demonized exes source code, and Anomaly 1.5.3 unpacked gamedata.
Code patterns and engine usage validated against established work by reputable GAMMA modders (Demonized, Vintar0, RavenAscendant, xcvb).
The code is validated in real time by a multi-stage pipeline: luacheck, selene, tree-sitter AST analysis, contract rules, cross-file dependency resolution, cyclomatic complexity analysis, crash and vulnerability pattern detection, lua54 integration testing with X-Ray engine stubs, gitleaks secret scanning.
Full report in doc/test-report.log.

FAQ:
Do I need modded exes?
  Yes. AlifeDiegetic needs themrdemonized modded exes (2025.9.10 or newer) or AOEngine (v0.55 or newer). Vanilla Anomaly does not expose the APIs it relies on.

Credits:
Altogolik - support, ideas, source materials

Usage and License:
  Modpacks: allowed and encouraged. Keep the readme and license files.
  Addons, patches, integrations: allowed. Credit "AlifeDiegetic by Damian Sirbu" visibly on your mod page.
  Reproducing the implementation in other software: not allowed, even with credit.
  Full license in LICENSE file and on GitHub.

Reporting issues and suggestions
Open a report at https://github.com/damiansirbu-stalker/AlifeDiegetic/issues/new/choose, or ask on the GAMMA, EFP, Anomaly, and Zona Discord servers. Read this readme and the MCM options first.

Include: exact repro steps (new game or named save, expected vs actual), engine build, modlist, load order, xray.log, and the mod debug log. With hundreds of mods loaded, only the log shows whether this one was involved.

The debug log is required, so set the MCM log level to DEBUG, reproduce, then set it back to WARN. DEBUG is not free: it writes a line for every event and can hitch a single-threaded exe.
