# CineDemos (WIP)
UZDoom mod for cinematic camera in demos playback

## Usage

Mod currently uses 3 CVars for demo events recording: `MRCinDem_Mode`, `MRCinDem_Recroding` and `MRCinDem_Saved`.

First one can be 3 values: 0 (auto), 1 (force recording) and 2 (force playing). When this CVar is set to 0, mod will automatically decide to record demo events if there's no demo playback spotted (it assumes that you are currently recording a demo), or run them otherwise. When set to 1, it will record events even if a demo is currently playing (that way you can record the events of previously recorded demo). The last value will force mod to always run recorded events, even if no demo playback was spotted.

`MRcinDem_Recording` is a boolean CVar so it can be 1 or 0 (true or false) and it sets to 0 automatically on every game closing. Its purpose is to prevent the mod from recording regular gameplay and accidently rewriting saved events. It also sets to 0 after successful events saving (if there was any).

`MRCinDem_Saved` is a string CVar that stores recorded events. There's no need in any interaction with it other than typing it into a console to check its current content.
#

So, if you are using the mod and want to watch a demo with it right after recording it, you'll need to set `MRCinDem_Mode` to 0, `MRCinDem_Recording` to 1, finish the demo and then just play it.
If you want to play some other demo, or a demo that was recorded previously without this mod, you'll have to play it at least 2 times, first time for the mod to record the events and second time to run them. For that, set `MRCinDem_Mode` and `MRCinDem_Recording` to 1, play a wanted demo once (you can set `i_timescale` CVar to value bigger than 1 to speed it up. It won't affect events recording). After it's finished, set `MRCinDem_Mode` to 0 and play the demo again.

Unfortunately, it's impossible to save multiple sets of events for different demos, so every time you want to play a different demo, you'll have to record its events first.

Also, I can't guarantee that the demos which was recorded without the mod will always play properly with it, especially if there were other mods used in them.
