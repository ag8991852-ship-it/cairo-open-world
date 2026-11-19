# Implementation Checklist

## Stage 0 — project foundation
- [x] Confirm one game target for Android and Windows PC.
- [x] Approve third-person default camera and first-person toggle.
- [x] Preserve the current Vercel prototype as a fallback.
- [x] Create a separate development branch for the native-game direction.
- [x] Record the approved scope and acceptance gates.
- [ ] Confirm access to a Windows development machine that can run Unreal Editor.
- [ ] Install a compatible Unreal Engine 5 version and Android toolchain.
- [ ] Create the native Unreal project and configure Android + Windows targets.
- [ ] Add a minimal CI validation path for source/config changes where practical.

## Stage 1 — playable vertical slice
- [ ] Create one downtown-inspired block with collision and navigation boundaries.
- [ ] Implement third-person character movement and animation.
- [ ] Implement first-person camera mode and safe camera switching.
- [ ] Add Android touch UI and Windows keyboard/mouse input.
- [ ] Add one pedestrian interaction and one mission.
- [ ] Add one vehicle with enter/drive/exit.
- [ ] Add one enterable interior.
- [ ] Add local save/load.
- [ ] Package and smoke-test Android build.
- [ ] Package and smoke-test Windows build.

## Stage 2 — life simulation
- [ ] Expand pedestrian schedules and contextual reactions.
- [ ] Add traffic rules and more vehicle types.
- [ ] Add jobs, shops, inventory, and economy.
- [ ] Add apartment ownership and customization.
- [ ] Add day/night, weather, and ambient sound.

## Stage 3 — scale and release
- [ ] Expand to additional districts only after streaming and performance are proven.
- [ ] Add scalable graphics profiles for low/mid/high Android and PC.
- [ ] Profile CPU, GPU, memory, load times, and battery/thermal behavior.
- [ ] Run regression tests on representative Android and Windows hardware.
- [ ] Publish signed release packages and a Vercel download/updates page.

## Current verified state
- Existing repository contains a single-page Three.js browser prototype (index.html) and README.md.
- Existing prototype is not an Unreal Engine project and does not contain a native Android APK or Windows executable.
- Current Vercel deployment should remain untouched while the native direction is prepared.
