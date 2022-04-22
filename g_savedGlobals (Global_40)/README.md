<h2>g_savedGlobals</h2>

```
struct g_savedGlobals
{
	BOOL bGameInitialized = *getGlobalPtr(BASE); // Global_40 + 0 or 1
	Hash eCurrentBaitEquipped = *getGlobalPtr(BASE + 11184 + 1); // Global_40.f_11184[0]
	int _localWorldStateBitfields = *getGlobalPtr(BASE + 283 + 1); // See Examples.md for more info -- Global_40.f_283[iVar1]

	// int PLAYER_SADDLE_SET_HORSE_SLOT = *getGlobalPtr(BASE + 1095 + 3054); // enum _ePlayerHorseSlot
	// int PLAYER_SADDLE_SET_STATE = *getGlobalPtr(BASE + 1095 + 3054 + 1); // enum _ePlayerHorseSaddleState
private:
	static const int BASE = 40;
};
```

# Player Stats
- g_savedGlobals contains lots of information about player stats. [Some examples](https://github.com/Halen84/RDR3-Script-Global-Research/blob/master/g_savedGlobals%20(Global_40)/Examples.md)

# Horse Stats
- g_savedGlobals also contain some horse stats. The only known globals are ones that only affect pause menu stats. [Some examples](https://github.com/Halen84/RDR3-Script-Global-Research/blob/master/g_savedGlobals%20(Global_40)/Examples.md)

# Local World State Bitfields
- g_savedGlobals can also set local world state bitfields. [Example](https://github.com/Halen84/RDR3-Script-Global-Research/blob/master/g_savedGlobals%20(Global_40)/Examples.md)

# Enums
```
enum _ePlayerHorseSlot // eSlot
{
	PH_SLOT_INVALID = -1,
	PH_SLOT_PRIMARY,
	PH_SLOT_TEMPORARY,
	PH_SLOT_STABLE_1,
	PH_SLOT_STABLE_2,
	PH_SLOT_STABLE_3,
	PH_SLOT_LOST,
	PH_SLOT_PRE_TEMP,
	PH_SLOT_CURRENT
};
```
#
```
enum _ePlayerHorseSaddleState
{
	PSS_EQUIPPED,
	PSS_CARRIED,
	PSS_DROPPED,
	PSS_IN_SHOP
};
```

# Snippets from the scripts (b1436)
- event_area_appleseed_stg4.ysc
- Line 30803
```
int func_1022()
{
	if (Global_40.f_11095.f_35 <= -320)
	{
		return 1;
	}
	else if (Global_40.f_11095.f_35 <= -280)
	{
		return 2;
	}
	else if (Global_40.f_11095.f_35 <= -240)
	{
		return 3;
	}
	else if (Global_40.f_11095.f_35 <= -200)
	{
		return 4;
	}
	else if (Global_40.f_11095.f_35 <= -160)
	{
		return 5;
	}
	else if (Global_40.f_11095.f_35 <= -120)
	{
		return 6;
	}
	else if (Global_40.f_11095.f_35 <= -80)
	{
		return 7;
	}
	else if (Global_40.f_11095.f_35 < 0)
	{
		return 8;
	}
	else if (Global_40.f_11095.f_35 <= 40)
	{
		return 9;
	}
	else if (Global_40.f_11095.f_35 >= 320)
	{
		return 16;
	}
	else if (Global_40.f_11095.f_35 >= 280)
	{
		return 15;
	}
	else if (Global_40.f_11095.f_35 >= 240)
	{
		return 14;
	}
	else if (Global_40.f_11095.f_35 >= 200)
	{
		return 13;
	}
	else if (Global_40.f_11095.f_35 >= 160)
	{
		return 12;
	}
	else if (Global_40.f_11095.f_35 >= 120)
	{
		return 11;
	}
	else if (Global_40.f_11095.f_35 >= 80)
	{
		return 10;
	}
	return 9;
}
```
