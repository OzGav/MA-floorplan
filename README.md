To use this you need the following custom components added via HACS

- [ha-floorplan](https://github.com/ExperienceLovelace/ha-floorplan)
- [browser mod](https://github.com/thomasloven/hass-browser_mod)
- [card mod](https://github.com/thomasloven/lovelace-card-mod)

There are 3 files needed

- `media-player-card.svg` You can modify this as you like with Inkscape
- `media-player-card.css` 
- `media-card.yaml` This is a [package](https://www.home-assistant.io/docs/configuration/packages/)

You need all your MA players in HA to have `ma_` in their `entity_id`

You need to edit `media-card.yaml` and add the friendly names for your players to the first `input_select`. These are case sensitive.

You need to ensure port 8095 is enabled for the MA webserver

This is provided as-is without support.
