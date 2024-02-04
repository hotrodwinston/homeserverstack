# homeserverstack
A short list of my configs for setting up a home media/file server


This is a documentaion project for my home server so I can have all my links and any tips ready if I need to rebuild.

I made this repo public so I can share everything for tech support and so others can use the data I collect.

# Hardware
I am running an HP EliteDesk 800 G1 SFF with 256GB SSD boot drive and i5-4590 with 16 GB RAM and 1 TB internal HDD

I purchased this refurb from Amazon for about $120 (USD) in May 2023

External storage is a few USB3 HDD connected via a tp-link powered USB3 hub

Hardware issues noted:
  Will not boot headless.
    
    Fixed by plugging a "dummy display" into the system.
 
 The generic laptop-style dvd drive from the refurbisher will sometimes hang against the front panel on eject.
    
    (This is not a major issue during day-to-day just during setup and media ripping.)


    
Potential upgrades:
  
  This hardware supports up to 32 GB of RAM and has internal PCIe slots so future expansion is possible
  
  Replacing the DVD drive with a Blu-ray drive is an option - but ripping Blu-ray will require both a compatible drive and a MakeMKV license.
  
   (MakeMKV beta keys are currently free on their forum but this could change at any time and requires the key be updated from time to time where a full paid license does not require updating so it is worth the money if ripping Blu-ray, especially considering my ripping is not done thru the MakeMKV gui but via CLI script.)

# Secondary Hardware

Rpi 4 2gb running docker with duckDNS and WireGuardEasy containers to provide an external connection to control panel.


# Software
I started in May 2023 with CasaOS running on top of Lubuntu 22.04 LTS but in Feb 2024 due to issues with trying to get more up-to-date docker images on CasaOS causing failures I moved to Open Media Vault 6 with the OMV-Extras add-on.

OMV provides storage management and system backend and for day to day frontend I use a dashboard.

Docker 

  Docker apps:
  
  Plex - I am a Plex pass subscriber as of writing.
  
  Automatic Ripping Machine (ARM) - installed via instructions from https://github.com/automatic-ripping-machine/automatic-ripping-machine and pointed to my media folder via casa GUI.
  
    ARM required me to set the "arm" user as the owner of the folders
    - the container seems picky about things being right so make sure you RTFM.

Portainer
      
  YouTube Dl Material - installed via portainer
    I recently ran into issues with YTDL Material so I am running MeTube alongside it for redundancy.

OpenHAB for Home Automation
  Some tech geeks will give me issues for not using Home Assistant but I prefer OpenHAB and deploying the docker is easy as you don't have to set up separate docker apps for Z-wave and Zigbee to work like you do with HA.
  It just works. Plus I have been using OH since 2018 back when you had to be fluent in YAML to use HA and OpenHAB was all GUI then so I am used to it.
      
      I have a separate doc in this repo for config tips for my OH setup
  
Homarr for a dashboard 



# More Resources

https://www.reddit.com/r/CasaOS/ (simple frontend if you are ok with being slightly behind on container updates and only need simple containers)

https://www.reddit.com/r/homelab/

https://www.reddit.com/r/homelab/wiki/software/#wiki_oblecto

https://umbrel.com/#umbrelos (alternative to casaos)

https://github.com/awesome-selfhosted/awesome-selfhosted

https://github.com/SelfhostedPro

https://www.home-assistant.io/

https://www.openhab.org/

https://www.awesome-ha.com/
    
