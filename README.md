# ngx-steel-beams

<a href="https://ngxui.com" target="_blank" style="display: flex;gap: .5rem;align-items: center;cursor: pointer; padding: 0 0 0 0; height: fit-content;">
  <img src="https://ngxui.com/assets/img/ngxui-logo.png" style="width: 64px;height: 64px;">
</a>

This library is part of the NGXUI ecosystem.
View all available components at [https://ngxui.com](https://ngxui.com)

`@omnedia/ngx-steel-beams` is an Angular standalone component rendering **animated 3D steel beams** with a realistic procedural shader effect using Three.js. Highly customizable, performant, SSR-safe, and signals/zones-ready.

## Features

* Native 3D animated steel beams with procedural geometry and shader effects (noise, distortion, color, lighting).
* All settings (beam count, size, color, speed, noise, etc.) are dynamic via signals and @Input.
* Seamless Angular Standalone usage, SSR-safe, no zone required.
* Animation auto-pauses when scrolled out of view (IntersectionObserver).
* No external CSS or dependencies needed except Three.js (peer dep).
* Fully responsive: resizes to container and parent.
* No memory leaks: full resource cleanup and disposal.

## Installation

```
npm install @omnedia/ngx-steel-beams three
```

> **Note:** Requires `three` as a peer dependency.

## Usage

Import the `NgxSteelBeamsComponent` in your Angular module or component:

```typescript
import { NgxSteelBeamsComponent } from '@omnedia/ngx-steel-beams';

@Component({
  ...
  imports: [NgxSteelBeamsComponent],
})
export class DemoComponent {}
```

Use it in your template:

```html
<div style="width: 100vw; height: 400px; background: #15181a;">
  <om-steel-beams
    [beamWidth]="3"
    [beamHeight]="20"
    [beamNumber]="10"
    [lightColor]="'#ffffff'"
    [speed]="0.02"
    [noiseIntensity]="1.5"
    [scale]="0.2"
    [rotation]="30"
    style="width: 100%; height: 100%; display: block;"
  ></om-steel-beams>
</div>
```

## API

```html
<om-steel-beams
  [beamWidth]="number"
  [beamHeight]="number"
  [beamNumber]="number"
  [lightColor]="cssColor"
  [speed]="number"
  [noiseIntensity]="number"
  [scale]="number"
  [rotation]="number"
  [styleClass]="customClass"
></om-steel-beams>
```

* `beamWidth` (default: `3`): Width of each beam (float, world units).
* `beamHeight` (default: `20`): Height of each beam (float, world units).
* `beamNumber` (default: `6`): Number of animated beams.
* `lightColor` (default: `'#ffffff'`): Main directional light color.
* `speed` (default: `0.01`): Animation speed (float).
* `noiseIntensity` (default: `1.75`): Procedural noise effect (float).
* `scale` (default: `0.2`): Intensity/scale of the animated distortion.
* `rotation` (default: `45`): Scene rotation in degrees (float).
* `styleClass` (optional): Add your own CSS class to the host element.

## Styling

* Component fills parent by default—set size via style or CSS.
* No extra styles needed; all rendering is inside the WebGL canvas.

## Notes

* Animation automatically pauses when component is not visible (in view).
* Fully SSR-safe: DOM access is always guarded.
* All inputs can be changed at runtime and update immediately.
* Built for Angular 20 Standalone with signals, zero zone usage.
* Dispose and cleans up all WebGL/DOM resources on destroy.

## Contributing

Contributions welcome! PRs, issues, and feedback appreciated.

## License

MIT
