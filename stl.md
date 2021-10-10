# STL (SSH Tunnel Lib, core library) usage

# writted in go, provides windows, linux and macOS binary

## client side
```
stl connect <port>         -- establishes ssh tunnel
stl disconnect <port>      -- disconnects
stl key                    -- returns ssh publish key(stdout)
stl key renew              -- generates a new pair of key, replace the old one
stl status                 -- sets status (client)
```

## server side
```
stl key add <key>          -- adds a ssh public key (only exec in server side)
stl status [key]           -- gets status(on/off, uptime, reconnect times) according to ssh key (for server), returns all if key is not provided
```

