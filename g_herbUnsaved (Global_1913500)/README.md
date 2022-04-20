<h2>g_herbUnsaved</h2>

```
struct g_herbUnsaved
{
	// g_herbUnsaved[", Global_1913677, "].vLastFakePicked = Global_1913500[Global_1913677 /*4*/].f_1
	Vector3 vLastFakePicked = (Vector3)*getGlobalPtr(BASE + 1 + 1913677 + 1);
private:
	static const int BASE = 1913500; // or 1913677?
};
```

# Snippets from the scripts (b1436)
- herbal_plants.ysc
- Line 216
```
void func_13(vector3 vParam0)
{
	Global_1913677 = (Global_1913677 % 10);
	Global_1913500[Global_1913677 /*4*/].f_1 = { vParam0 };
	Global_1913677++;
}
```