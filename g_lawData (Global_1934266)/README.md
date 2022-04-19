<h2>g_lawData</h2>

```
struct g_lawData
{
	struct wantedUIData // BASE + 78
	{
		int eCurrentUIState = *getGlobalPtr(BASE + 78 + 59);
	};
	// Global_1934266.f_78.f_62 = g_lawData.wantedUIData.??? (is a SET value for eCurrentUIState?)
private:
	static const int BASE = 1934266;
};
```

#
```
enum _eCurrentUIState
{
	WANTED_UI_INVALID = -1,
	WANTED_UI_OFF,
	WANTED_UI_WITNESSED,
	WANTED_UI_LAW_INCIDENT_STARTED,
	WANTED_UI_LAW_INVESTIGATING,
	WANTED_UI_INTERROGATION,
	WANTED_UI_IDENTIFICATION,
	WANTED_UI_HOT_PURSUIT,
	WANTED_UI_EVASION,
	WANTED_UI_COOLDOWN,
	WANTED_UI_BOUNTY_POSTED,
	WANTED_UI_BOUNTY_HUNTERS,
};
```

# Snippets from the scripts (b1436)
- TODO
- Line 6079 - func_180
```
else if (bParam0)
{
	bVar1 = func_287(PLAYER::PLAYER_ID());
}
if (Global_1934266.f_78.f_62 != -1)
{
	if (Global_1934266.f_78.f_59 != Global_1934266.f_78.f_62)
	{
		func_799(Global_1934266.f_78.f_62);
	}
}
switch (Global_1934266.f_78.f_59)
```
