# SourceMod: Free Duels

A plugin that provides a database-backed duel system for players.
How to install ?


Free_duels.cfg in \tf\cfg\sourcemod => Auto generated
free_duels.smx in tf\addons\sourcemod\plugins
free_duels.sp in tf\addons\sourcemod\scripting
free_duels.inc in tf\addons\sourcemod\scripting\include
free_duels.phrases.txt in tf\addons\sourcemod\translations
free_duels_sprites.zip , decompress it and place the 2 sprites in tf\materials\free_duel

Need to work : morecolors.inc


ConVARS:
Code:

    duel_enabled "1"                  // Enable or disable the plugin.
    duel_tag "1"                  // add 'duels' tags.
    duel_immunity 0                // Flag to make duel ? a or b or o or p or q or r or s or t or z , 0 = no flag needed.
     
    duel_type1 "1"                   // Enable or disable `normal` duel (type 1) ?
    duel_type2 "1"                   // Enable or disable `time left` duel (type 2) ?
    duel_type3 "1"                   // Enable or disable `amount of kills` duel (type 3) ?
    duel_class "1"                         // Enable or disable duel with class restriction ?
    duel_godmod "1"                // Enable or disable duel with godmod ?
    duel_headshot "1"               // Enable or disable duel 'only head shot' for sniper ?
     
    duel_classrestrict 0              // 1 = classrestrict by DJ Tsunami, 2 = Max Class (Class Limit) by Nican , 0 = none.
    duel_godmod_flag "a"              // Flag to make godmod duel ? a or b or o or p or q or r or s or t or z , 0 = no flag needed.
    duel_headshot_flag "a"           // Flag to make 'only head shot' duel (sniper) ? a or b or o or p or q or r or s or t or z , 0 = no flag needed.

DataBase:

If you want to use MySQL, copy/paste this in sourcemod/configs/databases.cfg. Replace by your own data.

PHP Code:
 
"duel"
{
            "driver"                          "mysql"
            "host"                            "YourHost"
            "database"                        "YourDatabaseName"
            "user"                            "Login"
            "pass"                            "PassWord"
           //"timeout"                        "0"
           //"port"                           "0"
} 
Else use SQLite and do nothing.



----------------- Be Careful ! ------------------


If you use a Class restriction's plugin, like TF2 Class Restrictions or TF2 MaxClass :
Else if you don't run Class Restriction's plugin : duel_classrectrict 0



FOR server which run TF2 Class Restrictions :

Download, decompress ClassRestric 0.6.1 DJ Tsunami, Free_Duel version.zip and copy/paste the two files in your server. It's the same configs and CVARs as the original, but players in duel with class restriction are immune. Think to change cvar : duel_classrectrict 1
[SIZE=3]Use only this version ClassRestric 0.6.1 DJ Tsunami, Free_Duel version.zip if you run free_duels !


FOR server which run TF2 MaxClass (Class limit) : Just Think to change cvar : duel_classrectrict 2



-------------------------------------------------------------------------




Translations

English : Done
French : Done
Italian : by Petrov

Want more translation ? Give me your translation !

General:-------------------------------------------------------------------------------------------------------

- Player 1 wins if :

    - Player 2 writes !abort;
    - Player 2 changes team;
    - Player 2 disconnects;
    - Player 2 loses duel.


- Player 2 has 20 sec to accept or refuse Player 1 duel thanks to a panel which contain all duel data.

- A duel sprite will be add above dueler head. Only you and your challenger can see it.

- As Spy if you are cloaked, your duel sprite is hidden.




Options:-------------------------------------------------------------------------------------------------------



Possibilities: Scout, Sniper, Soldier, Demoman, Medic, Heavy, Pyro, Spy, Engineer, or ANY (=No class restriction)

Availability: Can be used with all duel Types.

Rules:
- If you tried to change class, you will receive a warning!
- You must !abort duel before change class.





Possibilities: ON - OFF

Availability: Can be used with all duel types BUT Class Restriction option must be as 'Sniper'.

Rules:
- Only head-shots will be recognized.
- You can do body-shots and kill some one, but it won't be recognized.





Possibilities: ON - OFF

Availability: Can be used with all duel types.

Rules:
- You can't hurt/kill other player, except your opponent.
- Players can't hurt/kill you.
- If you tried to take control point or flag, you loose your GodMod option.
- When you exit control point or drop flag, you re-find your GodMod option.
- GodMod player are colored as Blue or Red.
- Your building will be automatically destroyed.
