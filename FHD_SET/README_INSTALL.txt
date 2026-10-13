FHD_SET OneCore Performance Alpha — 2 variants

SOURCE
Built from the latest FHD_SET.rar from the supplied Google Drive folder (modified 2026-10-06).

VARIANTS
1. NORMAL
   Install CORE_NORMAL/Mods into the game root.

2. PURPLE_CARGO
   First install CORE_NORMAL/Mods, then copy PURPLE_CARGO_PATCH/Mods into the game root with replacement.
   This changes only BuildMode and puts all purple SET items (sets 11-15, 25 items) into the player's cargo.

ONE CORE
Both variants use the same optimized FHD_SET core. PURPLE_CARGO is only a replacement Lang.dat switch; there is no second heavy runtime.

PERFORMANCE CHANGES
- CountAllSets reads the existing FHDSETV2_SetIdMarker directly instead of compiling/executing GetSetId for every item.
- Set counting and ordinary-equipment durability selection are merged into one ShipItems pass (previously three full passes per Tick).
- The separate DurabilityTick call is removed from the daily hot path.
- EnsureSearchTool is no longer scanned every day; it follows the existing 10-turn maintenance cadence.
- Entering/re-entering UI forms does not run the entire FHD_SET Tick; only set count/resistance/stat refresh runs.
- ApplyStats is skipped on quiet days; dynamic late-game sets still refresh daily, and static stats get a safety refresh every 5 turns.
- Existing save migration/NormalizePieces remains, so old SET items receive/keep the fast marker.
- FHD_Ultra0 is preserved unchanged.

PURPLE_CARGO
- All purple sets 11, 12, 13, 14, 15 are included (25 pieces total).
- NORMAL remains normal GTU/shop progression.

IMPORTANT
Install only one behavior at a time. To return from PURPLE_CARGO to NORMAL, reinstall CORE_NORMAL/Mods/FHD_MODS/FHD_SET/CFG/Rus/Lang.dat.
