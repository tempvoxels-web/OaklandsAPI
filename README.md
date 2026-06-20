# Oaklands Remote Dehasher

## Installation

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/tempvoxels-web/OaklandsAPI/refs/heads/main/OaklandsRealtimeDehasher"))()
```

---

## Usage

### GetRemote()
```lua
local Remote = GetRemote("Original Remote Name")
Remote:FireServer()
```

---

## Notes

- `GetRemote(), GetAll() and HashToRemote()` are global functions available after the loadstring executes and fully loads.

- `GetRemote()` Returns an object (and the object class) that can be called with `:FireServer()` or `:InvokeServer()`.
- `GetAll()` Returns a table containing every successfully resolved remote.
- `HashToRemote()` Converts a hashed remote UUID back into its original remote name (also returns class).

- The dehasher output warnings go as followed:
  - The remote name is incorrect
  - An invalid remote type is provided

---

## Reference

- Full list of original (unhashed) remote names [here](https://github.com/tempvoxels-web/Oaklands-DEHASHED-REMOTES/blob/main/OaklandsDEHASHED_latest.lua)

- (Note that the dehasher itself updates from the latest dehashed github repo.)
