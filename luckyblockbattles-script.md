
local gui = Instance.new("ScreenGui")
gui.Name = "DraggableGUI"
gui.Parent = game.Players.LocalPlayer.PlayerGui


local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 500, 0, 100)
frame.Position = UDim2.new(0.5, -100, 0.5, -50)
frame.BackgroundColor3 = Color3.new(20, 20, 20)
frame.BorderSizePixel = 0
frame.Active = true
frame.Draggable = true
frame.Parent = gui

local button2 = Instance.new("TextButton")
button2.Size = UDim2.new(0, 120, 0, 30)
button2.Position = UDim2.new(0.4, 0, 0.5, -15)
button2.Text = "spawn Rainbow block"
button2.Parent = frame

local button3 = Instance.new("TextButton")
button3.Size = UDim2.new(0, 120, 0, 30)
button3.Position = UDim2.new(0.7, 0, 0.5, -15)
button3.Text = "spawn Galaxy block"
button3.Parent = frame

local button1 = Instance.new("TextButton")
button1.Size = UDim2.new(0, 30, 0, 30)
button1.Position = UDim2.new(0.1, 0, 0.5, -15)
button1.Text = "X"
button1.Parent = frame

local button4 = Instance.new("TextButton")
button4.Size = UDim2.new(0, 30, 0, 30)
button4.Position = UDim2.new(0.2, 0, 0.5, -15)
button4.Text = "clear"
button4.Parent = frame


button1.MouseButton1Click:Connect(function()
 
local gui = game.Players.LocalPlayer.PlayerGui:FindFirstChild("DraggableGUI")
if gui then

    gui:Destroy()
    print("GUI removed.")
else
    print("GUI not found.")
end

end)

button2.MouseButton1Click:Connect(function()
    game:GetService("ReplicatedStorage"):WaitForChild("SpawnRainbowBlock"):FireServer()
end)

button3.MouseButton1Click:Connect(function()
    game:GetService("ReplicatedStorage"):WaitForChild("SpawnGalaxyBlock"):FireServer()
end)

button4.MouseButton1Click:Connect(function()
   for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
v:Destroy()
end
end)
