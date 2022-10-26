# LittleNet
<div align="center">⚠️Repo is in development, EVERYTHING is subject to change, until v1.0.0⚠️</div>
<br>

<p align="center" width="100%">
    <img src="./assets/logo.png">
</p>

> The goal of LittleNet, is to reduce the amount of bandwidth as much as possible.

## Example]
```lua
-- server

local serverToClient = littleNet.new("SerevrToClientEvent")
local clientToServer = littleNet.new("ClientToServer")


serverToClient:FireTo(Player)
serverToClient:FireAll()

serverToClient:OnInvoke(function(Player: Player, ...)
    print(Player, ...)

    return
end)

clientToServer:Connect(function(Player: Player, ...)
    print(Player, ...)
end)

clientToServer:Once(function(Player: Player, ...)
    print(Player, ...)
end)
```

```lua
-- client

local serverToClient = littleNet.new("SerevrToClientEvent")
local clientToServer = littleNet.new("ClientToServer")

clientToServer:Fire()
clientToServer:Invoke()

clientToServer:Invoke():andThen(function(...)
    print(...)
end)

serverToClient:Connect(function(...)
    print(...)
emd)

serverToClient:Once(function(...)
    print(...)
emd)

```