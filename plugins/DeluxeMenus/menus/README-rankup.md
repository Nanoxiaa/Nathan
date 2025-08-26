### RankUp menu (DeluxeMenus)

- Required plugins: DeluxeMenus, PlaceholderAPI, LuckPerms, Vault, an economy plugin (e.g. EssentialsX)
- Required PAPI expansions: LuckPerms, Vault

Setup:
- Place `rankup.yml` in `plugins/DeluxeMenus/menus/` (already done).
- Install expansions, then reload PAPI:
```mcfunction
/papi ecloud download LuckPerms
/papi ecloud download Vault
/papi reload
```
- Reload DeluxeMenus:
```mcfunction
/dm reload
```
- Open the menu in-game:
```mcfunction
/rankup
```

How it works:
- Ranks B–F appear with 3 states per slot: Current, Available, Locked (handled by `priority`).
- To rank up, the player must be in the previous group and meet conditions:
  - Money thresholds: B 10k, C 25k, D 50k, E 100k, F 250k
  - Level thresholds: B 10, C 20, D 30, E 40, F 50
- On success: takes money, sets LuckPerms group, plays sound, shows message.

Customize:
- Edit costs/levels in `left_click_requirement.requirements` for each rank.
- Edit groups in `view_requirement.requirements.*.output` and `lp user %player_name% parent set <group>`.
- Change slots/materials/titles as you like.

Notes:
- Ensure your LuckPerms groups exist: `a`, `b`, `c`, `d`, `e`, `f` (case-insensitive).
- Economy deduction uses EssentialsX: `eco take`. If you use another economy plugin, adjust the command.