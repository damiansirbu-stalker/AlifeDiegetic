Diegetic Audio Control: In-world volume control for STALKER Anomaly, by Damian
Version: 1.0.8 (xlibs 1.5.1, demonized 20250908, AOEngine v0.55)
GitHub: https://github.com/damiansirbu-stalker/Diegetic-Audio-Control
Changelog: https://github.com/damiansirbu-stalker/Diegetic-Audio-Control/blob/main/doc/changelog
Russian / На русском: https://github.com/damiansirbu-stalker/Diegetic-Audio-Control/blob/main/doc/readme_ru.txt
Bugs, suggestions: https://github.com/damiansirbu-stalker/Diegetic-Audio-Control/issues

Anomaly has no way to control the volume of radios, megaphones, guitars, and harmonicas independently from the game's audio sliders. You can't turn down Duty propaganda without killing ambient sounds. Diegetic Audio Control fixes this.

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
2. Install Diegetic Audio Control
3. Load order does not matter
4. Configure via MCM

Uninstall (MO2):
Disable or remove in MO2.

Configuration:
All settings in MCM under Diegetic Audio Control. All defaults are 1.0 (unchanged from game behavior).

Compatibility:
Tested with vanilla Anomaly 1.5.3, Demonized main, Demonized MT, and AOEngine (latest versions).
Tested with GAMMA. Hooks into ph_sound, guitar_anim, and harmonica_anim. If those mods are not present the relevant controls are inactive. No base script modifications.

Development:
Written against X-Ray Monolith engine source, Demonized exes source code, and Anomaly 1.5.3 unpacked gamedata.
Code patterns and engine usage validated against established work by reputable GAMMA modders (Demonized, Vintar0, RavenAscendant, xcvb).
The code is validated in real time by a multi-stage pipeline: luacheck, selene, tree-sitter AST analysis, contract rules, cross-file dependency resolution, cyclomatic complexity analysis, crash and vulnerability pattern detection, lua54 integration testing with X-Ray engine stubs, gitleaks secret scanning.
Full report in doc/test-report.log.

Credits:
Altogolik - support, ideas, source materials

Usage and License:
  Modpacks: allowed and encouraged. Keep the readme and license files.
  Addons, patches, integrations: allowed. Credit "Diegetic Audio Control by Damian Sirbu" visibly on your mod page.
  Reproducing the implementation in other software: not allowed, even with credit.
  Full license in LICENSE file and on GitHub.
