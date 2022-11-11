# Prices config
*Arguably the most important config for the plugin and the place where you will need to spend most time getting prices
tuned to your liking.*

Since IFS 5 a new prices format was introduced. It uses the new name based system to target specific Minecraft items and offers
advanced features such as expressions.


# Configuration file

### Items
Minecraft item IDs are used as keys in the configuration file. It looks like this:
```yaml
item_prices:
  ...
  acacia_leaves:
    buyprice: 8
    sellprice: 1
  ...
```

### Prices
As demonstrated in the above example, you can set default buy *and/or sell prices*, these will then be used in all price calculations
done by IFS. If a default sell price is set, the sell factor configuration setting is not used as this only applies when
calculating a sell price based on multiplying the buy price.

### Expressions
Expressions currently only apply to buy prices. They allow you to include prices for other items to make a calculation.
Although they are very powerfull, they can also create issues or cause infinite loops when used improperly. It looks like this:
```yaml
item_prices:
  ...
  pufferfish_spawn_egg:
    buyprice: 50
  iron_ore:
    buyprice: 50
  pufferfish_bucket:
    expression: '%bucket% + %pufferfish_spawn_egg%'
  ...
```
When a shop with a pufferfish_bucket is created, this happens internally:

  1. Get the price of bucket (first checks config, then recipes, calculates iron ingot and then bucket price based on iron_ore price and smelting cost price)
  2. Get the price of pufferfish_spawn_egg (configured)
  3. Evaluate expression `%bucket% + %pufferfish_spawn_egg%`
  4. Final price for pufferfish_bucket is now known
  
# Pricing guide
## Getting the right price

 - sellFactor is usually lowered, as the default is still quite high
 - use the log file and shop info to analyse player behaviour and tune prices
 - figure out what kind of item is worth a lot
 - make sure you don't create feedback loops (where one item depends on another and then back again) as this will
   cause IFS (and possibly your server) to crash
   
To any server owner reading this, if you have a good strategy for keeping a stable economy and setting the correct prices,
please contact me. I will then add a section about this to this page.