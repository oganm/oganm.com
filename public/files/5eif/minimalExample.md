---
import: [helperfile.md,helpferfile2.md]
---

<!-- these are comments invisible to the player.
a few settings controlled by the yaml
above. import setting controls helper files
to be imported along with the main file. currently those files don't exist
but you get the point


The first h1 header is the name of
the adventure. The first section is meant to be used as an introduction
-->

The <b>minimal</b> example <!-- titles ignore tags in their names-->
=========



Introduction <!-- The title of a scene is used to reference that scene and will be visible to the user -->
----------------

This is a sample adventure to demonstrate and test the feature set of <b>5eSoloSystem</b>. <!-- use html tags for flair -->

Create 2 level 1 characters for this adventure

<!-- use brackets add commands. Non scene change commands also require a backslash.
addpc allows the player to upload characters. I might change this later to allow uploading
multiple characters with a single addpc so repeating won't be necesary.
-->

* {{\addpc}}
* {{\addpc}}

<!-- scene change commands do not require a backslash. syntax is kinda copied 
from twine. Both options below will lead to the room. The first option displays
the text "Open the door", the second will display "The Room"-->

* {{Open the door|The Room}}
* {{The Room}}


The Room
----------------

There is a chest in this room.

If you want to check for traps, roll an investigation check (DC 15)

<!-- different ways to define skill checks. always start with the skill name, 
followed by an optional specifier, followed by an optional DC. "group" checks 
roll for the entire party, if DC is provided, will report success if half passes.
"best" rolls with the modifier of the most skilled party member. "all" will 
allow the player the pick the character they want. Defaults to "best"-->

{{\investigation:group,15}} <!--do a group roll. report pass if half above 15 -->
{{\investigation:best,15}} <!-- best character rolls. report pass if above 15 -->
{{\investigation:best}} <!-- best character rolls. only report the roll -->
{{\investigation}} <!-- best character rolls. only report the roll -->
{{\investigation:15}} <!-- best character rolls. report pass if above 15. this might not work in the final version -->
{{\investigation:all}} <!-- any character can roll, player chooses. only report the roll -->



<!-- The "appendhere" argument adds the next scene right after the button instead
of writing to a fresh screen. "append" argument would append the scene under the
current scene-->

If you passed {{click here|Invest Pass:appendhere}} 

If you failed {{click here|Invest Fail:appendhere}}



Invest Pass
-----------------

You noticed a friendly character hiding behind a bush.

<!-- Add a predefined character named tim -->
{{\addpc:Tim}}
{{Continue:append}}


Invest Fail
------------------

Nothing to see here

{{Continue:append}}


Continue
----------------

Oh no baddies!

{{Encounter}}



Encounter
---------------
<!-- Exact format to be determined. might do interesting things with using multiple
images to form a larger map--> 
{{\encounter:tile.png}}
{{\monster:Goblin,15,15}}
{{\monster:Goblin,15,30}}
{{\placeParty:20,20}}


If you defeat the enemies click {{here|Victory}}, if you lose, you suck.



Victory
--------------------

A winner is you!


{{Stat blocks}}
--------------
<!-- this is a special section where you have NPC/monster stat blocks to use
in encounters. will determine the format later-->


{{Characters}}
---------------
<!-- this is a special section where you have predefined characters to add to the
party. will probably make a separate app to convert characters generated using 
the fifth edition app to this format. format to be determined -->

