<h2>g_skinningData</h2>

```
struct g_skinningData
{
	int state = *getGlobalPtr(BASE + 0); // enum _eSkinningState
	Entity _skinningEntity = *getGlobalPtr(BASE + 1); // The current entity you are skinning
	int _skinningRarityLevel = *getGlobalPtr(BASE + 2); // Returns enum eAnimalRarityLevel
	int _skinningFlags = *getGlobalPtr(BASE + 3);
	int eHeldInventoryItem = *getGlobalPtr(BASE + 15);
	Hash _animalCarcassPeltType = *getGlobalPtr(BASE + 16);
	BOOL unk = *getGlobalPtr(BASE + 17); // True if SCRIPT_TASK_LOOT_ENTITY is active on player, and g_skinningData.state is SKINNING_STATE_GIVE_PLAYER_RESULTS
	BOOL _isSmallAnimalPeltPerfect = *getGlobalPtr(BASE + 19); // True if pelt is perfect of animals: rabbit, opossum, skunk, beaver
private:
	static const int BASE = 36560;
};
```

#
```
enum _eSkinningState
{
	SKINNING_STATE_WAIT,
	SKINNING_STATE_CHECK_VALID_TARGET,
	SKINNING_STATE_INIT,
	SKINNING_STATE_UPDATE,
	SKINNING_STATE_CALCULATE_RESULTS,
	SKINNING_STATE_GIVE_PLAYER_RESULTS,
	SKINNING_STATE_CLEANUP,
	SKINNING_STATE_INVALID,
}
```

# Snippets from the scripts (b1491)
- player_camp.ysc
- Line 4519 - func_107
```
Global_1911914.f_1577 = 0;
if (func_62(Global_35, joaat("SCRIPT_TASK_LOOT_ENTITY")) && Global_36560 == 5)
{
	func_342(1);
}
func_343(Global_35, 1, 1);
TASK::CLEAR_PED_TASKS_IMMEDIATELY(Global_35, false, true);
if (ENTITY::DOES_ENTITY_EXIST(uParam0->f_248))
{
	PED::_0x9851DE7AEC10B4E1(ENTITY::GET_ENTITY_COORDS(uParam0->f_248, true, false), 0.5f, 1, 1);
}
```
