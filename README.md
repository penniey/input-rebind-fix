# Unity Input Rebinding Quickstart

This guide will help you set up robust runtime key rebindings in Unity using the Input System package, including support for saving and loading user preferences.

## Prerequisites

- **Unity Input System**: Install the [Input System package](https://docs.unity3d.com/Packages/com.unity.inputsystem@latest/manual/index.html) via Package Manager.
- **Sample Assets**: Download the Input System samples for rebinding (available in the package samples).

## Disclaimer

This ReadMe was made by AI the code isn't I am just too lazy to write this out.

## Setup Steps

1. **Import Samples**
   - In Package Manager, select Input System > Samples > "Rebinding UI" (or similar) > Import.
   - Locate the sample assets in your project, e.g., `KeyboardRebindingUI` and `GamepadRebindingUI`.

2. **Add Rebind UI to Scene**
   - Drag the `KeyboardRebindingUI` prefab into your scene.
   - (Optional) Drag in `GamepadRebindingUI` if you want gamepad support.

3. **Configure RebindActionUI**
   - Assign the desired action references in the `RebindActionUI` component for each rebindable input.
   - Make sure the actions match those configured in your `PlayerInput` component.

4. **Saving and Loading Rebinds**
   - In any UI/menu handler script that manages menus or input settings, call:
     - `InputAction.SaveBindingOverridesAsJson()` when disabling/closing the UI (e.g., in `OnDisable`).
     - `InputAction.LoadBindingOverridesFromJson()` when opening/loading the UI (e.g., in `OnEnable`).
   - Store the JSON string in `PlayerPrefs` or any other persistent storage.

5. **Consistency Across Scenes**
   - Ensure the same `PlayerInput` asset and action map are used across all relevant scenes and UI objects.
   - Avoid duplicating input definitions between scenes to maintain user rebinds.

## Notes

- Make sure all objects referencing `PlayerInput` use the same asset to ensure bindings persist.
- Rebinding UI samples can be customized for different control schemes (keyboard/gamepad).
- For multiplayer setups, manage bindings per player or per input device as needed.

## Troubleshooting

- If rebinds do not persist, verify that you are saving/loading binding overrides correctly and using the same action asset everywhere.
- Always test key rebinds and their persistence after a scene reload or application restart.

## Resources

- [Unity Input System Documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@latest/manual/index.html)
- [Unity Input System Samples](https://github.com/Unity-Technologies/InputSystem/tree/main/Assets/Samples)
