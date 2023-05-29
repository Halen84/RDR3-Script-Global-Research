## g_satchelData - b1491
-  Base Index: 1935689
###

| Name                            | Index       | Description                                         |
|---------------------------------|-------------|-----------------------------------------------------|
| int \_iActiveState              | BASE + 0    | Satchel active state                                |
| BOOL \_bVisible                 | BASE + 1    | Is the satchel is currently visible/open            |
| BOOL bEnabled                   | BASE + 2    | Is the satchel enabled                              |
| BOOL \_bJustOpened              | BASE + 5    |                                                     |
| BOOL bDisabledThisFrame         | BASE + 6    | Is the satchel disabled for this frame only         |
| BOOL bListItemFocused           | BASE + 7    | Is a list item currently opened in the satchel      |
| BOOL \_bDisableItemUse          | BASE + 8    | Disable player from using items in the satchel      |
| BOOL bReopenFromInspect         | BASE + 9    |                                                     |
| int \_iCurrFolderItemIndex      | BASE + 14   |                                                     |
| int \_iCategoryIndex            | BASE + 9417 |                                                     |
| Hash iCurrFolder                | BASE + 9438 | Hash of the current satchel folder                  |
| Hash eCurrCategory              | BASE + 9439 | Hash of the current satchel category                |
| Hash eCurrItem                  | BASE + 9440 | Hash of the current selected item in the satchel    |
| int iNumItemsInCategory         | BASE + 9443 | Number of items in the current category (iNumItems) |
| int iNumListItems               | BASE + 9444 | Number of list items in the focused list item       |
| int \_iFocusedItemIndex         | BASE + 9445 | Current selected index                              |
| int dse_CategoryCount           | BASE + 9451 | Use on <b>DATABINDING_READ_INT</b>                  |
| int dse_DefaultCategoryIndex    | BASE + 9452 | Use on <b>DATABINDING_READ_INT</b>                  |
| int dse_CategoryIndex           | BASE + 9453 | Use on <b>DATABINDING_READ_INT</b>                  |
| int dse_Name                    | BASE + 9454 | Use on <b>\_DATABINDING_READ_HASH</b>               |
| int dse_Description             | BASE + 9455 | Use on <b>\_DATABINDING_READ_HASH</b>               |
| int dse_Price                   | BASE + 9456 | Use on <b>\_DATABINDING_READ_DATA_STRING</b>        |
| int dse_PriceLabel              | BASE + 9457 | Use on <b>\_DATABINDING_READ_DATA_STRING</b>        |
| int dse_Category                | BASE + 9458 | Use on <b>\_DATABINDING_READ_HASH</b>               |
| int dse_IndexDescription        | BASE + 9459 | Use on <b>\_DATABINDING_READ_DATA_STRING</b>        |
| int dse_Tip                     | BASE + 9460 | Use on <b>\_DATABINDING_READ_DATA_STRING</b>        |
| int dse_Effects                 | BASE + 9461 | Use on <b>DATABINDING_READ_INT</b>                  |
| int dse_Folder                  | BASE + 9462 | Use on <b>\_DATABINDING_READ_HASH</b>               |
| int dse_PromptSelectLabel       | BASE + 9463 | Use on <b>\_DATABINDING_READ_HASH</b>               |
| int dse_PromptSelectEnabled     | BASE + 9464 | Use on <b>\_DATABINDING_READ_DATA_BOOL</b>          |
| int dse_PromptSelectVisible     | BASE + 9465 | Use on <b>\_DATABINDING_READ_DATA_BOOL</b>          |
| int dse_PromptHoldSelectLabel   | BASE + 9466 | Use on <b>\_DATABINDING_READ_HASH</b>               |
| int dse_PromptHoldSelectEnabled | BASE + 9467 | Use on <b>\_DATABINDING_READ_DATA_BOOL</b>          |
| int dse_PromptHoldSelectVisible | BASE + 9468 | Use on <b>\_DATABINDING_READ_DATA_BOOL</b>          |
| int dse_PromptDiscardAllEnabled | BASE + 9469 | Use on <b>\_DATABINDING_READ_DATA_BOOL</b>          |
| int dse_PromptDiscardAllVisible | BASE + 9470 | Use on <b>\_DATABINDING_READ_DATA_BOOL</b>          |
| int dse_PromptDiscardAllLabel   | BASE + 9471 | Use on <b>\_DATABINDING_READ_DATA_STRING</b>        |
| int dse_PromptSendLabel         | BASE + 9472 | Use on <b>\_DATABINDING_READ_HASH</b>               |
| int dse_PromptSendAllVisible    | BASE + 9473 | Use on <b>\_DATABINDING_READ_DATA_BOOL</b>          |
| int dse_PromptDropVisible       | BASE + 9474 | Use on <b>\_DATABINDING_READ_DATA_BOOL</b>          |
| int \_eSatchelState             | BASE + 9476 | SATCHEL_INIT, SATCHEL_UPDATE, SATCHEL_CLEANUP       |
| BOOL \_bJustOpenedOrClosed      | BASE + 9477 | Was the satchel opened or closed this frame         |


## g_satchelData.sFolderData
- Base Index: 1935689 + 19
###
| Name                    | Index           | Description                 |
|-------------------------|-----------------|-----------------------------|
| int iNumItemsInCategory | BASE + 19 + 203 | Number of items in category |


## Snippets from the scripts (b1491)
- short_update.ysc
- Line 963 - func_25
```cpp
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
		Global_1935689.f_13 = SCRIPTS::START_NEW_SCRIPT("satchel", (1 << 10));
		SCRIPTS::SET_SCRIPT_AS_NO_LONGER_NEEDED("satchel");
	}
}
```

