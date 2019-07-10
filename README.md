# Hangout Player
Basically the video player in Hangout House. This is **ONLY** for VRChat!

## Introduction
This player is very similar to the player in Hangout House, and even has slightly more features than that one. I decided to make this and release it for everyone to use, so have fun! :)

## Features
Here are the list of features of this player
- Playlist mode
- Master only control
- Toggle allowing others (non-Master) to enter links
- Toggle allowing others (non-Master) to control the player
- Toggle between old (VRCSyncVideo) and new (VRCSyncVideoStream) player
- 3D video support on old player (Requires TCL's 3d video shaders https://github.com/TCL987/UnityShaders)
- Toggleable screen emission (Must be baked)
- Button to locally toggle the player (For people who don't want to watch videos)
- Full set of player control buttons
- Local volume slider

## How To Use
If you just want a master only by default video player in your world, just plop down the **HangoutPlayer** prefab and done!

If you want anyone to be able to enter links and control the player by default, use the **HangoutPlayerAll** prefab instead.

### Emission
If you want to use the emission, just bake your lighting with **VRCVideoSyncEmission** enabled.

If you want the emission to be disabled by default, disable the **VRCVideoSyncEmission** game object under **Screen**, enable **EmissionToggleOn**, and disable **EmissionToggleOff**. If you don't want emission at all, just disable all three of the game objects **VRCVideoSyncEmission**, **EmissionToggleOn**, and **EmissionToggleOff**.

### 3D

3D is disabled by default. If you want 3D video support, get TCL's 3D video shaders and enable the **3D** game object.
