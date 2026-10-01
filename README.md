# Vortex Fighters 🥊

A 3D local two-player fighting game made in Unity by Jan Ali Hassan. Two fighters share one keyboard, face off in an arena, and trade punches and kicks until one runs out of lives.

![Vortex Fighters gameplay screenshot](https://janalihassan.dev/images/Vortex_Fighters_1.png)

▶️ [Watch the gameplay video](https://janalihassan.dev/videos/Vortex-Fighter.mp4) · 🌐 [More of my games at janalihassan.dev](https://janalihassan.dev/#library) · 💼 [LinkedIn post](https://lnkd.in/p/dyGKzQfm)

## Features

- Two players on one keyboard, each with their own input axes and keys
- Move, jump, punch and kick, all driven by Mecanim animation triggers (move, jump, punch, kick, hit, death)
- Fighters turn to face each other every frame, so you never lose track of your opponent
- Hits only count while the attacker's punch or kick is active: hand and foot trigger colliders check a short attack window before dealing damage
- Six lives per player, shown as two health bars of six icons that empty as you take hits
- A fighter who reaches zero lives plays a death animation and stops responding to input
- Animated pause menu (Esc) with Resume, Restart, Main Menu and Quit, using unscaled time so it animates while the game is frozen
- Cinemachine virtual camera with a damped follow on Player 1

## Controls

| Action | Player 1 | Player 2 |
| --- | --- | --- |
| Move | W A S D | Arrow keys |
| Jump | R | B |
| Punch | T | M |
| Kick | Y | N |
| Pause | Esc | Esc |

## Built with

- Unity 2019.4.40f1 (LTS)
- C#
- Cinemachine 2.6.17
- Unity UI (uGUI) for menus and health bars
- Unity's built-in Input Manager (separate `Horizontal-2` / `Vertical-2` axes for player 2)
- Character models and base animations from the free Fighter Pack Bundle (Mecanim animation packs), plus extra kick, hit, jump and death clips

## Key scripts

All game code is in `Assets/Vortex Fighters/Scripts/`.

- `Player.cs` / `Player_2.cs`: movement, jumping (grounded check against the `Ground` tag), punch and kick input, facing the opponent, taking damage and dying
- `PlayerAnimations.cs`: sets the Animator parameters and closes each attack window 0.3 seconds after a punch or kick
- `Attack.cs`: shared singleton holding the punch and kick state for both players, so each fighter knows when the other is attacking
- `Health_Bar_Controller.cs`: hides one life icon per hit for each player
- `UI_Manager.cs`: pause panel and its buttons (resume, restart, main menu, quit)
- `Main_Menu/Main_Menu.cs`: Play and Quit buttons on the title screen

## Running the project

1. Install Unity **2019.4.40f1** through Unity Hub.
2. Clone this repo and add the folder in Unity Hub, then open it.
3. Open `Assets/Vortex Fighters/Scenes/Main_Menu.unity` (the first scene in Build Settings; the fight itself is `Fighting_Ground.unity`).
4. Press Play, then hit Play in the menu.

## Status

The core fight loop is done. A game-over and winner screen is still to come.

## Author

Jan Ali Hassan · [Portfolio](https://janalihassan.dev) · [LinkedIn](https://www.linkedin.com/in/janalihassan) · [GitHub](https://github.com/janalihassan)
