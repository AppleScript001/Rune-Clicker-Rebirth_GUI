local Material = loadstring(game:HttpGet("https://raw.githubusercontent.com/Kinlei/MaterialLua/master/Module.lua"))()
local X = Material.Load({
	Title = "🍀 Rune Clicker Rebirth 🍀",
	Style = 2,
	SizeX = 320,
	SizeY = 320,
	Theme = "Dark",
	ColorOverrides = {
		MainFrame = Color3.fromRGB(0,9,55)
	}
})

local Y = X.New({
	Title = "Main"
})
Y.Dropdown({
    Text = "Select | Runes",
    Callback = function(t)
        Rune = t
    end,
    Options = {
            "Rarity [Rune]",
            "DeepSea [Rune]",
            "HiddenDeepSea [Rune]",
            "HotSand [Rune]",
            "Secret [Rune]",
    },
})
Y.Toggle({
	Text = "Auto Rune/Roll",
	Callback = function(Value)
	_G.Rune = Value
	while _G.Rune do
	task.wait(0.1)
	if Rune == "Rarity [Rune]" then
		for _,v in pairs(workspace.Runes.RarityRune:GetDescendants()) do
			if v:IsA("TouchTransmitter") then
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
			end
		end
	elseif Rune == "DeepSea [Rune]" then
		for _,v in pairs(workspace.Runes.DeepSeaRune:GetDescendants()) do
			if v:IsA("TouchTransmitter") then
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
			end
		end
	elseif Rune == "HiddenDeepSea [Rune]" then
		for _,v in pairs(workspace.Runes.HiddenDeepSeaRune:GetDescendants()) do
			if v:IsA("TouchTransmitter") then
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
			end
		end
	elseif Rune == "HotSand [Rune]" then
		for _,v in pairs(workspace.Runes.HotSandRune:GetDescendants()) do
			if v:IsA("TouchTransmitter") then
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
			end
		end
	elseif Rune == "Secret [Rune]" then
		for _,v in pairs(workspace.Runes.SecretRune:GetDescendants()) do
			if v:IsA("TouchTransmitter") then
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
			end
		end
	end
end
	end,
	Enabled = false
})
Y.Toggle({
	Text = "Auto Click",
	Callback = function(Value)
	_G.Click = Value
	while _G.Click do
	task.wait()
	game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Click"):FireServer()
	end
	end,
	Enabled = false
})
