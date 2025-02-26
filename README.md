# rolibwaita

* This is a fork of a [codeberg.org repository](https://codeberg.org/Blukez/rolibwaita) to add new features and fix issues.
A Roblox user interface library that looks like [gnome.](https://www.gnome.org/)
Please feel free to create a pull request or submit an issue.

## Documentation

### Booting the library

Place this at the top of your code.
```lua
local rolibwaita = loadstring(game:HttpGet("https://raw.githubusercontent.com/mlnitoon2/rolibwaita/refs/heads/main/Source.lua"))()
```

### Creating a window

```lua
local Window = rolibwaita:NewWindow({
    Name = "Window Example", -- Name of window | string, required
    Keybind = "RightShift", -- Keybind to open and close this window | string, required
    UseCoreGui = false, -- Whether to use coregui / gethui as the gui parent | bool, optional
    PrintCredits = true -- Whether to print ui library credits and info in the console | bool, optional
})
```

See [this](https://create.roblox.com/docs/reference/engine/enums/KeyCode) for info on the keybind argument.

### Remove an element

**This works on ALL elements.**
```lua
Element:Remove()
```

### Create a tab

```lua
local Tab = Window:NewTab({
    Name = "Tab Example", -- Name of the tab | string, required
    Icon = "rbxassetid://1234" -- Icon for the tab button | string, optional
})
```

See [this](https://create.roblox.com/docs/projects/assets) for info on rbxassetids.

### Edit an element

**This works on ALL elements.** Just remake your element, for example:
```lua
Tab:Edit({
    Name = "Tab Example", -- Name of the tab | string, optional
    Icon = "rbxassetid://1234" -- Icon for the tab button | string, optional
})
```

### Create a separator

```lua
local separator = Window:NewSeparator()
```

A separator is just a line inbetween tab buttons, only for stylistic purposes, example:
```lua
local Tab1 = Window:NewTab({
	Name = "Tab Example", -- Name of the tab | string, required
	Icon = "rbxassetid://1234" -- Icon for the tab button | string, optional
})

local separator = Window:NewSeparator()

local Tab2 = Window:NewTab({
	Name = "Tab Example 2", -- Name of the tab | string, required
	Icon = "rbxassetid://1234" -- Icon for the tab button | string, optional
})
```

> [!TIP]
> Separators can be helpful to organize your UI if you have a lot of tabs.

### Create a section

```lua
local Section = Tab:NewSection({
    Name = "Section Example", -- Name of the section | string, required
    Description = "Description Example", -- Description of the section | string, optional 
})
```
Sections are in the central part of the UI, containing buttons, toggles, sliders, etc

### Create a button

```lua
local Button = Section:NewButton({
    Name = "Example Button", -- Name of the button | string, required
    Description = "Example Description",  -- Description of the button | string, optional 
    Callback = function(value) -- code executed on interaction with the element | function,  optional

    end,
})
```

### Create a toggle

```lua
local Toggle = Section:NewToggle({
    Name = "Example Toggle", -- Name of the toggle | string, required
    Description = "Example Description",  -- Description of the toggle | string, optional 
    CurrentState = true, -- default state of the toggle | bool, optional
    Callback = function(value) -- code executed on interaction with the element | function,  optional

    end,
})
```

### Create a textbox

```lua
local TextBox = Section:NewTextBox({
    Name = "Example TextBox", -- Name of the textbox | string, required
    PlaceholderText = "Text here..", -- placeholder text of the textbox | string, optional
    Text = "Lorem Impulsum", -- text of the textbox | string, optional
    Trigger = "FocusLost", -- trigger that will execute the callback ( FocusLost or TextChanged ) | string, optional
    Callback = function(value) -- code executed on interaction with the element | function,  optional

    end,
})
```

### Create a dropdown

```lua
local Dropdown = Section:NewDropdown({
    Name = "Example Dropdown", -- Name of the dropdown | string, required
    Description = "Example Description",  -- Description of the dropdown | string, optional 
    Choices = {"Option 1", "Option 2"}, -- the choices the user can choose from | table, required
    CurrentState = "Option 1", -- default choice selected | string, required
    Callback = function(value) -- code executed on interaction with the element | function,  optional

    end,
})
```

### Create a slider

```lua
local Slider = Section:NewSlider({
    Name = "Example Slider", -- Name of the slider | string, required
    Description = "Example Description",  -- Description of the slider | string, optional 
    MinMax = {"0", "100"}, -- the minimum and maximum states of the slider | table, required
    Increment = 5, -- the increment the slider increases by | number required
    CurrentValue = 20, -- default value | number, required
    Callback = function(value) -- code executed on interaction with the element | function,  optional

    end,
})
```

### Create a color picker
```lua
local ColorPicker = Section:NewColorPicker({
    Name = "Example ColorPicker", -- Name of the color picker | string, optional
    Description = "Example Description",  -- Description of the color picker | string, optional 
    DefaultColor = Color3.fromRGB(255, 0, 0), -- Default color | Color3, optional
    Callback = function(value) -- Code executed when color is selected | function, optional
        
    end,
})
```
