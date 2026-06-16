(written with AI because lazy)

-- OAKLANDS REMOTE DEHASHER - API REFERENCE


-- Get the API (after script loads)
local API = getgenv().OaklandsRemotes

-- ============================================================================
-- API:Get(name)
-- Returns the actual remote instance (RemoteEvent/RemoteFunction)
-- ============================================================================
local remote = API:Get("BuyButton")
if remote then
    remote:FireServer()
end

-- ============================================================================
-- API:Hash(name)
-- Returns the hash string for a remote name
-- ============================================================================
local hash = API:Hash("BuyButton")
print(hash) -- "0x1a2b3c4d"

-- ============================================================================
-- API:UUID(name)
-- Returns the UUID (child name in REM folder)
-- ============================================================================
local uuid = API:UUID("BuyButton")
print(uuid) -- "Remote_123"

-- ============================================================================
-- API:Salt()
-- Returns the discovered salt string (e.g., "_DEHASHED")
-- ============================================================================
local salt = API:Salt()
print(salt) -- "_DEHASHED"

-- ============================================================================
-- API:All()
-- Returns a table of ALL resolved remotes with details
-- ============================================================================
local all = API:All()
for name, data in pairs(all) do
    print(name, data.hash, data.uuid, data.class)
end

-- Returns:
-- {
--     BuyButton = {
--         hash = "0x1a2b3c4d",
--         uuid = "Remote_123",
--         class = "RemoteFunction"
--     },
--     SellButton = {
--         hash = "0x5e6f7g8h",
--         uuid = "Remote_456",
--         class = "RemoteEvent"
--     }
-- }

-- ============================================================================
-- API:Pending()
-- Returns a list of catalog names still not resolved
-- ============================================================================
local pending = API:Pending()
if #pending > 0 then
    print("Still waiting for:", table.concat(pending, ", "))
end

-- ============================================================================
-- API:Unload()
-- Cleans up the hook and stops all background processes
-- ============================================================================
API:Unload()
-- Hook removed, polling stopped

-- ============================================================================
-- COMPLETE USAGE EXAMPLE
-- ============================================================================
local API = getgenv().OaklandsRemotes

if not API then
    warn("OaklandsRemotes not found!")
    return
end

-- Check what's resolved
local all = API:All()
print("Resolved remotes:", #all)

-- Check what's pending
local pending = API:Pending()
if #pending > 0 then
    print("Pending:", table.concat(pending, ", "))
end

-- Get and use a remote
local buyButton = API:Get("BuyButton")
if buyButton then
    buyButton:FireServer()
end

-- Get UUID
local uuid = API:UUID("BuyButton")
print("UUID:", uuid)

-- Get hash
local hash = API:Hash("BuyButton")
print("Hash:", hash)

-- Get salt
print("Salt:", API:Salt())

-- Iterate all remotes
for name, data in pairs(API:All()) do
    print(string.format("%-30s | %s | %s", name, data.uuid, data.class))
end

-- Clean up when done
-- API:Unload()
