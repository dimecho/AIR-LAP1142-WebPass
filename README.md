<p align="center"><img src="img/icon.png?raw=true"></p>

# Cisco Autonomous AP

This is a consent page replacement for Cisco "Web Pass"

Tested with AIR-1142N-A-K9

![Screenshot](img/screenshot.png?raw=true)

![WebPass](img/webpass.png?raw=true)

## Config

After converting into Autonomous Mode:

```
copy tftp://10.0.0.2/consent.html flash:

config t
    ip admission name webpass consent
    ip admission consent-banner file flash:consent.html
    ip admission max-login-attempts 64
end

show ip admission status
reload
```