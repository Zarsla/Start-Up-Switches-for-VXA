# Start-Up-Switches-for-VXA
#-============================================================================-#
#     Start Up Switches by Zarsla
#
#     Version 1.0 Realsed July 2, 2015 
#
#     Terms of Use:
#
#     Free for non commerical use, just credit if used, for commercial use, 
#     just send Zarsla a free copy and credit.  You are allowed to edit this 
#     script, just don't claim as your own,  you may aknowledge that you edited
#     it. If you do, give credit like this "Automatic Switches Start by Zarsla, 
#     Modified by Whomever", and all other terms of use still apply. You are not
#     allowed to redistrubute any edited versions of this script. If you wish fot
#     it to be redistrubute send it to Zarsla and then Zarlsa will redistrubte it
#     as "Modified Automatic Switches Start by Zarsla + Whomever", note that all 
#     terms  of use will follow the orignal Automatic Switches Start by Zarsla.
#
#     Email: zzarsla@gmail.com
#===============================================================================#
#     Description:                          
#     This script allows you to turn on up to 10 switches for your game 
#     when start a new game or load a game. To use simply follow the 
#     intructions below. Plug n' Play.
# ==============================================================================#
#                                    Instructions
#     -Under the heading S#O set, turn the switch you want on to true(on)or 
#      false(off). each S#O coorolates to a S#, thus S1O turns on S1.
#      This for turning on switches on a new game
#
#     -Under the heading S# set, set S# to the id of the switch you want on,
#      for example set S1 to 20, if I want switch 20 on. This is for switches
#      that are being turned on during a new game
#
#     -Under the heading L#O set, turn the switch you want on to true(on)or 
#      false(off). each L#O coorolates to a L#, thus L1O turns on L1.
#      This for turning on switches on a game that's being loaded
#
#     -Under the heading L# set, set L# to the id of the switch you want on,
#      for example set L1 to 20, if I want switch 20 on.This is for switches
#      that are being turned on during a game that's being loaded
#===============================================================================#
#
#                                 Editable Region Start
#================================================================================
module ZS
#-----------------#
# S#O Set
#-----------------#
  S1O = true 
  
  S2O = false
  
  S3O = false
  
  S4O = false
  
  S5O = false
  
  S6O = false 
  
  S7O = false
  
  S8O = false
  
  S9O = false
  
  S10O = false
#----------------#
# S# Set
#----------------#  
  S1 = 1
  
  S2 = 2
  
  S3 = 3
  
  S4 = 4
  
  S5 = 5
  
  S6 = 6
  
  S7 = 7
  
  S8 = 8
  
  S9 = 9
  
  S10 = 10

#-----------------#
# L#O Set
#-----------------#
  L1O = false 
  
  L2O = false
  
  L3O = false
  
  L4O = false
  
  L5O = false
  
  L6O = false 
  
  L7O = false
  
  L8O = false
  
  L9O = false
  
  L10O = false
#----------------#
# S# Set
#----------------#  
  L1 = 1
  
  L2 = 2
  
  L3 = 3
  
  L4 = 4
  
  L5 = 5
  
  L6 = 6
  
  L7 = 7
  
  L8 = 8
  
  L9 = 9
  
  L10 = 10  
  
end
#===============================================================================#
#
#                               End Editable Region      
#===============================================================================#

class Scene_Title < Scene_Base
  def command_new_game
    DataManager.setup_new_game
    close_command_window
    fadeout_all
    if ZS::S1O == true then $game_switches[ZS::S1] = true else end
    if ZS::S2O == true then $game_switches[ZS::S2] = true else end
    if ZS::S3O == true then $game_switches[ZS::S3] = true else end
    if ZS::S4O == true then $game_switches[ZS::S4] = true else end
    if ZS::S5O == true then $game_switches[ZS::S5] = true else end
    if ZS::S6O == true then $game_switches[ZS::S6] = true else end
    if ZS::S7O == true then $game_switches[ZS::S7] = true else end
    if ZS::S8O == true then $game_switches[ZS::S8] = true else end
    if ZS::S9O == true then $game_switches[ZS::S9] = true else end
    if ZS::S10O == true then $game_switches[ZS::S10] = true else end
    $game_map.autoplay
    SceneManager.goto(Scene_Map)
  end
end
class Scene_Load < Scene_Base
def on_load_success
    Sound.play_load
    fadeout_all
    $game_system.on_after_load
    if ZS::L1O == true then $game_switches[ZS::L1] = true else end
    if ZS::L2O == true then $game_switches[ZS::L2] = true else end
    if ZS::L3O == true then $game_switches[ZS::L3] = true else end
    if ZS::L4O == true then $game_switches[ZS::L4] = true else end
    if ZS::L5O == true then $game_switches[ZS::L5] = true else end
    if ZS::L6O == true then $game_switches[ZS::L6] = true else end
    if ZS::L7O == true then $game_switches[ZS::L7] = true else end
    if ZS::L8O == true then $game_switches[ZS::L8] = true else end
    if ZS::L9O == true then $game_switches[ZS::L9] = true else end
    if ZS::L10O == true then $game_switches[ZS::L10] = true else end
    SceneManager.goto(Scene_Map)
  end
end  
