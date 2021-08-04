local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local colors = {
	SchemeColor = Color3.fromRGB(25, 25, 25),
	Background = Color3.fromRGB(65, 65, 65),
	Header = Color3.fromRGB(34, 34, 34),
	TextColor = Color3.fromRGB(70, 255, 243),
	ElementColor = Color3.fromRGB(44, 44, 44)
}
local Window = Library.CreateLib("CHILL HUB", colors)

local Credits = Window:NewTab("Credits")
local credsection = Credits:NewSection("Credits")
credsection:NewButton("Mika's#0001", "Copy to clipboard", function()
    setclipboard("Mika's#0001")
	game.StarterGui:SetCore("SendNotification", {Title="INFO!"; Text="Copied To ClipBoard"; Duration=3;})
end)
 
credsection:NewButton("Discord Server", "Copy to clipboard", function()
    setclipboard("https://discord.gg/8vw6QbsbKk")
	game.StarterGui:SetCore("SendNotification", {Title="INFO!"; Text="Copied To ClipBoard"; Duration=3;})
end)

--credits ^

local Scripts_tab = Window:NewTab("Scripts")
local scriptsection = Scripts_tab:NewSection("scripts")
scriptsection:NewButton("Pet Simulator X", "petsim", function()
    game.StarterGui:SetCore("SendNotification", {Title="INFO!"; Text="gui hidden"; Duration=3;})
    Library:ToggleUI()
    loadstring(game:HttpGet(('https://raw.githubusercontent.com/Alleexxi/releasedscritps/main/script%20(1).lua'),true))()
end)
scriptsection:NewButton("Bedwars Script", "bedwars", function()
    game.StarterGui:SetCore("SendNotification", {Title="INFO!"; Text="Gui hidden"; Duration=3;})
    Library:ToggleUI()
    loadstring(game:HttpGet("https://gist.githubusercontent.com/DeveloperMikey/2b8ee3d5a38c56c2cc1db72554850384/raw/bedwar.lua", true))()
end)
scriptsection:NewButton("G to activate anime fighting simulator "AFS", function()
    game.StarterGui:SetCore("SendNotification", {Title="INFO!"; Text="Gui hidden"; Duration=3;})
    Library:ToggleUI()
    _G.key = "POLAR_IS_THE_BEST";loadstring(game:HttpGet("https://polarhub.xyz/PolarFreeScript.lua"))()

end)

--localplayer
local Lp = Window:NewTab("LocalPlayer")
local LPsection = Lp:NewSection("Movement")
LPsection:NewSlider("WalkSpeed", "Makes you walk faster", 250, 16, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
LPsection:NewSlider("JumpHeight", "Makes you Jump heigher", 250, 50, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = s
end)

local LPsection = Lp:NewSection("Player")
LPsection:NewKeybind("Noclip", "Makes you walk through walls", Enum.KeyCode.C, function()
	if noclip == false then
        noclip = true
    else
        noclip = false
    end
end)
LPsection:NewButton("Fly Toggle with E", "Makes you Fly", function()
    loadstring(game:HttpGet("https://pastebin.com/raw/7rXZ9VNc", true))()
    game.StarterGui:SetCore("SendNotification", {Title="INFO!"; Text="Re press if you die!"; Duration=3;})
end)


--Scriptsection ^

local Settings = Window:NewTab("Settings")
local settingsection = Settings:NewSection("Settings")
settingsection:NewKeybind("Toggle UI", "toggles ui", Enum.KeyCode.F, function()
	Library:ToggleUI()
end)


--Settings ^
noclip = false
game:GetService('RunService').Stepped:connect(function()
    if noclip then
        game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
    end
end)

