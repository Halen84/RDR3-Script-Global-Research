<h2>g_savedGlobals</h2>

```
struct g_savedGlobals
{
	BOOL bGameInitialized = *getGlobalPtr(BASE); // +0
	BOOL bInGameflow = *getGlobalPtr(BASE + 1);
	Vector3 vLastCampPosition = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 2));
	float fLastCampHeading = *getGlobalPtr(BASE + 5);
	Vector3 vCurrentCaravanBedPosition = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 6));
	int minigameUnlocked = *getGlobalPtr(BASE + 7854);
	int jobUnlocked = *getGlobalPtr(BASE + 7855);
	int procmissionUnlocked = *getGlobalPtr(BASE + 7856);
	int wornOutfit = *getGlobalPtr(BASE + 7729);
	Hash playerCharacterModel = *getGlobalPtr(BASE + 39);
	int lawBountyAchievement = *getGlobalPtr(BASE + 449);
	int eRCMIndexTracked = *getGlobalPtr(BASE + 1093);
	int iRCMsActive = *getGlobalPtr(BASE + 1094);
	int deadeyeLevel = *getGlobalPtr(BASE + 7755);
	BOOL bAttackedBurial = *getGlobalPtr(BASE + 11953);
	int iMickeyMemory = *getGlobalPtr(BASE + 11954);
	int iStudiedAnimalsNoBinoculars = *getGlobalPtr(BASE + 11955);
	int iLastPayoffTutorialMessage = *getGlobalPtr(BASE + 11956);
	int iSavedBounty = *getGlobalPtr(BASE + 11957);
	BOOL bHatKnockedOff = *getGlobalPtr(BASE + 7730);
	int iHerbArrLocation = *getGlobalPtr(BASE + 9273);
	int iSPMinigameAchievementTracker = *getGlobalPtr(BASE + 11958);
	int iSPChecksum = *getGlobalPtr(BASE + 11999);
	BOOL bEndlessSummerInitialized = *getGlobalPtr(BASE + 7860);
	int iMoneyBeforeGuarma = *getGlobalPtr(BASE + 7861);
	//int _specialWildHorse = *getGlobalPtr(BASE + 11945);
	BOOL bPhotoModeToastDelivered = *getGlobalPtr(BASE + 12017);
	BOOL bFlacoCabinCigBoxLooted = *getGlobalPtr(BASE + 12018);
	int eTutorialsRun = *getGlobalPtr(BASE + 7832);
	BOOL bUsedFirstPerson = *getGlobalPtr(BASE + 9421);

	//===========================================================//

	struct saveGameData // BASE + 9
	{
		Vector3 saveGameLocation = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 9)); // +0
		int iSaveGamePropset = *getGlobalPtr(BASE + 9 + 1);
		Vector3 vSaveGamePropsetPosition = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 9 + 2));
		float fSaveGamePropsetHeading = *getGlobalPtr(BASE + 9 + 5);
		Hash iSaveGameScenarioHash = *getGlobalPtr(BASE + 9 + 6);
		Vector3 vResetPosition =  reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 9 + 7));
		int iResetRespawnNode = *getGlobalPtr(BASE + 9 + 10);
		int iResetAnimIndex = *getGlobalPtr(BASE + 9 + 11);
		BOOL bForceAltAnim = *getGlobalPtr(BASE + 9 + 11);
		int fResetHeading = *getGlobalPtr(BASE + 9 + 11);
		int eSavedTOD = *getGlobalPtr(BASE + 9 + 11);
		int respawnRegion = *getGlobalPtr(BASE + 9 + 11);
		int iResetBounty = *getGlobalPtr(BASE + 9 + 11);
		int iRespawnPosHistory = *getGlobalPtr(BASE + 9 + 11);

		struct iRespawnPosHistory // BASE + 9 + 16
		{
			// Note: Size is 4
		}iRespawnPosHistory;

		struct missionReplayData // BASE + 9 + 21
		{
			int iBitStorage = *getGlobalPtr(BASE + 9 + 21); // +0
			int iGeneralStorage = *getGlobalPtr(BASE + 9 + 21 + 1); // Note: Size is 5
			float fGeneralStorage = *getGlobalPtr(BASE + 9 + 21 + 6); // Note: Size is 3
		}missionReplayData;

	}saveGameData;

	//===========================================================//

	struct sFlow // BASE + 40
	{
		BOOL isGameflowActive = *getGlobalPtr(BASE + 40); // +0
		BOOL flowCompleted = *getGlobalPtr(BASE + 40 + 1);
	}sFlow;

	//===========================================================//

	struct playerHorse // BASE + 1095
	{
		int eCurrentStableSlot = *getGlobalPtr(BASE + 1095); // +0

		
		struct sHorseSlotInfo // BASE + 1095 + 1
		{
			int txtHorseName = *getGlobalPtr(BASE + 1095 + 1); // +0
			Hash eHorseBreed = *getGlobalPtr(BASE + 1095 + 1 + 8);
			Hash eHorseModel = *getGlobalPtr(BASE + 1095 + 1 + 9);
			int eGender = *getGlobalPtr(BASE + 1095 + 1 + 10);
			int eLossType = *getGlobalPtr(BASE + 1095 + 1 + 11);
			int iTimeOfLoss = *getGlobalPtr(BASE + 1095 + 1 + 12);
			int todTimeOfLoss = *getGlobalPtr(BASE + 1095 + 1 + 13);
			int eSlotState = *getGlobalPtr(BASE + 1095 + 1 + 14);
			Vector3 vLastCoord = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 1095 + 1 + 427));
			float fLastHeading = *getGlobalPtr(BASE + 1095 + 1 + 430);
			int iTimeStampDismounted = *getGlobalPtr(BASE + 1095 + 1 + 431);
			int iTimeStampAcquired = *getGlobalPtr(BASE + 1095 + 1 + 432);
			BOOL bHasDefaultSaddle = *getGlobalPtr(BASE + 1095 + 1 + 433);
			BOOL bPlayerPurchasedHorse = *getGlobalPtr(BASE + 1095 + 1 + 434);
			BOOL bPlayerBrokeHorse = *getGlobalPtr(BASE + 1095 + 1 + 435);


			struct sCarriedData // BASE + 1095 + 1 + 15
			{
				Hash eModel = *getGlobalPtr(BASE + 1095 + 1 + 15); // +0
				Hash eItem = *getGlobalPtr(BASE + 1095 + 1 + 15 + 1);
				int eCarriableType = *getGlobalPtr(BASE + 1095 + 1 + 15 + 2);
				int eCarriableConfigInfo = *getGlobalPtr(BASE + 1095 + 1 + 15 + 3);
				int ePedQuality = *getGlobalPtr(BASE + 1095 + 1 + 15 + 4);
				int ePedSkinQuality = *getGlobalPtr(BASE + 1095 + 1 + 15 + 5);
				int ePedRarity = *getGlobalPtr(BASE + 1095 + 1 + 15 + 6);
				int eDamageCleanliness = *getGlobalPtr(BASE + 1095 + 1 + 15 + 7);
				Hash eOutfit = *getGlobalPtr(BASE + 1095 + 1 + 15 + 8);
				int iNumMetaAssets = *getGlobalPtr(BASE + 1095 + 1 + 15 + 9);
				int iCarcassAge = *getGlobalPtr(BASE + 1095 + 1 + 15 + 91);
				BOOL bSkinned = *getGlobalPtr(BASE + 1095 + 1 + 15 + 92);
				BOOL bLegendary = *getGlobalPtr(BASE + 1095 + 1 + 15 + 93);


				struct sMetaAssetData // BASE + 1095 + 1 + 15 + 10
				{
					Hash iDrawable = *getGlobalPtr(BASE + 1095 + 1 + 15 + 10); // +0
					Hash iAlbedo = *getGlobalPtr(BASE + 1095 + 1 + 15 + 10 + 1);
					Hash iNormal = *getGlobalPtr(BASE + 1095 + 1 + 15 + 10 + 2);
					Hash iMaterial = *getGlobalPtr(BASE + 1095 + 1 + 15 + 10 + 3);
					Hash iPalette = *getGlobalPtr(BASE + 1095 + 1 + 15 + 10 + 4);
					int iTint0 = *getGlobalPtr(BASE + 1095 + 1 + 15 + 10 + 5);
					int iTint1 = *getGlobalPtr(BASE + 1095 + 1 + 15 + 10 + 6);
					int iTint2 = *getGlobalPtr(BASE + 1095 + 1 + 15 + 10 + 7);
				}sMetaAssetData;

			}sCarriedData;


			struct sPeltSkinData // BASE + 1095 + 1 + 298
			{
				int iCount = *getGlobalPtr(BASE + 1095 + 1 + 298); // +0
			}sPeltSkinData;


			struct sVisualPeltSkinInfo // BASE + 1095 + 1 + 356
			{
				int SatchelItem = *getGlobalPtr(BASE + 1095 + 1 + 356); // +0
				Hash TextureLookupHash = *getGlobalPtr(BASE + 1095 + 1 + 356 + 1);
				int TextureLookupTint = *getGlobalPtr(BASE + 1095 + 1 + 356 + 2);
				int UnusedPad0 = *getGlobalPtr(BASE + 1095 + 1 + 356 + 3);
				int UnusedPad1 = *getGlobalPtr(BASE + 1095 + 1 + 356 + 4);
			}sVisualPeltSkinInfo;

			
			struct sBondingData // BASE + 1095 + 1 + 372
			{
				int iBondLevel = *getGlobalPtr(BASE + 1095 + 1 + 372); // +0
				float fBondXP = *getGlobalPtr(BASE + 1095 + 1 + 372 + 1);
				float fHorseEventXP = *getGlobalPtr(BASE + 1095 + 1 + 372 + 2);
			}sBondingData;

			
			struct sHorseCoreData // BASE + 1095 + 1 + 398
			{
				int iValue = *getGlobalPtr(BASE + 1095 + 1 + 398); // +0
				float fValueBuffer = *getGlobalPtr(BASE + 1095 + 1 + 398 + 1);
				float fDrainBuffer = *getGlobalPtr(BASE + 1095 + 1 + 398 + 2);
				int iLastGameTime = *getGlobalPtr(BASE + 1095 + 1 + 398 + 3);
			}sHorseCoreData;

			
			struct sEfficiencyData // BASE + 1095 + 1 + 407
			{
				int iValue = *getGlobalPtr(BASE + 1095 + 1 + 407); // +0
				float fValueBuffer = *getGlobalPtr(BASE + 1095 + 1 + 407 + 1);
				float fDrainBuffer = *getGlobalPtr(BASE + 1095 + 1 + 407 + 2);
				int iLastGameTime = *getGlobalPtr(BASE + 1095 + 1 + 407 + 3);
			}sEfficiencyData;

			
			struct sWrithingData // BASE + 1095 + 1 + 420
			{
				BOOL bIsWrithing = *getGlobalPtr(BASE + 1095 + 1 + 420); // +0
				float fWrithingDuration = *getGlobalPtr(BASE + 1095 + 1 + 420 + 1);
			}sWrithingData;

			
			struct sStableOwnedData // BASE + 1095 + 1 + 422
			{
				BOOL bIsStableOwned = *getGlobalPtr(BASE + 1095 + 1 + 422); // +0
				int eShop = *getGlobalPtr(BASE + 1095 + 1 + 422 + 1);
				int todStolen = *getGlobalPtr(BASE + 1095 + 1 + 422 + 2);
			}sStableOwnedData;

			
			struct sHorseBurdenData // BASE + 1095 + 1 + 425
			{
				BOOL bIsStableOwned = *getGlobalPtr(BASE + 1095 + 1 + 425); // +0
				int todBurdenPlaced = *getGlobalPtr(BASE + 1095 + 1 + 425 + 1);
			}sHorseBurdenData;

		}sHorseSlotInfo;


		struct sSaddleInfo // BASE + 1095 + 3054
		{
			int eSaddleSlot = *getGlobalPtr(BASE + 1095 + 3054); // +0
			int eSaddleState = *getGlobalPtr(BASE + 1095 + 3054 + 1);
			int eDeadOrDroppedTime = *getGlobalPtr(BASE + 1095 + 3054 + 2);
			Vector3 vSaddleCoords = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 1095 + 3054 + 77));


			struct sPeltSkinData // BASE + 1095 + 3054 + 3
			{
				int iCount = *getGlobalPtr(BASE + 1095 + 3054 + 3); // +0
			};


			struct sVisualPeltSkinInfo // BASE + 1095 + 3054 + 61
			{
				int SatchelItem = *getGlobalPtr(BASE + 1095 + 3054 + 61); // +0
				Hash TextureLookupHash = *getGlobalPtr(BASE + 1095 + 3054 + 61 + 1);
				int TextureLookupTint = *getGlobalPtr(BASE + 1095 + 3054 + 61 + 2);
				int UnusedPad0 = *getGlobalPtr(BASE + 1095 + 3054 + 61 + 3);
				int UnusedPad1 = *getGlobalPtr(BASE + 1095 + 3054 + 61 + 4);
			}sVisualPeltSkinInfo;
		}sSaddleInfo;
		

		struct sHorseBreakingInfo // BASE + 1095 + 3134
		{
			BOOL bMinigameSuccessful = *getGlobalPtr(BASE + 1095 + 3134); // +0
		}sHorseBreakingInfo;


		struct sTutorialInfo // BASE + 1095 + 3135
		{
			int iHighestBondLevelReached = *getGlobalPtr(BASE + 1095 + 3135); // +0
			int iTimesOverspurred = *getGlobalPtr(BASE + 1095 + 3135 + 1);
			int iTimesRevived = *getGlobalPtr(BASE + 1095 + 3135 + 2);
			int iTimesDirtyOver50Percent = *getGlobalPtr(BASE + 1095 + 3135 + 3);
			BOOL bDeadHorseTutorialShouldRun = *getGlobalPtr(BASE + 1095 + 3135 + 4);
		}sTutorialInfo;


		struct sHorseRaceInfo // BASE + 1095 + 3140
		{
			BOOL bSprintBondingBonusUnlocked = *getGlobalPtr(BASE + 1095 + 3140); // +0
			BOOL bSpeedStatBonusUnlocked = *getGlobalPtr(BASE + 1095 + 3140 + 1);
		}sHorseRaceInfo;

	}playerHorse;

	//===========================================================//

	// NOT DONE
	struct postOfficeData // BASE + 9910
	{
		// NOTE: THESE ARE WRONG. TODO -- FIX THESE

		struct trackedParcels // BASE + 9910 -- Does this exist?
		{
			int eMailSendFlags = *getGlobalPtr(BASE + 9910); // +0
			int eMailReplyFlags = *getGlobalPtr(BASE + 9910 + 1);
			int eSentTime = *getGlobalPtr(BASE + 9910 + 2);
			int eDeliveryTime = *getGlobalPtr(BASE + 9910 + 3);
			int eTrackedParcel = *getGlobalPtr(BASE + 9910 + 4);
			BOOL bOverrideDeliveryTime = *getGlobalPtr(BASE + 9910 + 5);
		}trackedParcels;

	}postOfficeData;

	//===========================================================//

	// NOT DONE
	struct caravanCamp // BASE + 4283
	{
		int eCurrentCamp = *getGlobalPtr(BASE + 4283); // +0
		int eCurrentCampRegion = *getGlobalPtr(BASE + 4283 + 1);
		int eCampFlags = *getGlobalPtr(BASE + 4283 + 2);
		int eCampAppearance = *getGlobalPtr(BASE + 4283 + 3);
		int eCampSetupState = *getGlobalPtr(BASE + 4283 + 4);
		int eCampSubstate = *getGlobalPtr(BASE + 4283 + 5);
		int iCampLevel = *getGlobalPtr(BASE + 4283 + 312);
		int iCampChickenCoopLevel = *getGlobalPtr(BASE + 4283 + 313);
		int iCampVehicleLevel = *getGlobalPtr(BASE + 4283 + 314);
		int iCampToolsLevel = *getGlobalPtr(BASE + 4283 + 315);
		int iCampCraftingFireLevel = *getGlobalPtr(BASE + 4283 + 316);
		int iCampShavingKitLevel = *getGlobalPtr(BASE + 4283 + 317);
		int iCampPearsonLevel = *getGlobalPtr(BASE + 4283 + 318);
		int iCampStraussLevel = *getGlobalPtr(BASE + 4283 + 319);
		int iCampArthurLevel = *getGlobalPtr(BASE + 4283 + 320);
		int iCampTentLevel = *getGlobalPtr(BASE + 4283 + 321);
		int iCampHitchLevel = *getGlobalPtr(BASE + 4283 + 322);
		int iNumInnocentsKilled = *getGlobalPtr(BASE + 4283 + 323);
		int iCampFundsCents = *getGlobalPtr(BASE + 4283 + 324);
		int iGangSavingsCents = *getGlobalPtr(BASE + 4283 + 325);
		int iBankDebtCents = *getGlobalPtr(BASE + 4283 + 326);
		int iCarcassesDonated = *getGlobalPtr(BASE + 4283 + 327);
		int todCampSupplyDecrement = *getGlobalPtr(BASE + 4283 + 328);
		int todCampFoodDecrement = *getGlobalPtr(BASE + 4283 + 329);
		int todNextPlayerStewServe = *getGlobalPtr(BASE + 4283 + 330);
		int todNextCompanionDonation = *getGlobalPtr(BASE + 4283 + 331);
		int eLastDonationCompanions = *getGlobalPtr(BASE + 4283 + 332);
		int eLastDonationCompanions0 = *getGlobalPtr(BASE + 4283 + 333);
		int eLastDonationCompanions1 = *getGlobalPtr(BASE + 4283 + 334);
		int eCheckinState = *getGlobalPtr(BASE + 4283 + 335); // this may be a struct?
		int eLongAbsenceInstancesSeen = *getGlobalPtr(BASE + 4283 + 574);
		int todLongAbsenceTOD = *getGlobalPtr(BASE + 4283 + 575);
		int eMiniExchangeQueue = *getGlobalPtr(BASE + 4283 + 578); // Note: Size is 81


		struct activeCampStateTags // BASE + 4283 + 6
		{
			// NOTE: Size is 301. TODO: Fix these

			int eTag = *getGlobalPtr(BASE + 4283 + 6); // +0
			int eExpiry = *getGlobalPtr(BASE + 4283 + 6 + 1);
			int ePersistence = *getGlobalPtr(BASE + 4283 + 6 + 1);
			int iPriority = *getGlobalPtr(BASE + 4283 + 6 + 1);
			int eCategory = *getGlobalPtr(BASE + 4283 + 6 + 1);
		}activeCampStateTags;


		// DONE
		struct sPearsonUnlocks // BASE + 4283 + 307
		{
			int iUnlockedBitset = *getGlobalPtr(BASE + 4283 + 307); // +0
			int iItemsCrafted = *getGlobalPtr(BASE + 4283 + 307 + 1);
			int iAnimalsDonated = *getGlobalPtr(BASE + 4283 + 307 + 2);
			int iCentsDonated = *getGlobalPtr(BASE + 4283 + 307 + 3);
			int iTrinkedDonated = *getGlobalPtr(BASE + 4283 + 307 + 4); // nice spelling R*
		}sPearsonUnlocks;


		struct caravanPurchaseList // BASE + 4283 + 367
		{
			// NOTE: Size is 41. TODO: Fix these

			int eGlobalItemIdx = *getGlobalPtr(BASE + 4283 + 367); // +0
			int iPurchaseTimer = *getGlobalPtr(BASE + 4283 + 367 + 1);
			int iPurchaseCount = *getGlobalPtr(BASE + 4283 + 367 + 2);
			int eShopPurchasedFrom = *getGlobalPtr(BASE + 4283 + 367 + 3);
		}caravanPurchaseList;

		// DONE
		struct sCaravanChoreData // BASE + 4283 + 408
		{
			int iChoresCompletedBitMask = *getGlobalPtr(BASE + 4283 + 408); // +0
			int todLastChoreCompleted = *getGlobalPtr(BASE + 4283 + 408 + 1);
			float fMilkAmount = *getGlobalPtr(BASE + 4283 + 408 + 2);
			float fEggAmount = *getGlobalPtr(BASE + 4283 + 408 + 3);
			int iNumberOfChoresCompletedTotal = *getGlobalPtr(BASE + 4283 + 408 + 4);
			int iTimesCowWasMilkedToday = *getGlobalPtr(BASE + 4283 + 408 + 5);
			BOOL bStallsCleaned = *getGlobalPtr(BASE + 4283 + 408 + 6);
		}sCaravanChoreData;

		// DONE
		struct sSupplyGroups // BASE + 4283 + 415
		{
			int iGroupItemsRemovedBitset = *getGlobalPtr(BASE + 4283 + 415); // +0   Note: Size is 5
			int todCompanionNextRemoval = *getGlobalPtr(BASE + 4283 + 415 + 5);
			int iUnlockHashes = *getGlobalPtr(BASE + 4283 + 415 + 6); // Note: Size is 18
			int iUnlockHashCount = *getGlobalPtr(BASE + 4283 + 415 + 24);
		}sSupplyGroups;


		struct sContData // BASE + 4283 + 440
		{
			// Note: Size is 127 -- TODO: Fix these

			int iCarriedOverCents; // ???
			int sCont; // ???
			int iContributionCount; // ???
		}sContData;

		// DONE
		struct sCampHitchedHorseSavedData // BASE + 4283 + 567  (Another name R* uses is sCampHorseData)
		{
			BOOL bCampHorseHitched = *getGlobalPtr(BASE + 4283 + 567); // +0
			int eCampIndex = *getGlobalPtr(BASE + 4283 + 567 + 1);
			Vector3 vHitchedAtCoords = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 4283 + 567 + 2));
			float fHitchedAtHeading = *getGlobalPtr(BASE + 4283 + 567 + 5);
			int iHorseGender = *getGlobalPtr(BASE + 4283 + 567 + 6);
		}sCampHorseData;


		// DONE
		struct sCampAmbientStreams // BASE + 4283 + 576
		{
			int iCounterStreamBeenPlayed = *getGlobalPtr(BASE + 4283 + 576); // +0
			int todLastStreamPlayed = *getGlobalPtr(BASE + 4283 + 576 + 1);
		}sCampAmbientStreams;

	}caravanCamp;

	//===========================================================//

	struct loansharkingData // BASE + 9052
	{
		int iLSActiveDebtors = *getGlobalPtr(BASE + 9052); // +0
		int todLSVictimRespawn = *getGlobalPtr(BASE + 9052 + 1); // Note: Size is 10
		int eLSSavedMissionFlags = *getGlobalPtr(BASE + 9052 + 11); // Note: Size is 10
		int eLSSavedSystemFlags = *getGlobalPtr(BASE + 9052 + 21); // Note: Size is 10
	}loansharkingData;

	//===========================================================//

	struct bountyhuntingData // BASE + 9074
	{
		int iBountiesCompleted = *getGlobalPtr(BASE + 9074); // +0
		int eFlags = *getGlobalPtr(BASE + 9074 + 1);
		int eRCMStage = *getGlobalPtr(BASE + 9074 + 2);
		int iRewardAlive = *getGlobalPtr(BASE + 9074 + 3);
		int iRewardDead = *getGlobalPtr(BASE + 9074 + 4);
	}bountyhuntingData;

	//===========================================================//

	struct bankRobberyData // BASE + 9079
	{
		int eFlags = *getGlobalPtr(BASE + 9079); // +0  Note: Size is 5
		int eStatus = *getGlobalPtr(BASE + 9079 + 5); // Note: Size is 5
		int todLastRobTime = *getGlobalPtr(BASE + 9079 + 10); // Note: Size is 5
		int iCompletedRobberies = *getGlobalPtr(BASE + 9079 + 15);
		BOOL bIsBraveClientActive = *getGlobalPtr(BASE + 9079 + 16);
	}bankRobberyData;

	//===========================================================//

	struct coachRobbery // BASE + 9146
	{
		int iCompletedRobberies = *getGlobalPtr(BASE + 9146); // +0
		int eCurrentRobberyRho = *getGlobalPtr(BASE + 9146 + 1);
		int eCurrentRobberyStr = *getGlobalPtr(BASE + 9146 + 2);
		int eActiveRobbery = *getGlobalPtr(BASE + 9146 + 3);
		int eStatus = *getGlobalPtr(BASE + 9146 + 4); // Note: Size is 15
		int eCurrentVariant = *getGlobalPtr(BASE + 9146 + 19); // Note: Size is 15
		int eCurrentDifficulty = *getGlobalPtr(BASE + 9146 + 34); // Note: Size is 15
		int todCoachRobExp = *getGlobalPtr(BASE + 9146 + 79); // Note: Size is 15
		int todCoachRobAct = *getGlobalPtr(BASE + 9146 + 64); // Note: Size is 15
		int iTimesOffered = *getGlobalPtr(BASE + 9146 + 49); // Note: Size is 15
		BOOL bNoteHasBeenRead = *getGlobalPtr(BASE + 9146 + 94); // Note: Size is 15
		int iRobberiesSinceLastPoliceTrap = *getGlobalPtr(BASE + 9146 + 111); // Note: Size is 15
		int eCoachBitflags = *getGlobalPtr(BASE + 9146 + 126);
		int todCoachRobberyCompleted = *getGlobalPtr(BASE + 9146 + 109);
		int todTipGivenByFreightWorker = *getGlobalPtr(BASE + 9146 + 110);
	}coachRobbery;

	//===========================================================//

	// NOT DONE
	struct tutorialSaved // BASE + 7756
	{
		// TODO

		int sTimedData;
		int iTimeLastRun;
		int iTimesRun;
		int eTutorial;
	}tutorialSaved;

	//===========================================================//

	// NOT DONE
	struct lawStateData // BASE + 358
	{
		// TODO

		int iStateBounty;
		Vector3 vLastKnownLocation;
		float fLastKnownRadius;
		int eStateFlags;
		int eLastOuftitSeenByLaw;
		int eSideburnsStyle;
		int eChinStyle;
		int eMustacheStyle;
		int eTimeOutfitLastSeen;
		int eAppearanceLawMemoryFlags;

		struct stateLawMemoryData
		{
			// TODO		 Note: Size is 6

		}stateLawMemoryData;

	}lawStateData;

	//===========================================================//

	// NOT DONE
	struct lawDistrictData // BASE + 431
	{
		// TODO		 Note: Size is 18

		int eLawDistrictFlags;
	}lawDistrictData;

	//===========================================================//

	// NOT DONE
	struct caravanEventData // BASE + 7100
	{
		// TODO		 Note: Size is 57

		int iTimesCompleted;
		int iTimesSeen;
		int iTimesLaunched;
		int iTimesSpawned;
		int todNextAvailable;
		int iGeneric1;
		int iGeneric2;
		BOOL bUnlocked;
	}caravanEventData;

	//===========================================================//

	// NOT DONE
	struct pendingRCMStage // BASE + 450
	{
		// TODO		Note: Size is 40
	}pendingRCMStage;

	//===========================================================//

	// NOT DONE
	struct rcmDataSaved // BASE + 490
	{
		float iSavedFloat1; // Note: Size is 201
		float iSavedFloat2; // Note: Size is 201
		int eRCMSavedFlags; // Note: Size is 201
	}rcmDataSaved;

	//===========================================================//

	// NOT DONE
	struct playerOnlyGreetStack // BASE + 4237
	{
		// TODO		Note: Size is 46

		int eRuleset;
		int todExpiry;
		BOOL bTempDisable;
	}playerOnlyGreetStack;

	//===========================================================//

	// NOT DONE
	struct companionData // BASE + 4942
	{
		// TODO		Note: Size is 1621

		int companionFlags;
		int iTrustLevel;
		int iFollowerLevel;
		int companionOutfit;
		int lastWornOutfitOnMission;
		int wornItems;
		int modelCompanion;
		int modelCompanionHorse;
		int immediateGreetOverride;
		int eRuleset;
		int todExpiry;
		BOOL bTempDisable;
		int eTemporaryMood;
		int ePersistentMood;
		int todTemporaryMoodExpiry;
		int todLastItemInteraction;
		int todLastChore;
		int todLastActivity;
		int todRoleCooldown;
		int eTimedEventType;
		int todTimedEvent;
		int txtSchedule;
		int eDeedReservedFor;

		struct greetOverrides
		{
			int eRuleset;
			int todExpiry;
			BOOL bTempDisable;
		}greetOverrides;

	}companionData;

	//===========================================================//

	// NOT DONE
	struct companion_manager // BASE + 6563
	{
		int iItemRequestCompleteBitset = *getGlobalPtr(BASE + 6563 + 271);
		int eReturnedJackBook = *getGlobalPtr(BASE + 6563 + 272);
		int iNumAvailableActivities = *getGlobalPtr(BASE + 6563 + 273);
		int todHungoverExpiry = *getGlobalPtr(BASE + 6563 + 475);

		struct itemRequests
		{
			// Note: size is 271

			int eRequest;
			int eRequestItem;
			int iNumRequested;
			int eCompanion;
			int eHandInType;
			int eResultType;
			int txtConversation;
			int txtThankDialogue;
			int txtHandOverScenePath;
			int eVignette;
			int ePickupReward;
			int eModelReward;
			int iRewardSupplyGroupHash;
			int eState;
			BOOL bHasThankDialoguePlayed;
			BOOL bRewardHelpTextShown;
		}itemRequests;


		struct availableActivities // BASE + 6563 + 274
		{
			// Note: size is 201

			int eActivity;
			int eActivityInstance;
			int eHost;
			int eParticipants;
			int eConditionFlags;
			int vInvitePos;
			int vActivityPos;
			BOOL bEnabledInFlow;
			BOOL bHasBeenLaunched;
			BOOL bMustOffer;
			BOOL bOfferUntilHasRun;
			BOOL bForceLaunch;
			int eActivityDeed;
			int eTODAvailable;
			int iWeight;
			int iNumTimesOffered;
		}availableActivities;

	}companion_manager;

	//===========================================================//

	// NOT DONE
	struct activities // BASE + 7039
	{
		// TODO		Note: Size is 61

		BOOL bHasBeenPerformed;
		BOOL bHasBeenOffered;
	}activities;

	//===========================================================//

	// NOT DONE
	struct outfits // BASE + 7157
	{
		// TODO		Note: size is 286

		int status;
		int effect;
		int tags;
	}outfits;

	//===========================================================//

	// NOT DONE
	struct playerFacialHair // BASE + 7731
	{
		int eFacialHairFlags = *getGlobalPtr(BASE + 7731 + 16);

		struct facialHair // BASE + 7731 + 0 ?
		{
			// Note: Size is 16

			int facialHairLength;
			int facialHairCut;
			int facialHairStyle;
			int facialHairNextGrowthTimer;
			int iNumAcceleratedGrowthCycles;
		}facialHair;

	}playerFacialHair;

	//===========================================================//

	struct playerHeadHair // BASE + 7748
	{
		int ePomadeWearOffTimer = *getGlobalPtr(BASE + 7748); // +0
		int headHairLength = *getGlobalPtr(BASE + 7748 + 1);
		int eHeadHairCut = *getGlobalPtr(BASE + 7748 + 2);
		int eHeadHairStyle = *getGlobalPtr(BASE + 7748 + 3);
		int eHeadHairFlags = *getGlobalPtr(BASE + 7748 + 4);
		int headHairNextGrowthTimer = *getGlobalPtr(BASE + 7748 + 5);
		int iNumAcceleratedGrowthCycles = *getGlobalPtr(BASE + 7748 + 6);
	}playerHeadHair;

	//===========================================================//

	// NOT DONE
	struct mapBlipData // BASE + 7862
	{
		// TODO		Note: Size is 1001

		int blipRegion;
		int blipType;
		Vector3 blipPackedPosition;
		int blipTODFlags;
	}mapBlipData;

	//===========================================================//

	struct discoverableData // BASE + 8863
	{
		int eFlags = *getGlobalPtr(BASE + 8863); // +0	Note: Size is 144
		int DiscoEasel_timesViewed = *getGlobalPtr(BASE + 8863 + 145);
		int todDiscoEasel_timeStamp = *getGlobalPtr(BASE + 8863 + 144);
		int DiscoEasel_currentlyViewed = *getGlobalPtr(BASE + 8863 + 147);
		int DiscoPhonograph_visits = *getGlobalPtr(BASE + 8863 + 146);
		int DiscoDreamcatchers_bitField = *getGlobalPtr(BASE + 8863 + 148);
		int DiscoCarriable_iBitField = *getGlobalPtr(BASE + 8863 + 149);
		int DiscoCarriableMore_iBitField = *getGlobalPtr(BASE + 8863 + 150);
		int DiscoCarriableArrows_iBitField = *getGlobalPtr(BASE + 8863 + 151);
		int DiscoLocationVersion_iBitField = *getGlobalPtr(BASE + 8863 + 152);
		int DiscoLocationMoreVersion_iBitField = *getGlobalPtr(BASE + 8863 + 153);
		int DiscoLocationOtherVersion_iBitField = *getGlobalPtr(BASE + 8863 + 154);
		int DiscoCorpse_iBitField = *getGlobalPtr(BASE + 8863 + 155);
		int DiscoDisable = *getGlobalPtr(BASE + 8863 + 156);
	}discoverableData;

	//===========================================================//

	struct showManagerData // BASE + 9028
	{
		int eCurrentShow = *getGlobalPtr(BASE + 9028); // +0	Note: Size is 6
		int TODLastTimeViewed = *getGlobalPtr(BASE + 9028 + 6); // +0	Note: Size is 6
		int iShowBits = *getGlobalPtr(BASE + 9028 + 12);
		int iTotalShowViews = *getGlobalPtr(BASE + 9028 + 13);
		int iTotalMCViews = *getGlobalPtr(BASE + 9028 + 14);
		int iTotalMagicLanternViews = *getGlobalPtr(BASE + 9028 + 15);
		int iTotalMovieViews = *getGlobalPtr(BASE + 9028 + 16);
	}showManagerData;

	//===========================================================//

	struct townSecretData // BASE + 9020
	{
		int eFlags = *getGlobalPtr(BASE + 9020); // +0	Note: Size is 5
		int TownSecret_VanHorn_bitfield = *getGlobalPtr(BASE + 9020 + 5);
		int iTownSecret_Saint_Denis_bitfield = *getGlobalPtr(BASE + 9020 + 6);
		int eStrawberryLastDayUFOSeen = *getGlobalPtr(BASE + 9020 + 7);
	}townSecretData;

	//===========================================================//

	// NOT DONE
	struct eventArea // BASE + 9096
	{
		// TODO		Note: Size is 49

		int iStage;
		int iForceTransitionStage;
		int todNextStage;
		int todCounter;
		int eFlags;
		int eStateFlags;
		int iEventAreaCustomData;
		int iEventAreaCustomCounter;
		int iEventAreaMassacreCount;
		int iAggroStage;
		int todAggroed;
		int todMassacred;
	}eventArea;

	//===========================================================//

	struct duelingData // BASE + 9145
	{
		int eFlags = *getGlobalPtr(BASE + 9145); // +0
	}duelingData;

	//===========================================================//

	struct herbs // BASE + 9274
	{
		int eHerbTypeFlags = *getGlobalPtr(BASE + 9274); // +0	Note: Size is 45
	}herbs;

	//===========================================================//

	// NOT DONE
	struct huntingZoneData // BASE + 9319
	{
		// TODO

		struct sHuntingZoneTypes // BASE + 9319 + 0 ?
		{
			// Note: Size is 65

			BOOL bDiscovered;
			BOOL bCompleted;
			int eLaunchTime;
			BOOL bLegendaryHasBeenSkinned;
		}sHuntingZoneTypes;

	}huntingZoneData;

	//===========================================================//

	// NOT DONE
	struct propertyData // BASE + 9384
	{
		// TODO		Note: Size is 35

		int eFlags;
		int eTimeOfDay;
	}propertyData;

	//===========================================================//

	// NOT DONE
	struct homeRobberyData // BASE + 9422
	{
		// Note: Size is 57

		int todNextAvailable = *getGlobalPtr(BASE + 9422); // +0
		int todLastVisited = *getGlobalPtr(BASE + 9422 + 1);
		int eFlags = *getGlobalPtr(BASE + 9422 + 4);
		int eFlagsPlus = *getGlobalPtr(BASE + 9422 + 5);
		int eFlagsSet3 = *getGlobalPtr(BASE + 9422 + 6);
		int iTimesRobbed = *getGlobalPtr(BASE + 9422 + 2);
		int iPlayerCentsLostAtHome = *getGlobalPtr(BASE + 9422 + 3);
	}homeRobberyData;

	//===========================================================//

	// NOT DONE
	struct newspapers // BASE + 9479
	{
		// TODO		Note: Size is 57

		int eStatus;
		int eDynamicStory1;
		int eDynamicStory2;
		int eFishingStory;
	}newspapers;

	//===========================================================//

	// NOT DONE
	struct dynamicArticles // BASE + 9536
	{

	}dynamicArticles;

	//===========================================================//

	struct itemData // BASE + 11943
	{
		int todSurvivalistActive = *getGlobalPtr(BASE + 11943); // +0
		int todChewingGumActive = *getGlobalPtr(BASE + 11943 + 1);
	}itemData;

	//===========================================================//

	// NOT DONE
	struct gangs // BASE + 9571
	{
		// TODO		Note: Size is 61

		int gangSavedFlags;
		int gangStatus;
		int iKillsSinceStatusChange;
		int todLastKill;
		int iGenericInt1;
		int iNumCampfiresCleared;
		int iNumCampfiresSpawned;
		int iNumCampfiresSeen;
		int iNumCampfiresPersisted;
		int iGangEncounterStage;
	}gangs;

	//===========================================================//

	// NOT DONE
	struct ambush // BASE + 9632
	{
		int eAmbushSavedFlags = *getGlobalPtr(BASE + 9632 + 191);
		int todLastAmbushTime = *getGlobalPtr(BASE + 9632 + 192);
		int eLastAmbushGang = *getGlobalPtr(BASE + 9632 + 193);
		int eLastAmbush = *getGlobalPtr(BASE + 9632 + 194);
		int iAmbushesCompleted = *getGlobalPtr(BASE + 9632 + 195);
		int iNumRecognizeAmbushesStraight = *getGlobalPtr(BASE + 9632 + 196);

		struct ambushTrack // BASE + 9632 + 0 ?
		{
			// Note: Size is 177

			int iCompletedCount;
			int iSeenCount;
			int iSpawnedCount;
			int iNextAllowedSpawnMinutes;
		}ambushTrack;


		struct gangAmbushesSeen
		{
			// Note: Size is 7
		}gangAmbushesSeen;


		struct gangAmbushesStraight
		{
			// Note: Size is 7
		}gangAmbushesStraight;

	}ambush;

	//===========================================================//

	struct campfires // BASE + 10991
	{
		int eFoothillsStoriesSpoken = *getGlobalPtr(BASE + 10991); // +0
		int eMountainsStoriesSpoken = *getGlobalPtr(BASE + 10991 + 1);
		int ePlainsStoriesSpoken = *getGlobalPtr(BASE + 10991 + 2);
		int eSwampsStoriesSpoken = *getGlobalPtr(BASE + 10991 + 3);
		Vector3 vCampfireUsedPositions = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 10991 + 4)); // Note: Size is 31
		int iVignetteVariations = *getGlobalPtr(BASE + 10991 + 35); // Note: Size is 2
		int eCampSavedFlags = *getGlobalPtr(BASE + 10991 + 37);
	}campfires;

	//===========================================================//

	struct worldStates // BASE + 283
	{
		// bitfields. See EXAMPLES.md
	}worldStates;

	//===========================================================//

	struct worldStateTimers // BASE + 297
	{
		// bitfields. Note: Size is 61
	}worldStateTimers;

	//===========================================================//

	struct featureUnlocked // BASE + 7857
	{
		// bitfields. Note: Size is 3
	}featureUnlocked;

	//===========================================================//

	// NOT DONE
	struct jailData // BASE + 9829
	{
		struct sPrisoners // BASE + 9829 + 0 ?
		{
			// Note: Size is 81

			int eJailRegion;
			int ePrisoner;
			int ePrisonerFlag;
			int ePrisonerDialogue;
		}sPrisoners;
	}jailData;

	//===========================================================//

	struct trainData // BASE + 11029
	{
		// Note: Size is 66

		int trainFlags = *getGlobalPtr(BASE + 11029); // +0
		Vector3 vTrainLoc = reinterpret_cast<Vector3&>(*getGlobalPtr(BASE + 11029 + 1));
		BOOL bDirection = *getGlobalPtr(BASE + 11029 + 4);
	}trainData;

	//===========================================================//

	struct playerRPGData // BASE + 11095
	{
		float fPlayerEfficiency = *getGlobalPtr(BASE + 11095); // +0 -- TODO: THIS IS A STRUCT THAT CONTAINS fCorePoints
		int iHonor = *getGlobalPtr(BASE + 11095 + 35);
		int iHighestHonorRank = *getGlobalPtr(BASE + 11095 + 36);
		int iLowestHonorRank = *getGlobalPtr(BASE + 11095 + 37);
		int iHighestBountyHonorReached = *getGlobalPtr(BASE + 11095 + 38);
		float fDeadeyeAmount = *getGlobalPtr(BASE + 11095 + 39);
		float fPlayerWeightLowerLimit = *getGlobalPtr(BASE + 11095 + 40);
		float fPlayerWeightUpperLimit = *getGlobalPtr(BASE + 11095 + 41);
		float fPlayerTankSickMod = *getGlobalPtr(BASE + 11095 + 44);
		float fPlayerStamWeightMod = *getGlobalPtr(BASE + 11095 + 45);
		int RPG_TIME_BEFORE_DEADEYECORE_EMPTY = *getGlobalPtr(BASE + 11095 + 46);
		int RPG_TIME_BEFORE_STAMINACORE_EMPTY = *getGlobalPtr(BASE + 11095 + 47);
		int RPG_TIME_BEFORE_HEALTHCORE_EMPTY = *getGlobalPtr(BASE + 11095 + 48);
		int iOverfedTimer = *getGlobalPtr(BASE + 11095 + 42);
		BOOL bPlayerPoisoned = *getGlobalPtr(BASE + 11095 + 43);
		float fGritResist = *getGlobalPtr(BASE + 11095 + 49);
		float fInstinctResist = *getGlobalPtr(BASE + 11095 + 50);
		float fStrengthResist = *getGlobalPtr(BASE + 11095 + 51);
		float fFatResist = *getGlobalPtr(BASE + 11095 + 52);
		float fHeatResist = *getGlobalPtr(BASE + 11095 + 53);
		float fColdResist = *getGlobalPtr(BASE + 11095 + 54);
		float fBonusHealthXP = *getGlobalPtr(BASE + 11095 + 55);
		float fBonusDeadeyeXP = *getGlobalPtr(BASE + 11095 + 56);
		float fBonusStaminaXP = *getGlobalPtr(BASE + 11095 + 57);
		int ePlayerSickness = *getGlobalPtr(BASE + 11095 + 67);
		float fEagleEyeDepleteMod = *getGlobalPtr(BASE + 11095 + 58);
		float fEagleEyeRangeBonus = *getGlobalPtr(BASE + 11095 + 59);
		float fWeaponDegradeResist = *getGlobalPtr(BASE + 11095 + 60);
		float fDamageScaleMelee = *getGlobalPtr(BASE + 11095 + 61);
		float fDamageMod = *getGlobalPtr(BASE + 11095 + 62);
		float fDamageTakenOnHorseModifier = *getGlobalPtr(BASE + 11095 + 63);
		float fBowStaminaModifier = *getGlobalPtr(BASE + 11095 + 64);
		int iGrappledKilledBears = *getGlobalPtr(BASE + 11095 + 65);
		int iTimesEatenFood = *getGlobalPtr(BASE + 11095 + 66);
		float fHorseBondingXPMod = *getGlobalPtr(BASE + 11095 + 68);
		float fHealthRefillMod = *getGlobalPtr(BASE + 11095 + 69);
		float fFortifyMod = *getGlobalPtr(BASE + 11095 + 70);

		struct sAttributeOverpoweredTime // BASE + 11095 + 4
		{
			// Note: Size is 7?

			float fTankTime;
			float fCoreTime;
		}sAttributeOverpoweredTime;


		struct fAttributePoints
		{
			// Note: Size is 24
		}fAttributePoints;

	}playerRPGData;

	//===========================================================//

	// NOT DONE
	struct moralChoices // BASE + 11166
	{
		// TODO		Note: Size is 16

		int eChoiceType;
	}moralChoices;

	//===========================================================//

	struct cacheOutfitData // BASE + 7443
	{
		// Note: Size is 286

		int cachedOutfits;
	}cacheOutfitData;

	//===========================================================//

	struct playerCampData // BASE + 9419
	{
		int eFlags = *getGlobalPtr(BASE + 9419); // +0
		int iNumberOfCamps = *getGlobalPtr(BASE + 9419 + 1);
	}playerCampData;

	//===========================================================//

	struct jailbreakData // BASE + 11182
	{
		int iViewedJailbreaks = *getGlobalPtr(BASE + 11182); // +0
		int lastViewedJailbreakTime = *getGlobalPtr(BASE + 11182 + 1);
	}jailbreakData;

	//===========================================================//

	struct sFishingDataSaved // BASE + 11184
	{
		Hash eCurrentBaitEquipped = *getGlobalPtr(BASE + 11184); // +0	Note: Size is 5
		BOOL bHasLegendaryFishBeenCaught = *getGlobalPtr(BASE + 11184 + 5); // Note: Size is 16
		int iFishingDataSavedBits = *getGlobalPtr(BASE + 11184 + 21);
	}sFishingDataSaved;

	//===========================================================//

	// NOT DONE
	struct managedTowns // BASE + 11206
	{
		// eActiveTownStateTags - possible struct (26) that contains the following:

		int eTag;
		int eTagPriority;
		int eTagPersistence;
		int eTODExpiry;
	}managedTowns;

	//===========================================================//

	// NOT DONE
	struct specialPeds // BASE + 11623
	{
		// TODO		Note: Size is 241

		int ePedStage;
		int eSavedFlags;
		int todLastSeen;
		int todLastEncounter;
		int todDeathTime;
		int iTimesSeen;
		int iInteracts;
		int iDeaths;
	}specialPeds;

	//===========================================================//

	struct dataShacksSaved // BASE + 11959
	{
		int iSavedFloat1 = *getGlobalPtr(BASE + 11959); // +0	Note: Size is 20
		int iSavedFloat2 = *getGlobalPtr(BASE + 11959 + 20); // Note: Size is 20
	}dataShacksSaved;

	//===========================================================//

	// NOT DONE
	struct hideouts // BASE + 11864
	{
		// TODO		Note: Size is 19

		int eFlags;
		int iNumActorsRemaining;
	}hideouts;

	//===========================================================//

	struct sFilletDataSaved // BASE + 11883
	{
		int iBestLaps = *getGlobalPtr(BASE + 11883); // +0	Note: Size is 13
		int iFastestLap = *getGlobalPtr(BASE + 11883 + 13); // Note: Size is 13
		int iLongestTime = *getGlobalPtr(BASE + 11883 + 26); // Note: Size is 13
	}sFilletDataSaved;

	//===========================================================//

	struct eBufferedJournalEntryUnlocks // BASE + 11922
	{
		// Note: Size is 21
	}eBufferedJournalEntryUnlocks;

	//===========================================================//

	struct collectiblesData // BASE + 9045
	{
		BOOL bDinoBonesStage2RCM = *getGlobalPtr(BASE + 9045); // +0
		BOOL bLegendaryFishStage2RCM = *getGlobalPtr(BASE + 9045 + 1);
		BOOL bRockCarvingsStage2RCM = *getGlobalPtr(BASE + 9045 + 2);
		BOOL bTaxidermyStage1RCM = *getGlobalPtr(BASE + 9045 + 3);
		BOOL bCarolinaParakeetExtinction = *getGlobalPtr(BASE + 9045 + 4);
		BOOL bChalTownHoldups = *getGlobalPtr(BASE + 9045 + 5);
		BOOL bTSAnnesburgRiddle = *getGlobalPtr(BASE + 9045 + 6);
	}collectiblesData;

	//===========================================================//

	struct sCheatManagerSaved // BASE + 12000
	{
		int iUnlockedCheats = *getGlobalPtr(BASE + 12000); // +0	Note: Size is 3
	}sCheatManagerSaved;

	//===========================================================//

	struct reinforcedequipmentSaved // BASE + 12003
	{
		int eEquipmentRewardFlags = *getGlobalPtr(BASE + 12003); // +0
	}reinforcedequipmentSaved;

	//===========================================================//

	struct collectableUiLogSaved // BASE + 12004
	{
		int eUiCigCardsSavedFlags = *getGlobalPtr(BASE + 12004); // +0
		int eUiDinoBonesSavedFlags = *getGlobalPtr(BASE + 12004 + 1);
		int eUiExoticsSavedFlags = *getGlobalPtr(BASE + 12004 + 2);
		int eUiLegendaryFishSavedFlags = *getGlobalPtr(BASE + 12004 + 3);
		int eUiParakeetsSavedFlags = *getGlobalPtr(BASE + 12004 + 4);
		int eUiRockCarvingsSavedFlags = *getGlobalPtr(BASE + 12004 + 5);
		int eUiTaxidermySavedFlags = *getGlobalPtr(BASE + 12004 + 6);
		int eUiTHJackHallSavedFlags = *getGlobalPtr(BASE + 12004 + 7);
		int eUiTHHighStakesSavedFlags = *getGlobalPtr(BASE + 12004 + 8);
		int eUiTHPoisonTrailSavedFlags = *getGlobalPtr(BASE + 12004 + 9);
		int eUiTHTresorMortsSavedFlags = *getGlobalPtr(BASE + 12004 + 10);
		int eUiTHElementalTrailSavedFlags = *getGlobalPtr(BASE + 12004 + 11);
		int eUiTHLandmarksOfRichesSavedFlags = *getGlobalPtr(BASE + 12004 + 12);
	}collectableUiLogSaved;

	//===========================================================//

	// NOT DONE
	struct shared // BASE + 12019
	{
		// TODO

		// cards
		// rockCarvings
		// legendaryFish
		// gatorEggs
		// egretFeathers
		// taxidermyAnimals
		// taxidermyMarital
		// journalData
		// exotics
		// firstRecipePamphlets
		// treasureHunter
	};

	//===========================================================//


	// TODO: Other structs


private:
	static const int BASE = 40;
};
```

# Player Stats
- g_savedGlobals contains lots of information about player stats. [Some examples](https://github.com/Halen84/RDR3-Script-Global-Research/blob/master/g_savedGlobals%20(Global_40)/Examples.md)

# Horse Stats
- g_savedGlobals also contain some horse stats. [Some examples](https://github.com/Halen84/RDR3-Script-Global-Research/blob/master/g_savedGlobals%20(Global_40)/Examples.md)

# Local World State Bitfields
- g_savedGlobals can also set local world state bitfields. [Example](https://github.com/Halen84/RDR3-Script-Global-Research/blob/master/g_savedGlobals%20(Global_40)/Examples.md)

# Enums
```
enum _ePlayerHorseSlot // eSlot
{
	PH_SLOT_INVALID = -1,
	PH_SLOT_PRIMARY,
	PH_SLOT_TEMPORARY,
	PH_SLOT_STABLE_1,
	PH_SLOT_STABLE_2,
	PH_SLOT_STABLE_3,
	PH_SLOT_LOST,
	PH_SLOT_PRE_TEMP,
	PH_SLOT_CURRENT
};
```
#
```
enum _ePlayerHorseSaddleState
{
	PSS_EQUIPPED,
	PSS_CARRIED,
	PSS_DROPPED,
	PSS_IN_SHOP
};
```

# Snippets from the scripts (b1436)
- event_area_appleseed_stg4.ysc
- Line 30803
```
int func_1022()
{
	if (Global_40.f_11095.f_35 <= -320)
	{
		return 1;
	}
	else if (Global_40.f_11095.f_35 <= -280)
	{
		return 2;
	}
	else if (Global_40.f_11095.f_35 <= -240)
	{
		return 3;
	}
	else if (Global_40.f_11095.f_35 <= -200)
	{
		return 4;
	}
	else if (Global_40.f_11095.f_35 <= -160)
	{
		return 5;
	}
	else if (Global_40.f_11095.f_35 <= -120)
	{
		return 6;
	}
	else if (Global_40.f_11095.f_35 <= -80)
	{
		return 7;
	}
	else if (Global_40.f_11095.f_35 < 0)
	{
		return 8;
	}
	else if (Global_40.f_11095.f_35 <= 40)
	{
		return 9;
	}
	else if (Global_40.f_11095.f_35 >= 320)
	{
		return 16;
	}
	else if (Global_40.f_11095.f_35 >= 280)
	{
		return 15;
	}
	else if (Global_40.f_11095.f_35 >= 240)
	{
		return 14;
	}
	else if (Global_40.f_11095.f_35 >= 200)
	{
		return 13;
	}
	else if (Global_40.f_11095.f_35 >= 160)
	{
		return 12;
	}
	else if (Global_40.f_11095.f_35 >= 120)
	{
		return 11;
	}
	else if (Global_40.f_11095.f_35 >= 80)
	{
		return 10;
	}
	return 9;
}
```
