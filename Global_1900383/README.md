<h2>Global_1900383</h2>
- The only thing I've researched on this global is that I can disable horse whistling every frame.

```
*getGlobalPtr(1900383 + 316) = 2; // Disables horse whistling every frame
```

# Snippets from the scripts (b1436)
- long_update.ysc
- Line 48353 - func_1522
```
iVar7 = ATTRIBUTE::GET_ATTRIBUTE_RANK(bVar5, 7);
Global_40.f_1095.f_1[iParam0 /*436*/].f_372 = iVar7;
PED::_0xA69899995997A63B(bVar5, iVar7);
// Stuff from previous function ^^^^^^

void func_1522(int iParam0)
{
	Global_1900383.f_316 = (Global_1900383.f_316 || iParam0);
}
```