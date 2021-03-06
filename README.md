# Particle Driver
  
[![Generic badge](https://img.shields.io/badge/Unity-2019.4.31f1-informational.svg)](https://unity3d.com/unity/whats-new/2019.4.31)
[![Generic badge](https://img.shields.io/badge/SDK-AvatarSDK3-informational.svg)](https://vrchat.com/home/download)
[![Generic badge](https://img.shields.io/badge/License-MIT-informational.svg)](https://github.com/VRLabs/Particle-Driver/blob/main/LICENSE)
[![Generic badge](https://img.shields.io/github/downloads/VRLabs/Particle-Driver/total?label=Downloads)](https://github.com/VRLabs/Particle-Driver/releases/latest)

A legacy method for animating on particle death that uses the [Layer Weight Tool](https://github.com/VRLabs/Layer-Weight-Tool).

## How it works

Here is a map of the hierarchy:

```
Your Avatar ("ParticleDeath" layer)
...
- Particle Driver (Stay Active.controller)
-- Particle System (Weight.controller)
-- Collider
```

The "Stay Active.controller" animates "Particle System" on, to re-enable it immediately after it's been disabled.

The "Particle System" object is disabled on particle death via [Stop Action](https://docs.unity3d.com/ScriptReference/ParticleSystemStopAction.html). When re-enabled, the "Weight.controller" will reset.

"Weight.controller" uses [Animator Layer Control](https://docs.vrchat.com/docs/state-behaviors) to change the weight of the "ParticleDeath" layer.

The "ParticleDeath" layer animates a float parameter. The parameter value is multiplied by the weight and can be used as a transition condition.

In short: Weight.controller resets and changes a parameter value when the particle dies.

## Install guide

Merge the FX controller to your own FX controller, using the [Avatars 3.0 Manager](https://github.com/VRLabs/Avatars-3.0-Manager) tool.
 
"Particle Driver.prefab" should go to the base of your Unity scene, which will give it base Unity scaling.

Unpack the prefab by right-clicking it.

Remove "Collider" outside of "Particle Driver" and place it in your avatar's hierarchy as needed. 

"Particle System" should remain under "Particle Driver". Place "Particle Driver" anywhere in your avatar's hierarchy, as needed.

Adjust the transforms of "Particle System" and "Collider" to your taste.

Use the [Layer Weight Tool](https://github.com/VRLabs/Layer-Weight-Tool/). Open VRLabs from the menu bar. Click "Apply Weight Controls".

## How to use

Testing in Unity requires the [3.0 emulator by Lyuma](https://github.com/lyuma/Av3Emulator). 

The merged "ParticleDeath" layer is provided for you in the "FX.controller" as a template. Build your own logic and use this layer to run [Parameter Driver](https://docs.vrchat.com/docs/state-behaviors).

To avoid avatar initialization side-effects, the default state is "Init". This state plays a 60 frame "Buffer.anim" and then checks for IsLocal == True.

"Start Float" plays "Float.anim". Every state after "Start Float" should also play "Float.anim". To skip the first entry of "Max Weight" when the avatar loads, this state transitions to "Idle" when "Min Weight" is run by "Weight.controller".

"Idle" is the state you want to work from. Transition from here to states which drive synced parameters. Use the synced parameter changes in other layers to animate globally.

ParticleDeath < 1.0 means the Particle System is alive.

ParticleDeath > 0.1 means the Particle System is dying.

## Downloads

You can grab the latest version of the Particle Driver in [Releases](https://github.com/VRLabs/Particle-Driver/releases/latest).

## License

Particle Driver is available as-is under MIT. For more information see [LICENSE](https://github.com/VRLabs/Particle-Driver/blob/main/LICENSE).

## Contact us

If you need help, our support channel is on [Discord](https://discord.vrlabs.dev).
