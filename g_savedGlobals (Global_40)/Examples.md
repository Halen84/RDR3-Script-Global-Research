# Examples for g_savedGlobals

# Player Stats
- g_savedGlobals also holds lots of player stats. Not all are known, but here's quite a bit. See README.md for most members
- Some of these may be wrong
- They are stored in (g_savedGlobals.playerRPGData)
```
// Health Stats
float GetHealthCoreAmount()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 1));
}
int GetHealthExperience()
{
	return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 12));
}
float GetHealthOverpowerTime()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 5));
}


// Stamina Stats
float GetStaminaCoreAmount()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 2));
}
int GetStaminaExperience()
{
	return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 13));
}
float GetStaminaOverpowerTime()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 7));
}
float GetStaminaDrainRate()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 62)); // Player --> Arthur --> General --> Weight
}


// Deadeye Stats
float GetDeadeyeCoreAmount()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 3));
}
int GetDeadeyeExperience()
{
	return (int)reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 14));
}
float GetDeadeyeOverpowerTime()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 9));
}


// Misc stats
float GetDamageTakenRate()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 45)); // Player --> Arthur --> General --> Weight
}
float GetWeightCoreDrainRate() // ?
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 25));
}
float GetUNKDrunknessGlobal()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 22)); // Not exactly sure what this returns, but it's related to drunk/soberness
}
int GetPlayerHonor()
{
	return *getGlobalPtr(40 + 11095 + 35);
}
float GetPlayerCleanliness()
{
	return reinterpret_cast<float&>(*getGlobalPtr(40 + 11095 + 28)); // -100.0f if fully clean
}
int GetTotalNumberOfItemsConsumed()
{
	return *getGlobalPtr(40 + 11095 + 66); // Total number of things ate/drank
}
Hash GetPlayerModel()
{
	return *getGlobalPtr(40 + 39);
}
```

# Horse Stats
- g_savedGlobals also contains some horse stats. Again, not all are known.
- Note: These ones that I found below only change the pause menu stats, and not its actual stats.
- Some of them are stored in (g_savedGlobals + 1095 + 1 + 1 + _ePlayerHorseSlot + x)
```
// These 3 funcs don't actually change horse, only its stats in the pause menu
void SetHorseModelStat(Hash model)
{
	//Global_40.f_1095.f_1[iParam0 /*436*/].f_9
	*getGlobalPtr(40 + 1095 + 1 + 1 + PH_SLOT_PRIMARY + 9) = model;
}

void SetHorseBreedStat(Hash breed)
{
	//Global_40.f_1095.f_1[iParam0 /*436*/].f_8
	*getGlobalPtr(40 + 1095 + 1 + 1 + PH_SLOT_PRIMARY + 8) = breed;
}

void SetHorseGenderStat(int gender)
{
	if (gender < 0 || gender > 2) { gender = 2; }
	// 0 = Unknown, 1 = Male, 2 = Female
	//Global_40.f_1095.f_1[iParam0 /*436*/].f_10
	*getGlobalPtr(40 + 1095 + 1 + 1 + PH_SLOT_PRIMARY + 10) = gender;
}

// Horse name address: *getGlobalPtr(40 + 1095 + 1 + 1 + PH_SLOT_PRIMARY) 
```

# Local World States
- g_savedGlobals can also set local world state bitfields
```
void setLocalWorldState(WorldState worldState, bool set)
{
	int worldstateIndex = (int)worldState;
	int iVar1 = (worldstateIndex / 31);
	int iVar2 = (worldstateIndex % 31);

	// Global_40.f_283[iVar1]
	UINT64* localWorldStateBitfield = getGlobalPtr(40 + 283 + 1 + iVar1);
	
	if (set) {
		MISC::SET_BIT(localWorldStateBitfield, iVar2);
	} else {
		MISC::CLEAR_BIT(localWorldStateBitfield, iVar2);
	}

	UINT64* g_worldStates_UNK = getGlobalPtr(1934765);
	*g_worldStates_UNK = 0;
}


enum class WorldState
{
	WB_DISCO_ALCHEMIST_HOUSE = 29,
	WS_ANNES_SETTLERS_CLOSED_OFF = 240,
	WS_ANTENOR_DOCKED = 266,
	WS_ARMADILLO_LOCKDOWN_SALOON = 144,
	WS_ARMADILLO_LOCKDOWN_SALOON_DOORS = 145,
	WS_BACCHUS_BRIDGE_DESTROYED = 260,
	WS_BEAVER_HOLLOW_HIDEOUT = 116,
	WS_BEECHERS_BARN_FINISHED = 184,
	WS_BEECHERS_CAMP_WITH_RUBBLE = 181,
	WS_BEECHERS_CAMP_WITH_SHACK = 180,
	WS_BEECHERS_CAMP_WITH_SUPPLIES = 182,
	WS_BEECHERS_HOUSE_ABIGAIL3 = 185,
	WS_BEECHERS_HOUSE_DECORATED = 186,
	WS_BEECHERS_HOUSE_FINISHED = 183,
	WS_BEECHERS_HOUSE_FULLY_DECORATED = 187,
	WS_BEECHERS_SHACK = 178,
	WS_BEECHERS_SHACK_WITH_FIRE = 179,
	WS_BGV_SHACK_LADDER_DOWN = 377,
	WS_BLACKWATER_BURIAL = 159,
	WS_BLACKWATER_LOCKDOWN_SALOON = 146,
	WS_BLACKWATER_LOCKDOWN_SALOON_DOORS = 147,
	WS_BLACKWATER_PHOTOGRAPHER_FURNITURE = 379,
	WS_BOOBY_TRAP_GUAMA_01 = 162,
	WS_BOOBY_TRAP_GUAMA_01_END = 163,
	WS_BOOBY_TRAP_ROANOKE_01 = 164,
	WS_BOOBY_TRAP_ROANOKE_01_END = 165,
	WS_BOOBY_TRAP_ROANOKE_02 = 166,
	WS_BOOBY_TRAP_ROANOKE_02_END = 167,
	WS_BRAITHWAITES_3_ACTIVE = 4,
	WS_BRAITHWAITE_MANSION_BURNED = 2,
	WS_BRAITHWAITE_MANSION_ENDLESS_SUMMER = 3,
	WS_BRAITHWAITE_MANSION_INTACT = 1,
	WS_BRONTE_MANSION_CLOSE_SHUTTERS = 247,
	WS_CALIGA_HALL_TABACCO_BURNING = 42,
	WS_CALIGA_HALL_TABACCO_BURNT = 43,
	WS_CALIGA_HALL_TABACCO_DURING_MISSION = 41,
	WS_CALIGA_HALL_TABACCO_START = 40,
	WS_CARMODY_DELL_ABANDONED = 54,
	WS_CHELONIAN_CAMP = 239,
	WS_CINCO_TORRES_DOOR_INTACT = 38,
	WS_CLAY_EXIST = 197,
	WS_CLEMENS_POINT_BARREL = 161,
	WS_CLM_DOMINOES_LANTERN = 273,
	WS_COLTER_STAGE_CABIN_BURNING = 45,
	WS_COLTER_STAGE_FIRES_LIT = 46,
	WS_COLTER_STAGE_HIGH_SNOW = 47,
	WS_COLTER_STAGE_MEDIUM_SNOW = 48,
	WS_COLTER_STAGE_MP = 52,
	WS_COLTER_STAGE_MUDTOWN1 = 51,
	WS_COLTER_STAGE_SCHOOL_INTERIOR = 50,
	WS_COLTER_STAGE_THAWED_SNOW = 49,
	WS_COLTER_STAGE_WINTER1_INTRO = 44,
	WS_COOTS_GRAVE_1_DUG = 304,
	WS_COOTS_GRAVE_2_DUG = 305,
	WS_COOTS_GRAVE_FILLED_IN = 306,
	WS_CRASHED_BOAT = 39,
	WS_CRD_CHIMNEY_OFF = 311,
	WS_CRN1_BURNT_BARN = 286,
	WS_DEWCLM_DOMINOES_SEATS = 276,
	WS_DISCO_DEAD_SNAKE = 30,
	WS_DISCO_LOVE_MESSAGE_HEARTLAND = 28,
	WS_DOWNS_RANCH_DOWNS = 5,
	WS_DOWNS_RANCH_EDITH = 6,
	WS_DOWNS_RANCH_EMPTY = 7,
	WS_DOWNS_RANCH_REPOPULATED = 8,
	WS_DROUGHT_ENDED = 31,
	WS_FAST_TRAVEL_MARKERS = 195,
	WS_FEUD1_WATER_TOWER_UP = 372,
	WS_FIN1_BURNT_LADDER = 287,
	WS_FIN1_DISABLE_VANHORN_FIRE = 253,
	WS_FIN2_EXT_P19_FRAMES = 290,
	WS_FLAG_BRONTE_ADD_MP_DRESSING = 248,
	WS_FLAG_BRONTE_ADD_SP_DRESSING = 249,
	WS_FOR_MY_ART_NOBARPROPS = 109,
	WS_FUSSAR2_LIGHTING = 281,
	WS_FUSSAR2_NOCLIMB = 282,
	WS_GRAND_KORRIGAN_DOCKED_INTERIOR = 264,
	WS_GRAND_KORRIGAN_HIDE_ON_WATER = 262,
	WS_GRAND_KORRIGAN_LOW_RAILING = 265,
	WS_GRAND_KORRIGAN_SHOW_DOCKED = 263,
	WS_GRAVE_ARTHUR_BAD = 299,
	WS_GRAVE_ARTHUR_GOOD = 298,
	WS_GRAVE_EAGLE_FLIES = 293,
	WS_GRAVE_HOSEA = 297,
	WS_GRAVE_KIERAN = 294,
	WS_GRAVE_LENNY = 296,
	WS_GRAVE_SEAN = 295,
	WS_GRAVE_SUSAN = 300,
	WS_GRZ_WEST_CAMP_SITE = 277,
	WS_GUARMA3_ARTILLERY_01_DESTROYED = 194,
	WS_GUARMA3_GUARDS_DISABLED = 193,
	WS_GUARMA3_TOWER_DESTROYED = 192,
	WS_GUARMA3_TOWER_FRAG = 191,
	WS_GUARMA3_TOWER_NORMAL = 190,
	WS_GUARMA_EXISTS = 188,
	WS_GUARMA_RUIN1_FLOOR_INTACT = 33,
	WS_HERE_KITTY_3_CLUE_TRAIL_OFF = 200,
	WS_HERE_KITTY_3_CLUE_TRAIL_ON = 201,
	WS_HERE_KITTY_WAGONS_FIXED_NO_CAMP = 206,
	WS_HERE_KITTY_WAGONS_FIXED_WITH_CAMP = 205,
	WS_HERE_KITTY_WAGONS_GONE = 202,
	WS_HERE_KITTY_WAGONS_PART_FIXED = 204,
	WS_HERE_KITTY_WAGONS_TRASHED = 203,
	WS_HIDEOUT_BEAVER_HOLLOW_ENDLESS = 90,
	WS_HIDEOUT_BEAVER_HOLLOW_INACTIVE = 81,
	WS_HIDEOUT_FORT_MERCER_INACTIVE = 82,
	WS_HIDEOUT_HANGING_DOG_ENDLESS = 89,
	WS_HIDEOUT_HANGING_DOG_INACTIVE = 83,
	WS_HIDEOUT_HANGING_DOG_MARSTON4 = 93,
	WS_HIDEOUT_SHADY_BELLE_INACTIVE = 84,
	WS_HIDEOUT_SIX_POINT_INACTIVE = 85,
	WS_HIDEOUT_SIX_POINT_LIGHTS = 92,
	WS_HIDEOUT_SIX_POINT_TABLE = 91,
	WS_HIDEOUT_SMUGGLER_DOCKS_INACTIVE = 86,
	WS_HIDEOUT_THIEVES_LANDING_INACTIVE = 87,
	WS_HIDEOUT_TWIN_ROCKS_INACTIVE = 88,
	WS_HORSESHOE_BARREL = 160,
	WS_HSO_DOMINOES_LANTERN = 274,
	WS_HSO_DOMINOES_SEATS = 302,
	WS_HSO_TABLE_SEATS = 303,
	WS_HUNTING_2_ABANDONED_CAMP = 217,
	WS_INDUSTRY3_POKER_TABLES = 233,
	WS_LAK_BUNKHOUSE_SHOOT_THROUGH = 236,
	WS_LIGHT_ANIMALS_GRIZZLIES = 74,
	WS_LONE_MULE_CELLAR_DOORS_OPEN = 268,
	WS_MAC_CHIMNEY_OFF = 308,
	WS_MEDIUM_ANIMALS_GRIZZLIES = 75,
	WS_MFR_CHIMNEY_OFF = 307,
	WS_MICAH_CAMP = 95,
	WS_MICAH_CAMP_EMPTY = 94,
	WS_MICAH_CAMP_POST = 96,
	WS_MICAH_HIDEOUT = 291,
	WS_MICAH_HIDEOUT_ABANDON = 292,
	WS_MOB3_TROLLEY_DAMAGE = 368,
	WS_MP_BLACKWATER = 216,
	WS_MP_CAMP_DEFEND_GREAT_PLAINS_CIRCLE = 352,
	WS_MP_CAMP_DEFEND_GRIZZLIES_CIRCLE = 351,
	WS_MP_CAMP_DEFEND_HEARTLANDS_CIRCLE = 350,
	WS_MP_CAMP_DEFEND_HEARTLANDS_HILLTOP = 349,
	WS_MP_CAMP_DEFEND_ROANOKE_CIRCLE = 353,
	WS_MP_CAMP_DEFEND_TWO_ROCKS = 354,
	WS_MP_EVENT_AREAS = 214,
	WS_MP_FETCH_OTH_CASTORS = 358,
	WS_MP_FETCH_OTH_MAC = 355,
	WS_MP_FETCH_OTH_SHEPHERDS_RISE = 356,
	WS_MP_FETCH_OTH_TALL_TREES = 357,
	WS_MP_HIDEOUT_ABANDONED_MINING_STATION = 326,
	WS_MP_HIDEOUT_BEAVER_HOLLOW = 315,
	WS_MP_HIDEOUT_CHOLLA_SPRINGS = 339,
	WS_MP_HIDEOUT_CLEMENS_COVE = 328,
	WS_MP_HIDEOUT_COLTER = 325,
	WS_MP_HIDEOUT_CUERA_SECO = 334,
	WS_MP_HIDEOUT_CUMBERLAND_FALLS = 322,
	WS_MP_HIDEOUT_FARMHOUSE = 317,
	WS_MP_HIDEOUT_FORT_RIGGS = 323,
	WS_MP_HIDEOUT_HANGING_DOG = 314,
	WS_MP_HIDEOUT_LAKAY = 313,
	WS_MP_HIDEOUT_MANTECA_FALLS = 335,
	WS_MP_HIDEOUT_MILLESANI_CLAIM = 316,
	WS_MP_HIDEOUT_MOSSY_FLATS = 318,
	WS_MP_HIDEOUT_OLD_BACCHUS_PLACE = 340,
	WS_MP_HIDEOUT_QUAKERS_COVE = 320,
	WS_MP_HIDEOUT_RATTLESNAKE_HOLLOW = 336,
	WS_MP_HIDEOUT_REPENTANCE = 337,
	WS_MP_HIDEOUT_ROCKY_SEVEN = 331,
	WS_MP_HIDEOUT_SEA_OF_CORONADO = 338,
	WS_MP_HIDEOUT_SHIP_ROCK = 330,
	WS_MP_HIDEOUT_SOLOMONS_FOLLY = 332,
	WS_MP_HIDEOUT_STILLWATER_STRANDS = 324,
	WS_MP_HIDEOUT_TALL_TREES = 329,
	WS_MP_HIDEOUT_THE_LOFT = 321,
	WS_MP_HIDEOUT_TWIN_ROCKS = 333,
	WS_MP_INTRO_HIDEOUT_BLACKWATER = 347,
	WS_MP_INTRO_HIDEOUT_RHODES = 345,
	WS_MP_INTRO_HIDEOUT_TUMBLEWEED = 348,
	WS_MP_INTRO_HIDEOUT_VALENTINE = 346,
	WS_MP_INTRO_JESSICA_CAMP_BLACKWATER = 343,
	WS_MP_INTRO_JESSICA_CAMP_RHODES = 341,
	WS_MP_INTRO_JESSICA_CAMP_TUMBLEWEED = 344,
	WS_MP_INTRO_JESSICA_CAMP_VALENTINE = 342,
	WS_MP_LAKAY = 215,
	WS_MP_PROPERTY_LOCATIONS = 53,
	WS_MP_SDS_WELL_COVER = 360,
	WS_MP_STRAWBERRY_DR_MILO = 213,
	WS_MP_VALENTINE_AMBIENT = 212,
	WS_NATIVE1_ARMY_CAMP = 370,
	WS_NATIVE1_COH_DESTROYED = 369,
	WS_NATIVE_SON2_TREE_FALLEN = 102,
	WS_NBD1_ABANDONED_BUILDING_INTERIOR = 229,
	WS_NBX_ART_EXHIBIT_CANCELLED = 108,
	WS_NBX_ART_EXHIBIT_OPEN = 107,
	WS_NBX_ART_RC_MASON_PASSED = 110,
	WS_NBX_BUILDING_FUNDED = 112,
	WS_NBX_MAUSOLEUM_PLUNDERED = 111,
	WS_NEW_COM_BANK_AFTER = 226,
	WS_NEW_COM_BANK_BEFORE = 223,
	WS_NEW_COM_BANK_POST = 227,
	WS_NEW_COM_BANK_SHOOTOUT = 225,
	WS_NEW_COM_BANK_START = 224,
	WS_NEW_COM_BANK_VAULT_RF = 228,
	WS_NEW_GAR_BRON_MPCOVER_01 = 359,
	WS_NEW_MRK_04_HIDEFORIND3 = 267,
	WS_NORMAL_ANIMALS_GRIZZLIES = 76,
	WS_NO_ANIMALS_GRIZZLIES = 73,
	WS_NO_OIL_DELIVERY_WAGONS = 312,
	WS_OLDFORTWALLACE_WALL_BROKEN = 37,
	WS_OLDFORTWALLACE_WALL_BROKEN_NTS3 = 36,
	WS_OLDFORTWALLACE_WALL_INTACT = 34,
	WS_OLDFORTWALLACE_WALL_INTACT_NTS3 = 35,
	WS_ON_THE_RUN_SHACK_HELPED_CONVICT = 270,
	WS_ON_THE_RUN_SHACK_REWARD_FOUND = 271,
	WS_ORCHIDS_APPLESEED = 79,
	WS_PAI_CHIMNEY_OFF = 310,
	WS_PHONOGRAPH_BOAT_FOUND = 374,
	WS_POISONED_WELL_BLOCKED_ENTRY = 371,
	WS_POST_CARAVAN_BEAVERHOLLOW = 365,
	WS_POST_CARAVAN_CLEMENS = 363,
	WS_POST_CARAVAN_HORSESHOE = 362,
	WS_POST_CARAVAN_SHADY = 364,
	WS_PRONGHORN_GEDDES_UNAVAILABLE = 196,
	WS_PRONGHORN_RANCH_BURNED = 177,
	WS_PRONGHORN_RANCH_EMPTY = 174,
	WS_PRONGHORN_RANCH_EXIST = 175,
	WS_PRONGHORN_RANCH_FENCE_FIXED = 176,
	WS_RARE_FISH_CABIN_END = 80,
	WS_RE_MUC_KNIFE_SCENE = 232,
	WS_RE_MUC_ROCK_SCENE = 231,
	WS_RE_MUC_TREE_SCENE = 230,
	WS_RE_SP_SAVAGEWARNING_01 = 284,
	WS_RE_SP_SAVAGEWARNING_02 = 285,
	WS_RHODES_BANK_LIGHTS_OFF = 64,
	WS_RHODES_BANK_WALL_INTACT = 278,
	WS_RHODES_BURIAL = 158,
	WS_RHODES_ENDLESS_SUMMER = 67,
	WS_RHODES_FENCE_OPEN = 261,
	WS_RHODES_GRAVE_FRESHLY_DUG = 56,
	WS_RHODES_GRAVE_NORMAL = 55,
	WS_RHODES_GRAVE_OPEN = 57,
	WS_RHODES_GRAYS3_COVER_ON = 58,
	WS_RHODES_GUNSMITH_FIRE_OFF = 66,
	WS_RHODES_JAIL_INTACT = 234,
	WS_RHODES_LOCKDOWN_SALOON = 148,
	WS_RHODES_LOCKDOWN_SALOON_DOORS = 149,
	WS_RHODES_SADIE3_COVER_ON = 59,
	WS_RHODES_SALOON2_GRAVE = 63,
	WS_RHODES_SALOON_POST_BRAITHWAITES = 60,
	WS_RHODES_SALOON_TABLE_DOWN = 62,
	WS_RHODES_SALOON_TABLE_UP = 61,
	WS_RHODES_SHERIFF_LOCKED = 65,
	WS_RHODES_TRELAWNY_WAGON_ABANDONED = 68,
	WS_RIDE_THE_LIGHTNING_BARRELS = 106,
	WS_RIDE_THE_LIGHTNING_CHAIR = 104,
	WS_RIDE_THE_LIGHTNING_WAGON = 105,
	WS_RID_CHIMNEY_OFF = 309,
	WS_ROANOKE_BOOBY_TRAP_HOLES = 283,
	WS_ROCKY_SEVEN_ENDLESS = 32,
	WS_SADIE_BEDROLL = 198,
	WS_SAINTDENIS_BOAT = 250,
	WS_SAINTDENIS_MAGIC_LANTERN_ES = 252,
	WS_SAINT_DENIS_BOATS_FOUND = 376,
	WS_SAINT_DENIS_DOCK_BOATS = 280,
	WS_SAINT_DENIS_DOCK_TRAINS = 279,
	WS_SAINT_DENIS_LOCKDOWN_SALOON = 150,
	WS_SAINT_DENIS_LOCKDOWN_SALOON_DOORS = 151,
	WS_SAINT_DENIS_LOCKDOWN_SALOON_SLUMS = 152,
	WS_SAINT_DENIS_LOCKDOWN_SALOON_SLUMS_DOORS = 153,
	WS_SAINT_DENIS_PHOTOGRAPHER_FURNITURE = 378,
	WS_SAVAGE_AFTERMATH_LAST_WORDS_01 = 168,
	WS_SAVAGE_AFTERMATH_LAST_WORDS_02 = 169,
	WS_SAVAGE_AFTERMATH_LAST_WORDS_03 = 170,
	WS_SAVAGE_AFTERMATH_WEEPING_01 = 171,
	WS_SAVAGE_AFTERMATH_WEEPING_02 = 172,
	WS_SAVAGE_AFTERMATH_WEEPING_03 = 173,
	WS_SEAN_1_CAMP = 367,
	WS_SEAN_1_TENT = 366,
	WS_SERIAL_KILLER_CABIN_OPEN = 103,
	WS_SHADY_BELLE_ABANDON = 119,
	WS_SHADY_BELLE_DOMINO_SEATS = 254,
	WS_SHADY_BELLE_EXTRA_BLOCKER = 120,
	WS_SHADY_BELLE_GANG_0_2 = 118,
	WS_SHADY_BELLE_HIDEOUT = 117,
	WS_SHADY_BELLE_SHUTTERS_CLOSED = 255,
	WS_SHB_DOMINOES_LANTERN = 275,
	WS_SHOWS_SD_MAG_01 = 20,
	WS_SHOWS_SD_MAG_02 = 21,
	WS_SHOWS_SD_MAG_03 = 22,
	WS_SHOWS_SD_MAG_04 = 23,
	WS_SHOWS_SD_MAG_05 = 24,
	WS_SHOWS_SD_MOV_01 = 25,
	WS_SHOWS_SD_MOV_02 = 26,
	WS_SHOWS_SD_MOV_05 = 27,
	WS_SHOWS_SD_VAUD_01 = 9,
	WS_SHOWS_SD_VAUD_02 = 10,
	WS_SHOWS_SD_VAUD_03 = 11,
	WS_SHOWS_SD_VAUD_04 = 12,
	WS_SHOWS_SD_VAUD_05 = 13,
	WS_SHOWS_VAL_MAG_01 = 14,
	WS_SHOWS_VAL_MAG_02 = 15,
	WS_SHOWS_VAL_MAG_03 = 16,
	WS_SHOWS_VAL_MAG_04 = 17,
	WS_SHOWS_VAL_MAG_05 = 18,
	WS_SHOWS_VAL_MAG_CLOSED = 19,
	WS_SISIKA_WINDOW_COVER = 361,
	WS_STD_DOCTORS_OFFICE = 114,
	WS_STD_GALA_BALCONY_HIGH_MEM = 113,
	WS_STD_GAMBLING_DEN = 115,
	WS_STRAWBERRY_HOUSE_STAGE_0 = 241,
	WS_STRAWBERRY_HOUSE_STAGE_1 = 242,
	WS_STRAWBERRY_HOUSE_STAGE_2 = 243,
	WS_STRAWBERRY_HOUSE_STAGE_3 = 244,
	WS_STRAWBERRY_IGNORE_NEM_HOUSE = 246,
	WS_STRAWBERRY_JAIL_IGNORE = 210,
	WS_STRAWBERRY_JAIL_INTACT = 209,
	WS_STRAWBERRY_TOURISTS_ENDLESS_SUMMER = 245,
	WS_SWA_CHAIRS_CINEMATIC = 289,
	WS_SWA_CHAIRS_REGULAR = 288,
	WS_TANNERSREACH_BURNT = 199,
	WS_TAXIDERMY_MARITAL = 77,
	WS_TAXIDERMY_NOTICES = 78,
	WS_THIEVES_LANDING_BOAT = 251,
	WS_THOMAS_DOWNES = 301,
	WS_TRAINROB1_SHOOTOUT = 373,
	WS_TRELAWNY_1_HOUSE_TRASHED = 211,
	WS_TUMBLEWEED_LOCKDOWN_SALOON = 154,
	WS_TUMBLEWEED_LOCKDOWN_SALOON_DOORS = 155,
	WS_UTOPIA_TREE_FALLEN = 99,
	WS_UTOPIA_TREE_MISSION = 98,
	WS_UTOPIA_TREE_STANDING = 97,
	WS_UTOPIA_TREE_STUMP = 100,
	WS_UTP1_COVER01 = 101,
	WS_VALENTINE_AUCTION_GATES_OPEN = 72,
	WS_VALENTINE_BANK_SHUTTERS_CLOSED = 257,
	WS_VALENTINE_BANK_WINDOWS = 123,
	WS_VALENTINE_BURIAL_DRUNK = 126,
	WS_VALENTINE_BURIAL_MURDER = 125,
	WS_VALENTINE_BURIAL_POST_DRUNK = 128,
	WS_VALENTINE_BURIAL_POST_MURDER = 127,
	WS_VALENTINE_BUTCHER_ACTIVE = 259,
	WS_VALENTINE_GENSTORE_ACTIVE = 258,
	WS_VALENTINE_GENSTORE_LIGHTS_OFF = 71,
	WS_VALENTINE_HOTEL_CURTAINS_MUD3 = 129,
	WS_VALENTINE_JAIL_INTACT = 235,
	WS_VALENTINE_LOCKDOWN_BANK = 131,
	WS_VALENTINE_LOCKDOWN_DOCTOR = 132,
	WS_VALENTINE_LOCKDOWN_GENERAL_STORE = 133,
	WS_VALENTINE_LOCKDOWN_GUNSMITH = 134,
	WS_VALENTINE_LOCKDOWN_HOTEL = 135,
	WS_VALENTINE_LOCKDOWN_JAIL = 136,
	WS_VALENTINE_LOCKDOWN_LAW_OFFICE = 137,
	WS_VALENTINE_LOCKDOWN_RENT = 138,
	WS_VALENTINE_LOCKDOWN_RESTAURANT = 139,
	WS_VALENTINE_LOCKDOWN_SALOON = 140,
	WS_VALENTINE_LOCKDOWN_SALOON_DOORS = 141,
	WS_VALENTINE_LOCKDOWN_SALOON_SLUMS = 142,
	WS_VALENTINE_LOCKDOWN_SALOON_SLUMS_DOORS = 143,
	WS_VALENTINE_MAGIC_LANTERN_DOOR = 122,
	WS_VALENTINE_POKER_LESS_CHAIRS = 70,
	WS_VALENTINE_RES_CURTAINS_CLOSED = 256,
	WS_VALENTINE_SALOON_BED_BLOODY = 130,
	WS_VALENTINE_SALOON_WINDOWS = 124,
	WS_VALENTINE_SHOOTOUT = 238,
	WS_VALENTINE_SHOOTOUT_START = 237,
	WS_VALENTINE_WAGON = 121,
	WS_VANHORN_BOATS_FOUND = 375,
	WS_VAN_HORN_LOCKDOWN_SALOON = 156,
	WS_VAN_HORN_LOCKDOWN_SALOON_DOORS = 157,
	WS_WAPITI_TENT_OPEN = 272,
	WS_WAR_VETERAN_FISH_TROPHY_ON = 207,
	WS_WAR_VETERAN_WOLF_TROPHY_ON = 208,
	WS_WATSON_GRAVE = 69
};
```