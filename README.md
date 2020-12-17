![CSGOlogo](https://github.com/ironhack-daft-ray/final_project_CSGO/blob/main/csgo_steampicture.png)

# A strategy guide to pro play in CSGO
*Rayan Hawili - Ironhack DAFT Final Project - December 2020*

---
### PROJECT SUMMARY

**GOAL:**

This project aims to help players upskill their game and make use of data to play at a more pro level in the domains of:
- Map Knowledge
- Strategy
- In-Game Economy Management

**DATA SOURCES:**

Primary first hand data (directly from CSGO developer Valve Corporation) were unobtainable due to GDPR.

Thus secondary hand data had to be made use of. I've utilized as a foundation the data found in this Kaggle [dataset](https://www.kaggle.com/skihikingkevin/csgo-matchmaking-damage) dating from 2018, covering just over 1400 competitive matchmaking matches. The data here was at the time extracted from competitive matchmaking replays submitted to csgo-stats.

**FOLDER CONTENT:**

- [Presentation - PDF](https://github.com/ironhack-daft-ray/final_project_CSGO/blob/main/RH_CSGO_presentation_final_pdf.pdf) -- PDF version of the presentation for quick access
- [Presentation - Keynote](https://github.com/ironhack-daft-ray/final_project_CSGO/blob/main/RH_CSGO_presentation_final.key) -- presentation slides for the CSGO project
- [Tableau Notebook](https://github.com/ironhack-daft-ray/final_project_CSGO/blob/main/RH_CSGO_heatmap.twbx) -- map and strategy recommender
- [Jupyter Notebook](https://github.com/ironhack-daft-ray/final_project_CSGO/blob/main/RH_CSGO_IGES_final.ipynb) -- first steps toward a game economy recommender
- [Data Source Zip](https://github.com/ironhack-daft-ray/final_project_CSGO/blob/main/mm_master_demos.csv.zip) -- unzipping needed to run the Jupyter notebook

---

### GAME INTRODUCTION - CSGO

Counter-Strike: Global Offensive (CSGO) is a first-person shooter that has become a global phenomenon and one of the hallmarks of the esport world. 

**GAME OBJECTIVE:**

In Competitive Demolition Mode, two teams of 5 players each battle each: the Terrorists and the Counter-Terrorists.
- As a Terrorist you are tasked with eliminating the opposition or planting the C4 bomb before the round time limit is reached and securing its detonation.
- As a Counter-Terrorist you are tasked with eliminating the opposition, defusing the bomb if planted, or stalling the Terrorist attack long enough until the round time limit is reached.  

**GAME LENGHT:**

Matches are played as over a maximum of 30 rounds, the first team to secure 16 rounds wins the game. At the end of the 15th round the two teams switch sides.

In regular matchmaking, if both teams secure 15 rounds then the match ends in a tie, however, in professional play and competitive leagues, the match will continue to an overtime.

**GAME ECONOMICS:**

Players start out a match with a specified amount of money, and will receive more as the match goes on by getting kills or going for the objectives. Money can then be used at the start of rounds to buy weapons and equipment, any residual amount is taken over to the next round (reset at side-switch) to a maximum of $16000.

---

### DATA SOURCE LEXICON

**file:**
*the file name that the demo was scraped from. This is a unique field for each match.*

**map:**
*the Valve official map the match was played on.*

**date:**
*date the match was played (unverified if they are correct).*

**round:**
*the round that the duel took place.*

**tick:**
*the current tick in the demo the entry took place. A tick is represented as a state in the game, Valve's competitive matchmaking sets every match at 64 ticks which represents that there are 64 states within each second of the game.*

**seconds:**
*the converted tick to seconds within the game since match start.*

**att_team:**
*the team that the attacking player is on that dealt damage to the victim. Usually Team 1 and 2 but in some recorded pro matches, can have custom team name e.g Games Academy.*

**vic_team:**
*the team that the victim player is on that received damage from the attacker.*

**att_side:**
*the side that the attacker was on. Can be Terrorist or CounterTerrorist.*
