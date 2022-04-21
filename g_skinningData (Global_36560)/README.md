<h2>g_skinningData</h2>

```
struct g_skinningData
{
	int state = *getGlobalPtr(BASE); // enum _eSkinningState
	Entity _skinningEntity = *getGlobalPtr(BASE + 1); // Returns current entity you are skinning
	int _skinningEntityRarityLevel = *getGlobalPtr(BASE + 2); // Returns enum eAnimalRarityLevel (i only ever got 3)
	int _skinningFlag = *getGlobalPtr(BASE + 3);
	int eHeldInventoryItem = *getGlobalPtr(BASE + 15);
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

# Snippets from the scripts (b1436)
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
