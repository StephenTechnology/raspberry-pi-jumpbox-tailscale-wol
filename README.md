# Raspberry Pi jumpbox
- A RPi build that allows secure external SSH for the purpose of WOL my host server

## Architecture
- Laptop > Tailsacle network > Raspberry Pi > Host server

## Tech Used
- Raspberry Pi zero w 2 (Low power and alsways on)
- Tailscale (Used to work around my ISPs CGNAT)
- SSH (WOL had to come from inside my network so SSH made sense)
- Etherwake (Preinstalled WOL app in Raspbian)

## Key Configuration
- External SSH is only allowed for a single user and uses an authentication key only on my laptop
- Shell is disabled and the SSH session is terminated immediatley after the WOL request is sent
- SSH is also only available from devices in my Tailscale network, which is my Laptop and the PI

## Outcome
- It has been working as expected so far although there were some issues along the way
- Would like to add a notification to say the WOL was sent before the SSH is termincated. Currently the session ends and then I can reach TrueNas on my host a few minutes after
