# Oaklands Remote Dehasher

## Installation

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/tempvoxels-web/OaklandsAPI/refs/heads/main/OaklandsRealtimeDehasher"))()
```

---

## Usage

### GetRemote()
```lua
local Remote, Class = GetRemote("GetMoney")
Remote:FireServer()

-- Returns:
--
-- Remote = Remote instance inside REM
-- Class = Remote ClassName ("RemoteEvent" or "RemoteFunction")
```

### GetAll()
```lua
local RemoteTable = GetAll()

-- Returns a table containing every successfully resolved remote.
--
-- Example:
-- {
--     GetMoney = {
--         Remote = Instance, -- Remote instance inside REM
--         Class = "RemoteEvent"
--     },
--
--     SellItem = {
--         Remote = Instance, -- Remote instance inside REM
--         Class = "RemoteFunction"
--     }
-- }
--
-- RemoteTable.GetMoney -> Original remote name before hashing
-- RemoteTable.GetMoney.Remote -> Remote instance callable via FireServer() or InvokeServer()
-- RemoteTable.GetMoney.Class -> Remote ClassName ("RemoteEvent" or "RemoteFunction")
```

### HashToRemote()
```lua
local Name, Class = HashToRemote("2frrn4-d32rrfv-34f34f3")

-- Converts a hashed remote UUID back into its original remote name (also returns the class).
--
-- Example:
-- HashToRemote("2frrn4-d32rrfv-34f34f3") -> Name = "GetMoney", Class = "RemoteEvent"
-- HashToRemote("f4jhujf-43fsd-193-fghr-26") -> Name = "AnchorObject", Class = "RemoteFunction"
```

---

## Notes

- `GetRemote(), GetAll() and HashToRemote()` are global functions available after the loadstring executes and fully loads.
<br>

- `GetRemote()` Returns an object (and the object class) that can be called with `:FireServer()` or `:InvokeServer()`.
- `GetAll()` Returns a table containing every successfully resolved remote.
- `HashToRemote()` Converts a hashed remote UUID back into its original remote name (also returns class).
<br>

- The dehasher output warnings go as followed:
  - The remote name is incorrect
  - An invalid remote type is provided
  - A remote was not found or does not exist

---

## Reference

- Full list of original (unhashed) remote names [here](https://github.com/tempvoxels-web/Oaklands-DEHASHED-REMOTES/blob/main/OaklandsDEHASHED_latest.lua)

- (Note that the dehasher itself updates from the latest dehashed github repo.)
