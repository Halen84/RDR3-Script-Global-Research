<h2>g_skinningData</h2>

```
struct g_skinningData
{
	int state = *getGlobalPtr(BASE);
	int eHeldInventoryItem = *getGlobalPtr(BASE + 15);
private:
	static const int BASE = 36560;
};
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
