# synology-reference

Collection of guides, templates, and more

## Sonarr

Sonarr is used for tracking and automatically gathering data from indexers for TV shows.

Sonarr is a PVR for Usenet and BitTorrent users. It can monitor multiple RSS feeds for new episodes of your favorite shows and will grab, sort and rename them. It can also be configured to automatically upgrade the quality of files already downloaded when a better quality format becomes available.

## Radarr

Radarr, originally a fork of Sonarr, is used for tracking and automatically gathering torrents for movies available from MovieDB.

Radarr is an independent fork of Sonarr reworked for automatically downloading movies via Usenet and BitTorrent. The project was inspired by other Usenet/BitTorrent movie downloaders such as CouchPotato.

## Lidarr

Lidarr is a music collection manager for Usenet and BitTorrent users. It can monitor multiple RSS feeds for new tracks from your favorite artists and will grab, sort and rename them. It can also be configured to automatically upgrade the quality of files already downloaded when a better quality format becomes available.

## Bazarr

Bazarr is a companion application to Sonarr and Radarr that manages and downloads subtitles based on your requirements.

## Jackett

Allows the use of indexers and trackers not available as built-ins to either Radarr or Sonarr.

Jackett works as a proxy server: it translates queries from apps (Sonarr, Radarr, SickRage, CouchPotato, Mylar, etc) into tracker-site-specific http queries, parses the html response, then sends results back to the requesting software. This allows for getting recent uploads (like RSS) and performing searches. Jackett is a single repository of maintained indexer scraping & translation logic - removing the burden from other apps.

## Transmission

Transmission is a very small torrent client that Just Works™ out of the box and plays well with Radarr and Sonarr. It requires very little configuration to run, uses an incredibly low amount of memory, is less CPU-intensive than most other clients, and is native across many platforms. It also has a tonne of features including: “encryption, a web interface, peer exchange, magnet links, DHT, µTP, UPnP and NAT-PMP port forwarding, webseed support, watch directories, tracker editing, global and per-torrent speed limits, and more.”
