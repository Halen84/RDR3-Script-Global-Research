<h2>g_worldStates</h2>

```
struct g_worldStates
{
	BOOL bForceWorldStateUpdate = *getGlobalPtr(BASE + 272);
	int iCurPopBudget = *getGlobalPtr(BASE + 286);
private:
	static const int BASE = 1934765;
};
```

# Snippets from the scripts (b1436)
- long_update.ysc
- Line 34934 - func_1148
```
fVar3 = 15f;
MISC::_GET_FORCED_WEATHER(&uVar4, &uVar5);
if (func_1794(21, 4))
{
	if (func_1548(func_538()) < 22 && func_1567(func_538()) >= 30)
	{
		if (Global_1934765.f_68 != joaat("SNOW"))
		{
			Global_1934765.f_68 = joaat("SNOW");
			MISC::SET_WEATHER_TYPE(joaat("SNOW"), false, true, true, (fVar2 * IntToFloat((60 - func_1567(func_538())))), false);
		}
	}
	else if (Global_1934765.f_68 != joaat("BLIZZARD"))
	{
		Global_1934765.f_68 = joaat("BLIZZARD");
		MISC::SET_WEATHER_TYPE(joaat("BLIZZARD"), false, true, true, fVar3, false);
	}
}
```