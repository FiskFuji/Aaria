#==============================================================================#
#                                   AARIA                                      #
#==============================================================================#
#                                 Written By:                                  #
#                                 Kirk Worley                                  #
#==============================================================================#
#   Aaria is a text based adventure game based on the text game "Zork."        #      
#   It is not as complex as Zork, and may contain bugs.                        #
#   The game's answers may not always be straightforward, and the game is      #
#   what you make of it.                                                       #
#   Feel free to take a look at the code!                                      #
#==============================================================================#
#                   BEGIN CODE                                                 #
#==============================================================================#
#                   IMPORT MODULES                                             #
#==============================================================================#
import random
import os
#==============================================================================#
#                   END IMPORT MODULES                                         #
#==============================================================================#
#
#==============================================================================#
#                   BEGIN INITIAL VARIABLES, LOOP                              #
#==============================================================================#
igame = 0

inventory = []
ground = []
journal = []

w_north = "Went North."
w_east = "Went East."
w_west = "Went West."
w_south = "Went South."
w_block = "Blocked."
w_took = "Took an Item."
w_drop = "Dropped an Item."
w_read = "Read something."

Paper = "Paper"


#==============================================================================#
#                   END INITIALIZING VARIABLES, LOOP                           #
#==============================================================================#
#
#==============================================================================#
#                   DEFINE FUNCTIONS                                           #
#==============================================================================#

#=======================================================#
#                   LOCATION 0                          # 
#=======================================================#
def location0():
    print "You find yourself in a large, amber field that appears to be dying." 
    print "Stumbling to your feet and regaining your composure, you survey"
    print "the surroundings. To the North you see a large, looming tree that"
    print "seems to stretch up past the clouds. To the East and West are dirt"
    print "paths that seem to stretch around the tree. Looking to the South"
    print "it appears a thick underbrush is present, and impassable at the"
    print "moment. Upon further inspection, you find a scrap of paper in the"
    print "dirt near where you first awoke. In the distance you can hear"
    print "loud thundering booms, as if a storm is approaching. But there"
    print "are no clouds in the sky."
    a1 = raw_input("What will you do?\n")
    #=======================================================#
    #                   READ PAPER                          # 
    #=======================================================#
    if a1.lower() == "read paper":
        print "---------------------------------------------"
        print "You pick up the paper and turn it over. Scrawled into it"
        print "are the words:"
        print "Find enlightenment, %s. Beware the clouds." %name
        print "The paper crumbles to dust in your hands..."
        loc = 1
        journal.append(w_read)
        return loc
    #=======================================================#
    #                   TAKE PAPER                          # 
    #=======================================================#
    elif a1.lower() == "take paper":
        print "---------------------------------------------"
        print "The paper crumbles to dust as you pick it up."
        print "..."
        print "A whisper is heard all around you."
        print '"Find enlightenment... %s..."' %name
        print '"Beware the clouds..."'
        ground.remove(Paper)
        loc = 1
        return loc
    #=======================================================#
    #                   LOOK                                # 
    #=======================================================#
    elif a1.lower() == "look":
        print "Items on ground:"
        print ", ".join(ground)
        location0()
    #=======================================================#
    #                   INVENTORY                           # 
    #=======================================================#
    elif a1.lower() == "inventory":
        print ", ".join(inventory)
        locaction0()
    #=======================================================#
    #                   READ, BRANCH                        # 
    #=======================================================#
    elif a1.lower() == "read":
        a1read = raw_input("Read what?\n")
        if a1read.lower() == "paper":
            print "---------------------------------------------"
            print "You pick up the paper and turn it over. Scrawled into it"
            print "are the words:"
            print "Find enlightenment, %s. Beware the clouds." %name
            print "The paper crumbles to dust in your hands..."
            loc = 1
            journal.append(w_read)
            ground.remove(Paper)
            return loc
        else:
            print "I don't understand that statement."
            location0()
    #=======================================================#
    #                   TAKE, BRANCH                        # 
    #=======================================================#
    elif a1.lower() == "take":
        a1take = raw_input("Take what?\n")
        if a1take == "paper":
            print "---------------------------------------------"
            print "The paper crumbles to dust as you pick it up."
            print "..."
            print "A whisper is heard all around you."
            print '"Find enlightenment... %s.."' %name
            print '"Beware the clouds..."'
            ground.remove(Paper)
            loc = 1
            return loc
        else:
            print "---------------------------------------------"
            print "I don't understand that statement."
            location0()
    #=======================================================#
    #                   NORTH                               # 
    #=======================================================#
    elif ((a1.lower() == "go north") or (a1.lower() == "north")):
        print "---------------------------------------------"
        print "As you leave, the paper crumbles to dust."
        loc = 2
        journal.append(w_north)
        ground.remove(Paper)
        return loc
    #=======================================================#
    #                   EAST                                # 
    #=======================================================#
    elif ((a1.lower() == "go east") or (a1.lower() == "east")):
        print "---------------------------------------------"
        print "As you leave, the paper crumbles to dust."
        loc = 3
        journal.append(w_east)
        ground.remove(Paper)
        return loc
    #=======================================================#
    #                   WEST                                # 
    #=======================================================#
    elif ((a1.lower() == "go west") or (a1.lower() == "west")):
        print "---------------------------------------------"
        print "As you leave, the paper crumbles to dust."
        loc = 4
        journal.append(w_west)
        ground.remove(Paper)
        return loc
    #=======================================================#
    #                   SOUTH                               # 
    #=======================================================#
    elif ((a1.lower() == "go south") or (a1.lower() == "south")):
        print "---------------------------------------------"
        print "You cannot go that way."
        location0()
        journal.append(w_south)
        journal.append(w_blocked)
    #=======================================================#
    #                   OTHERWISE                           # 
    #=======================================================#
    else:
        print "---------------------------------------------"
        print "I don't understand that statement."
        location0()
#=======================================================#
#                   END LOCATION 0                      # 
#=======================================================#
#
#=======================================================#
#                   FUNCTION                            # 
#=======================================================#

    
#==============================================================================#
#                   END FUNCTION DEFINITIONS                                   #
#==============================================================================#
#
#==============================================================================#
#                   BEGIN INTRO                                                #
#==============================================================================#
print "Hello! Welcome to the world of Aaria. A strange distant"
print "land which you will be thrust into. This land contains"
print "dangers and treasures alike. Seek enlightenment, for it is Truth."
print "Before you brave the dangers of this new world, you must"
print "first learn the basics if you so choose."
tut = 1
#==============================================================================#
#                   TUTORIAL YES/NO?                                           #
#==============================================================================#
while(tut == 1):
    tutask = raw_input("\nWould you like to view the tutorial? (y/n): ")
    if tutask.lower() == ("y"):
        print "---------------------------------------------"
        print "Very well. Here are the basic commands used in Aaria."
        print "'look'          ---  Examine your surroundings and items on the ground."
        print "'inventory'     ---  Display your current inventory."
        print "'take x'        ---  Take item X, if possible."
        print "'drop x'        ---  Drop item X, from your inventory if possible."
        print "'go north'      ---  Go North, if possible. ('north' also works.)"
        print "'go east'       ---  Go East, if possible. ('east' also works.)"
        print "'go west'       ---  Go West, if possible. ('west' also works.)"
        print "'go south'      ---  Go South, if possible. ('south' also works.)"
        print "'use x on y     ---  Use item X on item Y if possible."
        print "And a variety of other lesser commands that may be situational."
        print "All of your actions will be recorded."
        print "Try your best."
        tut = 0
    elif tutask.lower() == ("n"):
        print "---------------------------------------------"
        print "Very well."
        tut = 0
    else:
        print "---------------------------------------------"
        print "Please enter y/n."
#==============================================================================#
#                   END TUTORIAL                                               #
#==============================================================================#
#                   BEGIN NAME INPUT                                           #
#==============================================================================#
print "---------------------------------------------"
print "Lastly, you must remember your name..."
name = raw_input("Try to recall your name:\n")
print "---------------------------------------------"
print "Very well %s. Without further delay, enter the world of Aaria..." %name
#==============================================================================#
#                   END NAME INPUT                                             #
#==============================================================================#
print "---------------------------------------------"
print "Your eyes feel heavy. You struggle to open them. With as much"
print "strength as you can muster, you pry them open. You awake, drowsy"
print "and disoriented."
ground.append(Paper)
loc = 0

#==============================================================================#
#                   INITIAL OBSERVATION                                        #
#==============================================================================#
location0()    
#==============================================================================#
#                   END INITIAL OBSERVATION                                    #
#==============================================================================#
#
#==============================================================================#
#                   BEGIN LOOP FOR GAME START                                  #
#==============================================================================#
while (igame == 0):
        
#==============================================================================#
#                   INDENT ALL SUBSEQUENT LINES BY 1                           #
#==============================================================================#
#                   LOCATION 1, PAPER GONE                                     #
#==============================================================================#
    while loc == 1:
        print "You are in a large, amber field that appears to be dying."
        print "To the North you see a large, looming tree that seems to stretch"
        print "up past the clouds. To the East and West are dirt paths that"
        print "seem to stretch around the tree. Looking to the South it appears"
        print "a thick underbrush is present, and impassable at the moment."
        print "In the distance you can hear loud thundering booms, as if a storm"
        print "is approaching. But there are no clouds in the sky."
        a2 = raw_input("What will you do?\n")
        #=======================================================#
        #                   LOOK                                # 
        #=======================================================#
        if a2.lower() == "look":
            print "Items on ground:"
            print ", ".join(ground)
            loc = 1
        #=======================================================#
        #                   NORTH                               # 
        #=======================================================#
        elif ((a2.lower() == "go north") or (a2.lower() == "north")):
            print "---------------------------------------------"
            loc = 2
            journal.append(w_north)
        #=======================================================#
        #                   EAST                                # 
        #=======================================================#
        elif ((a2.lower() == "go east") or (a2.lower() == "east")):
            print "---------------------------------------------"
            loc = 3
            journal.append(w_east)
        #=======================================================#
        #                   WEST                                # 
        #=======================================================#
        elif ((a2.lower() == "go west") or (a2.lower() == "west")):
            print "---------------------------------------------"
            loc = 4
            journal.append(w_west)
        #=======================================================#
        #                   SOUTH                               # 
        #=======================================================#
        elif ((a2.lower() == "go south") or (a2.lower() == "south")):
            print "---------------------------------------------"
            print "You cannot go that way."
            loc = 1
            journal.append(w_south)
            journal.append(w_blocked)
        #=======================================================#
        #                   INVENTORY                           # 
        #=======================================================#
        elif a2.lower() == "inventory":
            print ", ".join(inventory)
            loc = 1
        #=======================================================#
        #                   OTHERWISE                           # 
        #=======================================================#
        else:
            print "---------------------------------------------"
            print "I don't understand that statement."
            loc = 1
#==============================================================================#
#                   END LOCATION 1, FIELD                                      #
#==============================================================================#
#
#==============================================================================#
#                   LOCATION 2, LARGE TREE                                     #
#==============================================================================#
    while (loc == 2):
        print "You are in front of the large, looming tree. The material of the"
        print "tree looks unlike any you've ever seen before. The distant"
        print "booming sounds seem to have quieted here, as if the tree blocks the"
        print "sound. Looking upwards it seems the tree rises up through the clouds."
        print "There is a small hole in the tunk of the tree. The dirt paths"
        print "to the East and West have developed thick brush near the tree,"
        print "and cannot be accessed from this close to the tree. There is also"
        print "what appears to be a wooden bench near the base of the tree."
        a3 = raw_input("")
        #=======================================================#
        #                   LOOK                                # 
        #=======================================================#
        if a3.lower() == "look":
            print ", ".join(ground)
            loc = 2
        #=======================================================#
        #                   INVENTORY                           # 
        #=======================================================#
        elif a3.lower() == "inventory":
            print ", ".join(inventory)
            loc = 2
        #=======================================================#
        #                   NORTH                               # 
        #=======================================================#
        elif ((a3.lower() == "go north") or (a3.lower() == "north")):
            print "---------------------------------------------"
            
        #=======================================================#
        #                   EAST                                # 
        #=======================================================#
        #=======================================================#
        #                   WEST                                # 
        #=======================================================#
        #=======================================================#
        #                   SOUTH                               # 
        #=======================================================#
        elif ((a3.lower() == "go south") or (a3.lower() == "south")):
            print "---------------------------------------------"
            loc = 1
        #=======================================================#
        #                   INVENTORY                           # 
        #=======================================================#
        else:
            print "I don't understand that statement."
    
        
        
        
    




