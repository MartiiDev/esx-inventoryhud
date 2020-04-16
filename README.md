FR. Fork de esx_inventoryhud avec ajout du double clic pour utiliser un item.
Plus possible de sélectionner du texte par erreur avec la souris.

EN. Fork of esx_invetoryhud adding double click to use the items.
You can't select text anymore with mouse while in inventory.

## Requirements
- [es_extended](https://github.com/ESX-Org/es_extended)
- [cron](https://github.com/ESX-Org/cron)
- [esx_addonaccount](https://github.com/ESX-Org/esx_addonaccount)
- [esx_addoninventory](https://github.com/ESX-Org/esx_addoninventory)
- [esx_datastore](https://github.com/ESX-Org/esx_datastore)
- [B1G Notify](https://forum.cfx.re/t/release-esx-b1g-notify-system-full-costumizable/)

## Installation
You need to do a couple steps to get it working.
First you start adding the resources to your server.cfg.

- Put all folders in your resources folder and start:
```
start esx_inventoryhud
start esx_inventoryhud_trunk
start esx_inventoryhud_glovebox
```

- Add this at the top of your server.cfg:
```
set mysql_debug 1
set mysql_debug_output "console"
set mysql_slow_query_warning 200
```

## Usage
Press F2 for your personal inventory.
Press F3 inside a car for the glovebox inventory.
Press F3 behind a car for the trunk inventory.

### Disable default esx inventory:

Open es_extended, then find and remove this code in `client/main.lua`:
```
-- Menu interactions
Citizen.CreateThread(function()
	while true do

		Citizen.Wait(0)

		if IsControlJustReleased(0, Keys['F2']) and IsInputDisabled(0) and not isDead and not ESX.UI.Menu.IsOpen('default', 'es_extended', 'inventory') then
			ESX.ShowInventory()
		end

	end
end)
```

### Fix for esx_addoninventory:

Go to `esx_addoninventory\server\classes\addoninventory.lua` line 39

Replace `label = Items[name]` to `label = items[name]`
    
> Read other support files to make esx_inventoryhud work with esx_policejob and esx_propery!


## Features
- Drag and drop
- Using items
- Dropping items
- Giving items
- Cash included
- Accounts support (bank, black money, ...)
- Weapons support
- esx_property support
- Another players inventory support
- Fully configurable (check config.lua and html/js/config.js)
- Locale files included (check locales/ and html/locales/ directories)

### Known bugs
- If you enable cash in inventory: players can turn money into black money from inventory to glovebox or trunk.

## Language support
Currently, only Dutch is supported. If you want to translate it then feel free to pull a request!

## Screens
![1](https://raw.githubusercontent.com/dutchplayers/esx-inventoryhud/master/esx_inventoryhud.PNG)
![2](https://raw.githubusercontent.com/dutchplayers/esx-inventoryhud/master/esx_inventoryhud_trunk.PNG)
    

# Support
We can give you support in our [Dutch Discord Server](https://www.dutch-players.nl/go/discord/)

# Original threads: 
https://forum.fivem.net/t/esx-inventoryhud-glovebox/687328

https://forum.fivem.net/t/release-esx-inventory-hud-2-0/388318

https://forum.fivem.net/t/addon-esx-inventory-hud-vehicle-trunk/458152
