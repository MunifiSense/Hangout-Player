# VRChat URL Input Video Panel

Hey, this is Munificent, creator of the world Hangout House for VRChat.
A lot of people have been asking me how to make a panel like the one in my world, so here it is!

First of all, you need VRCSDK installed in Unity. If for some reason you don't have it, get it from:
https://www.vrchat.com/download/sdk

## Video Panel

This video panel has a UI under it with Play, Pause, Next, Previous, and also a InputField for inputting
a URL. This is all MasterBufferOne, so only the Master of the room can use it. If you want to change the
default videos, just edit it as you would in the VRC_SyncVideoPlayer script. 

## Video Emission

The prefab also has an emission video panel (EmissionScreen) behind the video panel. This allows for the
player to emit light like an actual screen with baked lights. You will need Realtime Global Illumination 
enabled in the Unity Lighting panel. VRC_CustomRendererBehaviour is the script on this that updates the
GI for the screen every tick. If the emission is too bright or not bright enough, you can adjust it in
the VRCVideoSyncEmission material. Just change the value next to Color in the Emission category. The 
emission does have a performance hit on the world, so you could make EmissionScreen disabled by 
default so people can pick if they want it or not. You can remove EmissionScreen, if you don't want 
emission.

## UI

If you want to move the UI, move the ScreenUI game object. If you move the Canvas itself, it can do
weird things in Unity. If you want to customize the UI, similar to my world, you can draw your sprites, 
or you can find some on the Asset Store, just look up "UI" or "GUI" and you should be able to find some.

## Extra Info

StartTimer Trigger: Starts a timer to hit "Next" on the VRC_SyncVideoPlayer. This is to make sure the
video is done processing by VRChat before the player tries to play it. This is configurable through the
NextTimer trigger, but I've found 10 seconds to be pretty good for it.

If you want to know how it works:
When text is inputted in the UI InputField, and Enter or anywhere outside of the text box is clicked
(On End Edit) the UI:
1. Clears the playlist with VRC_SyncVideoPlayer.Clear
2. Add two of the same URL with VRC_SyncVideoPlayer.AddURL 
	(Two of the same URL is added because videos do not loop properly if there is only one video 
	in the playlist of the VRC_SyncVideoPlayer.)
3. Interacts with the trigger StartTimer, which enables NextTimer
4. Clears the text box
5. NextTimer hits 10 seconds and uses SendRPC to use VRC_SyncVideoPlayer.Next
