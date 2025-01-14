# Welcome to the Cuttlefish Project!

This is a project developed in rust that seeks to provide a feature-complete configuration GUI and manual for Hyprland and waybar, for the purposes of making them easier to begin using for the average user.

## Goals of the Project

1. Hyprland configs for the masses

    Hyprland configuration with this tool should be simple-- someone with no window manager experience should be able to use it to generate a usable config.

2. Simplicity first, features second

    Not every feature should be accessible though this GUI-- for example, disabling XWayland should not be included because the average user should not need to know what XOrg even is. (Additionally, this decision provides some idiot-proofing, as disabling XWayland can cause breakages in the current year). As a rule, if you cannot explain a feature in 1 sentence, it likely should not be included.

3. Keep explanations of features short

    Features such as the scratchpad should be described using more common analogies such as minimization, which is a more common and well-known functionality. Another example is saving the config file should automatically reload it as well by running `hyprctl reload`, as it is very likely that users would want to reload after editing anyway, and separating reloads would only make more confusion.

4. Allocate a secondary config file for user-picked additions

    Write to hyprland.conf, but source a second file titled usercfg.conf that the user can use to make their own additions and tweaks to the config tool provided config

5. Store data in cfg.toml

    This is more of a principle so that I don't have to rip apart Hyprland configs to retrieve data, instead storing it in clean toml files that are easier to parse (for starters, there is a crate that can parse them for you)

6. Keep localization data in toml files as well

    This keeps the dependency tree small, reducing build times.

7. Support full keyboard navigation

    Hyprland is built with a keyboard-based workflow, so for the sake of usability, we should comply with that and support navigation of this interface without moving your hands off of the keyboard
