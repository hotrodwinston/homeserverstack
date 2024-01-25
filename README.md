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

As of Jan 2024, the SSD is throwing some errors - I will replace it soon
    
Potential upgrades:
  
  This hardware supports up to 32 GB of RAM and has internal PCIe slots so future expansion is possible
  
  Replacing the DVD drive with a Blu-ray drive is an option - but ripping Blu-ray will require both a compatible drive and a MakeMKV license.
  
   (MakeMKV beta keys are currently free on their forum but this could change at any time and requires the key be updated from time to time where a full paid license does not require updating so it is worth the money if ripping Blu-ray, especially considering ripping is not done thru the MakeMKV gui but via CLI script.)

# Secondary Hardware

Rpi 4 2gb running docker with duckDNS and WireGuardEasy containers to provide an external connection to CasaOS control panel.


# Software
Lubuntu current LTS (22.04 as of writing) with getscreen to access the GUI if needed.

Lubuntu takes very few resources versus a no desktop "server" distro and provides easier troubleshooting as I can connect a monitor or remote in as needed.

Fail2Ban

Docker - managed by CasaOS ( www.casaos.io ).

  Docker apps:
  
  Plex - installed via the Casa app store and pointed to my media folder. I am a Plex pass subscriber as of writing.
  
  Automatic Ripping Machine (ARM) - installed via instructions from https://github.com/automatic-ripping-machine/automatic-ripping-machine and pointed to my media folder via casa GUI.
  
    ARM required me to set the "arm" user as the owner of the folders
    - the container seems picky about things being right so make sure you RTFM.

Portainer for installing things that are more complex than Casa can (currently) handle
      
      With the release of casaos V0.4.4, this may not be needed. I keep the container stopped.
  
  YouTube Dl Material - installed via portainer then pointed at media folders via casa GUI.
    I recently ran into issues with YTDL Material so I am running MeTube alongside it for redundancy.

OpenHAB for Home Automation
  Some tech geeks will give me issues for not using Home Assistant but I prefer OpenHAB and deploying the docker is easy as you don't have to set up separate docker apps for Z-wave and Zigbee to work like you do with HA. It just works. Plus I have been using OH since 2018 soooo.
    I have a separate doc in this repo for config tips for my OH setup
  
# Future
I'm looking at running a VPN tunnel for BitTorrent - probably Gluetun https://github.com/qdm12/gluetun .

Guide for all-in-one setup of gluetun and bittorrent (not compatible with casa install method so will need to install manually https://code.mendhak.com/run-docker-through-vpn-container/ .



# More Resources

https://www.reddit.com/r/CasaOS/

https://www.reddit.com/r/homelab/

https://www.reddit.com/r/homelab/wiki/software/#wiki_oblecto

https://umbrel.com/#umbrelos (alternative to casaos)

https://github.com/awesome-selfhosted/awesome-selfhosted

https://github.com/SelfhostedPro

https://www.home-assistant.io/

https://www.openhab.org/

https://www.awesome-ha.com/
    
