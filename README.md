# NameClaimer

NameClaimer is a personal, non-commercial desktop application written in Python that claims a Minecraft Java Edition profile name at the moment it becomes available.

## How it works
- The user signs in their own Microsoft accounts (each owning Java Edition) using the standard Microsoft device code flow.
- Tokens are exchanged through Xbox Live and XSTS, then login_with_xbox, to obtain a Minecraft access token.
- The app uses the Minecraft Services profile endpoints to read the profile and submit a name change request.
- If several of the user's accounts are configured, each sends its own requests through a separate proxy with randomized timing offsets, backing off on rate-limit responses.

## What it does not do
- It does not bypass authentication, licensing or ownership checks.
- It does not modify the game or use accounts the user doesn't own.
- Tokens are stored locally in encrypted form and are only sent to Microsoft, Xbox and Minecraft Services (and, for claim requests, through the user's own proxies).

Personal project, not distributed publicly.
