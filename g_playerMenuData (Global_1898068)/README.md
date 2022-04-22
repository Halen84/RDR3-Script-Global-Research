<h2>g_playerMenuData</h2>

```
struct g_playerMenuData
{
	BOOL bVisible = *getGlobalPtr(BASE);
	BOOL bEnabled = *getGlobalPtr(BASE + 1);
	BOOL _bClosed = *getGlobalPtr(BASE + 3);
private:
	static const int BASE = 1898068;
};
```

# Snippets from the scripts (b1436)
- short_update.ysc
- Line 7124
```
void func_205(bool bParam0)
{
	if (bParam0)
	{
		if (!Global_1898068)
		{
			Global_1898068 = bParam0;
		}
	}
	else if (Global_1898068)
	{
		Global_1898068 = bParam0;
	}
}
```