# Summoner
Warlock Summoning tool heavily based on SummonsMonitor addon made by Zayla


Functionnalities :

1 - Small box with nice design. decursive behaviour with ktm look&feel
2 - Free Button to clic to cast a summon with Ayeri macro function in it.

Top bar shows : [(trumpet) a   b/c (-)(x)]
(trumpet) = Announce in raid : Want a summon ? Say : 123
a = Warlocks in raid
b = Summon requests
c = People in different zone than you
(-) = Minimize window to top bar
(x) = Close window
Top bar behaviour : 
Summoning : gets replaced by the casting bar, and then when on Channeling : Reads "Channeling"
Completion : Reads "Complete" with timer bar decreasing in 5s
On Timer ending : Reads "Received"

Bottom bar :
Grow vertically, down, like Decursive. 
populates with names of people asking for summons.
Each individual bar shows :
Name --- Class Icon / Combat Icon (if possible) / Tombstone (if dead - optionnal) / Zone




Announcement model: 

Raid : SendChatMessage("Summoning " .. UnitName("target") .. "", "RAID", nil)
Whisper : SendChatMessage("I'm summoning you", "WHISPER", nil, UnitName("target"))

/raid : Want a summon ? Say : 123

Requests model:

whisper can you summon me ?
sum please
123

useful stuff to add :

/aftercast +done /in 1+ /script if oCB.channeling then BWLCB("5", 'Summon') else SM_INFRAME:Hide() end

/script if not CheckInteractDistance("target", 4) then if not oCB.casting or oCB.channeling then SendChatMessage("Summoning %t", "RAID", nil); CastSpellByName("Ritual of Summoning"); end; end

Zone Checking :

name, rank, subgroup, level, class, fileName, 
  zone, online, isDead, role, isML = GetRaidRosterInfo(raidIndex);

/script for i = 1, GetNumRaidMembers() do local name, _, _, _, _, class, zone, online, isDead = GetRaidRosterInfo(i); message("Player : "..name.." is in "..zone.."") end
