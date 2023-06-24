# homeserverstack
A short list of my configs for setting up a home media/file server


This is a documentaion project for my home server so I can have all my links and any tips ready if I need to rebuild.

I made this repo public so I can share everything for tech support and so others can use the data I collect.

# Hardware
I am running an HP EliteDesk 800 G1 SFF with 256GB ssd boot drive and i5-4590 with 16gb RAM and 1tb internal HDD

I purchased this refurb from amazon for about $120 (usd) in May 2023

External storage is a couple of usb3 HDD connected via a tp-link powered usb3 hub

Hardware issues noted:
  Will not boot headless.
    
    Fixed by plugging a "dummy display" to the system.
 
 The generic laptop style dvd drive from the refurbisher will sometimes hang against the front panel on eject.
    
    (This is not a major issue during day to day just during setup and media ripping.)
    
Potential upgrades:
  
  This hardware supports up to 32gb of RAM and has internal PCIe slots so future expansion is possible
  
  Replacing the DVD drive with a blu-ray drive is an option - but ripping blu-ray will require both a compatible drive and a MakeMKV license.
  
   (MakeMKV beta keys are currently free on their forum but this could change at any time and requires the key be updated from time to time where a full paid license does not require updating so is worth the money if ripping blu-ray especially considering ripping is not done thru the MakeMKV gui but via CLI script.)
    
# Software
Running Lubuntu current LTS (22.04 as of writing) with NoMachine to access the GUI if needed.

Lubuntu takes very little resources vs a no desktop "server" distro and provides easier troubleshooting as I can connect a monitor or remote in as needed.

Docker managed by CasaOS ( www.casaos.io ).

  Docker apps:
  
  Plex - installed via the casa app store and pointed to my media folder. I am a plex pass subscriber as of writing.
  
  Automatic Ripping Machine (ARM) installed via instructions from https://github.com/automatic-ripping-machine/automatic-ripping-machine and pointed to my media folder via casa GUI.
  
    ARM required me to set the "arm" user as owner of the folders
    - the container seems picky about things being right so make sure you RTFM.

Portainer for installing things that are more complex than casa can (currently) handle
  
  YouTube Dl Material - installed via portainer then pointed at media folders via casa GUI.
  
# Future
Looking at running a vpn tunnel for bittorrent - probably gluetun https://github.com/qdm12/gluetun .

Guide for all in one setup of gluetun and bittorrent (not compatible with casa install method so will need to install manually https://code.mendhak.com/run-docker-through-vpn-container/ .

May transfer my Home Assistant install to the server to free up space. (And a rpi.)
 This idea seems to be a no-go as only the "core" version seems to be available. My pi4 is running HA just fine just wanted to simplify my hardware stack.

# More Resources

https://www.reddit.com/r/CasaOS/

https://www.reddit.com/r/homelab/

https://www.reddit.com/r/homelab/wiki/software/#wiki_oblecto

https://umbrel.com/#umbrelos (alternative to casaos)

https://github.com/awesome-selfhosted/awesome-selfhosted

https://github.com/SelfhostedPro

https://www.home-assistant.io/

https://www.awesome-ha.com/
    
