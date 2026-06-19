# Oaklands Remote Dehasher

## Installation

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/tempvoxels-web/OaklandsAPI/refs/heads/main/OaklandsRealtimeDehasher"))()
```

---

## Usage

```lua
local Remote = GetRemote("Original Remote Name")
Remote:FireServer()
```

---

## Notes

- `GetRemote()` is a global function available after the loadstring executes.
- It returns an ObjectValue (hashed remote) that can be called with `:FireServer()` or `:InvokeServer()`.
- The dehasher will output warnings if:
  - The remote name is incorrect
  - An invalid remote type is provided

---

## Reference

- Full list of original (unhashed) remote names [here](https://github.com/tempvoxels-web/Oaklands-DEHASHED-REMOTES/blob/main/OaklandsDEHASHED_latest.lua)

- (Note that the dehasher itself updates from the latest dehashed github repo.)
