<h2>g_herbOverrideUnsaved</h2>

```
struct g_herbOverrideUnsaved
{
	BOOL bUseOverrides = *getGlobalPtr(BASE + 133);

private:
	static const int BASE = 1913678;
};
```

# Snippets from the scripts (b1436)
- herb_acunas_star_orchid.ysc
- Line 2320
```
int func_99(int iParam0)
{
	var uVar0;
	int iVar45;
	bool bVar46;

	if (Global_1913678.f_133)
	{
		uVar0 = 44;
		iVar45 = 0;
		while (iVar45 <= 1)
		{
			if (Global_1913678[iParam0 /*3*/][iVar45] != 0)
			{
				bVar46 = true;
			}
			else
			{
				iVar45++;
			}
		}
		if (!bVar46)
		{
			return iParam0;
		}
		func_181(&uVar0, 44, 1);
		iVar45 = 0;
		while (iVar45 <= 43)
		{
			if (iVar45 == iParam0)
			{
			}
			else if (func_182(&(Global_1913678[iParam0 /*3*/]), iVar45, 44))
			{
				return iVar45;
			}
			iVar45++;
		}
		return iParam0;
	}
	return iParam0;
}
```