![http://bot-wars.googlecode.com/files/scrn1.jpeg](http://bot-wars.googlecode.com/files/scrn1.jpeg)         ![http://bot-wars.googlecode.com/files/scrn2.jpeg](http://bot-wars.googlecode.com/files/scrn2.jpeg)

# 1200+ Downloads!!! #
## Bot Wars is now hosted on [GitHub](https://github.com/dipenpradhan/bot-wars)! https://github.com/dipenpradhan/bot-wars ##


**_Bot Wars_** is a multiplayer touch-screen game built for Android devices, as our college project.



A side scrolling, arcade style [platformer](http://en.wikipedia.org/wiki/Platform_game) 2D game, with multiplayer over either bluetooth or internet (3G/WiFi), on the lines of the classic Super Contra.

A _**Compiled .apk**_ and **screenshots** can be found under the **[Downloads](http://code.google.com/p/bot-wars/downloads/list)** tab, just download the .apk, copy it to your phone or tablet and install (tick allow unknown sources when prompted)

Source Code, XML layouts, images, sounds, and maps can be found under the **[Source](http://code.google.com/p/bot-wars/source/browse/)** tab


Version history illustrating the Development Timeline can be found under **[Source->Changes](http://code.google.com/p/bot-wars/source/list)**

Beginners trying to learn game development with AndEngine and Box2D will find it to be a good starting point, feel free to use parts of the code, just give credits and drop a mail before you do so. If something is too confusing, ask!


---


### Highlights ###

  1. Animated **Player** who can be moved using on-screen bidirectional controller, jump & shoot buttons.
  1. Animated **Enemies** which are spawned using object groups in TMX maps.
  1. Player can shoot and kill enemies.
  1. Enemies jump towards the player (attack) when player is in close proximity.
  1. **Multiplayer over internet (3G/WiFi) and Bluetooth in a co-operative style.**
  1. Uses **tiled maps** with **TMX** map format for building levels.
  1. **Object layers** in the TMX maps are used to define **collision areas** and **enemy spawn points**.
  1. An image is used as background layer.
  1. **Multiple bullets** can be shot at a time.
  1. **MultiTouch Pinch Zoom** gesture enabled for supported devices.
  1. The interface includes a **Splash Screen**, **Main Menu**, **Settings Menu** for changing a few parameters, a **Map Menu** with image previews of levels, dialogs for selecting and displaying bluetooth devices and connecting to a device over internet by entering an IP address.
  1. **Hardware independent**, works on any android device with an ARM processor and dedicated graphics processor, and can scale to any screen resolution.


---


### Description of the classes: ###

  * **[BotWars.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/BotWars.java)**
The main game activity, containing all code for game mechanics, loading maps, images, sounds required for the game, essentially the whole game, can be run independently without other classes

  * **[BotWars\_MultiPlayer.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/BotWars_MultiPlayer.java)**
The superclass for MultiPlayer, inherits from BotWars.java, and adds support for MultiPlayer, responsible for adding player 2 and handling messages. It contains sendMessage() and receiveMessage() stub methods

  * **[MultiPlayer\_UDP.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/MultiPlayer_UDP.java)**
The class responsible for MultiPlayer over internet, inherits from BotWars\_MultiPlayer.java and adds methods for receiving and sending MultiPlayer Messages using UDP packets

  * **[MultiPlayer\_BT.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/MultiPlayer_BT.java)**
The class responsible for MultiPlayer over Bluetooth, inherits from BotWars\_MultiPlayer.java and adds methods for receiving and sending MultiPlayer Messages using BluetoothSockets (obtained from MapMenu\_BT.java)

  * **[StartMenu.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/StartMenu.java)**
  * **[MenuTextTouchListener.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/MenuTextTouchListener.java)**

Main menu and touchlistener for the text, uses xml layouts from /res/layout folder

  * **[SplashScreen.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/SplashScreen.java)**

The splash screen shown when game is launched


  * **[MapMenu.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/MapMenu.java)**

A menu for selecting levels/maps with image preview for all maps

  * **[MapMenu\_UDP.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/MapMenu_UDP.java)**

Inherits from MapMenu.java, and adds dialog to enter IP for playing over internet

  * **[MapMenu\_BT.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/MapMenu_BT.java)**
  * **[DeviceListActivity.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/DeviceListActivity.java)**

Inherits from MapMenu.java and adds required code for retrieving nearby bluetooth devices and establishing an RFCOMM socket to another device, this socket is handed to Multiplayer\_BT.java for sending/receiving MultiPlayer Messages.


  * **[SettingsMenu.java](http://code.google.com/p/bot-wars/source/browse/src/botwars/main/SettingsMenu.java)**

Menu for changing a few  game parameters




---


  * The game mechanics use **[AndEngine](http://www.andengine.org/)** libraries along with the **[Box2D](http://box2d.org/)** physics extension

  * The **Multiplayer** feature is based on a custom message passing protocol with UDP packets and message passing over Bluetooth sockets.

  * In multiplayer, movement of all players and all enemies is calculated **locally** on each phone, messages contain **ONLY** direction of player movement, stop, jump, and shoot
  * A location update is sent every 2 seconds to ensure player and enemy positions do not vary by a large margin and both players see each other, and enemies at the same location on map
  * A force kill message is sent to kill enemies such that both players have same  enemies on screen even with network delay

  * The **interface** uses android specific APIs, XML layouts and styles

  * Images and sprites used for characters are from freely available examples, tilesets for maps are taken from replica-island, a free, open source game.

  * Tested working on Samsung, LG, Sony Ericsson and AOSP(CyanogenMod) Gingerbread and Froyo firmware, with HVGA,WVGA,FWVGA and SVGA resolutions, should work on other versions, but not tested.