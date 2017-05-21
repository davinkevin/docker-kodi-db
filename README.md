# Shared KODI Database

## Installation

1. Get docker image of Mysql 5.5

```
$ docker pull mysql:5.5
```

2. Install service

```bash
$ cp kodi-db.service /etc/systemd/system/kodi-db.service
$ systemctl enable kodi-db.service
$ systemctl start kodi-db
```

3. Add configuration block in each Kodi installation 

In `userdata/advancedsettings.xml`, add the following lines : 

```xml
<?xml version="1.0" encoding="utf-8"?>
<advancedsettings>
 <videodatabase>
  <host>IP_OF_SERVER</host>
  <user>root</user>
  <pass>kodi</pass>
  <type>mysql</type>
  <port>3306</port>
 </videodatabase>
 <musicdatabase>
  <host>IP_OF_SERVER</host>
  <user>root</user>
  <pass>kodi</pass>
  <type>mysql</type>
  <port>3306</port>
 </musicdatabase>
</advancedsettings>
```
