# B+ Ark Server Controller — Unraid Community Applications template

This repository contains the Unraid Community Applications (CA) metadata for the Linux/Unraid build of **B+ Ark Server Controller**.

The controller manages one or more **ARK: Survival Ascended** dedicated-server profiles from a browser UI. It keeps one shared ARK installation to reduce disk use while maintaining separate server configuration, saves, maps, ports, logs and backups for every profile.

The controller itself does not start ARK automatically. Servers start only when you choose **Start** in the controller.

## Install on Unraid

1. In Unraid, open **Apps → Settings**.
2. Under **Template Repositories**, add:

   ```text
   https://raw.githubusercontent.com/Boss898989/B-Plus-Ark-Server-Controller-CA/main/ca_profile.xml
   ```

3. Save, then open **Apps** and search for **B+ Ark Server Controller**.
4. Install it and keep the default persistent paths unless you already have an existing B+ installation.
5. Open the WebUI at `http://<your-unraid-ip>:8088`.
6. Install ARK files from the controller, then create and configure server profiles.

## Container settings

| Setting | Purpose |
| --- | --- |
| Web UI Port | Browser port for the controller; defaults to `8088`. |
| Controller data | Stores controller state, profile registry and settings. |
| ARK server data | Stores the shared ARK installation, server data, mods, plugins, saves, logs and backups. |
| Docker socket | Lets the controller create and manage the individual ASA containers. Required. |
| Host time | Makes the controller use Unraid's timezone. |

The Docker socket gives the controller the ability to manage Docker on the host. Do not use a controller image you do not trust.

## Updates

Use Unraid's normal container update action. Server profile data stays in the two mapped appdata folders and is not removed by an image update.

## Support

- [GitHub project](https://github.com/Boss898989/B-Plus-Ark-Server-Controller)
- [Discord support](https://discord.gg/6qDKS5Z5S5)

## Licensing

The CA metadata in this repository is MIT licensed. The B+ Ark Server Controller image and application are distributed under their own terms. The controller includes a free tier and optional B+ Pro features handled inside the application.
