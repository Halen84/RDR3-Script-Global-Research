# Examples for g_savedGlobals

# Player Stats
- g_savedGlobals also holds lots of player stats. Not all are known, but here's quite a bit
- They are stored in (g_savedGlobals + 11095)
```
// Health Stats
float GetHealthCoreAmount()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 1));
}
int GetHealthExperience()
{
	return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 12));
}
float GetHealthOverpowerTime()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 5));
}


// Stamina Stats
float GetStaminaCoreAmount()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 2));
}
int GetStaminaExperience()
{
	return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 13));
}
float GetStaminaOverpowerTime()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 7));
}
float GetStaminaDrainRate()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 62)); // Player --> Arthur --> General --> Weight
}


// Deadeye Stats
float GetDeadeyeCoreAmount()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 3));
}
int GetDeadeyeExperience()
{
	return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 14));
}
float GetDeadeyeOverpowerTime()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 9));
}


// Misc stats
float GetDamageTakenRate()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 45)); // Player --> Arthur --> General --> Weight
}
float GetWeightCoreDrainRate() // ?
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 25));
}
float GetUNKDrunknessGlobal()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 22)); // Not exactly sure what this returns, but it's related to drunk/soberness
}
int GetPlayerHonor()
{
	return *getGlobalPtr(40 + 11095 + 35);
}
float GetPlayerCleanliness()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 28)); // -100.0f if fully clean
}
int GetTotalNumberOfItemsConsumed()
{
	return *getGlobalPtr(40 + 11095 + 66); // Total number of things ate/drank
}
Hash GetPlayerModel()
{
	return *getGlobalPtr(40 + 39);
}
```

# Horse Stats
- g_savedGlobals also contains some horse stats. Again, not all are known.
- Note: These ones that I found below only change the pause menu stats, and not its actual stats.
- Some of them are stored in (g_savedGlobals + 1095 + 1 + 1 + _ePlayerHorseSlot + x)
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