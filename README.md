# Bazzite Deck Sleep Inhibitor

Bazzite Deck Sleep Inhibitor is a minimal ScreenSaver implementation designed to allow games running under Bazzite/SteamOS Game Mode to request system sleep inhibitors. This is useful especially for HTPC (console) usage, to prevent the system from sleeping while watching content.

This package will be added to Bazzite in the future (https://github.com/ublue-os/bazzite/pull/5234), but is currently blocked by a Steam client bug (https://github.com/ValveSoftware/SteamOS/issues/2619), but manual installation is available.


## Manual installation:

Bazzite-Deck-Sleep-Inhibitor is hosted on Fedora COPR, and can be installed into Bazzite using these commands:
```bash
sudo dnf5 copr enable addmixbb/Bazzite-Deck-Sleep-Inhibitor #enable the COPR repository
rpm-ostree install Bazzite-Deck-Sleep-Inhibitor #install Bazzite-Deck-Sleep-Inhibitor
```


**SteamOS Usage:** The project itself should function on SteamOS, however I have not set up an arch package to do so yet.


## Possible Issues:

The large majority of games do not attempt to inhibit sleep, which is great. However, some games will inhibit sleep which may be problematic for handheld/Steam Deck usage.

See: [Games and Engines that inhibit sleep](docs/inhibiting-games.md) and [Survey of games that inhibit sleep](docs/sleep-inhibit-survey.md)