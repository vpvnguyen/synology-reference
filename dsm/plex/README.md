# syno.plexupdate

Forked from: https://github.com/michealespinola/syno.plexupdate

Automatically Update Plex Media Server on the Synology NAS platform

DSM 6.2.4

## Setup

- Save script (syno.plexupdate.sh) to NAS
- Download Plex's public key: https://downloads.plex.tv/plex-keys/PlexSign.key
- Configure NAS to accept packages published by Synology Inc and trusted publishers (Package Center > Settings > General)
- Import Plex's public key to NAS (Package Center > Settings > Certificate)
- Setup a Scheduled Task in the DSM (Control Panel > Task Scheduler > Create > Scheduled Task > User-defined script)
- General: Set user to `root`
- Task Settings: Run command `bash /volume1/scripts/syno.plexupdate.sh`

## Default Settings (config.ini)

The script utilizes (4) default but user-configurable variables:

MinimumAge=7
A 7-day age requirement for installing the latest version as a bug/issue deterrent
OldUpdates=60
A 60-day age requirement for deleting old package installer files
NetTimeout=900
A 900-second (15 minute) network timeout for hung network connections
SelfUpdate=0
A 0=off 1=on toggle to enable self-updating to the latest packaged release. Change this to 1 to enable self-updating that follows the same minimum age requirement as the Plex updates

## Known Non-Issues

If the DSM is not configured to allow 3rd-party "trusted publishers", the script will log "error = [289]" during the package installation process. Synology DSM has been known to sporadically "lose" 3rd-party security certificates for unknown reasons. If this happens, you will have to re-add the Plex 'Public Key Certificate' to your system.
If the script runs successfully, the DSM Task status will show "Interrupted (1)" and the notification email will state "Current status: 1 (Interrupted)". This exit/error status of (1) is intentionally caused by the script in order to force the DSM to perform an email notification of a successful update (in the form of an interruption/error). The DSM otherwise would only send notifications of failed task events, and notifications of successful Plex updates would not be possible.
