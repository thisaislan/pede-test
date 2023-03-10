# Persistence easy to delete in editor (Pede) 

Persistence easy to delete in editor, or just Pede, is a small library for easy saving and deleting common persistence in the unit editor.

Pede allows us to use Unity's `PlayerPrefs` to persist`bool, byte, sbyte, char, decimal, double,float, int, uint, nint, nuint, long, ulong, short, ushort, string` and `object`, also abstracts the logic to persist object as `files`.      

At runtime, all data saved by Pede is compressed to save space and to protect the data, a similar process is applied to all used keys.  

When in the editor, Pede uses a ScriptableObject to store the data, this approach allows us to see and modify the data during development. Pede also provides us with features in the editor to easily manipulate and validate the data used in the test, these features can be accessed through the editor's menu.     

Please note this is still in development! Check [Issues](https://github.com/thisaislan/persistence-easy-to-delete-in-editor/issues) for any current support issues or bugs that may exist!


<p align="center">
    <a href="https://unity3d.com/get-unity/download">
        <img src="https://img.shields.io/badge/unity-tools-blue" alt="Unity Download Link"></a>
    <a href="https://github.com/thisaislan/persistence-easy-to-delete-in-editor/blob/main/LICENSE.md">
        <img src="https://img.shields.io/badge/License-MIT-brightgreen.svg" alt="License MIT"></a>
</p>


## Table of Contents
- [How it works](#How-it-works)
- [Installation](#Installation)
- [Features](#Features)
- [Support](#Support)
- [Note](#Note)
- [Thanks](#Thanks)
- [License](#License)


## How it works

It's simple, do you want to save a int PlayerPrefs? Just do it:
```csharp
    Pede.SetPlayerPrefs(key, intValue);
```

Now maybe you want to save some booleans! The following code can help you:
```csharp
    Pede.SetPlayerPrefs(key, booleanValue);
```

Time for save an entire object:
```csharp
    Pede.SetPlayerPrefs(key, someNonEngineObject);
```

Ok, ok, you got the idea, but save an entire object in PlayerPrefs isn't a good idea, maybe you would rather to save a object in a file. In that case just ask to the Pede:
```csharp
    Pede.SetFile(key, someNonEngineObject);
```

Additionally, any value saved in editor mode will be stored in a PedeData ScriptableObject, so you can change its values, type and key by inspector or just delete or duplicate it.

For default Pede create a folder named Pede to create a PedeData if it doesn't exist, and put a ScriptableObject named PedeSettings in the Settings folder to point out which PedeData is being used at that moment .

## Installation

Pede can be installed directly through the git url
```
https://github.com/thisaislan/persistence-easy-to-delete-in-editor.git
```

If you need more information about installing package from a Git URL, you can click [here](https://docs.unity3d.com/Manual/upm-ui-giturl.html). :slightly_smiling_face:


## Features

Currently, this is what Pede does have
| Features                   |       Status      |
| -------------------------- | :----------------:|
| SetCustomSerializer        |         ✔️         |
| Serialize                  |         ✔️         |
| Deserialize                |         ✔️         |
| SetPlayerPrefs             |         ✔️         |
| GetPlayerPrefs             |         ✔️         |
| DeletePlayerPrefs          |         ✔️         |
| DeleteAllPlayerPrefs       |         ✔️         |
| HasPlayerPrefsKey          |         ✔️         |
| SavePlayerPrefs            |         ✔️         |
| SetFile                    |         ✔️         |
| GetFile                    |         ✔️         |
| DeleteFile                 |         ✔️         |
| DeleteAllFiles             |         ✔️         |
| HasFileKey                 |         ✔️         |
| DeleteAll                  |         ✔️         |


## Support
Please submit any queries, bugs or issues, to the [Issues](https://github.com/thisaislan/persistence-easy-to-delete-in-editor/issues) page on this repository. All feedback is appreciated as it not just helps myself find problems I didn't otherwise see, but also helps improve the project.


## Note

By default Pede uses JsonUtility so it has all the limitations of that library. If you want to change the serializer class, check the `SetCustomSerializer` method and also the `Custom Serializer` field in the PedeSettings file. 


## Thanks
My friends and family, and you for having come here!


## License
Copyright (c) 2021-present Aislan Tavares (@thisaislan) and Contributors. Git Hero is free and open-source software licensed under the [MIT License](https://github.com/thisaislan/persistence-easy-to-delete-in-editor/blob/main/LICENSE.md).