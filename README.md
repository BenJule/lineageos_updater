LineageOS Updater Backend
=======================
Copyright (c) 2017 The LineageOS Project<br>

Initial set up:
---
1. Requires python3, mongoengine and flask.
2. Requires a mongoDB instance set up and accessible.
3. Copy `config.json.example` to `config.json` and modify to your needs.
4. Copy `local_config.py.example` to `local_config.py` and modify to your needs (flask config options).
5. Run: `./app.py` from this directory.

To add entries a simple script has been added called `addrom.py`:<br>
`usage: addrom.py [-h] -f FILENAME -d DEVICE -v VERSION -dt DATETIME -t ROMTYPE -m MD5SUM`<br>
Alternatively `addon.py` can be included in another python script and the `addrom()` method can be called programatically.

Listens on `http://127.0.0.1:5000 by` default, this can be changed in local_config.py<br>

Example API Calls:
--
Obtaining rom list for a device:<br>
`/api/v1/<device>/<romtype>/<romversion (optional)>`<br>
`<device>` - Name of device. Example: d2vzw<br>
`<romtype>` - Type of rom. Example: nightly<br>
`<romversion>` - Version of rom. Example: 14.1<br>

Requesting a file:<br>
`/api/v1/requestfile/<id>`<br>
`<id>` - Id of requested file. Obtained from json in the api call above.


TODO
====
- Only present roms that are newer than the current rom
- Lots more I'm sure