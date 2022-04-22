<h2>g_autosaveData</h2>

```
struct g_autosaveData
{
	Hash _savegameType = *getGlobalPtr(BASE); // enum eSavegameType -- According to the scripts, this makes a "request" of some sort -- TODO: Test this
	int _saveFlag = *getGlobalPtr(BASE + 2);
	Vector3 _savegameCoords = (Vector3)*getGlobalPtr(BASE + 3); // In the scripts, this pointer just gets set to the players current position
private:
	static const int BASE = 0;
};
```

# Snippets from the scripts (b1436)
- pause_menu.ysc
- Line 1052
```
void func_31()
{
	Global_0.f_6 = MISC::GET_GAME_TIMER();
	Global_0.f_3 = { Global_36 };
	func_91(&Global_0);
}
```