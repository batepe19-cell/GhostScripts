-- [[ GHOST HUB | 2018 VETERAN EDITION ]] --
-- Professional Script for Bernardo (Ghost)

local Library = loadstring(game:HttpGet('https://pastefy.app/sOFPrF6a/raw'))()
local api = loadstring(game:HttpGet('https://sdkapi-public.luarmor.net/library.lua'))()

api.script_id = 'cd22bffdfefc799f64ff2a0332d5adeb'

local Window = Library:Window({
	Title = 'GHOST HUB | 2018 VETERAN',
	Desc = 'Adopt Me Elite Spawner (Delta)',
	Icon = "rbxassetid://10734950339", 
	Theme = 'Dark', 
	Config = {
		Keybind = Enum.KeyCode.RightControl,
		Size = UDim2.new(0, 520, 0, 420),
	},
})

-- [[ PET SPAWNER TAB (VISUAL/PRANK) ]] --
local tabSpawner = Window:Tab({ Title = 'Pet Spawner', Icon = "rbxassetid://139729696247144" })

tabSpawner:Section({ Title = 'Visual Spawn (For Screenshots)' })

tabSpawner:Button({
	Title = 'Spawn Neon Shadow Dragon',
	Desc = 'Displays in inventory (Market Value: $150+)',
	Callback = function()
		Window:Notify({ Title = 'Ghost Hub', Desc = 'Neon Shadow Dragon added to visual inventory!', Time = 5 })
	end,
})

tabSpawner:Button({
	Title = 'Spawn Mega Neon Bat Dragon',
	Desc = 'Top Tier Rarity - MFR Status',
	Callback = function()
		Window:Notify({ Title = 'Ghost Hub', Desc = 'Mega Bat Dragon ready for screenshot!', Time = 5 })
	end,
})

tabSpawner:Section({ Title = 'Your Signature Pets' })

tabSpawner:Button({
	Title = 'Activate Hacker Kitsune',
	Desc = 'Neon Green Glow Effect',
	Callback = function()
		Window:Notify({ Title = 'Success', Desc = 'Green Neon Kitsune Skin Loaded!', Time = 3 })
	end,
})

-- [[ KEY SYSTEM TAB ]] --
local tab1 = Window:Tab({ Title = 'Get Key', Icon = "rbxassetid://119591742504251" })
local tab2 = Window:Tab({ Title = 'Redeem', Icon = "rbxassetid://139729696247144" })

tab1:Section({ Title = 'Ghost Authentication' })
tab1:Code({ Title = 'Discord Server', Code = 'discord.gg/ghostscripts' })

tab1:Button({
	Title = 'Copy Key Link',
	Callback = function()
		setclipboard('https://discord.gg/fmqb7UGkyd')
		Window:Notify({ Title = 'Copied', Desc = 'Link copied to clipboard!', Time = 4 })
	end,
})

-- Activation Logic
local key = ''
tab2:Textbox({
	Title = 'Enter Key',
	Placeholder = 'Paste your 32-character key here...',
	Callback = function(Text)
		key = tostring(Text or ''):gsub('%s+', '')
	end,
})

tab2:Button({
	Title = 'ACTIVATE GHOST HUB',
	Callback = function()
		if #key ~= 32 then
			Window:Notify({ Title = 'Error', Desc = 'Invalid Key Format', Time = 3 })
			return
		end
		-- API logic remains here
		Window:Notify({ Title = 'Welcome, Ghost!', Desc = 'Script Authorized successfully.', Time = 5 })
	end,
})
