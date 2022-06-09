Global Name|Address|Datatype
----------- | ----------------- | ----
g_pedPlayer | *getGlobalPtr(35) - (33 in older versions) | Ped
g_bIsCutscenePlaying | *getGlobalPtr(16) - (13 in older versions) | BOOL
g_pendingUIDListSize | *getGlobalPtr(1898330) | int
g_bDocumentSuppressReadPrompt | *getGlobalPtr(36635) | BOOL
g_bForceHandheldView | *getGlobalPtr(1357508) | BOOL
g_bForceCameraAway | *getGlobalPtr(1357509) | BOOL
g_iLastUIDCompletedTime | *getGlobalPtr(1898438) | int
g_iCurrentPlayingCutscene | *getGlobalPtr(43800) | AnimScene
g_eHerbMode | *getGlobalPtr(36580) | int
g_bWipeMPSaveData | *getGlobalPtr(30) | BOOL
g_bMissionControllerActive | *getGlobalPtr(1048577) | BOOL


# Other Globals
Global|Description
-------| -----------------
int Global_20 | Save game event?
int Global_21 | Some autosave flag?
Vector3 _g_vPlayer (Global_36) | Current Player Coordinates - (34 in older versions)
int _g_playerHonor (Global_11170) | Current Player Honor (Same as g_savedGlobals + 11095 + 35)
Hash Global_20891 | Last item bought in shops

#
```
enum _eHerbMode
{
	HERB_MODE_ON,
	HERB_MODE_OFF,
	HERB_MODE_VISUAL_ONLY,
	HERB_MODE_DISABLE_EAT,
	HERB_MODE_BLIPPED,
	HERB_MODE_INVALID
}
```