local library = loadstring(game:GetObjects("rbxassetid://7657867786")[1].Source)()
local Wait = library.subs.Wait -- Only returns if the GUI has not been terminated. For 'while Wait() do' loops

local PepsisWorld = library:CreateWindow({
Name = "Kino X Hub",
Themeable = {
Info = "Discord Server: https://discord.gg/sgBw9AnskA"
}
})

local GeneralTab = PepsisWorld:CreateTab({
Name = "Main"
})

local MiscSection = GeneralTab:CreateSection({
    Name = "Farming"
    })
    MiscSection:AddToggle({
    Name = "Auto Farm",
    Callback = function()loadstring(game:HttpGet('https://raw.githubusercontent.com/Besty191/MAZI-API/main/Fake_Damage.lua'))()
        FakeDamage(1000)
        local CombatFramework = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
        local Camera = require(game.ReplicatedStorage.Util.CameraShaker)
        Camera:Stop()
        coroutine.wrap(function()
            game:GetService("RunService").Stepped:Connect(function()
                if getupvalues(CombatFramework)[2]['activeController'].timeToNextAttack then
                    getupvalues(CombatFramework)[2]['activeController'].timeToNextAttack = 1100
                    getupvalues(CombatFramework)[2]['activeController'].hitboxMagnitude = 10
                    getupvalues(CombatFramework)[2]['activeController']:attack()
                end
            end)
        end)()
    print("Fixed")
    end
})

local GeneralTab = PepsisWorld:CreateTab({
Name = "Island"
})

local MiscSection = GeneralTab:CreateSection({
    Name = "World",
    Side = "left"
    })

    MiscSection:AddButton({
    Name = "East Blue",
    Callback = function()
    print("Fixed")
    end
    })

    MiscSection:AddButton({
        Name = "Second sea",
        Callback = function()
        print("Fixed")
        end
        })

    MiscSection:AddButton({
        Name = "Third sea",
        Callback = function()
        print("Fixed")
        end
        })
