<h2>g_HudDataUnsaved</h2>

```
struct g_HudDataUnsaved
{
	BOOL bShowingInfoCard = *getGlobalPtr(BASE + 23);
	BOOL _bShowingWeaponWheel = *getGlobalPtr(BASE + 10);
	BOOL _bShowingItemWheel = *getGlobalPtr(BASE + 11);
	BOOL _bShowingHorseWheel = *getGlobalPtr(BASE + 12);
	BOOL _bShowingFishingWheel = *getGlobalPtr(BASE + 13);
	BOOL bIsHUDActive = *getGlobalPtr(BASE + 19);
	int iHudCurrentPage = *getGlobalPtr(BASE + 5);
	int eHighlightedItem = *getGlobalPtr(BASE + 30); // Incorrect?
	int _lastConsumableItemUsed = *getGlobalPtr(BASE + 31);
	int _lastNonConsumableItemUsed = *getGlobalPtr(BASE + 32);
	Hash _currentSelectedItem = *getGlobalPtr(BASE + 9633);
	
	struct dataUsability // BASE + 70
	{
		
	}dataUsability;
	
private:
	static const int BASE = 1935496;
};
```
# Snippets from the scripts (b1436)
- short_update.ysc
- Line 5715 - func_167
```
case 35:
	Global_1935496.f_23 = !Global_1935496.f_23;
	Global_1935496.f_6 = MISC::GET_GAME_TIMER();
	PLAYER::_0xDC68829BB3F37023(PLAYER::GET_PLAYER_INDEX(), Global_1935496.f_23);
	break;
```