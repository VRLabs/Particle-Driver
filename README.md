<div align="center">

# Particle Driver

[![Generic badge](https://img.shields.io/github/downloads/VRLabs/Particle-Driver/total?label=Downloads)](https://github.com/VRLabs/Particle-Driver/releases/latest)
[![Generic badge](https://img.shields.io/badge/License-MIT-informational.svg)](https://github.com/VRLabs/Particle-Driver/blob/main/LICENSE)
[![Generic badge](https://img.shields.io/badge/Unity-2019.4.31f1-lightblue.svg)](https://unity3d.com/unity/whats-new/2019.4.31)
[![Generic badge](https://img.shields.io/badge/SDK-AvatarSDK3-lightblue.svg)](https://vrchat.com/home/download)

[![Generic badge](https://img.shields.io/discord/706913824607043605?color=%237289da&label=DISCORD&logo=Discord&style=for-the-badge)](https://discord.vrlabs.dev/)
[![Generic badge](https://img.shields.io/endpoint.svg?url=https%3A%2F%2Fshieldsio-patreon.vercel.app%2Fapi%3Fusername%3Dvrlabs%26type%3Dpatrons&style=for-the-badge)](https://patreon.vrlabs.dev/)

A legacy method for animating on particle death that uses the [Layer Weight Tool](https://github.com/VRLabs/Layer-Weight-Tool)

## This package is depreated! If you want to drive a parameter on world or player collision, [get the new package here](https://github.com/hfcRed/collision-detection)

</div>

---

## How it works

* The ``Particle Driver Stay Active.controller`` continuously enables ``Particle System`` to re-enable the particle system immediately after it's been disabled.
* The ``Particle System`` object is disabled on collision via [Stop Action](https://docs.unity3d.com/ScriptReference/ParticleSystemStopAction.html). When re-enabled, the ``Particle Driver Weight.controller`` will reset.
* ``Weight.controller`` uses [Animator Layer Control](https://docs.vrchat.com/docs/state-behaviors) to change the weight of the ``Particle Driver`` layer based on its weight.
* The ``ParticleDeath`` parameter value is multiplied by the weight and can be used as a transition condition.

## Install guide

https://github.com/VRLabs/Particle-Driver/assets/76777936/6733fdd6-53b6-43ad-90cd-a43dea06bacc

* Merge the Animator Controller ``Particle Driver FX`` to your own FX Controller, using the [Avatars 3.0 Manager](https://github.com/VRLabs/Avatars-3.0-Manager) tool.
* Drag & drop the ``Particle Driver`` prefab into the base of your Hierarchy.
* Right click and unpack the prefab, then drag & drop it onto your avatar.
* Adjust the transforms of ``Particle System`` and ``Collider`` as needed.
* In the ``Resources/Animations/Particle Driver Weight`` controller, in the ``Max Weight`` and ``Min Weight`` animation state, change the ``Index`` to the index of the ``Particle Driver`` Layer on your FX Controller
  * The top layer is index 0, the second layer is index 1, etc.

## How to use

* When the Collider is colliding with the Particle, the ``ParticleDriver/IsColliding`` parameter will be set to ``True``, otherwise, it will be set to ``False``.

## Performance stats

```c++
Colliders:          1
Particle Systems:   1
FX Animator Layers: 1
Sub Animators:      2
```

## Hierarchy layout

```html
Particle Driver
|-Particle System
|-Collider
```

## Contributors

* [lin](https://github.com/oofdesu)

## License

Particle Driver is available as-is under MIT. For more information see [LICENSE](https://github.com/VRLabs/Particle-Driver/blob/main/LICENSE).

​

<div align="center">

[<img src="https://github.com/VRLabs/Resources/raw/main/Icons/VRLabs.png" width="50" height="50">](https://vrlabs.dev "VRLabs")
<img src="https://github.com/VRLabs/Resources/raw/main/Icons/Empty.png" width="10">
[<img src="https://github.com/VRLabs/Resources/raw/main/Icons/Discord.png" width="50" height="50">](https://discord.vrlabs.dev/ "VRLabs")
<img src="https://github.com/VRLabs/Resources/raw/main/Icons/Empty.png" width="10">
[<img src="https://github.com/VRLabs/Resources/raw/main/Icons/Patreon.png" width="50" height="50">](https://patreon.vrlabs.dev/ "VRLabs")
<img src="https://github.com/VRLabs/Resources/raw/main/Icons/Empty.png" width="10">
[<img src="https://github.com/VRLabs/Resources/raw/main/Icons/Twitter.png" width="50" height="50">](https://twitter.com/vrlabsdev "VRLabs")

</div>

