<h2>g_savedGlobals</h2>

```
struct g_savedGlobals
{
	BOOL bGameInitialized = *getGlobalPtr(BASE); // Global_40 + 0 or 1
	Hash eCurrentBaitEquipped = *getGlobalPtr(BASE + 11184 + 1); // Global_40.f_11184[0]

	// int PLAYER_SADDLE_SET_HORSE_SLOT = *getGlobalPtr(BASE + 1095 + 3054); // enum _ePlayerHorseSlot
	// int PLAYER_SADDLE_SET_STATE = *getGlobalPtr(BASE + 1095 + 3054 + 1); // enum _ePlayerHorseSaddleState
private:
	static const int BASE = 40;
};
```

# Player Stats
- g_savedGlobals also holds lots of player stats. Not all are known, but here's quite a bit
- They are stored in (g_savedGlobals + 11095)
```
float GetHealthCoreAmount() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 1)); }
int GetHealthExperience() { return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 12)); } // Actual datatype is float?
float GetHealthOverpowerTime() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 5)); }

float GetStaminaCoreAmount() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 2)); }
int GetStaminaExperience() { return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 13)); } // Actual datatype is float?
float GetStaminaOverpowerTime() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 7)); }

float GetDeadeyeCoreAmount() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 3)); }
int GetDeadeyeExperience() { return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 14)); } // Actual datatype is float?
float GetDeadeyeOverpowerTime() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 9)); }

float GetStaminaDrainRate() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 62)); } // Player --> Arthur --> General --> Weight
float GetDamageTakenRate() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 45)); } // Player --> Arthur --> General --> Weight
float GetWeightCoreDrainRate() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 25)); }
float GetUNKDrunknessGlobal() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 22)); } // Not exactly sure what this returns, but it's related to drunk/soberness
int GetHonorGlobal() { return *getGlobalPtr(40 + 11095 + 35); }
float GetPlayerCleanliness() { return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 28)); } // -100.0f if fully clean
int GetTotalNumberOfItemsConsumed() { return *getGlobalPtr(40 + 11095 + 66); } // Total number of things ate/drank
Hash GetPlayerModel() { return *getGlobalPtr(40 + 39); } // Returns PLAYER_ZERO if Arthur, or PLAYER_THREE if John
```

# Horse Stats
- g_savedGlobals also holds horse stats. Again, not all are known.
```
// These 3 funcs don't actually change horse, only its stats in the pause menu
void SetHorseModelStat(Hash model)
{
	//Global_40.f_1095.f_1[iParam0 /*436*/].f_9
	*getGlobalPtr(40 + 1095 + 1 + 1 + PH_SLOT_PRIMARY + 9) = model;
}

void SetHorseBreedStat(Hash breed)
{
	//Global_40.f_1095.f_1[iParam0 /*436*/].f_8
	*getGlobalPtr(40 + 1095 + 1 + 1 + PH_SLOT_PRIMARY + 8) = breed;
}

void SetHorseGenderStat(int gender)
{
	if (gender < 0 || gender > 2) { gender = 2; }
	// 0 = Unknown, 1 = Male, 2 = Female
	//Global_40.f_1095.f_1[iParam0 /*436*/].f_10
	*getGlobalPtr(40 + 1095 + 1 + 1 + PH_SLOT_PRIMARY + 10) = gender;
}
```


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
