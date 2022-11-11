#Changelog

### 6.5.1
- Removed shopMenuTitle feature. (it was no longer working properly) I may end up re-adding it in the future if there 
is an easier way to do so.

### 6.5.0
- Updated to Minecraft 1.18.1 (some prices may still be missing)
- Added additional fail safes to plugin load
- Updated internal dependencies
- Various bug fixes & code improvements

### 6.4.1
- Fixed errors related to synchronizeShops setting in case a shop is in an unloaded chunk (Thanks to @AcesGamingUK for 
sending over his server files so I could debug.) 

### 6.4.0
I asked for feedback, and most of your feedback was related to making shops easier to configure. To achieve that goal, 
I have started to add more GUIs to IFS that can be used to configure shops or teleport to them.

- Added the "IFS wand" - spawn it using the /ifs wand command. When you right click a shop with this wand, the config 
GUI will pop open
- Changed the /ifs GUI. It can now list (and configure) all shops and will allow you to teleport to shops provided that 
they are in loaded chunks

### 6.3.1
- Fixed issues with recalc and recalcall related to unloaded shops
- Added support for 1.16 Smithing recipes
- Added some important new default prices for 1.16 - not all new items have defaults yet
- This release is still compatible with 1.14 and up

### 6.3.0 (beta)
- Updated to work with **1.16.1**
- Updated recipe handling code so IFS doesn't error out if it finds a new type of recipe. (in this case Smithing)
- This is a **stable version without price calculation or default prices for items added in 1.16.1** - so I'm releasing it 
as a beta

### 6.2.2
- Sellhand and sellall commands will no longer sell an item if the calculated price is 0

### 6.2.1
- Improved error reporting in case there are syntax errors in messages.yml
- Added translation section to the manual with French translations for config files (thanks Zarteck123)

### 6.2.0
- IFS now properly supports reloads. No more workarounds. (but advice is still to restart your server)
- Some more of the backend code had been cleaned up in preparation for upcoming content updates. This update should be 
fine, but please let me know in case you notice any kind of issues.

### 6.1.1
- Now compiling with 1.15.2
- Fixed issue with dependency check causing generation of a (mostly) empty configuration file in cases where no economy 
plugin was found
- Better compatibility with economy plugins that load after IFS (BagOfGold, CMI Economy)

### 6.1.0
- Fixed 1.15 compatibility, should still work on 1.14
- Fixed issue with /ifs list, shops that have not been interacted with yet will show up 
without a location, but display a UUID instead. You can now also provide parameters to the list command to narrow the 
search like: cached, uncached, topsales, highestprice, leastsales, lowestprice. I did not spend a lot of time on this 
as I don't think it'll be used often. If you notice bugs, let me know.

### 6.0.5
- Minor bug fixed for item names in chat messages (names are now capitalized and custom names can now also be printed)

### 6.0.4
I'm taking 6.X out of beta, because I'm afraid it will otherwise stay in beta forever. Once you upgrade to this version 
**you will not be able to downgrade** again. **Backup before upgrading**! As for the upcoming functionality (custom 
discounts per shop) this will be delayed as I'm currently very busy.

- Compiled for 1.14.4 (did not need any code changes)
- Fixed WorldEdit commands not working
- IFS now targets WorldEdit 7.0.1
- Fixed another issue related to shops in unloaded chunks when using the `/ifs reload` command.
- IFS now limits the amount of transaction logs per shop to 300 in order to make sure the shops file does not grow to 
  enormous sizes. In the future this will be configurable

### 6.0.3 (beta)
- I've removed the `convertworth` command. In hindsight this was probably not used often and since the price file 
changes in the new IFS it just makes more sense to get rid of this. EssentialsX should no longer be any sort of 
dependency. Let me know if you were actually using this, I'll then try to add it back in properly :)

### 6.0.2 (beta)
- Fixed error in console on block destroy if a shop is in a chunk that is not loaded.
- Now using essentialsX for convertworth command. Untested!
- Fixed error with command completion
- Fixed issue with IFS and PermissionsEx (due to group autocomplete)

### 6.0.1 (beta)
- Fixed shops not loaded if frames were placed in unloaded chunks. Shops should now load as expected.

### 6.0.0 (beta)
Yet another big update for IFS! There are no breaking changes, but once you upgrade to this version **you will not be able
to downgrade** again. **Backup before upgrading**! 

I had to rush to get this release out because of the fixes it also contains, the rest of the new functionality will be 
added in the next update. See this as a **beta** release

- Shops can now be placed within the same "block" (like two shops in a corner)
- New format for shop data files: this adds an easier way for me to store extra data along with shops. I'll be able to 
add more customization for induvidual shops (like discounts) but also keep extra information like logs per shop. 
This does have a small drawback: shops will load slightly slower (barely noticeable)
- The first of using this new data: transactions logs per shop. This is currently in a very early state and the command
functionality will be expanded but you can view logs per shop using `/ifs transactions`, the amount of logs is not 
limited in any way yet, **if you have a very busy server I suggest waiting for the next update**.
- Fixed `/ifs create` command as it was checking for a frame being a shop before actually creating a shop, which made no
sense at all. Not sure when I introduced this issue, but it should be fixed now :)
- Improved command completion.
- Shops are no longer protected from blocks being placed over them to improve performance. Most users are using some 
other form of protection anyway. Let me know if this is an issue for you. (shops remain protected from explosions and 
 damage by other entities, the block they are hanging onto can not be removed)

### 5.1.2
I've added the CMIEInjector as a soft dependency for IFS so IFS loads after CMI's Vault Injector. 
This makes sure that both work together without using a modified Vault version. 
This should not have any effect for users that do not use CMI.

### 5.1.1
- Compiled for Minecraft 1.14.2 (no changes were needed)
- IFS no longer prints an auto-save message to console

### 5.1.0
- Updated to Minecraft 1.14: this means IFS now supports price calculation based on stonecutter, campfire, ... recipes. 
  Unfortunately, brewing recipes are still not available in the Bukkit API and thus IFS can also not handle them.
- Made sure shops are saved whenever shop prices or other settings are modified using the in game commands

#### Update considerations
- Sadly this is another breaking update. IFS will not start on versions other than 1.14 and newer. I'm planning on 
  backporting this to 1.13, but due to time constraints 1.13 support is not present in the current release.
- Custom shop menu titles are not supported for 1.14 until I find time to update the NMS code

### 5.0.7
- Fixed another issue that made IFS hard depend on WorldEdit
- Added more clear startup messages about versions and detected economy etc
- IFS now refuses to start up on Minecraft versions older than 1.13 since they are not supported for 5.X anyway

### 5.0.6
- Fix issue with `/ifs sellhand` not taking into account the amount of items in the stack.
- Make sure the API events are also triggered for sell commands

### 5.0.5
- New manual now available (work in progress)
- Added a basic AP

### 5.0.4
- Fixed a few small typos
- Fixed WorldEdit support - This requires the very latest WorldEdit!
  You can download it [here](http://builds.enginehub.org/job/worldedit/last-successful?branch=master)
  (you only need worldedit-bukkit)


### 5.0.3
- Added custom shop menu title support for Minecraft 1.13
- Improved update check performance impact (was barely noticeable, but all small improvements count)
- Add experimental workaround (needs to be enabled in config) to handle `/reload` automatically. Use at your own risk.
  This will only work for reloads triggered by the reload command, not when triggered through a plugin.
  To use it, edit config.yml and add the new setting like in this snippet: (or delete it and start your server to generate a new one)
``` yaml
  ...
  plugin:
    ...
    experimental:
      # Don't require /ifs reload after reloading. 
      # This is a very hacky workaround, use at your own risk!
      reloadHandling: true
```


### 5.0.2
- Fixed issues with `/ifs reload`.
- Updated for 1.13.2


### 5.0.1
Added fuel cost calculation. IFS will use the price it calculates for stick along with the cooking time needed for an item to calculate the cost for smelting that item.
For example, stick is calculated by IFS to cost 0.5$ (based on log price). Smelting 1 iron ore needs 2 sticks. This means that if iron ore costs 50$, iron ingot now costs 51$.


### 5.0.0
I'm happy to announce the release of the next major IFS update: IFS `5.0.0`. Quite a few things have changed, so please take the time to read the full changelog and all my notes.

- Updated to be fully compatible with 1.13, dropped support for all other older versions (I will still try to fix important bugs for the latest `4.4` release if required)
- Updated default prices for 1.13 (please provide feedback as these have not been tested at all!)
- No longer using data values for items, items will only use the id. All obtainable Minecraft items now have a unique ID
- Changed to a new configuration file for default prices that will also allow you to specify a default sell price (has not been tested much yet!)
- Added the ability to use "expressions" in this new default prices file. (see the defaults for examples)
- (Temporarily) removed feature that allows changing of shop titles since it depends on NMS code and I did not have time to update this
- Switched over to the Bukkit API to display the heart particle when selling to/buying from shops. This should now be update proof
- Removed all migration tools. Old configuration files and shop files will no longer be loaded. (applies to `config.properties`, and `shops.properties` files)
- Improved performance of various parts of the code
- Complete rewrite of price calculation code. Price calculation should now be more reliable
- Fixed pasting to HasteBin in `/ifs debug` command
- Stopped using Deprecated methods all over the code. Dropping support for prior versions allowed me to clean up A LOT
- Updated to newest Vault version and adapted code that was using removed APIs
- Added basic tab command completion

#### Update considerations
- Old configuration files and shop files will no longer be loaded. (applies to `config.properties`, and `shops.properties` files)
- Old `prices.properties` file is no longer used. Manually transferring prices will be neccesary as the material ids have changed.

#### Update FAQ
Are you abandoning older versions?

 - No. I will still fix bugs in `4.4.32` if needed. I will NOT be adding or backporting new features to these versions. I'm sorry, but it's just to much work to keep 2 parallel versions updated.

Why did you make the newest version only support 1.13?

- Simply, to make it easier for me. A large part of the code was becoming more and more bloated just to keep support for older versions.
  This change made it possible for me to clean up my codebase a lot and should provide better compatibility with future updates as well as better performance in general.

How about the default prices?

- Keep in mind that when first testing this new version, if a price cannot be found the default price will be returned. A message will be logged in console alerting you about this.
- I currently do not have a good reference to base my prices on since I no longer have my own server or actually play Minecraft.
  If people are willing to give me access to their server, I might be able to gather some statistics and come up with better default prices.
  Please let me know if you're willing to help and have a fairly active server. I will send you a plugin that can collect some statistics and help me to figure out good default pricing.
  The currently pricing is purely based on guesses and wanting to get things done. It is probably very bad. If you can help me with this in any way, let me know.
- I'm thinking about a dynamic pricing feature and doing some experiments with it, but I'm not making any promises regarding this being added eventually.

A few things are still missing/not completely working in this release:

- Migration tools (converting old configs): because they simply take a lot of time for me to work on and need maintenance. If there is a lot of demand for this I will provide them later.
- Potion recipes and default prices for potions: These depend on metadata. For now, prices for potions need to be set on each individual shop.
- No custom shop inventory titles: This depends on NMS, and that's just something I don't like. Again, if there is a lot of demand for it, I will add it again.
- As mentioned before, the default prices might not be all there, and those that have been specified could be way off. Feel free to contact me and help me with this!
- Some custom recipes can still cause a nasty lag spike and error when trying to create a shop. Please contact me if this happens.