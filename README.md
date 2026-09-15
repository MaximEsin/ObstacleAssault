# ObstacleAssault

Learning project for Unreal Engine 5.6 — an obstacle course game, built to practice
C++ basics in UE: Actor classes, UCLASS/UPROPERTY/UFUNCTION, Tick/BeginPlay,
and the C++ ↔ Blueprint workflow.

Based on the stock UE5 Third Person template (`Variant_Combat`, `Variant_Platforming`,
`Variant_SideScrolling` in `Source/ObstacleAssault/`), with custom classes and a level
added on top (`Content/MyAssets/`).

## Custom code

`Source/ObstacleAssault/MovingPlatform.h/.cpp` — an `AActor` that moves back and forth
and rotates:

- `PlatformVelocity`, `MoveDistance`, `RotationVelocity` — `EditAnywhere` properties
- `BeginPlay()` stores the start location; `Tick()` moves/rotates the actor each frame
- reaching `MoveDistance` flips the velocity to send it back

Used as Blueprint bases for level actors (`BP_MovingPlatform`, `BP_MovingPlatform_2`,
`RotatingPlatform`).

## Level

Obstacle course level in `Content/MyAssets/` (`GameMap.umap`, `MainLevel.umap`), built
with third-party asset packs (`Asian_Village`, `Construction_VOL1`,
`Survival_Character`).

## Tech notes

- Engine: UE 5.6
- Git LFS for binary assets (`.uasset`, `.umap`, textures, audio, `.fbx`)
- Generated folders (`Binaries/`, `Intermediate/`, `Saved/`, `DerivedDataCache/`) are
  gitignored

## Run

Open `ObstacleAssault.uproject` in UE 5.6 (regenerate VS project files if needed).
