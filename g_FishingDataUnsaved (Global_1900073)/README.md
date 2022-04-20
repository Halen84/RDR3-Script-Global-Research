<h2>g_FishingDataUnsaved</h2>

```
struct g_FishingDataUnsaved
{
	BOOL bAllowEquipRod = *getGlobalPtr(BASE + 17);
	BOOL bDisableFishingRodInwheel = *getGlobalPtr(BASE + 18);
	int _eFishType = *getGlobalPtr(BASE + 37); // ???
	int _fish_weight = *getGlobalPtr(BASE + 38); // ???
	//Hash eBaitSelectedInWheel = *getGlobalPtr(BASE + 153); // Incorrect? Needs more testing. enum _eBaitSelectedInWheel
	int iFishCaughtThisGameBoot = *getGlobalPtr(BASE + 220 + 1); // Global_1900073.f_220[0]
	int iFishCaughtThisSession = *getGlobalPtr(BASE + 215 + 1); // Global_1900073.f_215[0]
private:
	static const int BASE = 1900073;
};
```

#

```
enum _eBaitSelectedInWheel : Hash
{
	UPGRADE_FSH_BAIT_NONE = 1309979101,
	UPGRADE_FSH_BAIT_BREAD = 1059426360,
	UPGRADE_FSH_BAIT_CHEESE = 1380607804,
	UPGRADE_FSH_BAIT_CORN = 488496242,
	UPGRADE_FSH_BAIT_CRAYFISH = 149706141,
	UPGRADE_FSH_BAIT_CRICKET = 2541147957,
	UPGRADE_FSH_BAIT_LEG_LURE_LAKE = 1815744868,
	UPGRADE_FSH_BAIT_LEG_LURE_RIVER = 1334018438,
	UPGRADE_FSH_BAIT_LEG_LURE_SWAMP = 1055480217,
	UPGRADE_FSH_BAIT_LURE_LAKE = 3316807643,
	UPGRADE_FSH_BAIT_LURE_RIVER = 2100131425,
	UPGRADE_FSH_BAIT_LURE_SWAMP = 2253585192,
	UPGRADE_FSH_BAIT_SPINNER_FRESHWATER_LEG = 2378382336,
	UPGRADE_FSH_BAIT_WORM = 2767674267,
}
```

# Snippets from the scripts (b1436)
- fishing_core.ysc
- Line 13483
```
void func_525(var uParam0, var uParam1, var uParam2)
{
	if (Global_1900073.f_153 != 0)
	{
		if (Global_1900073.f_153 != Global_40.f_11184[0] && func_393(Global_1900073.f_153))
		{
			func_309(uParam0, uParam1, 0, Global_1900073.f_153, 1, 0);
			func_533(uParam0, uParam1, uParam2, 0, 2);
		}
		Global_1900073.f_153 = 0;
	}
}
```