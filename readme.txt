All scripts, descriptions, and sample configs

nuke.py
Large powerful artillery, highly configurable
Requires separate script to give as a reward for a killstreak etc
Cooldowns can be configured so that people have a personal and team cooldown, and those cooldowns are different for nukes that 'fail' and nukes that 'succeed', ie, get kills.
Sample config, can be pasted at the bottom of config.toml and edited:

[nuke]
explosionRadius = 10
maximumExplosionRadius = 50
flatness = 0.0083
shiftness = 131
propogationTime = 1.2
upHeight = 8
downHeight = 2
grenadeAmount = 400
teamSuccessCooldown = 30
playerSuccessCooldown = 30
teamCooldown = 5
playerCooldown = 5
friendlyFire = true
launchTime = 15
warningGlobalInitial = true
warningOnInterval = true
interval = 0.25
warningOnCountdown = false
warningCountdownStart = 2



hashtag.py
Same as the old version, kicks people who have a hashtag (pound sign) (#) in their name when they connect
no configuration, just enable in config.toml


infiniteBlocksAndLimitedGrenades.py
Gives players infinite blocks and more or less than the default amount of grenades, after throwing real grenades duds will be thrown, then the player will die
Sample config to give the player 5 real grenades and 3 duds before forcing suicide:
[grenades]
startingGrenades = 5
duds = 3


killstreak.py
A system to give players rewards such as a nuke 
No config.toml options, but customization is done within the python file right now.
To configure, line #4 of killstreak.py contains 

rewards = [[14, 7, 1, "nukesAvailable", "You have been given a nuke"]]

This reward gives the player 1(one) nuke at 14 kills, and 1(one) nuke every 7 after that.
the structure of this is 

Kills, loop, amount rewarded, connection stat rewarded, reward message

To add more streaks, expand the array and fill it with the correct data


regen.py
Functions exactly like the old regen.py, which added a COD style out of combat healing except cleaner code and more predictable
Configure options include the delay to start regenerating, and once regen is activated the speed and amount of the heal
For an almost immediate very fast heal:

[regen]
regenDelay = 5.0
healSpeed = 0.01
healAmount = 1.0

superGrenade.py
Allows for the next grenade to cause a much bigger explosion
Config options for the radius of the explosion and the amount of extra grenades spawned, recommended settings:

[superGrenade]
explosionRadius = 2.5
grenadeAmount = 50


spawnProtection.py
gives players invulnerability when they spawn for a set period of time
Config allows setting the time invulnerable:

[spawnProtection]
protectionTime = 5


Tag.py
Gamemode for Tag
Recommend a max player count of 17, higher numbers may break at the moment.

[tag]
safeTime = 5
shotsTag = false
pointsEveryXSeconds = 5
taggerTime = 30