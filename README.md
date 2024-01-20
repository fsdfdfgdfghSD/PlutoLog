# PlutoLog
A small oop logging lib made in 33 lines in [Pluto](https://pluto-lang.org/)

![plutolog](plutolog.png)

<hr>

## Installation
Copy & paste the [plutolog.pluto](src/plutolog.pluto) file in your directory and require it.

```lua
local plutolog <const> = require("src/plutolog")
```

## Features
PlutoLog supports the following log levels:

- trace
- debug
- info
- warn
- error
- fatal

The arguments are separated by tabs.

## Usage
You will need to require and config the class.

```lua
local plutolog <const> = require("src/plutolog")

local Log = new plutolog.PlutoLog(true)

Log:trace("This is a trace message!")
```

There are four configurable options for PlutoLog()

### Colors
Toggle colors using **true** or **false** (Colors are enabled by default). In the above example, we enabled colors.

### File
The second parameter is the file where you want to log the messages, if you dont provide one then it wont write to one.

### Print formatting
You can use a custom format for the printing, the default one is "%s[%-6s%s]%s %s: %s".

### File formatting
You can also use a custom format for the writting-to-file, the default one is "[%-6s%s] %s: %s\n".

## Customizing
You can create, modify, remove log levels because the logic is in the **Modes** table which is exported.

```lua
local plutolog <const> = require("src/plutolog")
plutolog.Modes["print"] = "\27[0m"

local Log = new plutolog.PlutoLog(true)

Log:print("This is a custom log message.")
```