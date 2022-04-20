<h2>g_DrinkData</h2>

```
struct g_DrinkData
{
	float fDrinkPotencyMeter = *getGlobalPtr(BASE + 9);

	struct sFXData // BASE + 12
	{
		float fCurrentDrunkenness = *getGlobalPtr(BASE + 12 + 1);
	};
private:
	static const int BASE = 1935436;
};
```

# Snippets from the scripts (b1436)
- long_update.ysc
- Line 12617 - func_393
```
fVar0 = ((Global_1935436.f_12.f_1 * 200f) - 100f);
func_1055(fVar0);
if (!Global_1935436.f_12.f_4)
{
	if (Global_1935436 == 2)
	{
		Global_1935436.f_12.f_4 = 1;
		if (func_388())
		{
			AUDIO::SET_AMBIENT_VOICE_NAME(Global_35, "ARTHUR_WASTED");
		}
		else
		{
			AUDIO::SET_AMBIENT_VOICE_NAME(Global_35, "JOHN_PLAYER_WASTED");
		}
	}
}
```