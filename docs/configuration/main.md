# Main config
Most of the configuration is done in the main configuration file. For the average server, most of the defaults will work 
fine.

!!! warning
    When making changes to any configuration file, make the edits while the server is offline or use the `/ifs reload` 
    command after making edits to make sure that they are not overwritten when your server stops.

This page is currently being worked on. For now, a copy of the configuration file is shown here.

``` yaml
#ItemFrameShops config file. Information about a setting can be found above the setting using a comment like this.
#More information can be found at: http://www.spigotmc.org/resources/itemframeshops.4667/
#If you have a problem, please use this page: http://wwx.be/itemframeshops/problem.php
#If you are going to set up prices, this page might come in handy: http://wwx.be/itemframeshops/
#Thank you for buying my plugin, I hope you enjoy using it!
plugin:
  # Change this to change how the plugin messages look in chat.
  tag: '&4[IFS]: &e'
  # Set this to true to enable logging. The plugin will create a logs.txt in the plugin folder.
  logging: true
  # Can enable or disable update checks.
  checkForUpdate: true
  # Automatically save shops every 15 minutes?
  autoSave: true
  # Experimental setting.
  # Set this to true to sync prices with existing shops when you create new ones.
  synchronizeShops: false
  # Set to true if you want the shop menu to stay open when a "button" was clicked.
  keepShopMenuOpen: false
  # Set to true if you want to block shop usage for people in creative mode.
  noCreativeUsage: false
  experimental:
    # Don't require /ifs reload after reloading. This is a very hacky workaround, use at your own risk!
    reloadHandling: true
prices:
  # All newly created shop prices will be multiplied by this number.
  priceMultiplier: 1.0
  # Buy price * this number = Sell price
  sellFactor: 0.1
  # The default price shops will use when they can not load or calculate a price.
  defaultPrice: 20.0
  # The next two settings are for discounts.
  # Value is in percent, must be between 1 and 99
  discountPercent32: 2
  discountPercent64: 4
  # Set this to true to show large numbers as 100k or 20M, ...
  convertLargeNumbers: false
inventory:
  misc:
    # Use this to change the shop title. This will use extra server bandwidth!
    # Colors are not supported.
    shopMenuTitle: This is a custom title!
    # Set this to false if you don't want to allow selling stacks for unstackable items.
    show3264forUnstackable: true
    # Set to true if you do not want to show an item when a feature is disabled.
    hideDisabledItem: false
    # Set to true if you do not want to show the preview item.
    hidePreviewItem: false
    # Set to true if you want the buy/sell buttons to be the same item as the item being sold.
    useItemAsIcon: false
    # Set to true to disable the sell all button.
    disableSellAll: false
    # Set to true to disable the fill inventory button.
    disableBuyAll: false
    # Change the item that is being used for buy/sell buttons.
    # A list of materials can be found here: http://wwx.be/itemframeshops/materials.php Use the "Bukkit Material"
    shopIconsMaterial: GOLD_INGOT
    # Change the item that is being used for "disabled" icons.
    # A list of materials can be found here: http://wwx.be/itemframeshops/materials.php Use the "Bukkit Material"
    disabledIconMaterial: BARRIER
  # Change names and lores for buy icons. Use ; for a new line.
  buy:
    nameBuy1: Buy 1
    nameBuy32: Buy 32
    nameBuy64: Buy 64
    nameBuyAll: Fill inventory
    loreBuy1: 'Buy just 1 from this shop;&6Price: {price}'
    loreBuy32: 'Buy half a stack from this shop;&6Price: {price}'
    loreBuy64: 'Buy a stack from this shop;&6Price: {price}'
    loreBuyAll: 'Fill your inventory;&6Total price: {price}'
    loreDiscount32: 'Buy half a stack from this shop;&6Price: {price};&a- {discount}%
      discount;&6Total: {total}'
    loreDiscount64: 'Buy a stack from this shop;&6Price: {price};&a- {discount}% discount;&6Total:
      {total}'
  # Change names and lores for sell icons. Use ; for a new line.
  sell:
    nameSell1: Sell 1
    nameSell32: Sell 32
    nameSell64: Sell 64
    nameSellAll: Sell All
    loreSell1: 'Sell just 1 to this shop;&6Price: {price}'
    loreSell32: 'Sell half a stack to this shop;&6Price: {price}'
    loreSell64: 'Sell a stack to this shop;&6Price: {price}'
    loreSellAll: 'Sell all to this shop;&6Price: {price}'
  # Change names and lores for disabled icons. Use ; for a new line.
  disabled:
    nameDisabled: '&4DISABLED'
    loreDisabled: This feature is disabled for this shop.
  # Do not change these numbers!
  # They are used by the plugin for the /ifs layout command.
  layout:
    sell1slot: 8
    sell32slot: 7
    sell64slot: 6
    sellAllSlot: 14
    buy1slot: 0
    buy32slot: 1
    buy64slot: 2
    buyAllSlot: 12
    previewSlot: 4
    inventorySize: 18

```