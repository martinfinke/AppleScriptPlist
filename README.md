# AppleScriptPlist

Access Property Lists (.plist) from AppleScript. Use `setProperty(key, value)` to store a key/value pair, and `getProperty(key)` to get a value for a key. Simple as that.

## Usage
1. Put this in your .scpt file (where you want to use plists):
```osascript
-- load the file:
property AppleScriptPlist : load script POSIX file "/path/to/AppleScriptPlist.scpt"
tell AppleScriptPlist
    -- where to store the .plist file:
    set dataFilePath to (path to preferences folder as Unicode text) & "com.your-name.YourAppName.plist"
    -- save a key/value pair in the plist file:
    setProperty("status", "up and running!")
    -- get a value from the plist:
    set myStatus to getProperty("status")
    return myStatus
end tell
```

2. Make BIG CA$H MONEY in the AppleScript industry. Yeeeah.

## Notes
- If the .plist file doesn't exist, an empty one will silently be created whenever you first call `setProperty` or `getProperty`.
