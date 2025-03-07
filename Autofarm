--// GPT HUB - Premium Script para Blox Fruits
--// Criado por ChatGPT

--// Interface Premium (Tema Escuro)
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/0x"))()
local Window = Library:CreateWindow("GPT HUB - Blox Fruits | Tema Escuro")

--// Seções do Menu
local AutoFarmTab = Window:CreateFolder("Auto Farm")
local CombatTab = Window:CreateFolder("Combate")
local TeleportTab = Window:CreateFolder("Teleport")
local ESPTab = Window:CreateFolder("ESP")
local TradeTab = Window:CreateFolder("Auto Trade")
local ExtraTab = Window:CreateFolder("Extras")
local ConfigTab = Window:CreateFolder("Configurações")

--// Auto Farm Melhorado
AutoFarmTab:Toggle("Auto Farm", function(state)
    _G.AutoFarm = state
    while _G.AutoFarm do
        pcall(function()
            local player = game.Players.LocalPlayer
            local character = player.Character
            for _, enemy in pairs(game.Workspace.Enemies:GetChildren()) do
                if enemy:FindFirstChild("Humanoid") and enemy.Humanoid.Health > 0 then
                    character.HumanoidRootPart.CFrame = enemy.HumanoidRootPart.CFrame * CFrame.new(0, 5, 0)
                    wait(0.2)
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Attack")
                end
            end
        end)
        wait(0.5)
    end
end)

--// Auto Buy Frutas (Compra frutas automaticamente)
local Frutas = {"Dragon", "Leopard", "Dough", "Venom", "Shadow", "Control"}
ExtraTab:Dropdown("Escolher Fruta para Comprar", Frutas, function(selectedFruit)
    _G.FrutaSelecionada = selectedFruit
end)

ExtraTab:Toggle("Auto Comprar Fruta", function(state)
    _G.AutoBuyFruit = state
    while _G.AutoBuyFruit do
        pcall(function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFruit", _G.FrutaSelecionada)
        end)
        wait(5)
    end
end)

--// Auto Fish (Farm de peixes raros no mar)
ExtraTab:Toggle("Auto Fish", function(state)
    _G.AutoFish = state
    while _G.AutoFish do
        pcall(function()
            local player = game.Players.LocalPlayer
            local fishingSpot = game.Workspace:FindFirstChild("FishingSpot")
            if fishingSpot then
                player.Character.HumanoidRootPart.CFrame = fishingSpot.CFrame
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartFishing")
            end
        end)
        wait(3)
    end
end)

--// Auto Defense (Desvia de ataques automaticamente)
ExtraTab:Toggle("Auto Desviar de Ataques", function(state)
    _G.AutoDefense = state
    while _G.AutoDefense do
        pcall(function()
            local player = game.Players.LocalPlayer
            local character = player.Character
            for _, projectile in pairs(game.Workspace:GetChildren()) do
                if projectile:IsA("Part") and projectile:FindFirstChild("ProjectileTag") then
                    character.HumanoidRootPart.CFrame = character.HumanoidRootPart.CFrame * CFrame.new(math.random(-10, 10), 0, math.random(-10, 10))
                end
            end
        end)
        wait(0.5)
    end
end)

--// Configuração e Segurança
ConfigTab:Button("Fechar Script", function()
    game.CoreGui["GPT HUB"]:Destroy()
end)

ConfigTab:Button("Discord do GPT HUB", function()
    setclipboard("https://discord.gg/seu-servidor") -- Troque pelo link do seu Discord
end)

