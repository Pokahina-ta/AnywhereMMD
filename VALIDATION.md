# Validation / 検証範囲

## Confirmed

- Compiles with Unity 2022.3.22f1 assemblies, VRChat SDK 3.10.4, Modular Avatar 1.17.1 and NDMF 1.14.1.
- The downloadable unitypackage contains the public source and its stable metadata; gzip integrity and source equality checks pass.
- No music, motion clips, avatars, credentials, local project paths, or third-party packages are included.
- The underlying shared-physics/appearance/display implementation was previously tested in a private project. That does not establish compatibility for every recipient avatar.

## Not yet verified for this authoring release

- Generating and building collections in a clean Unity project.
- Runtime playback, timing, rendering and PhysBones in VRChat.

Standalone compilation does not validate Unity editor generation or VRChat playback. Treat this as an initial preview and test generated prefabs before relying on them.

