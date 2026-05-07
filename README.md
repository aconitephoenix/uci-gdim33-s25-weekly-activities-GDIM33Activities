# GDIM 33 In-Class Activities
## W1
### Activity 1
[Inspo Board](https://docs.google.com/drawings/d/1KKztuXtzBfMj3h16-YdUnKpstt4FCLG6LIYFTS3AKeE/edit?usp=sharing)

1. The patterns that I see in the things that I've currently chosen to add to my inspiration board are kind of a psychological factor and self/mutual destruction. I've always found myself really interested in visual novels, especially psychological horror, because I feel like those kinds of stories are the ones that hit home the most for me. For mechanics, I'd say that I'm drawn to JRPGs because I just really like going around doing quests and talking to NPCs with my cute little sprite....
2. We have similar tastes for dark visual styles and deep narrative backgrounds!!! We generally are drawn to complex characters/relationships in the media that we consume.
3. Leah and I both share a liking for RPGs!!! We love singleplayer story games in general, and it made me think about all the old horror RPGs I played years ago (Mad Father, Ao Oni, Ib, Witch's House, etc.)

### Activity 2
![jess tran (gdim 33) - vertical slice breakdown](https://github.com/user-attachments/assets/27132741-7909-4a49-812f-bf8f351fe804)
## W2
No devlog this week; check commits!
## W3
### Activity 1
<img width="1085" height="914" alt="jess tran (gdim 33) - vertical slice breakdown(2)" src="https://github.com/user-attachments/assets/f3ec8036-3c48-4801-a11a-1e8ce6adf0b5" />

### Activity 2
1. It's better to save the event name for the explore-to-dialogue state transitions as a Scene variable because it makes the dialogue trigger event accessible to any object in the scene, making it easier to trigger certain behaviors without having to create a separate variable for every time you want to trigger the event (in other words you can kinda access it like a locator singleton...ish!)
2. I used a Debug.Log() node on both of the state transitions and the click event with the walrus. All of these nodes helped me test my graphs at an intermediate step by allowing me to test if the events were triggering properly, and to notice if something wrong was going on with behaviors even when the events were triggering. For example, I had an issue with triggering the walrus's dialogue and the Debug.Log() node told me that it was in fact triggering, so I went to edit the walrusW3 graph and noticed I hadn't been calling the clickNpcEventName event on the gameController object. Without the Debug.Log(), I would've had a much harder time finding exactly where this error was occurring.
3. I don't believe the Set Cursor Lock State is relevant to my Vertical Slice. My Vertical Slice is a visual novel, and for that reason I'd want the player to be able to move their cursor around even during dialogue in the case they'd like to navigate to the settings via the UI and such...in the case that I decide to move the settings to a key press instead, I would probably lock the cursor during dialogue sections and unlock it for dialogue options and game start/end screens.
4. I believe the concept of a "game state" might be relevant to my Vertical Slice. The way that I'm thinking of my Vertical Slice right now requires a standard start state, playing state, and end state for the game to be able to loop correctly. I do also believe that I might implement different end states as I'm planning on making branching endings alongside branching dialogue options. This is also just kind of spitballing, but I may or may not also make separate states for dialogue, dialogue selection, and cutscenes if I find that they need to be separated that far.
## W4
### Activity 1
#### Playable Build Stuff
I have a really barebones dialogue system working right now....  
Goals: seeing if there's any bugs with the dialogue right now + if it feels smooth enough to click thru
#### Playtesting Team
Frances Kim, Sebastian Magana, Kaleb Reyes, Rebecca Feng, Landon Her
#### Playtesting Notes
- they liked red capsule!
- liked the skip text function!!
### Activity 2
1. Assuming the activity has been finished, a designer should be able to add more dialogue via ScriptableObjects alone without having to go into code. The graph is set up so that buttons and dialogue progress appropriately with player input, so a designer should not have to worry about the logistics behind how the dialogue works and should be able to add dialogue with ease.
2. There's no limit to the amount of dialogue nodes a designer can make; there could be an infinite amount of dialogue nodes and the only limitation would be the computer's capacity to handle all that dialogue.
3. The regenerate nodes button basically acts as a "refresh" button for nodes to make sure that all nodes are registered in the game's settings and accessible in graphs.
## W5
### Activity 1
#### Chosen Feature: Game State Machine
##### Basic Steps
1. Set up different states for the game to switch between, Debug.Log() to check that the switch has triggered
2. Set up the states so that certain UI is enabled/disabled when states are switched
3. Run through the game to see that all states function
##### Detailed Steps
1. Add different script states to the state machine graph to represent the different game states
2. SM should change state based on whether the game has been started + if the Escape key has been pressed during the game. Test with Debug Log messages
3. SM should first be able to enable/disable dialogue UI based on whether the game is in the dialogue state. Test by enabling/disabling the game object between transitions
4. SM should be able to display pause button when player presses the Escape key. Test this while the game is running
5. SM should disable dialogue progression during the pause screen display. Click around during the pause screen to test if the dialogue UI is disabled correctly
6. SM should start off in a "game start" state; make sure that the game opens up on the start state when running and leaves the start state when pressing the button on the start screen
### Activity 2
I got the state machine to switch game states based on key presses + button clicks, and got the UI showing up (mostly) properly. I just need to fix when the pause screen goes back to the dialogue and the dialogue needs to type the line again.
## W6
### Activity 1
#### Playtest Build Stuff
New features:
- .......the progress bar animates itself .......... 😅

Link: https://cherrycxrnival.itch.io/vertical-slice-test-build-2

Goals:
- test state machine (bc i havent done that yet)
- test bugs in progress bar (changing value + anims)
#### Playtest Notes

### Activity 2
1. Why does the Multiply setting of the Blend node make the resulting color darker and less saturated than the input colors?
Hint 1: The Multiply option literally multiplies the values given, so a vector A = (R1, G1, B1) Blended with a vector B = (R2, G2, B2) with the Multiply option will result in a vector C = (R1*R2, G1*G2, B1*B2).
Hint 2: recall that we store the RGB channels as 0.0 - 1.0 values.
2. If we use Multiply to combine Alpha values, will the resulting value be more or less translucent than either of the original values, and why?
3. When we created the SampleTexture2D node, Unity auto-created the UV0 Node for us to get the UV coordinates for sampling the texture. Where does the shader get these UV values from?
4. You just learned that you can manipulate colors with math. Does that sound interesting or exciting to you?