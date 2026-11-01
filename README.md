# echo-speaks-server
## Why this fork (howarddavidp)

This fork exists to stop the biweekly Amazon session drop / login wipe that hits the original tonesto7 echo-speaks-server when cookie refresh fails.

**What the fix does (plain terms):** if refreshing the Amazon cookie fails, the server **keeps the existing session** instead of clearing Hubitat auth and restarting. It returns `kept_existing`, backs off and retries, and hardens the Amazon register path when Amazon rejects an expired token. Details are in `PATCHES.md` and release **v2.8.1-grokbot**.

**Intended use:** run this as the local (non-Heroku) cookie server for Hubitat Echo Speaks — for example at `http://192.168.50.35:8091` — and point the Hubitat Echo Speaks app at that URL. Pair with the Hubitat package fork [howarddavidp/echo-speaks](https://github.com/howarddavidp/echo-speaks) when you also need the HTTPS auth-redirect fix.

