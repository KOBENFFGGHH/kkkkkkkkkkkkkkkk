local ScreenGui = Instance.new("ScreenGui")
local OpButton = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")
local MainFrame = Instance.new("Frame")
local UICorner_2 = Instance.new("UICorner")
local Frame = Instance.new("Frame")
local ImageLabel = Instance.new("ImageLabel")
local Name1 = Instance.new("TextLabel")
local Teb = Instance.new("TextButton")
local Name2 = Instance.new("TextLabel")
local MAINHEE = Instance.new("ScrollingFrame")
local Toggle = Instance.new("TextButton")
local Frame_2 = Instance.new("Frame")
local UICorner_3 = Instance.new("UICorner")
local Toggle_2 = Instance.new("TextButton")
local ImageLabel_2 = Instance.new("ImageLabel")
local CaButton = Instance.new("ImageButton")
local UICorner_4 = Instance.new("UICorner")
local function MakeDraggable(topbarobject, object)
	local Dragging = nil
	local DragInput = nil
	local DragStart = nil
	local StartPosition = nil

	local function Update(input)
		local Delta = input.Position - DragStart
		local pos = UDim2.new(StartPosition.X.Scale, StartPosition.X.Offset + Delta.X, StartPosition.Y.Scale, StartPosition.Y.Offset + Delta.Y)
		local Tween = TweenService:Create(object, TweenInfo.new(0.15), {Position = pos})
		Tween:Play()
	end

	topbarobject.InputBegan:Connect(
		function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				Dragging = true
				DragStart = input.Position
				StartPosition = object.Position

				input.Changed:Connect(
					function()
						if input.UserInputState == Enum.UserInputState.End then
							Dragging = false
						end
					end
				)
			end
		end
	)

	topbarobject.InputChanged:Connect(
		function(input)
			if
				input.UserInputType == Enum.UserInputType.MouseMovement or
				input.UserInputType == Enum.UserInputType.Touch
			then
				DragInput = input
			end
		end
	)

	UserInputService.InputChanged:Connect(
		function(input)
			if input == DragInput and Dragging then
				Update(input)
			end
		end
	)
end
ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
OpButton.Name = "OpButton"
OpButton.Parent = ScreenGui
OpButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
OpButton.BorderColor3 = Color3.fromRGB(0, 0, 0)
OpButton.BorderSizePixel = 0
OpButton.Position = UDim2.new(0.0108843585, 0, 0.334261835, 0)
OpButton.Size = UDim2.new(0.0817861035, 0, 0.144301727, 0)
OpButton.Image = "http://www.roblox.com/asset/?id=15640661640"
UICorner.CornerRadius = UDim.new(0, 10)
UICorner.Parent = OpButton

MainFrame.Name = "MainFrame"
MainFrame.Parent = OpButton
MainFrame.BackgroundColor3 = Color3.fromRGB(44, 44, 44)
MainFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
MainFrame.BorderSizePixel = 0
MainFrame.Position = UDim2.new(9.74600029, 0, -1.86899996, 0)
MainFrame.Size = UDim2.new(-7.61650181, 0, 4.82575703, 0)
UICorner_2.Parent = MainFrame
MakeDraggable(MainFrame,MainFrame)
Frame.Parent = MainFrame
Frame.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0.00185485359, 0, -6.103636e-08, 0)
Frame.Size = UDim2.new(0.204256698, 0, 1.00000012, 0)

ImageLabel.Parent = Frame
ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel.BackgroundTransparency = 1.000
ImageLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
ImageLabel.BorderSizePixel = 0
ImageLabel.Position = UDim2.new(0.280970544, 0, 1.52590882e-08, 0)
ImageLabel.Size = UDim2.new(0.424838603, 0, 0.115362085, 0)
ImageLabel.Image = "http://www.roblox.com/asset/?id=16663324629"

Name1.Name = "Name1"
Name1.Parent = Frame
Name1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Name1.BackgroundTransparency = 1.000
Name1.BorderColor3 = Color3.fromRGB(0, 0, 0)
Name1.BorderSizePixel = 0
Name1.Position = UDim2.new(0, 0, 0.112002164, 0)
Name1.Size = UDim2.new(1.00514603, 0, 0.104002036, 0)
Name1.Font = Enum.Font.SourceSans
Name1.Text = "Attack Hub"
Name1.TextColor3 = Color3.fromRGB(255, 255, 255)
Name1.TextScaled = true
Name1.TextSize = 14.000
Name1.TextWrapped = true

Teb.Name = "Teb"
Teb.Parent = MainFrame
Teb.BackgroundColor3 = Color3.fromRGB(31, 31, 31)
Teb.BorderColor3 = Color3.fromRGB(0, 0, 0)
Teb.BorderSizePixel = 0
Teb.Position = UDim2.new(0.198425949, 0, 0.256005079, 0)
Teb.Size = UDim2.new(-0.144152284, 0, 0.0800015777, 0)
Teb.Font = Enum.Font.SourceSans
Teb.Text = "Ganeral"
Teb.TextColor3 = Color3.fromRGB(255, 255, 255)
Teb.TextScaled = true
Teb.TextSize = 14.000
Teb.TextWrapped = true

Name2.Name = "Name2"
Name2.Parent = Teb
Name2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Name2.BackgroundTransparency = 1.000
Name2.BorderColor3 = Color3.fromRGB(0, 0, 0)
Name2.BorderSizePixel = 0
Name2.Position = UDim2.new(2.41733241, 0, -3.20000005, 0)
Name2.Size = UDim2.new(1.85672653, 0, 1.39999998, 0)
Name2.Font = Enum.Font.SourceSans
Name2.Text = "Main"
Name2.TextColor3 = Color3.fromRGB(255, 255, 255)
Name2.TextScaled = true
Name2.TextSize = 14.000
Name2.TextWrapped = true

MAINHEE.Name = "MAINHEE"
MAINHEE.Parent = MainFrame
MAINHEE.Active = true
MAINHEE.BackgroundColor3 = Color3.fromRGB(118, 118, 118)
MAINHEE.BorderColor3 = Color3.fromRGB(0, 0, 0)
MAINHEE.BorderSizePixel = 0
MAINHEE.Position = UDim2.new(0.20611164, 0, 0.115362078, 0)
MAINHEE.Size = UDim2.new(0.792033374, 0, 0.884637833, 0)

Toggle.Name = "Toggle"
Toggle.Parent = MAINHEE
Toggle.BackgroundColor3 = Color3.fromRGB(22, 22, 22)
Toggle.BorderColor3 = Color3.fromRGB(22, 22, 22)
Toggle.BorderSizePixel = 0
Toggle.Position = UDim2.new(0.0592296682, 0, 0.0442268699, 0)
Toggle.Size = UDim2.new(0.880974472, 0, 0.0636212975, 0)
Toggle.Font = Enum.Font.SourceSans
Toggle.Text = "Auto Parry"
Toggle.TextColor3 = Color3.fromRGB(255, 255, 255)
Toggle.TextScaled = true
Toggle.TextSize = 14.000
Toggle.TextWrapped = true
Toggle.TextXAlignment = Enum.TextXAlignment.Right

Frame_2.Parent = Toggle
Frame_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame_2.BorderSizePixel = 0
Frame_2.Position = UDim2.new(0.0281717163, 0, 0.0314361565, 0)
Frame_2.Size = UDim2.new(0.100000001, 0, 0.945866168, 0)

UICorner_3.CornerRadius = UDim.new(0, 50)
UICorner_3.Parent = Frame_2

Toggle_2.Name = "Toggle"
Toggle_2.Parent = Toggle
Toggle_2.BackgroundColor3 = Color3.fromRGB(22, 22, 22)
Toggle_2.BorderColor3 = Color3.fromRGB(22, 22, 22)
Toggle_2.BorderSizePixel = 0
Toggle_2.Position = UDim2.new(-0.00313014281, 0, 0.0314361565, 0)
Toggle_2.Size = UDim2.new(1.00000107, 0, 1.00000095, 0)
Toggle_2.Visible = false
Toggle_2.Font = Enum.Font.SourceSans
Toggle_2.Text = "Auto Parry"
Toggle_2.TextColor3 = Color3.fromRGB(255, 255, 255)
Toggle_2.TextScaled = true
Toggle_2.TextSize = 14.000
Toggle_2.TextWrapped = true
Toggle_2.TextXAlignment = Enum.TextXAlignment.Right

ImageLabel_2.Parent = Toggle_2
ImageLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel_2.BackgroundTransparency = 1.000
ImageLabel_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
ImageLabel_2.BorderSizePixel = 0
ImageLabel_2.Position = UDim2.new(-0.0283434894, 0, -0.377676725, 0)
ImageLabel_2.Size = UDim2.new(0.217865303, 0, 1.72662711, 0)
ImageLabel_2.Image = "http://www.roblox.com/asset/?id=16984390747"

CaButton.Name = "CaButton"
CaButton.Parent = MainFrame
CaButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
CaButton.BorderColor3 = Color3.fromRGB(0, 0, 0)
CaButton.BorderSizePixel = 0
CaButton.Position = UDim2.new(-0.271407455, 0, 0.37200737, 0)
CaButton.Size = UDim2.new(0.161165893, 0, 0.250630438, 0)
CaButton.Image = "http://www.roblox.com/asset/?id=15640661640"

UICorner_4.CornerRadius = UDim.new(0, 10)
UICorner_4.Parent = CaButton

-- Scripts:

local function HBCQXY_fake_script() -- Toggle_2.LocalScript 
	local script = Instance.new('LocalScript', Toggle_2)

	script.Parent.MouseButton1Click:Connect(function()
		script.Parent.Parent.Toggle.Visible = false
	end)
end
coroutine.wrap(HBCQXY_fake_script)()
local function LDVVZ_fake_script() -- Toggle.LocalScript 
	local script = Instance.new('LocalScript', Toggle)

	script.Parent.MouseButton1Click:Connect(function()
		script.Parent.Toggle.Visible = true
	end)
end
coroutine.wrap(LDVVZ_fake_script)()
local function IXNE_fake_script() -- CaButton.LocalScript 
	local script = Instance.new('LocalScript', CaButton)

	function NTR ()
		script.Parent.Parent.Parent.MainFrame.Visible = false
	end
	script.Parent.MouseButton1Click:Connect(NTR)
end
coroutine.wrap(IXNE_fake_script)()
local function LYDQVOH_fake_script() -- OpButton.LocalScript 
	local script = Instance.new('LocalScript', OpButton)

	function MN ()
		script.Parent.MainFrame.Visible = true
	end
	script.Parent.MouseButton1Click:Connect(MN)
end
coroutine.wrap(LYDQVOH_fake_script)()
