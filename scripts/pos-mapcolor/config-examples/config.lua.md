# config.lua

```lua
Config = {}

Config.MapSettings = {
    fog = false,
    mapColor = true,
    darkMode = true,
}

Config.MapZones = {
    { zone = 0x41332496, 			color = 'brown'},	-- New Hanover Full int
	{ zone = 0x5CD2A36F, 			color = 'black'},	-- New Hanover Full ext	
	{ zone = 0x724E7654, 			color = 'Green'},	-- The Heartlands    (West)
	{ zone = 0x30FAE29B, 			color = 'Green'},	-- Roanoke Ridge  	 (East)	
	{ zone = 0x717F4A96, 			color = 'Green'},  	-- Cumberland Forest (North)
	{ zone = 0x0079B7EE, 			color = 'Green'}, 	-- Valentine Int
	{ zone = 0x2A24C8D9, 			color = 'Green'}, 	-- Valentine Ext
	{ zone = 0x0A8B2CBE, 			color = 'Green'}, 	-- Annesburg Int
	{ zone = 0x9CC09C3D, 			color = 'Green'}, 	-- Annesburg Ext
	{ zone = 0x507B5360, 			color = 'Green'}, 	-- Van Horn	Int
	{ zone = 0x194E52AF, 			color = 'Green'}, 	-- Van Horn Ext
	{ zone = 0x6E7BDAC4, 			color = 'Green'}, 	-- Emerald Ranch Int
	{ zone = 0x13A98173, 			color = 'Green'},  	-- Emerald Ranch Ext
	{ zone = 0xA053D058, 			color = 'Green'},	-- Hunter Butcher Camp	Int
	{ zone = 0xB6831F62, 			color = 'black'}, 	-- Hunter Butcher Camp	Ext
	{ zone = 0x7B23B4C7, 			color = 'Green'}, 	-- Cornwall Kerosene Int
	{ zone = 0x150D72E9, 			color = 'Green'}, 	-- Cornwall Kerosene Ext
	{ zone = 0x1BDD5A12, 			color = 'black'},	-- Fort Wallace Int
	{ zone = 0x2FE84F0E, 			color = 'black'}, 	-- Fort Wallace Ext
	
	-- AMBARINO --
	{ zone = 0x3B8DD21A, 			color = 'white'},	-- Ambarino Full Int
	{ zone = 0x3BBA228A, 			color = 'black'},	-- Ambarino Full Ext
	{ zone = 0xD41D039A, 			color = 'white'},   -- Grizzlies West Int
	{ zone = 0x943198D3, 			color = 'yellow'},	-- Grizzlies East Int
	{ zone = 0xBB785C8A, 			color = 'Green'},	-- Wapiti Camp Int
	{ zone = 0x4F45BE43, 			color = 'Green'}, 	-- Wapiti Camp Ext	

	-- WEST ELIZABETH --
	{ zone = 0xD69B5B49, 			color = 'Grey'},	-- West Elizabeth Full Int
	{ zone = 0xF030C0B2, 			color = 'black'},	-- West Elizabeth Full Ext
	{ zone = 0x763A8A87, 			color = 'white'},   -- Tall Tree	
	{ zone = 0x8DCC574F, 			color = 'white'}, 	-- Big Valley
	{ zone = 0x0E95FF51, 			color = 'white'},	-- Great Plains
	{ zone = 0x5647E155, 			color = 'Green'},	-- Blackwater Int
	{ zone = 0x129E1411, 			color = 'Green'}, 	-- Blackwater Ext	
	{ zone = 0x4663EEB9, 			color = 'Green'}, 	-- Strawberry Int
	{ zone = 0x3B4A5D5B, 			color = 'Green'}, 	-- Strawberry Ext	

	-- LEMOYNE --
	{ zone = 0x945395DF, 			color = 'black'}, 	-- Lemoyne Full Int
	{ zone = 0x0F32B44D, 			color = 'black'},	-- Lemoyne Full Ext	
	{ zone = 0x0BB92EEF, 			color = 'BLUE'}, 	-- Scarlett Meadows
	{ zone = 0x024C01CA, 			color = 'white'}, 	-- BlueWater Marsh East
	{ zone = 0x2843E325, 			color = 'white'}, 	-- Bayou
	{ zone = 0x9652B96E, 			color = 'black'}, 	-- Bayou Lagras Int
	{ zone = 0x049BBBD4, 			color = 'black'},  	-- Bayou Lagras Ext		
	{ zone = 0x2A6CBBA2, 			color = 'Green'}, 	-- Saint Denis Int
	{ zone = 0xC354EAC2, 			color = 'Green'}, 	-- Saint Denis Ext	
	{ zone = 0xD3F2B8A7, 			color = 'Green'}, 	-- Rhodes Int
	{ zone = 0x09FAE063, 			color = 'Green'}, 	-- Rhodes Ext	
	{ zone = 0xD218D90D, 			color = 'white'},   -- Caliga Hall Int
	{ zone = 0xE074391B, 			color = 'white'},	-- Caliga Hall Ext
	{ zone = 0xFC531E7A, 			color = 'Green'},	-- Braith Waite Manor Int
	{ zone = 0x5E68036B, 			color = 'Green'}, 	-- Braith Waite Manor Ext
	{ zone = 0x2D1A7AF2, 			color = 'Red'},		-- Sisika Penitenciary

	-- NEW AUSTIN --
	{ zone = 0x41759831, 			color = 'grey'},    -- New Austin Full Int
	{ zone = 0xD339F6AB, 			color = 'black'},	-- New Austin Full Ext	
	{ zone = 0x3AC128F9, 			color = 'yellow'},	-- TumbleWeed Gaptooth Ridge	
	{ zone = 0xD428627B, 			color = 'orange'}, 	-- Rio Bravo
	{ zone = 0x99B6A1E6, 			color = 'yellow'}, 	-- Cholla Springs
	{ zone = 0x33D88587, 			color = 'yellow'}, 	-- Hennigan's Stead

	-- GUARMA --
	{ zone = 0x9307FD41, 			color = 'Green'},   -- Guarma Full Int
	{ zone = 0x6009F334, 			color = 'black'}, 	-- Guarma Full Ext
	{ zone = 0x95B1E77A, 			color = 'black'}, 	-- Aguasdulces Int	
	{ zone = 0x90CA4AF8, 			color = 'white'}, 	-- Aguasdulces Ext	
	{ zone = 0x6E10D212, 			color = 'black'}, 	-- Village 1 Int
	{ zone = 0x21FE6ED8, 			color = 'white'}, 	-- Village 1 Ext
	{ zone = 0xBBB91AAD, 			color = 'black'}, 	-- Village 2 Int
	{ zone = 0x46837F42, 			color = 'white'}, 	-- Village 2 Ext
	{ zone = 0xC1C68746, 			color = 'black'}, 	-- Guarma Port Int
	{ zone = 0x703A27B1, 			color = 'white'} 	-- Guarma Port Ext
}

-- https://github.com/femga/rdr3_discoveries/tree/master/useful_info_from_rpfs/blip_modifiers
Config.Colors = {
    ['brown'] = 'BLIP_MODIFIER_MP_ENEMY_HOLDING',
    ['black'] = 'BLIP_MODIFIER_SP_DOWNED',
    ['Green'] = 'BLIP_MODIFIER_MP_COLOR_8',
    ['white'] = 'BLIP_MODIFIER_MP_COLOR_32',
    ['yellow'] = 'BLIP_MODIFIER_MP_COLOR_6',
    ['Grey'] = 'BLIP_MODIFIER_MISSION_UNAVAILABLE',
    ['BLUE'] = 'BLIP_MODIFIER_MP_COLOR_25',
    ['orange'] = 'BLIP_MODIFIER_MP_COLOR_4',
    ['Red'] = 'BLIP_MODIFIER_MP_ENEMY_HOLDING'
}
```
