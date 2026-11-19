# Cairo Open World — Approved Game Direction

## Product decision
Build one shared Cairo-inspired open-world life-simulation game for Android and Windows PC. The target experience is a fully playable game, not a static 3D scene or a menu prototype.

## Camera and controls
- Third-person camera as the default, with a first-person toggle available during play.
- Android: touch movement stick, camera swipe, and contextual action buttons.
- PC: keyboard/mouse first; gamepad support can follow.
- Keep gameplay rules and save data shared across platforms.

## Engine and delivery decision
- Target Unreal Engine 5 for the native high-fidelity game.
- Produce separate Android and Windows packaged builds from the same project.
- Vercel remains suitable for a landing page, patch notes, and links to builds; it does not host a native Unreal Android APK or Windows executable as a playable browser game.
- Mobile and PC use platform-specific scalability profiles. Do not assume PC-quality rendering can run on every phone.
- Do not replace or break the existing Vercel prototype until a tested native vertical slice is ready.

## First playable vertical slice
Keep the first milestone deliberately small and testable:
1. One detailed, fictionalized downtown Cairo block and intersection.
2. A controllable human character with walk, run, jump, collision, and natural locomotion.
3. Third-person and first-person camera switching.
4. A small set of pedestrians with basic idle/walk behavior.
5. One drivable vehicle with enter/exit interaction.
6. One enterable shop or building interior.
7. One short Egyptian-Arabic mission with a reward.
8. Save/load for player position, money, and mission completion.
9. Android touch controls and Windows keyboard/mouse controls.
10. Performance and stability checks on a real Android device and a Windows PC.

## Later gameplay systems
- More districts and recognizable Cairo-inspired landmarks.
- Traffic, public transport, pedestrians, and contextual interactions.
- Jobs, income, shops, buying/selling, apartments, vehicles, and customization.
- Day/night cycle, weather, ambient audio, and random events.
- Side activities and longer mission chains.
- Optional cloud saves and account synchronization only after local saves are reliable.

## Technical project layout
Create a separate Unreal project (do not mix Unreal binaries/assets into the current static website):
- `CairoOpenWorld.uproject`
- `Config/` for input, rendering, and device profiles.
- `Content/Maps/` for the vertical-slice district.
- `Content/Characters/`, `Vehicles/`, `Environment/`, `UI/`, `Audio/`.
- `Source/CairoOpenWorld/` for core gameplay systems.
- `Build/Android/` and `Build/Windows/` for generated packages (do not commit generated builds).
- Use Git LFS for large source assets where appropriate.

## Acceptance gates
A milestone is not complete because a page loads or a build command starts. It must:
- Launch on the target device.
- Have working movement and camera controls.
- Have collision and interaction that can be played repeatedly.
- Save and restore progress.
- Meet a defined performance target on the selected test hardware.
- Pass a smoke test on both Android and Windows before release.

## Known constraints and honesty
- Unreal Engine development and native packaging require a supported desktop development environment and platform toolchains. An Android phone alone cannot run Unreal Editor or produce the native Windows/Android builds.
- Android packaging requires the Android SDK/NDK toolchain; Epic's current setup documentation recommends Android Studio/SDK configuration and a mobile-targeted scalable starting point.
- Mobile hardware has tighter rendering and memory budgets than desktop, so quality tiers, profiling, and real-device testing are required from the beginning.
- Do not claim photorealism, complete AI behavior, online multiplayer, or full-city scale until those features exist and have been tested.
