To create a vehicle spawner menu for FiveM, you will need to use the following steps:

First, open your server's server.cfg file and add the following line: start spawnmanager. This will start the spawn manager resource on your server, which is required for spawning vehicles.

Next, create a new resource for your vehicle spawner menu. This can be done by creating a new folder in your server/resources directory, and then creating a __resource.lua file inside it.

In the __resource.lua file, add the following code:

Copy code
resource_manifest_version '44febabe-d386-4d18-afbe-5e627f4af937'
client_scripts {
  'spawnmanager.lua'
}
This will tell the server to start the spawn manager resource and load the spawnmanager.lua script when the resource is started.

In the same resource folder, create a new file called spawnmanager.lua. This is where you will write the code for your vehicle spawner menu.

To create the menu, you will need to use the following code:

Copy code
local vehicles = {}

-- Add the vehicles you want to be able to spawn here
vehicles[1] = {name = "Porsche 911 GT3", model = "gt3"}
vehicles[2] = {name = "Lamborghini Aventador", model = "aventador"}
vehicles[3] = {name = "Bugatti Chiron", model = "chiron"}
vehicles[4] = {name = "Ford Mustang GT", model = "mustanggt"}
vehicles[5] = {name = "McLaren 720S", model = "mclaren720s"}

-- Create the main menu
local mainMenu = Menu("Vehicle Spawner", "Spawn a vehicle")

-- Create a submenu for each vehicle
for i, v in ipairs(vehicles) do
  local subMenu = Menu(v.name, "Spawn this vehicle")
  subMenu:Button("Spawn now", function()
    local player = PlayerId()
    local ped = GetPlayerPed(player)
    local x, y, z = table.unpack(GetEntityCoords(ped, false))
    local vehicle = v.model
    RequestModel(vehicle)
    while not HasModelLoaded(vehicle) do
      Wait(500)
    end
    CreateVehicle(vehicle, x + 2, y + 2, z + 1, GetEntityHeading(ped), true, false)
  end)
  mainMenu:AddSubMenu(subMenu, v.name)
end

-- Create a function to open the menu
function openMenu()
  mainMenu:Visible(not mainMenu:Visible())
end

-- Bind the "F7" key to open the menu
BindMenuButton("F7", openMenu)
This code will create a menu with a list of vehicles, and a button to spawn each one. The menu can be opened by pressing the "F7" key.

Finally, add the following line to your server.cfg file to start your vehicle spawner resource: start [resource name], where [resource name] is the name of your resource folder.
