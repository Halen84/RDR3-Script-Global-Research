<h2>Global_1900383</h2>
- This global contains data about your horses

```
struct Global_1900383
{
	Ped _currentSaddleHorse = *getGlobalPtr(BASE + 1);
	Vector3 _lastHitchCoords = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 1 + PH_SLOT_PRIMARY + 28)); // Global_1900383[iParam0 /*45*/].f_28
	int eBodyWeightOutfit = *getGlobalPtr(BASE + 1 + PH_SLOT_PRIMARY + 1); // Could be a hash? -- Global_1900383[iParam0 /*45*/].f_1
	Object _saddleObject = *getGlobalPtr(BASE + 393);

	struct _whistleData // Guessed name - BASE + 378
	{
		int _eHorseWhistleState = *getGlobalPtr(BASE + 378); // enum _eHorseWhistleState
		int eWhistleType = *getGlobalPtr(BASE + 378 + 9); // enum eWhistleType
		Hash eAudPedWhistleType = *getGlobalPtr(BASE + 378 + 10); // enum _eAudPedWhistleType
		int _iLastWhistleTime = *getGlobalPtr(BASE + 378 + 11);
	};

private:
	static const int BASE = 1900383;
};
```
#
```
*getGlobalPtr(1900383 + 316) = 2; // Disables horse whistling every frame
```

# Enums
```
enum _eHorseWhistleState
{
	HWS_INVALID = -1,
	HWS_INIT,
	HWS_RESET_WHISTLE,
	HWS_WAITING_FOR_WHISTLE,
	HWS_WHISTLE_DETECTED,
	HWS_CHECK_FAIL_CASES,
	HWS_HANDLE_RESPONSE
};

enum _eAudPedWhistleType : Hash
{
	WHISTLEHORSERESPONSIVE = 4222757766,
	WHISTLEHORSETALK = 640210656,
	WHISTLEHORSELONG = 869278708,
	WHISTLEHORSEDOUBLE = 1051485804,
	WHISTLEHORSESHORT = 1704957293,
	WHISTLEANIMALNOISES = 1807639261
};
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