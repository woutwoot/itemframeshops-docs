# Reload handling

!!! warning
    All of the information on this page no longer applies for versions 6.2.0 and up. I discovered a supported way of 
    dealing with reloads. (ServerLoadEvent) That being said, restarting your server is still the better option if 
    possible.
    
IFS does not support server reloads and if you reload your server your shops will no longer work until you run
`/ifs reload`. For those that really do want to use `/reload`, IFS does offer a workaround, which will be explained 
here.

## The workaround
In the main configuration file you can find `reloadHandling: true`. This setting will enable a (hacky) workaround to 
load your shops on reload as expected. This seems to be working fine, but due to the way this is implemented it has the
potential to fail.

## Why not support reloads?
IFS loads your shops as soon as a world gets loaded. This means IFS can protect your shops before any player is able to 
join the server. Additionally, this gives IFS some time to calculate all available recipes and combinations of these 
recipes once at world load. The problem here is that if you reload your server, worlds stay loaded and do not reload.
There is no (clean) way for IFS to know whether it was reloaded or started, as it's memory is wiped on reload by the 
server.

A completely seperate (and controversial) topic is that reloads are bad for your server anyway, and that they can cause
issues. (see threads like: 
[1](https://bukkit.org/threads/is-reload-that-bad.129514/) 
[2](https://bukkit.org/threads/petition-to-remove-the-reload-command.43212/)
[3](https://www.spigotmc.org/threads/lets-kill-reload-or-make-it-better.35611/)
...
)

## Technical details
IFS hooks and detects the use of the `/reload` command. As soon as it is used, IFS will create a file in the plugin 
folder that it will look for when starting up, this works as a memory substitute. If the file is there, IFS knows that 
this is a reload, and not a "cold start". It will then be able to handle this appropriately by force loading your shops.
The reason that this is hacky is that the file can go missing for any reason, or take a while to show up if your disk is
slow. A file write could fail, ...