#docker SubSonic

## Description:

This is a Dockerfile for "SubSonic" - (http://www.subsonic.org/).
Specifically for use within an unRAID environment.

Forked and removed https

## Build from docker file:

```
git clone https://github.com/adamrbell/docker-subsonic.git 
cd docker-subsonic
docker build -t subsonic . 
```

## Volumes:

#### `/subsonic`

Home directory for subsonic, subsonic stores it's log, database properties in this folder. (i.e. /opt/appdata/subsonic)

#### `/music`

Defualt music folder. If remote share ensure it's mounted before run command is issued. 
(i.e. /opt/downloads/music or /media/Tower/music)

#### `/podcasts`

Defualt podcasts folder. If remote share ensure it's mounted before run command is issued.
(i.e. /opt/downloads/podcasts or /media/Tower/podcasts)

## Docker run command:

```
docker run -d --net=host -v /*your_subsonichome_location*:/subsonic \
                         -v /*your_music_folder_location*:/music \
                         -v /*your_podcast_folder_location*:/podcasts \
                         -v /etc/localtime:/etc/localtime:ro
                         --name=subsonic hurricane/docker-subsonic
```
