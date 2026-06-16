-- OAKLANDS REMOTE DEHASHER - API REFERENCE -- written with AI cuz lazy

local API = loadstring(game:HttpGet("https://raw.githubusercontent.com/tempvoxels-web/OaklandsAPI/main/Oaklands%20DEHASH%20API.lua"))()

(or API = getgenv().OaklandsRemotes)

-- Returns the actual remote instance
local remote = API:Get("BuyButton")
if remote then remote:FireServer() end

-- Returns the hash string
local hash = API:Hash("BuyButton")

-- Returns the UUID
local uuid = API:UUID("BuyButton")

-- Returns the salt string
local salt = API:Salt()

-- Returns a table of all resolved remotes
local all = API:All()
for name, data in pairs(all) do
    print(name, data.hash, data.uuid, data.class)
end

-- Returns a list of pending remotes
local pending = API:Pending()

-- Cleans up and stops all processes
API:Unload()

-- ============================================================================
-- COMPLETE EXAMPLE
-- ============================================================================

local API = getgenv().OaklandsRemotes
if not API then return end

-- Get a remote
local buy = API:Get("BuyButton")
if buy then
    buy:FireServer()
end

-- Get UUID
print(API:UUID("BuyButton"))

-- Get hash
print(API:Hash("BuyButton"))

-- Get salt
print(API:Salt())

-- Iterate all
for name, data in pairs(API:All()) do
    print(name, data.uuid, data.class)
end

-- Check pending
local pending = API:Pending()
if #pending > 0 then
    print("Pending:", table.concat(pending, ", "))
end

-- Clean up
-- API:Unload()
