# AnywhereMMD

A PC VRChat avatar tool that generates an MMD video performance using a recording double of the recipient's own avatar.
**No music, dance motions, camera motions or avatar models are included.**

This is an initial preview. See [validation scope](VALIDATION.md) and [dependency names](Requirements.txt).

## Create a collection

1. In the Unity Project window, choose **Create > Anywhere MMD > Collection**.
2. Select the asset and choose Japanese or English in its Inspector.
3. Add 1–16 songs and assign audio, a non-Legacy Humanoid dance clip, and a camera clip.
4. Click **Generate prefab**. A new folder appears under `Assets/AnywhereMMD-Generated`.
5. Place its `Anywhere MMD.prefab` under the Humanoid avatar root. The upload build generates the avatar-specific doubles.

Generation never overwrites source media or existing prefabs. After changing songs, generate again and replace the old instance yourself.
VMD import/conversion is not included. Supply Unity AnimationClips.
The camera and dance must share the same timeline origin and coordinate system; automatic music alignment is not provided.

## Camera input

The default rig has `Pivot/Camera` relative to its root. Supply your own camera rig prefab if the camera clip uses different paths.
Only active Transforms and exactly one Camera are supported. An AudioListener is removed from the generated copy.
Scripts, animators, renderers and audio sources are rejected. Transform and Camera curves are supported; object-reference curves are not.
A separate outer transform handles height fitting, so camera animation does not overwrite that adjustment.

## Settings and controls

The prefab root keeps the bilingual appearance, resolution, range and grabbing settings. Each Track keeps camera height and framing adjustments; reference eye height defaults to 1.5m.
Appearance following mirrors supported avatar FX outfit/material changes. Independent mode uses build-time clothing and fixed lighting for supported lilToon/lilSSRT copies.
Normal PhysBone simulation and colliders remain. Compatible multi-song physics is shared; shared hair/outfit grabbing is off by default. Original avatar and retained per-song finger settings are unchanged.

The generated expression menu has Songs and Display submenus. Display options are Camera Only, Local, and Local + Camera Only. Local modes restrict both video and audio to the wearer. Camera Only by itself does not make audio local.
Stop before selecting the same song again to restart it. Use one collection per avatar to avoid overlapping playback.

## Limits

- PC only; viewers must permit avatar cameras.
- Late-join playback position synchronization and continuous audio-clock correction are not implemented.
- Unsupported shaders, custom scripts and outfit changes outside FX need individual testing.
- The elevated capture space does not categorically exclude world geometry that enters it.
- Upload size and physics counts depend on the avatar and song count.
- This shares component GUIDs with earlier Anywhere MMD / Dance Lounge builds. Do not install duplicate implementations in the same project.

No third-party packages or media are redistributed here. Respect the terms of your own media.
No software license has been selected yet; public visibility does not grant unrestricted reuse or redistribution.
