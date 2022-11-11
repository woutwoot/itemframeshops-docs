# Commands

!!! note
    All commands listed on this page are sub-commands to the main command. (`/ifs [sub-command]`)

## General

|Command|Description|Permission|
|---|---|---|
|help|Shows information about commands|ifs.command.help|
|version|Shows the current IFS version number.|ifs.command.version|
|wand|Gives the magic IFS wand, holding this while clicking an item frame will open up the config GUI.|ifs.command.wand|
|materials|Saves a file containing all possible materials (blocks and items) in the game. Useful to customize default prices.|ifs.command.materials|
|reload|Reloads config files and data from disk|ifs.command.reload|
|save|Saves config files and data to disk|ifs.command.save|
|iteminfo|Used for debugging prices stuff. Shows item info.|ifs.command.iteminfo|
|setdefaultprice [new default price]|Allows changing the default price (in prices.properties) for the item in your hand. (does not work for custom items!)|ifs.command.setdefaultprice|

## WorldEdit

|Command|Description|Permission|
|---|---|---|
|createshopsinselection|Turns every itemframe in your WorldEdit selection into a shop.|ifs.command.createshopsinselection|
|removeshopsinselection|Removes every shop in your WorldEdit selection (but keeps items and frames).|ifs.command.removeshopsinselection|
|recalcshopsinselection|Recalculates prices for every shop in your WorldEdit selection.|ifs.command.recalcshopsinselection|
|modifypricesinselection|Multiplies prices by your provided factor for every shop in your WorldEdit selection.|ifs.command.modifypricesinselection|

## Induvidual shop settings

|Command|Description|Permission|
|---|---|---|
|create|Enables creating shops (click on item frame to create shop, toggles)|ifs.command.create|
|remove|Removes shop (click on item frame to apply, toggles)|ifs.command.remove|
|setmode [BUYING/SELLING/BOTH/DISABLED]|Set if shop is disabled or allowed to sell and/or buy items|ifs.command.mode|
|setprice [new price]|Automatically sets sell price to buy price * sell factor (see config.yml) for shop (click on item frame to apply, toggles)|ifs.command.price|
|setbuyprice [new buyprice]|Sets buy price for shop (click on item frame to apply, toggles)|ifs.command.buyprice|
|setsellprice [new sellprice]|Sets sell price for shop (click on item frame to apply, toggles)|ifs.command.sellprice|
|recalc|Recalculates buy/sell prices for shop (click on item frame to apply, toggles)|ifs.command.recalc|
|info|Shows statistics and information about a shop. (toggle on/off)|ifs.command.info|
|copy|Copy shop prices, settings and whitelist.|ifs.command.copy|
|paste|Paste shop prices, settings and whitelist.|ifs.command.paste|

## Global shop commands
|Command|Description|Permission|
|---|---|---|
|list|Lists all shops.|ifs.command.list|
|removeall|Removes all shops from the game.|ifs.command.removeall|
|recalcall|Recalculates and loads all shop prices. This will remove any custom set pricing!|ifs.command.recalcall|
|modifyallprices [multiplier]|Modifies all shop prices based on a multiplier. (does not calculate prices again!)|ifs.command.modifyallprices|

## Player
Commands that can be used by players if desired. (this has never been and might never be the focus of the plugin, use 
at your own risk!)

!!! note
    For some permission systems, it might be required to also add `ifs.command` as a permission before players will be
    able to use these.

|Command|Description|Permission|
|---|---|---|
|sellall|Sells your entire inventory at IFS calculated prices.|ifs.command.sellall|
|sellhand|Sells the item in your hand using a price calculated by IFS.|ifs.command.sellhand|

## Unfinished - beta
|Command|Description|Permission|
|---|---|---|
|groupwhitelist [group name]|Adds or removes a group from the group whitelist. (list of groups that are allowed to use the shop) - This feature and command is in beta!|ifs.command.groupwhitelist|
|shoplayout [amount of rows]|Allows you to change how a shop looks. You can reposition all "menu items" in a fake shop-like inventory. It is a work in progress and might be buggy!|ifs.command.shoplayout|
|worth|Shows the price and recipes ifs will use for the item in your hand.|ifs.command.worth|