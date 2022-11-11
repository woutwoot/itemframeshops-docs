# Messages config
These are all the messages that are configurable for the plugin. You can use these to translate player-facing messages
into your server language.

This page is currently being worked on. For now, a copy of the configuration file is shown:

``` yaml
file_encoding: UTF-8
actions:
  playerbuy:
    just_bought: You've just bought {amount} {itemname}
    could_not_withdraw: We could not withdraw the correct amount of funds from your
      account.
    no_permission: You cannot buy items from ifs shops. You do not have the permission.
    no_space_in_inventory: You don't have enough space in your inventory!
    not_in_group_whitelist: Your group/rank is not allowed to buy here!
  playersell:
    just_sold: You've just sold {amount} {itemname}
    could_not_withdraw: We could not withdraw the correct amount of items from your
      inventory. You don't have enough.
    no_permission: You cannot sell items to ifs shops. You do not have the permission.
    not_in_group_whitelist: Your group/rank is not allowed to sell here!
  create:
    empty: You can't create an empty shop!
    success: 'Success! This shop contains: {itemname} for {price}'
    no_permission: You do not have permission to create shops.
  remove:
    success: Shop successfully removed. The ItemFrame is now no longer protected and
      can be removed.
    no_permission: You do not have permission to remove shops.
  misc:
    no_blocks_on_shops: Please don't place blocks over shops!
    not_a_shop: Sorry, that frame is not a shop!
commands:
  GLOBAL:
    no_permission: 'You do not have permission to use this command. You need: {permission}'
    price_not_valid: That is not a valid price!
    player_only: This command can only be run by a player.

```