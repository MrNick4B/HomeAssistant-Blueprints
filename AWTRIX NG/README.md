# Home Assistant Blueprints for AWTRIX NG
This folder contains my AWTRIX NG blueprints for Home Assistant.
Feel free to use them in your Home Assistant instance!

Looking for the blueprints for the original AWTRIX 3 firmware? See the [Awtrix](../Awtrix) folder.

Requires Home Assistant 2025.7.0 or later because of a change in the entity selector behavior.

## Requirements
- AWTRIX NG connected to your MQTT broker with **Home Assistant discovery** enabled (see the [AWTRIX NG Home Assistant guide](https://blueforcer.github.io/awtrix-ng/guides/home-assistant/)).
- In the blueprint, select the **MQTT prefix** sensor of your device (for example `sensor.awtrix_ng_mqtt_prefix`).

### App Blueprint
Publish a pushed app to AWTRIX NG via MQTT.

**English Download**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/MrNick4B/HomeAssistant-Blueprints/blob/main/AWTRIX%2520NG/App/awtrix-ng-app.yaml)

**Dutch Download**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/MrNick4B/HomeAssistant-Blueprints/blob/main/AWTRIX%2520NG/App/awtrix-ng-app_nl.yaml)

### Notification Blueprint
Publish a notification to AWTRIX NG via MQTT.

**English Download**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/MrNick4B/HomeAssistant-Blueprints/blob/main/AWTRIX%2520NG/Notification/awtrix-ng-notification.yaml)

**Dutch Download**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/MrNick4B/HomeAssistant-Blueprints/blob/main/AWTRIX%2520NG/Notification/awtrix-ng-notification_nl.yaml)

## How to Use
Use the download links above, or:

1. Go into a folder and copy the link of a localized blueprint of your choice.
1. Open **Home Assistant**.
1. Navigate to **Settings** > **Automations & Scenes** > **Blueprints**.
1. Click **Import Blueprint** and enter the URL of the blueprint you want to use.
1. Create an automation from the blueprint and configure it according to your needs.

## Differences from the AWTRIX 3 blueprints
- Apps are published to `<prefix>/cmd/apps/pushed/<name>`, notifications to `<prefix>/cmd/notify`.
- "Start app on boot" listens to `<prefix>/availability`. This only works when the MQTT prefix contains no `/`.
- App names may only contain letters, digits, `_` and `-` (max. 32 characters); other characters are replaced by `_`.
- The **Top Text** option has been removed; AWTRIX NG has no equivalent.
- The **Clear** overlay has been removed; the empty option now uses the global overlay of the device.
- Pushed apps are not stored on the device. After a reboot they return as soon as the automation publishes them again (enable "Start app on boot").
