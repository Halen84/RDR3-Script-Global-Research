<h2>g_satchelData</h2>

```
struct g_satchelData
{
	BOOL _bVisible = *getGlobalPtr(BASE + 1);
	BOOL bEnabled = *getGlobalPtr(BASE + 2);
	BOOL bDisabledThisFrame = *getGlobalPtr(BASE + 6);
	BOOL bListItemFocused = *getGlobalPtr(BASE + 7);
	BOOL bReopenFromInspect = *getGlobalPtr(BASE + 9);
	int eCurrItem = *getGlobalPtr(BASE + 10190);
	int iCurrFolder = *getGlobalPtr(BASE + 10188);
	int _eCurrCategory = *getGlobalPtr(BASE + 10189);
	int dse_CategoryIndex = *getGlobalPtr(BASE + 10203);
	int iNumListItems = *getGlobalPtr(BASE + 10194);

	struct sFolderData // BASE + 19
	{
		int iNumItemsInCategory = *getGlobalPtr(BASE + 19 + 203);
	};

private:
	static const int BASE = 1935689;
};
```

# Snippets from the scripts (b1436)
- short_update.ysc
- Line 963 - func_25
```
if (bVar1 && !Global_1935689.f_1)
{
	if (func_200(0) != 4)
	{
		if (!SCRIPTS::IS_THREAD_ACTIVE(Global_1935689.f_13, false))
		{
			SCRIPTS::REQUEST_SCRIPT("satchel");
			Global_1935689.f_1 = 1;
			Global_1935689 = 0;
		}
	}
	else if (Global_1935689 == 1)
	{
		Global_1935689 = 0;
	}
}
else if (Global_1935689.f_1 && !SCRIPTS::IS_THREAD_ACTIVE(Global_1935689.f_13, false))
{
	if (SCRIPTS::HAS_SCRIPT_LOADED("satchel"))
	{
		Global_1935689.f_13 = SCRIPTS::START_NEW_SCRIPT("satchel", 1024);
		SCRIPTS::SET_SCRIPT_AS_NO_LONGER_NEEDED("satchel");
	}
}
```