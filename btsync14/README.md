# BitTorrent Sync

Docker image for [btsync](https://www.getsync.com/) based on Alpine Linux

# How to use this image
## Start btsync
Starting the btsync instance:

```
docker run -v /path/to/data:/btsync/data -v /path/to/folders:/btsync/folders -p 8885:8885 -d lilg/btsync
```
Then go to [http://localhost:8885/](http://localhost:8885/) and go through the wizard

## Persistent data

 - `-v /path/to/data:/btsync/data` local configuration.
 - `-v /path/to/folders:/btsync/folders` shared folders where the WebUI Folder browser starts
