# Getting Started

## Introduction
Thanks for purchasing ItemFrameShops! While the plugin is very easy to use, 
there are a few things you should take into account before starting to use the plugin on a live server. 
This page will help you get started and make sure that you've tuned everything to go live.  
Please note, I'll be abbreviating ItemFrameShops to IFS to save me some typing time.

## Installation and dependencies
Installing IFS is just as easy as installing any other Bukkit plugin: just drop the `.jar` file in your `plugins` 
folder. There are however a few dependencies that you'll also need to install on your server for IFS to work correctly. 
Keep in mind that some of these are version specific.

!!! note 
    Make sure you look at your console when starting up your server with IFS. IFS will try to be very descriptive in 
    case something went wrong. This is usually because of missing/incorrect dependencies.

### Minecraft 1.14, 1.15, 1.16+
These versions are currently the only versions compatible with the latest IFS updates.

 * `Vault` version 1.7.2 [download](https://dev.bukkit.org/projects/vault/files/2704903)
 * An `economy plugin` compatible with this Vault version (I suggest EssentialsX economy)
 * `WorldEdit` version 7.0.1 (if you want to use the WorldEdit commands) [download](https://dev.bukkit.org/projects/worldedit/files/2745997)
 * A permission manager (I suggest LuckPerms)

### Minecraft 1.13
Last working IFS version: `5.0.7`

 * `Vault` version 1.7.2 [download](https://dev.bukkit.org/projects/vault/files/2704903)
 * An `economy plugin` compatible with this Vault version (I suggest EssentialsX economy)
 * `WorldEdit` version 7.0.0 (if you want to use the WorldEdit commands) [download](https://dev.bukkit.org/projects/worldedit/files/2723275)
 * A permission manager (I suggest LuckPerms)

### Minecraft 1.8 - 1.12
Last working IFS version: `4.4.32`

!!! warning
    These versions are no longer receiving IFS updates unless they are absolutely critical. Please let me know if 
    you're still using one of these.

 * `Vault` version 1.5.6 [download](https://dev.bukkit.org/projects/vault/files/894359)
 * An `economy plugin` compatible with this Vault version (I suggest EssentialsX economy)
 * `WorldEdit` version 6.1.8 (if you want to use the WorldEdit commands) [download](https://minecraft.curseforge.com/projects/worldedit/files/2460570)
 * A permission manager (I suggest LuckPerms)

 
## Making some basic configuration changes
Please see the [page](configuration/main.md) related to the main configuration file for more information.
Some things that users often change:

 * `sellFactor` is usually lowered, as the default is still quite high
 * Servers with higher base prices usually enable `convertLargeNumbers`
 * Names and lores for items are usually changed for different languages
 
 See [messages.yml](configuration/messages.md) for information about changing default messages.

## Setting up prices
This is going to take up most of your time, as getting prices right is very important for a stable economy. For now, 
please see the [prices](configuration/prices.md) page for more information.

## Setting up permissions
This is how permissions are usually configured:

|Group|Permissions|
|--|--|
|Normal players|ifs.user.sell<br>ifs.user.buy<br>ifs.user.useSellAll<br>ifs.user.useBuyAll|
|Donators|ifs.user.discount32<br>ifs.user.discount64|
|Admins|ifs.admin.remove<br>ifs.admin.create<br>ifs.admin.gui<br>ifs.admin.shopgui|
|Server owner|ifs.command.*|

Of course, it is up to you to decide whether or not special ranks get perks like discounts or access to features like buy/sell-all.

## Creating/removing shops

### Actions
IFS supports simple actions to create or remove shops. To create a shop, crouch and right click an item frame. To remove
a shop, the same action applies, only this time you use left click. Quite intuitive even if I say so myself...

### Commands
If you prefer to use commands, IFS also supports the `/ifs create` and `/ifs remove` commands. See the [commands](commands.md)
page for more ways to create shops like using a WorldEdit selection.

!!! note 
    `/ifs create` or `/ifs remove` are toggle commands. This means that if you run the command once, you can use it to 
    create/remove multiple shops until you run the command again.

## Final fine tuning

Once your server is up and running with IFS enabled, I suggest keeping a close look on the blances of your players and
on the ItemFrameShops logs file. This allows you to identify potential problems with items that are to cheap or expensive.