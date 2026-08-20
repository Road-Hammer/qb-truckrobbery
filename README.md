# qb-truckrobbery

**GTA V / FiveM game resource.** Armored truck robbery mission for [QBCore](https://github.com/qbcore-framework).

This is **video-game content**. It is not a real-world trucking tool, not OSINT, not a pentest utility, and not logistics software. It only runs inside a FiveM (Grand Theft Auto V) roleplay server.

Upstream-style resource: QBCore `qb-truckrobbery` (author listed as Kakarot in `fxmanifest.lua`). License: GNU GPL v3 (QBCore Framework / Joshua Eger).

## What it does in-game

1. Player walks up to a dealer NPC and presses **E** to accept the mission.
2. Server checks bank cash (default `$500`), on-duty police count (default `2`), and that no other run is active.
3. A **Stockade** (armored van) spawns at a random configured location with three armed guards.
4. Player clears the guards, stops the vehicle, and plants a charge on the rear doors (default 30s fuse).
5. Loot: 1–3 `markedbills` (configurable payout) and a rare `security_card_01`.
6. Police receive a 10-90 blip (“Armored Truck Robbery”) and can silence the alarm.

## Requirements

A running **FiveM** server with:

- `qb-core`
- `qb-inventory`
- `qb-phone`
- `qb-policealerts`
- GTA V FiveM client

Without that stack, this resource does nothing.

## Install (FiveM only)

1. Place this folder in `resources/[qb]/qb-truckrobbery`
2. Add `ensure qb-truckrobbery` to `server.cfg`
3. Edit `config.lua` (dealer coords, spawn points, weapons, cop count, payout, cooldown)

## Layout

| File | Role |
|---|---|
| `fxmanifest.lua` | FiveM manifest (`game 'gta5'`, v1.5.0) |
| `config.lua` | Marker, dealer, spawns, weapons, payout, timers |
| `client.lua` | Mission accept, van/guards, plant charge, loot |
| `server.lua` | Start cost, police check, payout, cooldown |
| `LICENSE` | GNU GPL v3 |

## Config (defaults)

| Setting | Default | Meaning |
|---|---|---|
| `Config.ActivationCost` | 500 | Bank cash to start |
| `Config.ActivePolice` | 2 | On-duty LEO required |
| `Config.Payout.Min` / `Max` | 250 / 450 | Marked-bills worth |
| `Config.TimeToBlow` | 30 | Seconds until rear doors blow |
| `Config.ResetTimer` | 600 | Mission cooldown (seconds) |
| `Config.DriverWeap` / `NavWeap` | `WEAPON_MICROSMG` | Guard weapons |

## License

GNU General Public License v3. See `LICENSE`.
