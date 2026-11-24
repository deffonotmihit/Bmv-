# SIMFLATTC

Browser driving sim (three.js, no build step). Serve the folder statically (GitHub Pages works) and open `index.html`; add to the iPhone home screen if you like.
Locally: `python3 -m http.server`, then http://localhost:8000.

Controls: W/S throttle/brake, A/D steer, Space handbrake, E/Q shift, M manual/auto, L lights, N day/night, **P cycles 116d -> M140i -> M6 GT3**, T traction control, Enter respawn, **C next camera (Shift+C previous)**, **R live reflections on/off**.

## Lighting
Fixed low sun (~30° elevation) with soft 2048 shadows that follow the car (snapped to the shadow-map grid so they do not shimmer), a gradient sky with sun glow, a contact-shadow patch under the car, and live reflections: a small cube camera on the car refreshed every few frames so the paint and glass reflect the real sky, sun and ground. R toggles it (off by default on touch devices, where it holds a snapshot instead). N still switches to night.

## Cars
The BMW 116d and M140i are unchanged.

### 2018 BMW M6 GT3 (new)
No working lights yet (L does nothing in this mode).

| | |
|---|---|
| Engine | 4.4 l twin-turbo V8 (S63), ~585 PS (430 kW) at 6000 rpm, ~700 Nm from 3500 rpm, 7000 rpm limit |
| Drivetrain | RWD, limited-slip differential, 6-speed sequential paddle box (80 ms shifts), 4.2 final drive; 1st / 6th top out at about 84 / 285 km/h |
| Chassis | 1330 kg, 47 % front, CoG 0.44 m, wheelbase 2.90 m, track 1.70 m (measured from the supplied model) |
| Tyres / aero | slicks (about 1.5 g peak grip) plus aerodynamic downforce that grows with speed squared (about 2 g in fast corners); drag CdA 0.95 m² |
| Brakes | ABS, about 1.5 g from 100 km/h (26 m), ~92 m from 200 km/h |
| Aids | TC (T toggles it) and ABS, as on the real car |

Checked in the sim: 0-100 km/h 3.6 s, 0-200 km/h 9.2 s, top speed about 276 km/h. All values are in the `MODES.m6` table in `index.html`.

## Credits and licences
- BMW M140i model: Ddiaz Design, CC BY 4.0.
- BMW M6 GT3 model: "2018 BMW M6 GT3" by Ddiaz Design, **CC BY-NC-SA 4.0** (non-commercial, share-alike). Do not use it in anything commercial.
