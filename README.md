# homeserverstack
A short list of my configs for setting up a home media/file server


This is a documentaion project for my home server so I can have all my links and any tips ready if I need to rebuild.

I made this repo public so I can share everything for tech support and so others can use the data I collect.

# Hardware
I am running an HP EliteDesk 800 G1 SFF swapped into a Thermaltake Chaser MK-1 Case ( https://youtu.be/Zxw_4KV5DHM?si=MirhrU_Hl9WOW1NG for how to do the swap) with 256GB SSD boot drive and i5-4590 with 16 GB RAM (4x 4GB)
I have the boot drive, a 1TB HDD for containers, and a DVD drive connected to the motherboard SATA ports. I have all nas storage connected thru an LSI 9207-8i HBA.

External storage (Plex Video Storage) is a few USB3 HDD connected via a tp-link powered USB3 hub

Hardware issues noted:
  Will not boot headless.
    
    Fixed by plugging a "dummy display" into the system.

 HP designed this system to use extra pins on the USB headers to prevent booting in other cases - when I did the case swap I just moved the HP front panel into the new case as an internal usb hub
 HP used a Non-Standard Power connection on the PSU that required an adapter to connect a standard ATX PSU - the above YT video has links to a similar adapter to the one I used.
   If building a similar system make sure the adapter you buy clearly supports the system you are using.
   Even if you dont plan to case swap, it's a good idea to buy the power adapter for your system for the future.
 
    
Potential upgrades:
  
  This hardware supports up to 32 GB of RAM and has internal PCIe slots so future expansion is possible (one PCIe slot already in use by HBA)
  
  Replacing the DVD drive with a Blu-ray drive is an option - but ripping Blu-ray will require both a compatible drive and a MakeMKV license.
  
   (MakeMKV beta keys are currently free on their forum but this could change at any time and requires the key be updated from time to time where a full paid license does not require updating so it is worth the money if ripping Blu-ray, especially considering my ripping is not done thru the MakeMKV gui but via CLI script.)

# Secondary Hardware

Dell optiplex 7010 with 8gb ram and 4tb storage across 3 disks plus a 120gb ssd for boot running OMV and syncthing as a remote backup.
This machine is stored at my parents house and accessed via Twingate VPN.


# Software
Open Media Vault 7 with the OMV-Extras add-on.

OMV provides storage management and system backend; I use a dashboard for day-to-day frontend.

Docker 

  Docker apps:
  (I have a separate doc in this repo for docker-compose files and settings)
  
  Plex - I am a Plex pass subscriber as of writing.
  
  Automatic Ripping Machine (ARM) - installed via instructions from https://github.com/automatic-ripping-machine/automatic-ripping-machine .
  
    ARM required me to set the "arm" user as the owner of the folders
    - the container seems picky about things being right so make sure you RTFM.

Portainer
      
  PinchFlat for download of youtube videos (with proper rename and organization for Plex!)

Twingate for remote access    

OpenHAB for Home Automation.
      
    Some tech geeks will give me issues for not using Home Assistant but I prefer OpenHAB.
    And deploying the docker is easy as you don't have to set up separate docker apps for Z-wave and Zigbee to work like you do with HA.
    It just works. Plus I have been using OH since 2018 back when you had to be fluent in YAML to use HA and OpenHAB was all GUI then so I am used to it.
      
      
  (I have a separate doc in this repo for config tips for my OH setup)
  
Homarr for a dashboard.



# More Resources

https://www.openmediavault.org/

https://casaos.io/
(What I started with - a simple frontend if you are ok with being slightly behind on container updates and only need simple containers)

https://www.reddit.com/r/CasaOS/

https://www.reddit.com/r/homelab/

https://www.reddit.com/r/homelab/wiki/software/#wiki_oblecto

https://umbrel.com/#umbrelos (alternative to casaos)

https://github.com/awesome-selfhosted/awesome-selfhosted

https://github.com/SelfhostedPro

https://www.home-assistant.io/

https://www.openhab.org/

https://www.awesome-ha.com/

https://github.com/kieraneglin/pinchflat
    
