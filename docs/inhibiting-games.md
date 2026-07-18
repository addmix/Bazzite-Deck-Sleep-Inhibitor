# Games that inhibit system sleep:

The following is a list of popular games and engines that are known to inhibit sleep, which may cause issues if you expect your system to sleep:

> See also: [Sleep Inhibit Survey](sleep-inhibit-survey.md)


## Diagnostic methods

You can verify if a game inhibits sleep by using the following methods:

> Linux: from **terminal**, use the command `systemd-inhibit --list`

The important info here is WHO, WHAT, and MODE, \
tl;dr: if you see your game listed under WHO, with WHAT set to `sleep`, and MODE set to `block`, that means the current game is preventing sleep.

- WHO is the program requesting an inhibitor (look for the running game)
- WHAT is the type of inhibitor, for this test, we are focused on `sleep`
- MODE is what the inhibitor does. we are focused on items listed as `block`

> Windows: from an **admin PowerShell**, use the command `powercfg /requests`

- Items listed under `DISPLAY:` prevent the display from turning off, and as a result prevent system sleep/hibernation
- Items listed under `SYSTEM:` do not prevent the display from turning off, but prevent system sleep/hibernation


## Engines

### Godot

Godot projects [inhibit sleep by default](https://github.com/godotengine/godot-proposals/issues/15187), meaning the majority of games made using Godot will inhibit sleep. For this reason, Godot games are omitted from this list.

<details> <summary>Workaround:</summary>
This can be circumvented in most Godot games by creating an `override.cfg` file next to the game's executable with the following text:

```
[display]
window/energy_saving/keep_screen_on=false
```
</details>

### SteamVR

SteamVR inhibits sleep through vrwebhelper and/or vrcompositor. This is most likely intentional, as the user would not be making inputs using normal means that the system would detect to stay awake.


### Source 2

All sampled Source 2 games inhibit sleep by default.
<details><summary>Games</summary>

- Counter Strike 2
- Deadlock
- Aperture Desk Job
- Half-Life Alyx (VR)

</details>

### SDL3, SDL2

SDL2 disables sleep by default, according to the [SDL2 Docs](https://wiki.libsdl.org/SDL2/SDL_HINT_VIDEO_ALLOW_SCREENSAVER): "By default SDL will disable the screensaver."

<details><summary>Workaround:</summary>
The impact of this is much smaller, as most games do not directly use SDL. This can be disabled by setting the environment variable <code>SDL_VIDEO_ALLOW_SCREENSAVER</code> to <code>1</code>
</details>


# Games

- [Godot games](#godot)
- [Source 2 games](#source-2)
- [SteamVR Games](#steamvr)
- 7 Days To Die
- Assetto Corsa
- Halo Infinite
- Helldivers 2
- MudRunner
- Overwatch