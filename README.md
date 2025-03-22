# ScreenOverlayHandler

I’ve made a ModuleScript that you can use to make a screen overlay and have a function happen in the background. I figured since I probably wasn’t going to use it, that I’d share it here for anyone to use for free. The :Create() function of the ModuleScript takes in a function that is executed after the screen is completely covered. This is good for things like teleportations and cutscenes. There is also a textLabel that is made which can display input text (inputting text is optional). If you don’t input a function, it wont error and the text and all will still run. But why would you not input a function-- that is the entire point of this model: to cover up the screen while stuff happens in the background.

It's also cool that in the script that you calling it from (LocalScript), you can input a function within a function and set that fucntion as the function to be executed and it stills works! 


# ✨ Features
- Creates a smooth overlay animation to cover the screen.
- Executes a function in the background once the screen is fully covered.
- Displays optional overlay text for status updates.
- Start() and Stop() functions for manual animation control.

# 🔧 How to Use
1. Using :Create() to display the overlay, execute a function in the background, and then remove the overlay.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local ScreenOverlayHandler = require(ReplicatedStorage.ScreenOverlayHandler)


script.Parent.Activated:Connect(function()
	ScreenOverlayHandler:Create(function()
		task.wait(10)
		print("DONE")
	end) -- Message is optional
end)
```

2. Using :Start() and :Stop() Manually. For more control, you can use :Start() and :Stop() separately.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")
local Player = Players.LocalPlayer
local Character = Player.Character or Player.CharacterAdded:Wait()
local Humanoid: Humanoid | nil = Character:WaitForChild("Humanoid")

local ScreenOverlayHandler = require(ReplicatedStorage.ScreenOverlayHandler)


script.Parent.Activated:Connect(function()
	ScreenOverlayHandler:Start("Processing...") -- Message is optional
end)

if Humanoid then
	Humanoid.Died:Connect(function()
		-- This stop when player died
		ScreenOverlayHandler:Stop()
	end)
end
```

# 🎭 When to Use ScreenOverlayHandler?
- ✔ During player teleportation.
- ✔ For smooth cutscenes or transitions.
- ✔ To hide sudden background changes for a seamless experience.

# 📝 Changelog
You can check [here](/Changelog.md)