# Examples
```
// Flags: See enum _ePlayerFlags

void setPlayerFlag(int flag)
{
	flag /= 2; // Not in scripts, modified by me. TODO: Fix this in the enums instead
	*getGlobalPtr(BASE) = (*getGlobalPtr(BASE) | flag);
}

void clearPlayerFlag(int flag)
{
	flag /= 2; // Not in scripts, modified by me. TODO: Fix this in the enums instead
	*getGlobalPtr(BASE) = (*getGlobalPtr(BASE) - (*getGlobalPtr(BASE) & flag));
}


// Must call every frame to take effect
// Gives ability to run indoors
setPlayerFlag(PF_DISABLE_MOVE_LIMIT_INDOORS);

// And to remove this flag:
clearPlayerFlag(PF_DISABLE_MOVE_LIMIT_INDOORS);
```