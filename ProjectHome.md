# About #

This is a version of the CryEngine3 SDK with unnecessary features taken out. The goal is to take as much of it out while still having multiplayer work properly.

There's probably a lot more than can be removed, but this is it for now.

# Build #

It uses premake to generate project files for you to open. Currently it builds vs2010 and vs2012 files. Everything should compile out of box.

When you remove or add c++ files in CryGame it's recommended to rebuild the project files using generate\_project\_files.bat.

# Launch #

If you're using visual studio, you can just simply press F5 and it will build and launch both server and two clients that will attempt to connect to the server.

There is temporary code in GameStartup.cpp that launches the server, changes the map to "blank", launches a client and connects the client to the server. The client will also quit on disconnect so it's easier to restart with this debug setup. You can remove this in CGameRules::OnDisconnect.


# Features Removed #

  * HitReactions
  * HitDeathReactions
  * FeatureTester
  * AutoTester
  * Screen Effects
  * StatsAgent
  * SPAnalyst
  * Stereo3D
  * BattleDust
  * Weather Effects
  * Flownodes
  * Radio
  * Boids
  * Sample NPCS

  * All inventory related code (so no weapons or items exist)
  * All vehicle related code
  * All HUD and GUI Related code
  * All lobby related code

  * Forest map
  * All unused assets

# Tools #

### WinMerge ###

The [Portable](http://portableapps.com/apps/utilities/winmerge_portable) [WinMerge](http://winmerge.org/) is a diff checking tool that is used to check the minimal code against the original code after AStyle  has been applied to it. Launch compare\_sources.bat to check it out.

### AStyle ###

[AStyle](http://astyle.sourceforge.net/) is used to normalize the C++ code. It basically indents and forces a consistent style without breaking the code. This should be used before committing anything and is also used on the original game code to make the comparison easier. Launch normalize\_code.bat to run it.