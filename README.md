https://github.com/user-attachments/assets/3465043f-428d-4b56-9452-7132eab2cab1

This requires use of the `music_assistant.get_queue` action which is only available the with the official Music Assistant integration. Music Assistant 2.4 or later is also required.

To use this you need the following custom components added via HACS

- [ha-floorplan](https://github.com/ExperienceLovelace/ha-floorplan)
- [browser mod](https://github.com/thomasloven/hass-browser_mod)
- [card mod](https://github.com/thomasloven/lovelace-card-mod)

There are 3 files needed

- `media-player-card.svg` You can modify this as you like with Inkscape. This file goes in the location shown in the dashboard.yml file
- `media-player-card.css` This file goes in the location shown in the dashboard.yml file
- `media-card.yaml` This is a [package](https://www.home-assistant.io/docs/configuration/packages/) and goes in your packages directory. There are URLs in this file that need to be changed to your system

`dashboard.yml` is the frontend code which can be added via the UI or YAML. You need to edit the URL in there to be your MA URL

For the images `cd.png` needs to go in config/www and you need to grab this [empty.png](https://upload.wikimedia.org/wikipedia/commons/5/59/Empty.png) and place it in that folder as well

All other images go in an `images` folder below the location of the `media-player-card.svg`

In order for the identification of like players for linking you need to suffix your MA players in HA to have the following suffix at the end of their `entity_id` (dont worry about player types other than those listed)

- Airplay players - `_provap`
- Bluesound players - `_provbs`
- Slimproto players - `_provsp`
- Snapcast players - `_provsc`
- Sonos players - `_provsn`
- Universal Group Players - `_provug`

If you don't add the suffix then all MA players will be shown as an option to link and errors will be shown in the log if you try and link players that may not be linked.

You may see warnings in your HA log about an input select not having a valid option anymore. This is normal for dynamically created input_select lists

You need to edit `media-card.yaml` and add the friendly names for your players to the first `input_select`. These are case sensitive. You also need to change any IP addresses to your own server's IP address. Lastly you must change any instances of `config_entry_id` to your instance's. You can obtain that by going to the dev tools in HA and setting up a `get_library` action via the UI and selecting your MA instance from the dropdown and then switch to YAML mode and get the value. 

You need to ensure port 8095 is enabled for the MA webserver

You need to ensure the MA player custom name are identical to the HA friendly name

Discart is not always retrieveable

This is provided as-is without support.

Latest imagery:

![image](https://github.com/user-attachments/assets/5f23b29d-4b58-4871-b8e4-b3048854cbf3)
