<h2>g_playerData</h2>

```
struct g_playerData
{
	BOOL bPlayerDead = *getGlobalPtr(BASE + 12);
	BOOL _inRespawnSequence = *getGlobalPtr(BASE + 4); // Guessed name - True until player moves after respawning
	Hash _currentWeapon = *getGlobalPtr(BASE + 44); // Guessed name
	Hash _lastWeaponFired = *getGlobalPtr(BASE + 46); // Guessed name

	// Taken from the scripts - not actually in g_playerData
	// See enum _ePlayerFlags
	void setPlayerFlag(int flag)
	{
		flag /= 2; // Not in scripts, modified by me. TODO: Fix this in the enums instead
		*getGlobalPtr(BASE) = (*getGlobalPtr(BASE) | flag);
	}

	// Taken from the scripts - not actually in g_playerData
	// See enum _ePlayerFlags
	void clearPlayerFlag(int flag)
	{
		flag /= 2; // Not in scripts, modified by me. TODO: Fix this in the enums instead
		*getGlobalPtr(BASE) = (*getGlobalPtr(BASE) - (*getGlobalPtr(BASE) & flag));
	}

private:
	static const int BASE = 1935630;
};
```

#

```
enum _ePlayerFlags
{
	PF_ALL_PLAYER_FLAGS = -1,
	PF_NONE = 0,
	PF_MISSION_STARTED = (1 << 0),
	PF_MINIGAME_STARTED = (1 << 1),
	PF_JOB_STARTED = (1 << 2),
	PF_RCM_STARTED = (1 << 3),
	PF_PROCMISSION_STARTED = (1 << 4),
	PF_FETCH_STARTED = (1 << 5),
	PF_HIDEOUT_STARTED = (1 << 6),
	PF_SPECIAL_PED_STARTED = (1 << 7),
	PF_LOCATION_STARTED = (1 << 8),
	PF_COMPANION_ACTIVITY_STARTED = (1 << 9),
	PF_MC_LOBBY_STARTED = (1 << 10),
	PF_CONVO_VIG_DEBUG_STARTED = (1 << 11),
	PF_MISSION_RETRY = (1 << 12),
	PF_RESPAWNING = (1 << 13),
	PF_RECALC_GAME_COMPLETE = (1 << 14),
	PF_FAST_TRAVELLING = (1 << 15),
	PF_MISSION_LOCKED_IN = (1 << 16),
	PF_ANYTHING_JUST_STARTED = 81919, // Not sure why this one is 81919
	PF_ALLOW_HORSE_SPRINT_IN_CITIES = (1 << 17),
	PF_LOADING_FROM_SAVE = (1 << 18),
	PF_DISABLE_MOVE_LIMIT_INDOORS = (1 << 19),
	PF_MISSION_INTRO_CUT_SKIPPED = (1 << 20),
	PF_BLOCK_DO_MISSION_NOW = (1 << 21),
	PF_IN_MISSION_COMBAT = (1 << 22),
	PF_LAW_DISABLED = (1 << 23),
	PF_DOING_PRONGHORN_TIMELAPSE = (1 << 24),
};
```

# Snippets from the scripts (b1436)
- short_update.ysc
- Line 129013 - func_4340
```
case 1:
	Global_1935630.f_30 = PLAYER::_0x72AD59F7B7FB6E24(PLAYER::PLAYER_ID(), 4000);
	if (!Global_1935630.f_30)
	{
		if (Global_1935630.f_44 == joaat("WEAPON_LASSO"))
		{
			Global_1935630.f_30 = PED::_GET_LASSO_TARGET(Global_35) != 0;
		}
	}
	break;
```