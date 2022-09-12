# PlayFab Multiplayer SDK for Unity

## Overview
This is a PlayFab Multiplayer plugin for game development on Unity.

_(Please use Git client with Large File Storage (LFS) support to work with this repo)_

## Supported platforms:
- Windows
- Microsoft Game Core (just "Game Core" below)

## Version
|Multiplayer Unity SDK (main)
|-|
|1.3.0.0-main.0

Officially supported versions of PlayFabMultiplayer binaries with this release, by platform:

Platform|Version|Notes
|-|-|-|
Windows|1.3.0
Game Core|1.3.0|Compatible with GDK 2022.06 (June 2022) or later

## Prerequisites
- PlayFab account ([www.playfab.com](https://www.playfab.com)) registered and set up:
    - Studio and App configured, TitleID exists
    - Highly recommended: PlayFab Unity test app tried to ensure seamless PlayFab integration
- PlayFab Unity Editor Extensions plugin (recommended)
- PlayFab (Core) SDK (installed via PlayFab Unity Editor extensions)
- If you are targeting Windows:
    - Unity Windows Build Support (IL2CPP) Add-on installed
- If you are targeting Game Core platform (consoles and/or PC):
    - Have access to the [Microsoft Game Development Kit (GDK)](http://aka.ms/gdkdl)
    - GDK installed (with all optional components)
    - If you are targeting Game Core on Xbox consoles:
        - Unity Game Core Add-on for a necessary console installed (download from Unity)

## What's inside
The SDK contains the following:
- `/PlayFabMultiplayerSDK` – This folder contains APIs that you will call from your game to take advantage of Lobby, Matchmaking and other functionality offered by PlayFabMultiplayer.
- `/PlayFabMultiplayerSDK/Prefabs` – This folder contains the PlayfabMultiplayerEventProcessor prefab.
- `/PlayFabMultiplayerSDK/Setup/GameCore` – This folder contains set up scripts that need to be used once to prepare the SDK to build for Game Core.
- `/PlayFabMultiplayerSDK/Source/DLLs` – This folder contains the underlying PlayFabMultiplayer C++ library binaries for each supported platform.

## Getting Started
### Setting up your environment
- Create a new Unity project
- Open player settings from the Unity main menu: Edit > Project Settings...
- Next, select the 'Player' tab
- Scroll down and check the box: Allow 'unsafe' Code
- Close the Project Settings window
- Link your Unity project with PlayFab by installing the editor extensions: https://github.com/PlayFab/UnityEditorExtensions/releases
- Import this plugin
- Install latest version of PlayFabSDK plugin using PlayFab Unity Editor Extensions UI
- Log in to your PlayFab title using PlayFab Unity Editor Extensions UI
- Follow [README guidelines from PlayFabSDK](https://github.com/PlayFab/UnitySDK) to test basic PlayFab functionality
- Create a new, empty scene
- Import PlayFab Multiplayer Unity SDK plugin (unity package)
- If you are targeting Game Core: 
    - Go to `/Assets/PlayFabMultiplayerSDK/Setup/GameCore` folder in File Explorer and run `install-multiplayer-game-core-dependencies.ps1` (or `.cmd`) script, it will copy necessary redistributable dependency binaries installed with GDK (such as `XCurl.dll`) to `PlayFabMultiplayerSDK` assets. Please enable necessary platforms (Standalone, GameCoreScarlett, GameCoreXboxOne) or select "Any Platform" in the Inspector window of Unity Editor for `XCurl.dll`.
- Go to the `/Assets/PlayFabMultiplayerSDK/Prefabs` folder and drag and drop the `PlayfabMultiplayerEventProcessor` prefab into your scene
- Note: PlayFabMultiplayer SDK is x64, so when you build Standalone (Windows) please build for x64.

For a detailed guide please check out [Quickstart: PlayFab Multiplayer Unity Plugin](https://docs.microsoft.com/en-us/gaming/playfab/features/multiplayer/lobby/lobby-matchmaking-sdks/multiplayer-unity-plugin-quickstart)