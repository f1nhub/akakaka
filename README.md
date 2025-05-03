-- Abstração Hub Script
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Player = game.Players.LocalPlayer
local PlayerGui = Player:WaitForChild("PlayerGui")
local RemoteEvents = ReplicatedStorage:WaitForChild("RemoteEvents")

-- Funções utilitárias para o menu
local function createButton(name, func)
    local button = Instance.new("TextButton")
    button.Text = name
    button.Size = UDim2.new(0, 150, 0, 50)
    button.Parent = PlayerGui
    button.MouseButton1Click:Connect(func)
    return button
end

-- Função de notificação ao iniciar o script
local function notifyStart()
    local msg = Instance.new("TextLabel")
    msg.Text = "Sua hora chegou!"
    msg.Size = UDim2.new(0, 300, 0, 100)
    msg.Position = UDim2.new(0.5, -150, 0.5, -50)
    msg.Parent = PlayerGui
    wait(3)
    msg:Destroy()
end

-- Função para farm de XP com a pá selecionada
local function farmXP()
    local bestShovel = "Pá Ultra"  -- Aqui você pode ajustar a pá de acordo com a melhor disponí
