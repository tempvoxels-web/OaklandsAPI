# OAKLANDS REMOTE DEHASHER

**Usage:**

loadstring(game:HttpGet("https://raw.githubusercontent.com/tempvoxels-web/OaklandsAPI/refs/heads/main/OaklandsRealtimeDehasher"))

local Remote = GetRemote("Original Remote Name")


-- GetRemote is a global function. (after the loadstring)
-- GetRemote returns an objectvalue (hashed remote) that you are able to call like: Remote:FireServer()
-- Check: https://github.com/tempvoxels-web/Oaklands-DEHASHED-REMOTES/blob/main/OaklandsDEHASHED_latest.lua for original (unhashed) remote names.

-- The dehasher will return warnings if there are errors or if the user inputs a wrong type of remote/remote name.
