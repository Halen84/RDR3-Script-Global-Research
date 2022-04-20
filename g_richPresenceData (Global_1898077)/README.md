<h2>g_richPresenceData</h2>

```
struct g_richPresenceData
{
	int ePresenceType = *getGlobalPtr(BASE + 1); // enum _ePresenceType
private:
	static const int BASE = 1898077;
};
```

#
```
enum _ePresenceType
{
	PRESENCE_IDLE,
	PRESENCE_MATCHMAKING,
	PRESENCE_STORY_CHAPTER,
	PRESENCE_ACTIVITIES,
	PRESENCE_AMBIENT,
	PRESENCE_STRANGER
};
```

# Snippets from the scripts
- fishing_core.ysc
- Line 4902
```
void func_159(int iParam0)
{
	int iVar0;
	int iVar1;

	if ((Global_1898077.f_1 == 2 || Global_1898077.f_1 == 5) || Global_1898077.f_1 == 3)
	{
		return;
	}
	iVar0 = 0;
	if (func_26() != -1)
	{
		iVar0 = 1;
	}
	iVar1 = func_377(Global_1894899.f_2);
	Global_1898077.f_1 = 3;
	Global_1898077.f_2 = 0;
	Global_1898077.f_7 = iVar0;
	Global_1898077.f_8 = iParam0;
	Global_1898077.f_9 = iVar1;
	func_378(Global_1898077.f_7, Global_1898077.f_8, Global_1898077.f_9);
}
```