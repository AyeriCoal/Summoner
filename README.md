1 - Is this in RaidSummon already ?

- Is there a limit to the number of people in the list ?
- Is raidsummon scanning whispers ?

Needs to be added :

2 - GUI : 
- Being able to resize window like swstats
- Each individual bar shows :
	-Name
	-Class Icon or don't change and let Class Color
	-Combat Icon (if possible)
	-Tombstone (if dead - optionnal)
	-Zone
	
Top bar shows : [(trumpet) a   b/c (-)(x)]
(trumpet) = Announce in raid : Want a summon ? Say : 123
- a = Warlocks in raid
- b = Summon requests
- c = People in different zone than you
- (-) = Minimize window to top bar
- (x) = Close window
Replace TopBar by Castbar : 
- Summon cast - Reads : "Casting"
- Summon Channeling - Reads : "Channeling"
- Summon Sent - Decreasing bar (5sec)with : "Sending" 
- Summon Received - Reads : "Received" + Ding sound

3 - Request status from SummonsMonitor to implement if it is not already: 
- Format is:  SummonsList["PlayerName"] is a structure with entries
-   .name
-   .status
-   .warlock
-   .time
- .name is the name of the player
- .status is one of:
-   REQUEST   -- Has requested a summons
-   SUMMONED  -- Has been/is being summoned by a warlock 
-   CLOSE     -- Has requested but is nearby : CheckInteractDistance("target", 4) 
-   OUTZONE   -- Has requested but we are in an instance and they are not in it with us
-   NOTGROUP  -- this person is not in our group
-   MYSELF    -- this person is you... duh
- .warlock is the name of the Warlock we think summoned the player
- .time is the time that the request came in / last status change

Keybind to summon first of the list that you can spam. SUMMONING BOT \o/

4 - Overkill : 
- Once you are summoning, polls every 4 seconds if the cast is still on going and ask for people to come to your coordinates : "I need clickers to summon people @ x,y" then "come click" then repeat
