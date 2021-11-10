<div align="center">
  <h1>Particle Driver</h1>
  <p>
     A method for animating on particle death.
  </p>

  <a href="https://github.com/VRLabs/Particle-Driver/releases/latest">
    <img src="https://img.shields.io/github/v/release/VRLabs/Particle-Driver.svg?style=flat-square">
  </a>
  <a href="https://github.com/VRLabs/Particle-Driver/releases/latest">
    <img src="https://img.shields.io/badge/Unity-2019.4-green.svg?style=flat-square">
  </a>
  <br />
  <a href="https://github.com/VRLabs/Particle-Driver/issues">
    <img src="https://img.shields.io/github/issues-raw/VRLabs/Particle-Driver.svg?style=flat-square">
  </a>
  <a href="https://github.com/VRLabs/Particle-Driver/issues?q=is%3Aissue+is%3Aclosed">
    <img src="https://img.shields.io/github/issues-closed-raw/VRLabs/Particle-Driver.svg?style=flat-square">
  </a>
  <a href="https://github.com/VRLabs/Particle-Driver/pull">
    <img src="https://img.shields.io/github/issues-pr-raw/VRLabs/Particle-Driver.svg?style=flat-square">
  </a>
  <a href="https://github.com/VRLabs/Particle-Driver/pulls?q=is%3Apr+is%3Aclosed">
    <img src="https://img.shields.io/github/issues-pr-closed-raw/VRLabs/Particle-Driver.svg?style=flat-square">
  </a>
  <br />
  <br />
</div>

## How it works

The Particle System [Stop Action](https://docs.unity3d.com/ScriptReference/ParticleSystemStopAction.html) option is used to reset an animator. The animator uses [Animator Layer Control](https://docs.vrchat.com/docs/state-behaviors) to change parameters within playable layers.

## Install guide

Testing in Unity requires the [3.0 emulator by Lyuma](https://github.com/lyuma/Av3Emulator).

Merge the FX controller to your own FX controller, using the [Avatars 3.0 Manager](https://github.com/VRLabs/VRChat-Avatars-3.0/releases/download/1/AV3Manager.unitypackage) tool.
 
The Particle Driver.prefab should go to the base of your Unity scene, which will give it base Unity scaling.

Unpack the prefab by right-clicking it and move the prefab to base of your avatar.

Expand the prefab, and locate Particle Driver/Particle System. ...


Use the [Fix Order](https://github.com/VRLabs/VRChat-Avatars-3.0/releases/download/1/FixOrder.unitypackage) script before uploading or testing. Open VRLabs from the menu bar. Click "Fix Order". Run it again any time the layers related to this package change index order in your FX or Gesture controllers. This is so particle death controllers can reference the correct layers in their VRC Animator Layer Control state behaviors.

## Downloads

You can grab the latest version of the Particle Driver Constraint in [Releases](https://github.com/VRLabs/Particle-Driver/releases/latest).

## License

Particle Driver is available as-is under MIT. For more information see [LICENSE](https://github.com/VRLabs/Particle-Driver/blob/dev/LICENSE).

## Contact us

If you need help, our support channel is on [Discord](https://discord.vrlabs.dev).
