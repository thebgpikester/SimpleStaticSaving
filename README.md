UPDATED 12th July 2020.
I GIVE UP WITH STATICS. THIS IS BROKEN. IT USED TO WORK, IT WAS FIXED ONCE, BUT IS NOW PARTIALLY BROKEN AGAIN.
IT'S NOT THE SCRIPT BUT A COMBINATION OF DCS AND MOOSE
DONT BOTHER WITH THIS.
 
 
 --SIMPLE STATICS SAVING by Pikey, May 2019
 *UPDATED DEC 2019* 
 
 -- Usage of this script should credit the following contributors:
 --Pikey 
 --Speed & Grimes for their work on Serialising tables, included below,
 --FlightControl for MOOSE (Required)
 
 Use SGSDestroy.lua only unless you experience any errors relating to destroyed scenery. Ignore SGS.lua otherwise.
 LOAD MOOSE (at mission start)
 LOAD SGSDestroy before nearly every other type of script due to it altering the landscape.
 
 
 --INTENDED USAGE
 --DCS Server Admins looking to do long term multi session play that will need a server reboot in between and they wish to keep the Ground 
 --Unit positions true from one reload to the next.
 
 --USAGE
 --Ensure LFS and IO are not santitised in missionScripting.lua. This enables writing of files. If you don't know what this does, don't attempt to use this script.
 --Requires versions of MOOSE.lua supporting "SET:ForEachGroupAlive()". Should be good for 6 months or more from date of writing. 
 --MIST not required, but should work OK with it regardless.
 --Edit 'SaveScheduleUnits' below, (line 34) to the number of seconds between saves. Low impact. 10 seconds is a fast schedule.
 --Place Ground Groups wherever you want on the map as normal.
 --Run this script at Mission start
 --The script will create a small file with the list of Groups and Units.
 --At Mission Start it will check for a save file, if not there, create it fresh
 --If the table is there, it loads it and Spawns everything that was saved.
 --The table is updated throughout mission play
 --The next time the mission is loaded it goes through all the Groups again and loads them from the save file.
 
 --LIMITATIONS
--I experienced issues Spawning Statics and Destroying statics in some configurations, so I'm exploding them and not deleting them like SGS. 
