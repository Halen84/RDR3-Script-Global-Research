## g_worldStates - b1491
-  Base Index: 1934765
###

| Name                                    | Index      | Description                |
|-----------------------------------------|------------|----------------------------|
| BOOL bIgnoreInteriorEntitySetConditions | BASE + 271 |                            |
| BOOL bForceWorldStateUpdate             | BASE + 272 | Force a world state update |
| int iCurPopBudget                       | BASE + 286 | Current Population Budget  |

# Snippets from the scripts (b1491)
- long_update.ysc
- Line 34923 - func_1148
```cpp
		if (Global_1897952.f_40)
		{
			if (Global_1934765.f_68 != joaat("BLIZZARD") && !func_1794(6, 19))
			{
				Global_1934765.f_68 = joaat("BLIZZARD");
				MISC::_SET_WEATHER_TYPE_2(joaat("BLIZZARD"), 11, 0, 0, false);
			}
			return;
		}
		fVar3 = 15.0f;
		MISC::_GET_FORCED_WEATHER(&uVar4, &uVar5);
		if (func_1794(21, 4))
		{
			if (func_1548(func_538()) < 22 && func_1567(func_538()) >= 30)
			{
				if (Global_1934765.f_68 != joaat("SNOW"))
				{
					Global_1934765.f_68 = joaat("SNOW");
					MISC::SET_WEATHER_TYPE(joaat("SNOW"), false, true, true, (fVar2 * (float)(60 - func_1567(func_538()))), false);
				}
			}
			else if (Global_1934765.f_68 != joaat("BLIZZARD"))
			{
				Global_1934765.f_68 = joaat("BLIZZARD");
				MISC::SET_WEATHER_TYPE(joaat("BLIZZARD"), false, true, true, fVar3, false);
			}
		}
```