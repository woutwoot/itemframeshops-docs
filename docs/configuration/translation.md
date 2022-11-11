# Translation

IFS can be translated to your language by editing the main `config.yml` file and `messages.yml` file. Let me know in 
case you've done so, I will add translations to this page.

## French

### Config
Snippet of the relevant config settings (this is not the full configuration file!):
```yaml
  buy:
    nameBuy1: Acheter 1
    nameBuy32: Acheter 32
    nameBuy64: Acheter 64
    nameBuyAll: "Remplir l'inventaire"
    loreBuy1: "N'en acheter qu'un seul dans ce magasin;&6Prix: {price}"
    loreBuy32: "Acheter la moitié d'un stack dans ce magasin;&6Prix: {price}"
    loreBuy64: "Acheter un stack from dans ce magasin;&6Prix: {price}"
    loreBuyAll: "Remplir l'inventaire;&6Prix total: {price}"
    loreDiscount32: "Acheter la moitié d'un stack dans ce magasin;&6Prix: {price};&a- {discount}%
      discount;&6Total: {total}"
    loreDiscount64: "Acheter un stack dans ce magasin;&6Prix: {price};&a- {discount}% discount;&6Total:
      {total}"
  # Change names and lores for sell icons. Use ; for a new line.
  sell:
    nameSell1: Vendre 1
    nameSell32: Vendre 32
    nameSell64: Vendre 64
    nameSellAll: Vendre All
    loreSell1: "N'en vendre qu'un seul dans ce magasin;&6Prix: {price}"
    loreSell32: "Vendre la moitié d'un stack dans ce magasin;&6Prix: {price}"
    loreSell64: "Vendre un stack from dans ce magasin;&6Prix: {price}"
    loreSellAll: "Tous vendre dans ce magasin;&6Prix: {price}"
  # Change names and lores for disabled icons. Use ; for a new line.
  disabled:
    nameDisabled: "&4DESACTIVE"
    loreDisabled: Cette fonction est désactivée pour ce magasin.
```

### Messages
This is a full `messages.yml` config that was tested with IFS 6.2.0.
```yaml
file_encoding: UTF-8
actions:
  playerbuy:
    just_bought: "Vous venez d'acquérir {amount} {itemname}"
    could_not_withdraw: "Vous n'avez pas assez d'argent pour acheter cet item."
    no_permission: "Vous ne pouvez pas acheter d'articles dans les boutiques. Vous n'en avez pas l'autorisation."
    no_space_in_inventory: "Vous ne pouvez acheter cet item, vous n'avez plus de place dans votre inventaire!"
    not_in_group_whitelist: "Votre groupe n'est pas autorisé à acheter ici !"
  playersell:
    just_sold: "Vous venez de vendre {amount} {itemname}"
    could_not_withdraw: "La quantité des items que vous voulez vendre, est supérieure à la quantité d'item que vous possédez"
    no_permission: "Vous ne pouvez pas vendre d'articles dans les boutiques. Vous n'en avez pas l'autorisation."
    not_in_group_whitelist: "Votre groupe n'est pas autorisé à vendre ici !"
  create:
    empty: "Vous ne pouvez pas créer de boutique vide"
    success: "C'est bon! Ce magasin contient: {itemname} pour {price}"
    no_permission: "Vous n'avez pas la permission de créer des boutiques !"
  remove:
    success: "Magasin supprimé avec succès. L'itemframe peut-être supprimé."
    no_permission: "Vous n'avez pas la permission de supprimer des boutiques !"
  misc:
    no_blocks_on_shops: "S'il vous plaît, ne placez pas de blocs au-dessus des magasins !"
    not_a_shop: "Désolé, cet ItemFrame n'est pas un magasin !"
commands:
  GLOBAL:
    no_permission: "Vous n'avez pas la permission d'utiliser cette commande. Vous avez besoin de: {permission}"
    price_not_valid: "Ceci n'est pas un prix valide !"
    player_only: "Cette commande ne peut être exécutée que par un joueur."
```