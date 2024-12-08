To use this you need the following custom components added via HACS

- [ha-floorplan](https://github.com/ExperienceLovelace/ha-floorplan)
- [browser mod](https://github.com/thomasloven/hass-browser_mod)
- [card mod](https://github.com/thomasloven/lovelace-card-mod)

There are 3 files needed

- `media-player-card.svg` You can modify this as you like with Inkscape. This file goes in the location shown in the dashboard.yml file
- `media-player-card.css` This file goes in the location shown in the dashboard.yml file
- `media-card.yaml` This is a [package](https://www.home-assistant.io/docs/configuration/packages/) and goes in your packages directory. There are URLs in this file that need to be changed to your system

`dashboard.yml` is the frontend code which can be added via the UI or YAML. You need to edit the URL in there to be your MA URL

In order for the identification of like players for linking you need to suffix your MA players in HA to have the following suffix at the end of their `entity_id`

- Airplay players - `_provap`
- Bluesound players - `_provbs`
- Slimproto players - `_provsp`
- Snapcast players - `_provsc`
- Sonos players - `_provsn`
- Universal Group Players - `_provug`

If you don't add the suffix then all MA players will be shown as an option to link and errors will be shown in the log if you try and link players that may not be linked.

You may see warnings in your HA log about an input select not having a valid option anymore. This is normal for dynamically created input_select lists

You need to edit `media-card.yaml` and add the friendly names for your players to the first `input_select`. These are case sensitive.

You need to ensure port 8095 is enabled for the MA webserver

This is provided as-is without support.
